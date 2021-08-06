---
title: Dispatcher Configurations voor AEM Screens
seo-title: Dispatcher Configurations voor AEM Screens
description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
seo-description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
feature: Schermen beheren
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
source-git-commit: 89b4bc6b7eca18d37246be188eddad87443a96d6
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 2%

---

# Dispatcher Configurations voor AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen.

De volgende pagina verstrekt de richtlijnen voor het vormen verzender voor een project van AEM Screens.

>[!NOTE]
>
>Als een verzender beschikbaar is, kunnen verbindingen met de registratieserver worden verhinderd door in de verzeneringsregels te filtreren.
>
>Als er geen verzender is, maak de registratieserver in de OSGi componentenlijst onbruikbaar.

## Voorwaarden {#prerequisites}

Voordat u een dispatcher configureert voor een AEM Screens-project, moet u vooraf op de hoogte zijn van Dispatcher.
Raadpleeg [Dispatcher configureren](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) voor meer informatie.

## Dispatcher configureren voor manifestversie v2 {#configuring-dispatcher}

>[!IMPORTANT]
>De volgende Dispatcher-configuraties zijn alleen van toepassing op Manifest-versie v2. Raadpleeg [Dispatcher Configurations for Manifest version v3](#configuring-dispatcherv3) for manifest version v3.

AEM Screens-spelers of -apparaten gebruiken geverifieerde sessies om ook toegang te krijgen tot de bronnen in de publicatieinstanties. Als u dus meerdere publicatieinstanties hebt, moeten de aanvragen altijd naar dezelfde publicatieinstantie gaan, zodat de geverifieerde sessie geldig is voor alle aanvragen die afkomstig zijn van de AEM Screens-spelers/apparaten.

Voer de onderstaande stappen uit om de dispatcher voor een AEM Screens-project te configureren.

### Vaste sessies inschakelen {#enable-sticky-session}

Als u meerdere publicatie-instanties wilt gebruiken die worden voorafgegaan door één verzender, moet u het `dispatcher.any`-bestand bijwerken om kleverigheid mogelijk te maken

```xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

Als u één publicatie-instantie hebt voorafgegaan door één verzender, helpt het inschakelen van de kleverigheid bij de verzender niet omdat het taakverdelingsmechanisme elke aanvraag naar de verzender kan verzenden. In dit geval klikt u op **Enable** in het veld **Stickiness** om deze in te schakelen op het niveau van het taakverdelingsmechanisme, zoals in de onderstaande afbeelding wordt getoond:

![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

Bijvoorbeeld, als u AWS ALB gebruikt, verwijs naar [Doelgroepen voor uw Balancers van de Lading van de Toepassing ](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) voor het toelaten van kleverigheid op het niveau van ALB. Laat de kleverigheid 1 dag toe.

### Stap 1: Clientkoppen configureren {#step-configuring-client-headers}

Voeg het volgende toe aan `/clientheaders`sectie:

**x-requested-with**

**X-SET HEARTBEAT**

**X-REQUEST-COMMAND**

### Stap 2: Schermfilters configureren {#step-configuring-screens-filters}

Als u schermfilters wilt configureren, voegt u het volgende toe aan ***/filter***.

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

Schakel caching van dispatcher uit voor ***/content/screens path***.

Schermspelers gebruiken geverifieerde sessie, zodat de verzender geen van de schermspelers-aanvragen voor `channels/assets` in de cache plaatst.

Als u de cache voor de elementen wilt inschakelen zodat de elementen worden verzonden in de cache van de verzender, moet u:

* `/allowAuthorization 1` toevoegen in `/cache`-sectie
* Voeg de onderstaande regels toe aan `/rules`-sectie van `/cache`

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

Zorg ervoor dat u deze filters en cacheregels toestaat in verzenders die de publicatie-instanties voor het functioneren van schermen vooraf verzenden.

### Voorwaarden voor Manifest versie v3{#prerequisites3}

Zorg ervoor dat u aan deze twee voorwaarden voldoet voordat u Dispatcher (manifestversie v3) voor AEM Screens configureert:

* Zorg ervoor dat u `v3 manifests` gebruikt. Navigeer naar `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` en controleer of `Enable ContentSync Cache` is uitgeschakeld.

* Zorg ervoor dat de verzender flush agent bij `/etc/replication/agents.publish/dispatcher1useast1Agent` in publicatieinstantie wordt gevormd.

   ![afbeelding](/help/user-guide/assets/dispatcher/dispatcher-1.png)

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

* Voeg `/allowAuthorized "1"` aan `/cache` sectie in `publish_farm.any` toe.

* Alle schermspelers gebruiken geverifieerde sessies om verbinding te maken met AEM (auteur/publicatie). De uit-van-de-doos Dispatcher bewaart deze urls niet, zodat zouden wij die moeten toelaten.

* `statfileslevel "10"` toevoegen aan `/cache`-sectie in `publish_farm.any`
Dit zal caching tot 10 niveaus van cachedocroot steunen en dienovereenkomstig ongeldig maken wanneer de inhoud wordt gepubliceerd eerder dan alles ongeldig te maken. U kunt dit niveau wijzigen op basis van de diepte van de inhoudstructuur

* Voeg het volgende toe aan `/invalidate section in publish_farm.any`

```
/0003 {
    /glob "*.json"
    /type "allow"
}
```

Voeg de volgende regels toe aan `/rules` sectie in `/cache` in `publish_farm.any` of in een dossier dat van `publish_farm.any` inbegrepen is:

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
