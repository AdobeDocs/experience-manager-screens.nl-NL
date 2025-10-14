---
title: Authoring met gegevenstriggers
description: Meer informatie over hoe u kunt ontwerpen met gegevenstriggers in een AEM Screens-kanaal.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c95da2e9-a216-4d0a-85d0-a0fb895a8d8a
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Authoring met gegevenstriggers {#authoring-with-data-triggers}

Deze sectie benadrukt hoe te om het richten in uw kanalen toe te laten.

>[!IMPORTANT]
>
>De minimumversie die gegevenstriggers in een AEM Screens-kanaal ondersteunt, is AEM 6.5.3 Feature Pack 3.

## Vereisten {#prereqs}

Alvorens u de stappen hieronder volgt om het richten in kanalen toe te laten, leer de [&#x200B; Zeer belangrijke Termijnen in het Vormen in AEM Screens &#x200B;](configuring-context-hub.md) die voor het begrip ContextHub en het richten in AEM Screens wordt vereist.

>[!IMPORTANT]
>
>Men adviseert dat u configuraties ContextHub begrijpt en opstelling, alvorens het richten in een kanaal van AEM Screens toe te laten.

Volg onderstaande koppelingen voor meer informatie:

1. **[de Opslag van Gegevens van de Opstelling](configuring-context-hub.md)**
1. **[de Segmentatie van het Publiek van de Opstelling](configuring-context-hub.md)**

Wanneer u de voorafgaande stappen hebt voltooid, bent u klaar om het richten in uw kanalen toe te laten.

## Authoring met overzicht van gegevenstriggers {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Het toelaten van Targeting in een Kanaal van AEM Screens {#enabling-targeting}

Voer de onderstaande stappen uit om het activeren van doelwitbestanden in uw kanalen in te schakelen.

1. Ga naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door **DataDrivenRetail** te gebruiken *(opeenvolgingskanaal)* die in een kanaal van AEM Screens wordt gecreeerd.

1. Klik het kanaal **DataDrivenRetail** en klik **Eigenschappen** van de actiebar.

   ![&#x200B; screen_shot_2019-05-01at43332pm &#x200B;](assets/screen_shot_2019-05-01at43332pm.png)

1. Klik het **Personalization** lusje zodat kunt u opstelling de configuraties ContextHub en klik de weg ContextHub en van Segmenten.

   1. Klik de **Weg ContextHub** als **bibliotheken** > **montages** > **cloudsettings** > **gebrek** > **Configuraties ContextHub** en klik **klikken**.

   1. Klik de **Weg van Segmenten** als **conf** > **`We.Retail`** > **montages** > **wcm** > **segmenten** en klik **klikken**.

   1. Klik **sparen &amp; Sluiten**.

   >[!NOTE]
   >
   >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![&#x200B; screen_shot_2019-05-01at44030pm &#x200B;](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigeer en klik **DataDrivenRetail** van **DataDrivenAssets** > **Kanalen** en klik **uitgeven** van de actiebar. Sleep de elementen naar de Kanaaleditor en zet ze neer.

   >[!NOTE]
   >
   >Als u opstelling alles correct hebt, ziet u de **het richten** optie in drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

   ![&#x200B; screen_shot_2019-05-01at44231pm &#x200B;](assets/screen_shot_2019-05-01at44231pm.png)

1. Klik **het richten**.

1. Klik **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.

### Meer informatie: voorbeelden gebruiken {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Detailhandel gerichte Activering van de Inventaris](retail-inventory-activation.md)**
1. **[de Activering van de Temperatuur van het Centrum van de Reizen](local-temperature-activation.md)**
1. **[Activering van de Voorbehoud van de Ziekenhuis](hospitality-reservation-activation.md)**
