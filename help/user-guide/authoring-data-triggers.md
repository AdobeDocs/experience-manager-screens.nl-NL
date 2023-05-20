---
title: Authoring met gegevenstriggers
seo-title: Authoring with Data Triggers
description: Volg deze pagina om te leren hoe u ontwerpt met gegevenstriggers.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c95da2e9-a216-4d0a-85d0-a0fb895a8d8a
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---

# Authoring met gegevenstriggers {#authoring-with-data-triggers}

Deze sectie benadrukt hoe te om het richten in uw kanalen toe te laten.

>[!IMPORTANT]
>
>De minimumversie die gegevenstriggers in een AEM Screens-kanaal ondersteunt, is AEM 6.5.3 Feature Pack 3.

## Vereisten {#prereqs}

Voordat u de onderstaande stappen uitvoert om het gebruik van doelkanalen in te schakelen, moet u de opdracht [Belangrijke termen in configuratie in AEM Screens](configuring-context-hub.md) vereist voor het begrip ContextHub en het richten in AEM Screens.

>[!IMPORTANT]
>
>Men adviseert dat u configuraties ContextHub begrijpt en opstelling, alvorens het richten in een kanaal van AEM Screens toe te laten.

Volg onderstaande koppelingen voor meer informatie:

1. **[Gegevensopslag instellen](configuring-context-hub.md)**
1. **[Segmentering publiek instellen](configuring-context-hub.md)**

Nadat u de voorgaande stappen hebt uitgevoerd, kunt u het activeren van de doelgroep op uw kanalen inschakelen.

## Authoring met overzicht van gegevenstriggers {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Het toelaten van Targeting in een Kanaal van AEM Screens {#enabling-targeting}

Voer de onderstaande stappen uit om het activeren van uw doelbestanden in te schakelen.

1. Navigeer naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door te gebruiken **DataDrivenRetail** *(volgnummer)* gemaakt in een AEM Screens Channel.

1. Selecteer het kanaal **DataDrivenRetail** en klik op **Eigenschappen** in de actiebalk.

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Selecteer **Personalisatie** lusje aan opstelling de configuraties ContextHub en selecteer de weg ContextHub en van Segmenten.

   1. Selecteer **ContextHub-pad** als **libben** > **instellingen** > **cloudinstellingen** > **default** > **ContextHub-configuraties** en klik op **Selecteren**.

   1. Selecteer **Segmentpad** als **conf** > **Wij.Detailhandel** > **instellingen** > **wcm** > **segmenten** en klik op **Selecteren**.

   1. Klikken **Opslaan en sluiten**.
   >[!NOTE]
   >
   >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigeer en selecteer de **DataDrivenRetail** van **DataDrivenAssets** > **Kanalen** en klik op **Bewerken** in de actiebalk. Sleep de elementen naar de Kanaaleditor en zet ze neer.

   >[!NOTE]
   >
   >Als u alles correct hebt ingesteld, ziet u **Doelstelling** in de drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Klikken **Doelstelling**.

1. Selecteren **Merk** en de **Activiteit** in het keuzemenu en klik op **Doelstelling starten**.

### Meer informatie: Voorbeelden {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
