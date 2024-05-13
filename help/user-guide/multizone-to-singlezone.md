---
title: MultiZone naar SingleZone-overgangen gebruiken hoofdletters/kleine letters
description: Volg deze pagina zodat u meer kunt leren over de Gebruiksscenario's van MultiZone naar SingleZone-overgangen.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, User
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# Meerdere zones naar één zone overgang {#multizone-to-singlezone-use-case}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruiksvoorbeeld beschreven waarin wordt benadrukt hoe u een lay-outkanaal met meerdere zones instelt dat met een lay-outkanaal met één zone afwisselt. Het kanaal met meerdere zones heeft het rangschikken van beeld/video activa en het toont hoe u opstelling een project dat van multi-zone aan single-zone afwisselt en omgekeerd.

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

   1. Klik op de knop **Kanalen** map en klik op **Maken** van de actiebar en het openen van de tovenaar zodat kunt u een kanaal creëren.
   1. Klikken **Linkerbalk, gesplitst rasterkanaal** van de wizard en maakt u het kanaal met de naam **MultiZoneLayout**.
   1. Voeg inhoud toe aan het kanaal. Sleep de elementen naar elk van de zones. In het volgende voorbeeld wordt een **MultiZoneLayout** kanaal bestaande uit een video, een afbeelding en een tekstbanner (in een ingesloten reeks), zoals hieronder wordt weergegeven.

   ![element](assets/mz-to-sz2.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het maken van een lay-out met meerdere zones in uw kanaal naar [Layout meerdere zones](multi-zone-layout-aem-screens.md).


1. Een ander kanaal maken met de naam **Overnamekanaal** aan uw **Kanalen** map.

   ![element](assets/mz-to-sz3.png)

1. Klikken **Bewerken** op de actiebalk, zodat u inhoud aan dit kanaal kunt toevoegen. Voeg een **Kanaal** en een afbeeldingsmiddel waarop u voor dit kanaal wilt schakelen, zoals in de onderstaande afbeelding wordt getoond:

   ![element](assets/mz-to-sz4.png)

1. Open de instellingen voor de component Channel en wijs deze naar de **MultiZoneLayout** kanaal dat u in creeerde *stap 2*.

   ![element](assets/mz-to-sz5.png)

1. De duur instellen vanuit de **Reeks** veld naar **10000 milliseconden**.

   ![element](assets/mz-to-sz6.png)

1. Open op dezelfde manier de instellingen voor de afbeelding (het element dat u hebt toegevoegd) en stel de duur in op basis van de **Reeks** veld naar **3000 milliseconden**.

   ![element](assets/mz-to-sz7.png)

## De voorvertoning controleren {#checking-the-preview}

U kunt de gewenste uitvoer weergeven vanuit de speler of alleen door **Voorvertoning** uit de editor.

De uitvoer toont aan hoe een lay-out met meerdere zones wordt afgespeeld voor *10000 milliseconden*. Vervolgens wordt overgeschakeld naar een lay-out met één zone met een afspeelduur van *3000 milliseconden*. Tot slot gaat het terug naar de multi-zone layout.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>U kunt de kanaalovergang naar wens aanpassen (van multi-zone naar single-zone lay-out of omgekeerd).
