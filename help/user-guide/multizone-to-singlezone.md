---
title: Hoofdlettergebruik voor overgangen van MultiZone naar SingleZone
description: Volg deze pagina voor meer informatie over het gebruik van hoofdletters en kleine letters voor multiZone-overgangen.
seo-description: MultiZone naar SingleZone Overgangen gebruiken hoofdletters en kleine letters.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 6f770734941635a0cd404986c259022137355af3

---


# Overgang van meerdere zones naar één zone {#multizone-to-singlezone-use-case}


## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruikscasevoorbeeld beschreven waarin wordt benadrukt hoe u een lay-outkanaal met meerdere zones instelt dat met een lay-outkanaal met één zone afwisselt. Het kanaal met meerdere zones heeft het rangschikken van beeld/video activa en het toont hoe u opstellingsproject kunt dat van multi-zone aan single-zone en vice versa afwisselt.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Het project instellen {#setting-up-the-project}

Voer de onderstaande stappen uit om een project in te stellen:

1. Maak een AEM-schermproject met de naam **OvernameopLoop**, zoals hieronder wordt weergegeven.

   ![element](assets/mz-to-sz1.png)


1. **Een uit meerdere zones bestaand rasterkanaal maken**

   1. Selecteer de map **Kanalen** en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.
   1. Selecteer **Linkerstaafsplitsing > Schermkanaal** splitsen in de wizard en maak het kanaal genaamd **MultiZoneLayout**.
   1. Voeg inhoud toe aan het kanaal. Sleep de elementen naar elk van de zones. In het volgende voorbeeld ziet u een **MultiZoneLayout** -kanaal dat bestaat uit een video, een afbeelding en een tekstbanner (in een ingesloten reeks), zoals hieronder wordt getoond.
   ![element](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Raadpleeg Lay-out [met meerdere zones voor meer informatie over het maken van een lay-out](multi-zone-layout-aem-screens.md)met meerdere zones in uw kanaal.


1. Maak een ander kanaal met de naam **Overnamekanaal** naar de map **Kanalen** .

   ![element](assets/mz-to-sz3.png)

1. Klik op **Bewerken** op de actiebalk om inhoud toe te voegen aan dit kanaal. Voeg een **component van het Kanaal** en een beeldmiddel toe dat u, aan dit kanaal wilt schakelen, zoals aangetoond in het hieronder cijfer:

   ![element](assets/mz-to-sz4.png)

1. Open de instellingen voor de component Channel en wijs deze naar het kanaal **MultiZoneLayout** dat u in *stap 2* hebt gemaakt.

   ![element](assets/mz-to-sz5.png)

1. Stel de duur in van het veld **Reeks** op **10000 ms**.

   ![element](assets/mz-to-sz6.png)

1. Open op dezelfde manier de instellingen voor de afbeelding (het element dat u hebt toegevoegd) en stel de duur van de afbeelding in van het veld **Reeks** op **3000 ms**.

   ![element](assets/mz-to-sz7.png)

## De voorvertoning controleren {#checking-the-preview}

U kunt de gewenste uitvoer weergeven vanuit de speler of door in de editor op de **voorvertoning** te klikken.

De uitvoer zal tonen hoe een lay-out met meerdere zones *10000 ms* speelt en dan aan de lay-out van enige streek overschakelt die playbackduur van *3000 ms* heeft en dan naar de lay-out met meerdere zones terugschakelt.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>U kunt uw kanaalovergang (van multi-zone aan single-zone lay-out of vice versa), volgens uw vereisten aanpassen.