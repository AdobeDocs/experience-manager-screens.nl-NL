---
title: Authoring met gegevenstriggers
seo-title: Authoring met gegevenstriggers
description: Volg deze pagina om te leren hoe u ontwerpt met gegevenstriggers.
feature: Authoring Screens
role: Administrator, Developer
level: Intermediate
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---


# Ontwerpen met gegevenstriggers {#authoring-with-data-triggers}

Deze sectie benadrukt hoe te om het richten in uw kanalen toe te laten.

>[!IMPORTANT]
>
>De minimumversie die gegevenstriggers in een AEM Screens-kanaal ondersteunt, is AEM 6.5.3 Feature Pack 3.

## Vereisten {#prereqs}

Alvorens u de stappen hieronder volgt om het richten in kanalen toe te laten, moet u de [Zeer belangrijke Termijnen in het Vormen in AEM Screens](configuring-context-hub.md) leren die voor het begrip van ContextHub en het richten in AEM Screens wordt vereist.

>[!IMPORTANT]
>
>Men adviseert dat u configuraties ContextHub begrijpt en opstelling, alvorens het richten in een kanaal van AEM Screens toe te laten.

Volg onderstaande koppelingen voor meer informatie:

1. **[Gegevensopslag instellen](configuring-context-hub.md)**
1. **[Segmentering publiek instellen](configuring-context-hub.md)**

Nadat u de voorgaande stappen hebt uitgevoerd, kunt u het activeren van de doelgroep op uw kanalen inschakelen.

## Authoring met overzicht van gegevenstriggers {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Het toelaten van het Targeting in een Kanaal van AEM Screens {#enabling-targeting}

Voer de onderstaande stappen uit om het activeren van uw doelbestanden in te schakelen.

1. Navigeer naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door **DataDrivenRetail** *(opeenvolgingskanaal)* te gebruiken die in een Kanaal van AEM Screens wordt gecreeerd.

1. Selecteer het kanaal **DataDrivenRetail** en klik **Eigenschappen** van de actiebar.

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Selecteer **Personalization** lusje om de configuraties te opstelling ContextHub en de weg van ContextHub en van Segmenten te selecteren.

   1. Selecteer **ContextHub Path** als **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Configurations** en klik ****.

   1. Selecteer **Segmentpad** als **conf** > **We.Retail** > **settings** > **wcm** > **segments** en klik **Selecteer a1 >.**

   1. Klik **Opslaan en sluiten**.
   >[!NOTE]
   >
   >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigeer en selecteer **DataDrivenRetail** uit **DataDrivenAssets** > **Kanalen** en klik **Bewerken** op de actiebalk. Sleep de elementen naar de Kanaaleditor en zet ze neer.

   >[!NOTE]
   >
   >Als u opstelling alles correct hebt geplaatst, zult u **het richten** optie in drop-down van de redacteur zien, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Klik **gericht**.

1. Selecteer **Merk** en **Activiteit** van het drop-down menu en klik **Begin richten**.

### Meer informatie: Voorbeeld van gebruik van gevallen {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
