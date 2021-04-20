---
title: Overstappen van ContentSync naar SmartSync
seo-title: Overstappen van ContentSync naar SmartSync
description: Volg deze pagina voor meer informatie over de functie SmartSync en over de overgang van ContentSync naar SmartSync.
seo-description: Volg deze pagina voor meer informatie over de functie SmartSync en over de overgang van ContentSync naar SmartSync.
uuid: c0619b56-1f6f-465a-a428-6df28e40b555
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 822dfbc1-3584-4509-a35c-1d68e5f84509
docset: aem65
feature: Administering Screens
role: Administrator
level: Intermediate
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---


# Overstappen van ContentSync naar SmartSync {#transitioning-from-contentsync-to-smartsync}

Deze sectie biedt een overzicht van de functie SmartSync en hoe deze de belasting van de server/opslag en het netwerkverkeer minimaliseert om de kosten te verlagen.

## Overzicht {#overview}

SmartSync is het meest recente mechanisme dat door AEM Screens wordt gebruikt. Het dient als vervanging van de huidige methode die wordt gebruikt om offlinekanalen in de cache op te slaan en aan de speler te leveren.

Deze wordt zowel op de server als op de client uitgevoerd.

**Aan serverzijde**:

* Inhoud van de kanalen, inclusief elementen, wordt in het cachegeheugen opgeslagen in */var/contentsync*.
* Cache wordt aan de spelers blootgesteld via een manifest dat de beschikbare inhoud voor een vertoning beschrijft.

**Aan de clientzijde**:

* De speler werkt zijn inhoud bij die op hierboven geproduceerd manifest wordt gebaseerd.

### Voordelen van het gebruik van SmartSync {#benefits-of-using-smartsync}

De functie SmartSync biedt een aantal voordelen voor uw AEM Screens-project. Het staat

* Dramatische vermindering van het netwerkverkeer en de vereisten van de serveropslag
* De speler downloadt intelligent activa slechts als het middel ontbreekt of verandert
* Optimalisatie van server- en clientopslag

>[!NOTE]
>
>Adobe raadt u ten zeerste aan SmartSync te gebruiken voor AEM Screens-projecten.

## Migreren van ContentSync naar SmartSync {#migrating-from-contentsync-to-smartsync}

>[!NOTE]
>
>Als u al AEM 6.3 Feature Pack 5 en AEM 6.4 Feature Pack 3 hebt geïnstalleerd, kunt u SmartSync voor middelen inschakelen om het gebruik van schijfruimte te verbeteren. Als u SmartSync wilt inschakelen, volgt u de onderstaande sectie voor de overgang van ContentSync naar SmartSync en schakelt u SmartSync dus in.
>
>SmartSync is beschikbaar voor schermPlayer met ondersteunde servers AEM 6.4.3 FP3.
>
>Raadpleeg [AEM Screens Player Downloads](https://download.macromedia.com/screens/) om de nieuwste speler te downloaden. In de volgende tabel wordt de minimaal vereiste Player-versie voor elk platform beschreven:

| **Platform** | **Minimaal ondersteunde Player-versie** |
|---|---|
| Android | 3.3.72. |
| Chrome-besturingssysteem | 1.0.136 |
| Windows | 1.0.136 |

Voer de onderstaande stappen uit om van ContentSync over te schakelen op SmartSync:

1. Voor het migreren van ContentSync naar SmartSync moet de ContentSync-cache worden gewist voordat SmartSync wordt geactiveerd.

   Navigeer aan de console ContentSync van uw instantie gebruikend de verbinding ***https://localhost:4502/libs/cq/contentsync/content/console.html*** en klik **Duidelijke Cachegeheugen**, zoals aangetoond in het hieronder cijfer:

   ![clear_contesync_cache](assets/clear_contesync_cache.png)

   >[!CAUTION]
   >
   >Alle inhoudcache moet worden gewist voordat u SmartSync voor het eerst kunt gebruiken.

1. Navigeer naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![screen_shot_2019-02-11at15339pm](assets/screen_shot_2019-02-11at15339pm.png)

1. **Adobe Experience Manager Web Console** Configuration wordt geopend. Zoeken naar *offlinecontent service*.

   Voor het zoeken van **de eigenschap Offline Content Service** van Schermen, druk **Command+F** voor **Mac** en **Control+F** voor **Windows**.

   ![screen_shot_2019-02-19at22643pm](assets/screen_shot_2019-02-19at22643pm.png)

1. Klik op **Opslaan** om de eigenschap **Offline Content Services** voor schermen in te schakelen en gebruik daarom SmartSync voor AEM Screens.
1. Nadat u SmartSync hebt ingeschakeld, navigeert u naar uw project en klikt u op **Offlineinhoud bijwerken** *(vanuit de actiebalk),* zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-02-25at102605am](assets/screen_shot_2019-02-25at102605am.png)