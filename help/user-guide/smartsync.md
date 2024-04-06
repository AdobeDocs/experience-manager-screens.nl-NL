---
title: Overstappen van ContentSync naar SmartSync
seo-title: Transitioning from ContentSync to SmartSync
description: Volg deze pagina voor meer informatie over de functie SmartSync en over de overgang van ContentSync naar SmartSync.
seo-description: Follow this page to learn about SmartSync feature and how you can transition from ContentSync to SmartSync.
uuid: c0619b56-1f6f-465a-a428-6df28e40b555
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 822dfbc1-3584-4509-a35c-1d68e5f84509
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: b8d0c089-af79-403e-870f-fb46b66fecd3
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Overstappen van ContentSync naar SmartSync {#transitioning-from-contentsync-to-smartsync}

Deze sectie biedt een overzicht van de functie SmartSync en hoe deze de belasting van de server/opslag en het netwerkverkeer minimaliseert om de kosten te verlagen.

## Overzicht {#overview}

SmartSync is het meest recente mechanisme dat door AEM Screens wordt gebruikt. Het dient als vervanging van de huidige methode die wordt gebruikt om offlinekanalen in de cache op te slaan en aan de speler te leveren.

Deze wordt zowel op de server als op de client uitgevoerd.

**Op de server**:

* Inhoud van de kanalen, inclusief elementen, wordt in cache geplaatst in */var/contentSync*.
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
>Adobe raadt u ten zeerste aan om SmartSync te gebruiken voor AEM Screens-projecten.

## Migreren van ContentSync naar SmartSync {#migrating-from-contentsync-to-smartsync}

>[!NOTE]
>
>Als u al AEM 6.3 Feature Pack 5 en AEM 6.4 Feature Pack 3 hebt geïnstalleerd, kunt u SmartSync voor middelen inschakelen om het gebruik van schijfruimte te verbeteren. Als u SmartSync wilt inschakelen, volgt u de onderstaande sectie voor de overgang van ContentSync naar SmartSync en schakelt u SmartSync dus in.
>
>SmartSync is beschikbaar voor schermPlayer met ondersteunde servers AEM 6.4.3 FP3.
>
>Zie de [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/) om de nieuwste speler te downloaden. In de volgende tabel wordt de minimaal vereiste Player-versie voor elk platform beschreven:

| **Platform** | **Minimaal ondersteunde Player-versie** |
|---|---|
| Android | 3.3.72. |
| Chrome-besturingssysteem | 1.0.136 |
| Windows | 1.0.136 |

Voer de onderstaande stappen uit om van ContentSync over te schakelen op SmartSync:

1. Voor het migreren van ContentSync naar SmartSync moet de ContentSync-cache worden gewist voordat SmartSync wordt geactiveerd.

   Ga via de koppeling naar de ContentSync-console van uw instantie ***https://localhost:4502/libs/cq/contentsync/content/console.html*** en klik op **Cache wissen**, zoals weergegeven in onderstaande afbeelding:

   ![clear_contesync_cache](assets/clear_contesync_cache.png)

   >[!CAUTION]
   >
   >Alle inhoudcache moet worden gewist voordat u SmartSync voor het eerst kunt gebruiken.

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** via AEM instantie > hamerpictogram > **Bewerkingen** > **Webconsole**.

   ![screen_shot_2019-02-11at15339pm](assets/screen_shot_2019-02-11at15339pm.png)

1. **Configuratie Adobe Experience Manager-webconsole** wordt geopend. Zoeken naar *offlinecontent*.

   Voor het zoeken van de **Schermen offline-inhoudsservice** eigenschap, druk **Command+F** for **Mac** en **Ctrl+F** for **Windows**.

   ![screen_shot_2019-02-19at2643pm](assets/screen_shot_2019-02-19at22643pm.png)

1. Klikken **Opslaan** de **Schermen met services voor offline inhoud** en dus SmartSync voor AEM Screens gebruiken.
1. Nadat u SmartSync hebt ingeschakeld, moet u naar uw project navigeren en op **Offline inhoud bijwerken** *(vanaf de actiebalk),* zoals weergegeven in onderstaande afbeelding.

   ![screen_shot_2019-02-25at102605am](assets/screen_shot_2019-02-25at102605am.png)
