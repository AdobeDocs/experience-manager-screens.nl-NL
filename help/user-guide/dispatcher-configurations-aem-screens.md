---
title: Dispatcher Configurations voor AEM Screens
description: Deze pagina benadrukt richtlijnen voor het vormen van Dispatcher voor een project van AEM Screens.
feature: Administering Screens
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# Dispatcher Configurations voor AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is een Adobe Experience Manager-programma voor het in cache plaatsen en/of taakverdeling.

De volgende pagina verstrekt de richtlijnen voor het vormen van Dispatcher voor een project van AEM Screens.

>[!NOTE]
>
>Als een Dispatcher beschikbaar is, kunnen de verbindingen met registratieserver worden verhinderd door in de regels van de Verzender te filtreren.
>
>Als er geen Dispatcher is, maak registratieserver in de OSGi componentenlijst onbruikbaar.

Voordat u Dispatcher configureert voor een AEM Screens-project, moet u op de hoogte zijn van Dispatcher.
Zie [Dispatcher configureren](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration) voor meer informatie .

## Dispatcher configureren voor manifestversie v2 {#configuring-dispatcher}

>[!IMPORTANT]
>De volgende Dispatcher-configuraties zijn alleen van toepassing op Manifest-versie v2. Zie [Dispatcher Configurations voor Manifest versie v3](#configuring-dispatcherv3) voor manifestversie v3.

AEM Screens-spelers of -apparaten gebruiken geverifieerde sessies om ook toegang te krijgen tot de bronnen in de publicatie-instanties. Als u dus meerdere publicatieinstanties hebt, moeten de aanvragen altijd naar dezelfde publicatie-instantie gaan, zodat de geverifieerde sessie geldig is voor alle aanvragen die afkomstig zijn van de AEM Screens-spelers/apparaten.

Voer de onderstaande stappen uit om Dispatcher voor een AEM Screens-project te configureren.

### Vaste sessies inschakelen {#enable-sticky-session}

Als u meerdere publicatie-instanties wilt gebruiken die zijn voorafgegaan door één Dispatcher, werkt u de `dispatcher.any` bestand voor kleverigheid.

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Als u één publicatie-exemplaar hebt voorafgegaan door één Dispatcher, helpt het niet om de stickiness op Dispatcher in te schakelen, omdat het taakverdelingsmechanisme elke aanvraag naar Dispatcher kan verzenden. In dit geval selecteert u **Inschakelen** in **Sticiteit** veld voor het inschakelen van het taakverdelingsmechanisme, zoals in de onderstaande afbeelding wordt getoond:

![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Als u bijvoorbeeld AWS ALB gebruikt, raadpleegt u [Doelgroepen voor de taaktaakverdelingsbalansen van uw toepassing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) voor het mogelijk maken van kleverigheid op ALB-niveau. Laat de kleverigheid één dag toe.

### Stap 1: Klantkoppen configureren {#step-configuring-client-headers}

Voeg het volgende toe aan `/clientheaders`sectie:

**x-requested-with**

**X-SET HEARTBEAT**

**X-REQUEST-COMMAND**

### Stap 2: schermfilters configureren {#step-configure-screens-filters}

Als u schermfilters wilt configureren, voegt u het volgende toe: ***/filter***.

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

### Stap 3: Het onbruikbaar maken het Geheime voorgeheugen van de Verzender {#step-disabling-dispatcher-cache}

Dispatcher caching uitschakelen voor ***/content/screens pad***.

Schermspelers gebruiken geverifieerde sessies, zodat de Dispatcher geen van de schermspelers in de cache plaatst die om `channels/assets`.

Als u de cache voor de elementen wilt inschakelen zodat de elementen worden verzonden vanuit de Dispatcher-cache, moet u:

* Toevoegen `/allowAuthorization 1` in `/cache` sectie
* Voeg de onderstaande regels toe aan `/rules` deel van `/cache`

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

## Dispatcher configureren voor manifestversie v3{#configuring-dispatcherv3}

Zorg ervoor dat u deze filters en cacheregels toestaat in verzenders die de publicatie-instanties voor schermfuncties vooraf bekijken.

### Voorwaarden voor manifestversie v3{#prerequisites3}

Voer de volgende twee voorwaarden uit voordat u Dispatcher (manifestversie v3) voor AEM Screens configureert:

* Zorg ervoor dat u `v3 manifests`. Navigeren naar `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` en ervoor zorgen dat `Enable ContentSync Cache` is uitgeschakeld.

* Zorg ervoor dat de Dispatcher flush-agent is geconfigureerd op `/etc/replication/agents.publish/dispatcher1useast1Agent` in publicatieexemplaar.

  ![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-1.png)

  ![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-3.png)

### Filters  {#filter-v3}

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

* Toevoegen `/allowAuthorized "1"` tot `/cache` sectie in `publish_farm.any`.

* Alle AEM Screens-spelers gebruiken geverifieerde sessies om verbinding te maken met AEM (auteur/publicatie). De uit-van-de-doos Dispatcher bewaart deze urls niet, zodat zou u die moeten toelaten.

* Toevoegen `statfileslevel "10"` tot `/cache` sectie in `publish_farm.any`
Dit steunt caching tot tien niveaus van geheim voorgeheugendocroot en ongeldig maakt dienovereenkomstig wanneer de inhoud wordt gepubliceerd eerder dan alles ongeldig. U kunt dit niveau wijzigen op basis van de diepte van de inhoudstructuur

* Voeg het volgende toe aan `/invalidate section in publish_farm.any`

  ```
  /0003 {
      /glob "*.json"
      /type "allow"
  }
  ```

* Voeg de volgende regels toe aan `/rules` sectie in `/cache` in `publish_farm.any` of in een bestand waarvan `publish_farm.any`:

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

Als u gerichte campagnes gebruikt met AEM Screens, dan `segments.js file` Dient door de Dispatcher worden gediend moet ongeldig worden gemaakt, aangezien u toevoegt en nieuwe segmenten op AEM publiceert. Zonder deze validatieregel werken nieuwe doelcampagnes niet op de AEM Screens-speler (in plaats daarvan wordt de standaardinhoud weergegeven).

* Een validatieregel toevoegen aan `/etc/httpd/conf.dispatcher.d/available_farms/999_ams_publish_farm.any`. Hier volgt de regel die moet worden toegevoegd:

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

* Deze regel zorgt voor de `segments.js` Het bestand is ongeldig en de nieuwste versie wordt opgehaald wanneer deze wordt gewijzigd.
