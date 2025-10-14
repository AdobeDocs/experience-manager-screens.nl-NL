---
title: Overstappen van ContentSync naar SmartSync
description: Meer informatie over deze functie voor SmartSync en over de overgang van ContentSync naar SmartSync.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: b8d0c089-af79-403e-870f-fb46b66fecd3
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Overstappen van ContentSync naar SmartSync {#transitioning-from-contentsync-to-smartsync}

Deze sectie biedt een overzicht van de functie SmartSync en hoe deze de belasting van de server/opslag en het netwerkverkeer minimaliseert om de kosten te verlagen.

## Overzicht {#overview}

SmartSync is het meest recente mechanisme dat door AEM Screens wordt gebruikt. Het dient als vervanging van de huidige methode die wordt gebruikt om offlinekanalen in de cache op te slaan en aan de speler te leveren.

Deze wordt zowel op de server als op de client uitgevoerd.

**aan de kant van de Server**

* De inhoud van de kanalen, inclusief elementen, wordt in de cache opgeslagen in *`/var/contentsync`* .
* Cache wordt aan de spelers blootgesteld als manifest dat de beschikbare inhoud voor een vertoning beschrijft.

**aan de kant van de Cliënt**

* De speler werkt de inhoud bij op basis van het hierboven gegenereerde manifest.

### Voordelen van het gebruik van SmartSync {#benefits-of-using-smartsync}

De functie SmartSync biedt verschillende voordelen voor uw AEM Screens-project, zoals:

* Een drastische vermindering van het netwerkverkeer en de opslagvereisten aan de serverzijde.
* De speler downloadt op intelligente wijze elementen alleen als het element ontbreekt of is gewijzigd.
* Opslagoptimalisaties voor servers en clients.

>[!NOTE]
>
>Adobe raadt u aan SmartSync te gebruiken voor AEM Screens-projecten.

## Migreren van ContentSync naar SmartSync {#migrating-from-contentsync-to-smartsync}

>[!NOTE]
>
>Als u AEM 6.3 Feature Pack 5 en AEM 6.4 Feature Pack 3 al hebt geïnstalleerd, kunt u SmartSync voor middelen inschakelen om het gebruik van schijfruimte te verbeteren. Als u SmartSync wilt inschakelen, volgt u de onderstaande sectie voor de overgang van ContentSync naar SmartSync en schakelt u SmartSync dus in.
>
>SmartSync is beschikbaar voor Screens Player met ondersteunde servers AEM 6.4.3 FP3.
>
>Zie de [&#x200B; Downloads van de Speler van AEM Screens &#x200B;](https://download.macromedia.com/screens/) om de recentste speler te downloaden. In de volgende tabel wordt de minimaal vereiste Player-versie voor elk platform beschreven:

| **Platform** | **Minimum Ondersteunde Versie van de Speler** |
|---|---|
| Android™ | 3.3.72. |
| CHROME OS | 1.0.136 |
| Windows | 1.0.136 |

Voer de onderstaande stappen uit om van ContentSync over te schakelen op SmartSync:

1. Voor het migreren van ContentSync naar SmartSync moet de ContentSync-cache worden gewist voordat SmartSync wordt geactiveerd.

   Navigeer aan de console ContentSync van uw instantie gebruikend de verbinding ***https://localhost:4502/libs/cq/contentsync/content/console.html*** en klik **Duidelijk Geheime voorgeheugen**, zoals aangetoond in het hieronder cijfer:

   ![&#x200B; clear_contesync_cache &#x200B;](assets/clear_contesync_cache.png)

   >[!CAUTION]
   >
   >Alle inhoudcache moet worden gewist voordat u SmartSync voor het eerst kunt gebruiken.

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager** als instantie van AEM > hamerpictogram > **Verrichtingen** > **Console van het Web**.

   ![&#x200B; screen_shot_2019-02-11at15339pm &#x200B;](assets/screen_shot_2019-02-11at15339pm.png)

1. **de Configuratie van de Console van het Web van Adobe Experience Manager** opent. Onderzoek naar *offline contentservice*.

   Om het **Off-line bezit van de Dienst van de Inhoud van Screens te zoeken**, druk **Command+F** voor **Mac**, en **Control+F** voor **Vensters**.

   ![&#x200B; screen_shot_2019-02-19at22643pm &#x200B;](assets/screen_shot_2019-02-19at22643pm.png)

1. Klik **sparen** om het **Offline bezit van de Diensten van de Inhoud van Screens toe te laten** en vandaar SmartSync voor AEM Screens te gebruiken.
1. Wanneer u SmartSync hebt toegelaten, navigeer aan uw project en klik **Update Offline Inhoud** *(van de actiebar),* zoals aangetoond in het hieronder cijfer.

   ![&#x200B; screen_shot_2019-02-25at102605am &#x200B;](assets/screen_shot_2019-02-25at102605am.png)
