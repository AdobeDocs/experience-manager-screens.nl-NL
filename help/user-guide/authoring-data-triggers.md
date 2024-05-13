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

Leer voordat u de onderstaande stappen uitvoert om het gebruik van doelkanalen in te schakelen, de [Belangrijke termen in configuratie in AEM Screens](configuring-context-hub.md) vereist voor het begrip ContextHub en het richten in AEM Screens.

>[!IMPORTANT]
>
>Men adviseert dat u configuraties ContextHub begrijpt en opstelling, alvorens het richten in een kanaal van AEM Screens toe te laten.

Volg onderstaande koppelingen voor meer informatie:

1. **[Gegevensopslag instellen](configuring-context-hub.md)**
1. **[Segmentering publiek instellen](configuring-context-hub.md)**

Wanneer u de voorafgaande stappen hebt voltooid, bent u klaar om het richten in uw kanalen toe te laten.

## Authoring met overzicht van gegevenstriggers {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Het toelaten van Targeting in een Kanaal van AEM Screens {#enabling-targeting}

Voer de onderstaande stappen uit om het activeren van doelwitbestanden in uw kanalen in te schakelen.

1. Ga naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door te gebruiken **DataDrivenRetail** *(volgnummer)* gemaakt in een AEM Screens-kanaal.

1. Klik op het kanaal **DataDrivenRetail** en klik op **Eigenschappen** in de actiebalk.

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Klik op de knop **Personalisatie** lusje zodat kunt u opstelling de configuraties ContextHub en klik de weg ContextHub en van Segmenten.

   1. Klik op de knop **ContextHub-pad** als **libben** > **instellingen** > **cloudinstellingen** > **default** > **ContextHub-configuraties** en klik op **Klikken**.

   1. Klik op de knop **Segmentpad** als **conf** > **`We.Retail`** > **instellingen** > **wcm** > **segmenten** en klik op **Klikken**.

   1. Klikken **Opslaan en sluiten**.

   >[!NOTE]
   >
   >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigeren en op de knop **DataDrivenRetail** van **DataDrivenAssets** > **Kanalen** en klik op **Bewerken** in de actiebalk. Sleep de elementen naar de Kanaaleditor en zet ze neer.

   >[!NOTE]
   >
   >Als u alles correct hebt ingesteld, ziet u de **Targeting** in de drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Klikken **Targeting**.

1. Klikken **Merk** en de **Activiteit** in het keuzemenu en klik op **Doelstelling starten**.

### Meer informatie: voorbeelden gebruiken {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
