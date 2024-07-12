---
title: Dispatcher Configurations voor AEM Screens
description: Deze pagina benadrukt richtlijnen voor het vormen van een Dispatcher voor een project van AEM Screens.
feature: Administering Screens
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Dispatcher Configurations voor AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is Adobe Experience Manager in cache plaatsen, of gereedschap voor taakverdeling, of beide.

De volgende pagina verstrekt de richtlijnen voor het vormen van een Dispatcher voor een project van AEM Screens.

>[!NOTE]
>
>Als er een Dispatcher beschikbaar is, kunnen verbindingen met de registratieserver worden voorkomen door te filteren in de Dispatcher-regels.
>
>Als er geen Dispatcher is, maak de registratieserver in de OSGi componentenlijst onbruikbaar.

Voordat u Dispatcher voor een AEM Screens-project configureert, moet u eerst op de hoogte zijn van Dispatcher.
Zie [ Vormend Dispatcher ](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration) voor meer details.

## Dispatcher for Manifest versie v2 configureren {#configuring-dispatcher}

>[!IMPORTANT]
>De volgende Dispatcher-configuraties zijn alleen van toepassing op Manifest-versie v2. Zie [ de Configuraties van Dispatcher voor Manifest versie v3 ](#configuring-dispatcherv3) voor Manifest versie v3.

AEM Screens-spelers of -apparaten gebruiken een geverifieerde sessie om ook toegang te krijgen tot de bronnen in de publicatie-instanties. Wanneer u meerdere publicatie-instanties hebt, moeten de aanvragen altijd naar dezelfde publicatie-instantie gaan, zodat de geverifieerde sessie geldig is voor alle aanvragen die afkomstig zijn van de AEM Screens-spelers of -apparaten.

Voer de onderstaande stappen uit om de Dispatcher voor een AEM Screens-project te configureren.

### Vaste sessies inschakelen {#enable-sticky-session}

Als u meerdere publicatie-instanties wilt gebruiken die zijn voorafgegaan door één Dispatcher, werkt u het `dispatcher.any` -bestand bij om kleverigheid in te schakelen.

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Als één publicatie-exemplaar door één Dispatcher wordt voorafgegaan, kan het inschakelen van de kleverigheid op de Dispatcher niet helpen omdat het taakverdelingsmechanisme elke aanvraag naar Dispatcher kan verzenden. In dit geval, laat de klik **toe** Stickiness **gebied om het op uw niveau van het ladingsverdelingsmechanisme, zoals aangetoond in het hieronder cijfer aan te zetten:**

![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Bijvoorbeeld, als u AWS ALB gebruikt, zie [ groepen van het Doel voor uw Balancers van de Lading van de Toepassing ](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) voor het toelaten van kleverigheid op het niveau ALB. Laat de kleverigheid één dag toe.

### Stap 1: Klantkoppen configureren {#step-configuring-client-headers}

Voeg het volgende aan `/clientheaders` sectie toe:

**x-Gevraagd-met**

**x-SET-HEARTBEAT**

**x-VERZOEK-COMMAND**

### Stap 2: Screens-filters configureren {#step-configure-screens-filters}

Als u Screens-filters wilt configureren, voegt u het volgende toe aan ***`/filter`***.

```
## AEM Screens Filters
## # Login, Ping and Device Configurations
/0200 { /type "allow" /method "POST" /url "/libs/granite/core/content/login.validate/j_security_check" }
/0201 { /type "allow" /method "GET" /url "/libs/granite/csrf/token.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0204 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
## # Device Dashboard Configurations
/0210 { /type "allow" /method '(GET|POST)' /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0211 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0212 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0213 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
## # Content Configurations
/0220 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*/jcr:content/*/offline-config_*.zip" }
/0222 { /type "allow" /method '(GET|HEAD)' /url '/var/contentsync/content/screens/.+/jcr:content/.+/offline-config_.*\.[0-9]+\.zip' }
```

### Stap 3: Dispatcher Cache uitschakelen {#step-disabling-dispatcher-cache}

Dispatcher caching voor ***/content/screens path*** uitschakelen.

Screens-spelers gebruiken geverifieerde sessies, zodat de Dispatcher geen van de schermspelers-aanvragen voor `channels/assets` in cache plaatst.

Ga als volgt te werk om de cache voor de elementen in te schakelen, zodat de elementen worden verzonden vanuit de Dispatcher-cache:

* `/allowAuthorization 1` toevoegen in `/cache` -sectie
* Voeg de onderstaande regels toe aan de `/rules` -sectie van `/cache`

```xml
/0000
    {
        /glob "*"
        /type "allow"
    }   

/0001
    {
        # Disable Dispatcher Cache for Screens channels
        /glob "/content/screens/*.html"
        /type "deny" 
    }

/0002
    {
    # Disable Dispatcher Cache for Screens offline manifests
    /glob "/content/screens/*.json"
    /type "deny"
    }

/0003
    { # Disable Dispatcher Cache for Screens devices json 
    /glob "/home/users/screens/*.json"
    /type "deny"
    }
```

## Dispatcher for Manifest versie v3 configureren{#configuring-dispatcherv3}

Zorg ervoor dat u deze filters en cacheregels toestaat in verzenders die de publicatie-instanties voor de werking van Screens vooraf bekijken.

### Voorwaarden voor manifestversie v3{#prerequisites3}

Voer de volgende twee voorwaarden uit voordat u een Dispatcher (manifestversie v3) voor AEM Screens configureert:

* Zorg ervoor dat u `v3 manifests` gebruikt. Navigeer naar `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` en controleer of `Enable ContentSync Cache` is uitgeschakeld.

* Zorg ervoor dat de Dispatcher flush-agent is geconfigureerd in `/etc/replication/agents.publish/dispatcher1useast1Agent` in een publicatie-instantie.

  ![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-1.png)

  ![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-3.png)

### Filters {#filter-v3}

```
## AEM Screens Filters
## # Login, Ping and Device Configurations
/0200 { /type "allow" /method "POST" /url "/libs/granite/core/content/login.validate/j_security_check" }
/0201 { /type "allow" /method "GET" /url "/libs/granite/csrf/token.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0204 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
 
## # Device Dashboard Configurations
/0210 { /type "allow" /method '(GET|POST)' /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0211 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0212 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0213 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
 
## # Content Configurations
/0220 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
#/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/experience-fragments/*" } ## uncomment this, if you're using experience-fragments
/0222 { /type "allow" /extension '(css|eot|gif|ico|jpeg|jpg|js|gif|pdf|png|svg|swf|ttf|woff|woff2|html|mp4|mov|m4v)' /path "/content/dam/*" } ## add any other formats required for your project here
 
## # Enable clientlibs proxy servlet
/0230 { /type "allow" /method "GET" /url "/etc.clientlibs/*" }
```

### Cacheregels {#cache-rules-v3}

* Voeg `/allowAuthorized "1"` toe aan de sectie `/cache` in `publish_farm.any` .

* Alle AEM Screens-spelers gebruiken een geverifieerde sessie om verbinding te maken met AEM (auteur/publicatie). Een Dispatcher plaatst deze URL&#39;s niet in de cache en moet ze dus inschakelen.

* `statfileslevel "10"` toevoegen aan `/cache` -sectie in `publish_farm.any`
Deze regel ondersteunt caching tot tien niveaus vanaf de cachedocroot en maakt dienovereenkomstig ongeldig wanneer inhoud wordt gepubliceerd in plaats van alles ongeldig te maken. U kunt dit niveau wijzigen op basis van de diepte van de inhoudstructuur

* Voeg het volgende toe aan `/invalidate section in publish_farm.any`

  ```
  /0003 {
      /glob "*.json"
      /type "allow"
  }
  ```

* Voeg de volgende regels toe aan de sectie `/rules` in `/cache` in `publish_farm.any` of in een bestand dat wordt opgenomen vanuit `publish_farm.any` :

  ```
  ## Don't cache CSRF login tokens
  /0001
      {
      /glob "/libs/granite/csrf/token.json"
      /type "deny"
      }
  ## Allow Dispatcher Cache for Screens channels
  /0002
      {
          /glob "/content/screens/*.html"
          /type "allow"
      }
  ## Allow Dispatcher Cache for Screens offline manifests
  /0003
      {
      /glob "/content/screens/*.manifest.json"
      /type "allow"
      }
  ## Allow Dispatcher Cache for Assets
  /0004
      {
  
      /glob "/content/dam/*"
      /type "allow"
      }
  ## Disable Dispatcher Cache for Screens devices json
  /0005
      {
      /glob "/home/users/screens/*.json"
      /type "deny"
      }
  ## Disable Dispatcher Cache for Screens svc json
  /0006
      {
      /glob "/content/screens/svc.json"
      /type "deny"
      }
  ```

### Validatieregel toevoegen voor segments.js {#invalidsegmentjs}

Als u gerichte campagnes gebruikt met AEM Screens, dan moet `segments.js file` die door Dispatcher wordt gediend ongeldig worden gemaakt, aangezien u toevoegt en nieuwe segmenten op AEM publiceert. Zonder deze validatieregel werken nieuwe doelcampagnes niet op de AEM Screens Player (in plaats daarvan wordt de standaardinhoud weergegeven).

* Voeg een validatieregel toe aan `/etc/httpd/conf.dispatcher.d/available_farms/999_ams_publish_farm.any` . Hier volgt de regel die moet worden toegevoegd:

```
    /invalidate {
                        .
                        .
                        /0004 {
                               /glob "conf/<project-name>/settings/wcm/.js"
                               /type "allow"
                        }
                }
```

* Deze regel zorgt ervoor dat het `segments.js` -bestand ongeldig wordt gemaakt en dat het laatst wordt opgehaald wanneer het wordt gewijzigd.
