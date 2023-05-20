---
title: Hoofdlettergebruik voor overgangen van MultiZone naar SingleZone
description: Volg deze pagina voor meer informatie over het gebruik van hoofdletters en kleine letters voor multiZone-overgangen.
seo-description: MultiZone to SingleZone Transitions use case.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, User
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

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

1. Een AEM Screens-project maken met de naam **OvernamingLoop**, zoals hieronder weergegeven.

   ![element](assets/mz-to-sz1.png)


1. **Een uit meerdere zones bestaand rasterkanaal maken**

   1. Selecteer **Kanalen** map en klik op **Maken** in de actiebalk om de wizard te openen en een kanaal te maken.
   1. Selecteren **Linkerbalk, gesplitst rasterkanaal** van de wizard en maakt u het kanaal met de naam **MultiZoneLayout**.
   1. Voeg inhoud toe aan het kanaal. Sleep de elementen naar elk van de zones. In het volgende voorbeeld wordt een **MultiZoneLayout** kanaal bestaande uit een video, een afbeelding en een tekstbanner (in een ingesloten reeks), zoals hieronder weergegeven.

   ![element](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Voor meer informatie over het maken van een lay-out met meerdere zones in uw kanaal raadpleegt u [Layout meerdere zones](multi-zone-layout-aem-screens.md).


1. Een ander kanaal maken met de naam **Overnamekanaal** aan uw **Kanalen** map.

   ![element](assets/mz-to-sz3.png)

1. Klikken **Bewerken** in de actiebalk om inhoud toe te voegen aan dit kanaal. Voeg een **Kanaal** en een afbeeldingselement waarnaar u wilt schakelen, naar dit kanaal, zoals in de onderstaande afbeelding wordt getoond:

   ![element](assets/mz-to-sz4.png)

1. Open de instellingen voor de component Channel en wijs deze naar de **MultiZoneLayout** kanaal dat u in creeerde *stap 2*.

   ![element](assets/mz-to-sz5.png)

1. De duur instellen vanuit de **Reeks** veld naar **10000 ms**.

   ![element](assets/mz-to-sz6.png)

1. Open op dezelfde manier de instellingen voor de afbeelding (het element dat u hebt toegevoegd) en stel de duur in op basis van de **Reeks** veld naar **3000 ms**.

   ![element](assets/mz-to-sz7.png)

## De voorvertoning controleren {#checking-the-preview}

U kunt de gewenste uitvoer weergeven vanuit de speler of alleen door op de knop **Voorvertoning** uit de editor.

De uitvoer toont hoe een lay-out met meerdere zones wordt afgespeeld voor *10000 ms* en schakelt vervolgens over naar de lay-out met één zone waarvoor de afspeelduur *3000 ms* en schakelt dan terug naar de lay-out met meerdere zones.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>U kunt uw kanaalovergang (van multi-zone aan single-zone lay-out of vice versa), volgens uw vereisten aanpassen.
