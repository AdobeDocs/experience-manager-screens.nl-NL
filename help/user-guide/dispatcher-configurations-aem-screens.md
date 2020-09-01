---
title: Dispatcher Configurations voor AEM Screens
seo-title: Dispatcher Configurations voor AEM Screens
description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
seo-description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van AEM Screens.
translation-type: tm+mt
source-git-commit: 8e8413221d0f79f8e46e15d0f00a710296883739
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 4%

---


# Dispatcher Configurations voor AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen.

De volgende pagina verstrekt de richtlijnen voor het vormen verzender voor een project van AEM Screens.

>[!NOTE]
>
>Als een verzender beschikbaar is, kunnen verbindingen met de registratieserver worden verhinderd door in de verzeneringsregels te filtreren.
>
>Als er geen verzender is, maak de registratieserver in de OSGi componentenlijst onbruikbaar.

## Voorwaarden {#pre-requisites}

Voordat u een dispatcher configureert voor een AEM Screens-project, moet u vooraf op de hoogte zijn van Dispatcher.

Raadpleeg [Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) configureren voor meer informatie.

## Dispatcher configureren {#configuring-dispatcher}

Voer de onderstaande stappen uit om de dispatcher voor een AEM Screens-project te configureren.

### Stap 1: Clientkoppen configureren {#step-configuring-client-headers}

Voeg het volgende toe aan `/clientheaders`sectie:

**x-requested-with**

**X-SET HEARTBEAT**

**X-REQUEST-COMMAND**

### Stap 2: Schermfilters configureren {#step-configuring-screens-filters}

Voeg het volgende toe aan ***/filter*** om schermfilters te configureren.

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

Schakel caching van dispatcher voor ***/content/screens pad*** uit.

Schermspelers gebruiken geverifieerde sessies, zodat de verzender geen van de schermspelers-aanvragen `channels/assets`in de cache plaatst.

Als u de cache voor de elementen wilt inschakelen zodat de elementen worden verzonden in de cache van de verzender, moet u:

* Toevoegen `/allowAuthorization 1` in `/cache` sectie
* Voeg de onderstaande regels toe aan de sectie `/rule`s van `/cache`

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
