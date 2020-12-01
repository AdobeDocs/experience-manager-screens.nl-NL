---
title: Hoofdlettergebruik voor overgangen van MultiZone naar SingleZone
description: Volg deze pagina voor meer informatie over het gebruik van hoofdletters en kleine letters voor multiZone-overgangen.
seo-description: MultiZone naar SingleZone Overgangen gebruiken hoofdletters en kleine letters.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 6f770734941635a0cd404986c259022137355af3
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---


# Meerdere zones naar één zone - overgang {#multizone-to-singlezone-use-case}


## Hoofdletterbeschrijving gebruiken {#use-case-description}

In deze sectie wordt een gebruikscasevoorbeeld beschreven waarin wordt benadrukt hoe u een lay-outkanaal met meerdere zones instelt dat met een lay-outkanaal met één zone afwisselt. Het kanaal met meerdere zones heeft het rangschikken van beeld/video activa en het toont hoe u opstellingsproject kunt dat van multi-zone aan single-zone en vice versa afwisselt.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire ACTOR {#primary-actors}

Inhoudsauteurs

## Het project {#setting-up-the-project} instellen

Voer de onderstaande stappen uit om een project in te stellen:

1. Maak een AEM Screens-project met de naam **Overnameloop**, zoals hieronder wordt weergegeven.

   ![element](assets/mz-to-sz1.png)


1. **Een uit meerdere zones bestaand rasterkanaal maken**

   1. Selecteer de map **Kanalen** en klik op **Maken** op de actiebalk om de wizard te openen en een kanaal te maken.
   1. Selecteer **Linker-L Bar Split Screen Channel** van de tovenaar en creeer het kanaal genoemd als **MultiZoneLayout**.
   1. Voeg inhoud toe aan het kanaal. Sleep de elementen naar elk van de zones. In het volgende voorbeeld ziet u een kanaal **MultiZoneLayout** dat bestaat uit een video, een afbeelding en een tekstbanner (in een ingesloten reeks), zoals hieronder wordt weergegeven.

   ![element](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Raadpleeg [Layout met meerdere zones](multi-zone-layout-aem-screens.md) voor meer informatie over het maken van een lay-out met meerdere zones in uw kanaal.


1. Maak een ander kanaal met de naam **Overnamekanaal** naar de map **Kanalen**.

   ![element](assets/mz-to-sz3.png)

1. Klik op **Bewerken** op de actiebalk om inhoud aan dit kanaal toe te voegen. Voeg een **Kanaal** component en een beeldmiddel toe dat u wilt overschakelen aan dit kanaal, zoals aangetoond in het hieronder cijfer:

   ![element](assets/mz-to-sz4.png)

1. Open de instellingen voor de component Channel en wijs deze naar het kanaal **MultiZoneLayout** dat u hebt gemaakt in *stap 2*.

   ![element](assets/mz-to-sz5.png)

1. Stel de duur in van het veld **Reeks** op **10000 ms**.

   ![element](assets/mz-to-sz6.png)

1. Open op dezelfde manier de instellingen voor de afbeelding (het element dat u hebt toegevoegd) en stel de duur van de afbeelding in op **Reeks** in het veld **3000 ms**.

   ![element](assets/mz-to-sz7.png)

## Voorvertoning {#checking-the-preview} controleren

U kunt de gewenste output van de speler bekijken of enkel door op **Voorproef** van de redacteur te klikken.

De uitvoer toont hoe een lay-out met meerdere zones voor *10000 ms* wordt afgespeeld en dan overschakelt naar de lay-out met één zone die de afspeelduur van *3000 ms* heeft en vervolgens weer overschakelt naar de lay-out met meerdere zones.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>U kunt uw kanaalovergang (van multi-zone aan single-zone lay-out of vice versa), volgens uw vereisten aanpassen.