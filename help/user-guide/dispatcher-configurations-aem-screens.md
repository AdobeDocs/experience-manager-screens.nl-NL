---
title: Dispatcher Configurations voor AEM Screens
seo-title: Dispatcher Configurations voor AEM Screens
description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
seo-description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
translation-type: tm+mt
source-git-commit: 4a1fb81fa343983093590c36ccb6a4fd110cdad2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---


# Dispatcher Configurations for AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen.

De volgende pagina verstrekt de richtlijnen voor het vormen verzender voor een project van AEM Screens.

>[!NOTE]
>
>Als een verzender beschikbaar is, kunnen verbindingen met de registratieserver worden verhinderd door in de verzeneringsregels te filtreren.
>
>Als er geen verzender is, maak de registratieserver in de OSGi componentenlijst onbruikbaar.

## Voorwaarden {#pre-requisites}

Voordat u een dispatcher configureert voor een AEM Screens-project, moet u vooraf op de hoogte zijn van Dispatcher.

Raadpleeg [Dispatcher configureren](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) voor meer informatie.

## Dispatcher {#configuring-dispatcher} configureren

Voer de onderstaande stappen uit om de dispatcher voor een AEM Screens-project te configureren.

### Vaste sessies {#enable-sticky-session} inschakelen

Als u meer dan één publicatie-instantie met dispatcher wilt gebruiken, moet u het `dispatcher.any`-bestand bijwerken.

```xml
/stickyConnections {
  /paths
  {
    "/content/screens"
    "/home/users/screens"
    "/libs/granite/csrf/token.json"
  }
}
```

### Stap 1: Klantkoppen {#step-configuring-client-headers} configureren

Voeg het volgende toe aan `/clientheaders`sectie:

**x-requested-with**

**X-SET HEARTBEAT**

**X-REQUEST-COMMAND**

### Stap 2: Schermfilters {#step-configuring-screens-filters} configureren

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

### Stap 3: Dispatcher Cache {#step-disabling-dispatcher-cache} uitschakelen

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
