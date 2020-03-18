---
title: Dispatcher Configurations voor AEM-schermen
seo-title: Dispatcher Configurations voor AEM-schermen
description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van de Schermen AEM.
seo-description: Deze pagina benadrukt richtlijnen voor het vormen van dispatcher voor een project van de Schermen AEM.
uuid: ec5219b7-73f9-4026-99e5-e4a02201b128
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
discoiquuid: 1b1a36a4-4f95-41e3-b0a8-74249efb0119
docset: aem65
translation-type: tm+mt
source-git-commit: 9bee12b69ae85e84572b6f9e8c70f792895d9a32

---


# Dispatcher Configurations voor AEM-schermen{#dispatcher-configurations-for-aem-screens}

Dispatcher is het programma voor het in cache plaatsen en/of taakverdeling van Adobe Experience Manager.

De volgende pagina bevat de richtlijnen voor het configureren van dispatcher voor een AEM Screens-project.

>[!NOTE]
>Als een verzender beschikbaar is, kunnen verbindingen met de registratieserver worden verhinderd door in de verzeneringsregels te filtreren.
>Als er geen verzender is, maak de registratieserver in de OSGi componentenlijst onbruikbaar.

## Voorwaarden {#pre-requisites}

Voordat u een dispatcher configureert voor een AEM Screens-project, moet u over voorafgaande kennis van Dispatcher beschikken.

Raadpleeg [Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) configureren voor meer informatie.

## Dispatcher configureren {#configuring-dispatcher}

Voer de onderstaande stappen uit om de verzender voor een AEM-schermproject te configureren.

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
/0201 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
## # Device Dashboard Configurations
/0204 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0205 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0206 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0207 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
## # Content Configurations
/0208 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
/0209 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*/jcr:content/*/offline-config_*.zip" }
/0210 { /type "allow" /method '(GET|HEAD)' /url '/var/contentsync/content/screens/.+/jcr:content/.+/offline-config_.*\.[0-9]+\.zip' }
```

### Stap 3: Dispatcher Cache uitschakelen {#step-disabling-dispatcher-cache}

Schakel caching van dispatcher voor ***/content/screens pad*** uit.
