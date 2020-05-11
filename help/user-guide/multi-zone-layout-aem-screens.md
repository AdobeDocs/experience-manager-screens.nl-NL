---
title: Layout meerdere zones
seo-title: Layout meerdere zones
description: Met Layout meerdere zones kunt u inhoud voor meerdere zones maken en een groot aantal verschillende elementen gebruiken, zoals video's, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. Volg deze pagina voor meer informatie.
seo-description: Met Layout meerdere zones kunt u inhoud voor meerdere zones maken en een groot aantal verschillende elementen gebruiken, zoals video's, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. Volg deze pagina voor meer informatie.
uuid: 2ad689ef-700a-4eed-b5e2-fc57f2288388
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 4c073172-d93c-4b73-87ab-0b08789193a3
noindex: true
translation-type: tm+mt
source-git-commit: e33175a8c4282d89ed77fc430b1a48eb8470585f
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---


# Layout meerdere zones {#multi-zone-layout}

De volgende pagina beschrijft het gebruik van lay-out met meerdere zones en behandelt de volgende onderwerpen:

* Overzicht
* Layout meerdere zones maken
* Vereisten
* Single Assets in een of meer zones gebruiken
* Gesegrafeerde inhoud gebruiken in een of meer zones

## Overzicht {#overview}

***Met Layout*** voor meerdere zones kunt u inhoud voor meerdere zones maken en verschillende elementen gebruiken, zoals video&#39;s, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. U kunt afbeeldingen, video&#39;s en tekst aan elkaar trekken, zodat deze allemaal kunnen overvloeien en een intuïtieve digitale ervaring ontstaat.

Zoals bij de projectvereisten, soms hebt u veelvoudige streken in een kanaal nodig en geeft hen uit als één uitvoerige eenheid. Bijvoorbeeld, een productopeenvolging met een verwante sociale media voer die in drie afzonderlijke streken op één enkel kanaal loopt.

## Layout meerdere zones maken {#creating-multi-zone-layout}

Tijdens het maken van een kanaal kunt u verschillende sjablonen gebruiken om zones in uw kanaal te maken. U kunt één afbeelding, video of ingesloten kanaal toevoegen waarmee meerdere elementen in een reeks kunnen worden weergegeven.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project gereed hebt als voorwaarde voor het implementeren van een lay-out met meerdere zones. Bijvoorbeeld,

* Een AEM-schermproject maken met de naam **Zones**
* Een weergave maken onder **Locaties** met de naam **MultiZoneDisplay**

Maak een kanaal met de naam **MultiZone** in het project **Zones** . Voer de onderstaande stappen uit:

**Het kanaal maken**

1. Selecteer de koppeling Adobe Experience Manager (linksboven) en vervolgens **Schermen**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens`.
1. Navigeer naar de map **Kanalen** en klik op **Maken** op de actiebalk.

1. Selecteer **Linker L-bar Gesplitste het Kanaal** van het Scherm van de **Create** tovenaar.

1. Klik op **Volgende** en voer de **titel** in als **MultiZone**.

1. Klik op **Maken** om het maken van het kanaal te voltooien.

![screen_shot_2018-12-07at120026pm](assets/screen_shot_2018-12-07at120026pm.png)

### Single Assets in een of meer zones gebruiken {#using-single-assets-in-one-or-more-zones}

U kunt afzonderlijke elementen, zoals een afbeelding of een video, in alle drie verschillende zones gebruiken. Volg de onderstaande stappen voor implementatie:

1. **Inhoud toevoegen aan het kanaal**

   1. Navigeer naar **zones** —> **Kanalen**—>**MultiZone**.
   1. Selecteer het kanaal **MultiZone** en klik op **Bewerken** op de actiebalk om de editor te openen.
   ![screen_shot_2018-12-07at14917pm](assets/screen_shot_2018-12-07at14917pm.png)

1. **Afbeeldingen toevoegen aan het kanaal**

   Als u één afbeelding of video in alle drie zones wilt afspelen, sleept u de afbeelding en zet u deze neer in de kanaaleditor, zoals hieronder wordt weergegeven.

   ![new1-1](assets/new1-1.gif)

### Gesegrafeerde inhoud gebruiken in een of meer zones {#using-sequenced-content-in-one-or-more-zones}

Als u wilt dat de zones een reeks afbeeldingen of inhoud en een statische afbeelding in drie verschillende zones weergeven, volgt u de onderstaande stappen voor meer informatie.

1. **Een kanaalmap maken**

   1. Navigeer naar **zones** —> **MultiZone** —> **Kanalen** en klik op **Maken** op de actiebalk.
   1. Selecteer **de Omslag** van Kanalen van de **Create** tovenaar en klik **daarna**.
   1. Voer de titel in als **EmbeddedChannels** en klik op **Maken**.
   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Twee kanalen toevoegen aan de kanaalmap**

   1. Navigeer naar **zones** —> **Kanalen** —> **Ingesloten kanalen** en klik op **Maken** op de actiebalk.
   1. Selecteer **Volgkanaal** in de wizard **Maken** om een kanaal met de naam **Zone1** te maken.
   1. Selecteer **Zone1** en klik op **Bewerken** op de actiebalk om de editor te openen.
   1. Sleep enkele afbeeldingen naar dit kanaal.
   Maak op dezelfde manier een ander volgnummer met de naam **Zone2** in de map **EmbeddedChannel** .

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   De afbeeldingen die zijn toegevoegd aan de editor van het kanaal van de **Zone1** -reeks worden hieronder weergegeven:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-1.png)

   De afbeeldingen die zijn toegevoegd aan de editor van het kanaal van de **Zone2** -reeks worden hieronder weergegeven:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-2.png)

1. **Ingesloten reeksen/componenten toevoegen aan hoofdkanaal (MultiZone)**

   1. Navigeer naar **zones** —> **Kanalen** —> **MultiZone**.
   1. Klik op **Bewerken** op de actiebalk om de editor te openen.
   1. Sleep de component **Ingesloten reeks** naar twee van de zones.

1. **Inhoud toevoegen aan alle drie zones**

   1. Navigeer naar **zones** —> **Kanalen** —> **MultiZone**.
   1. Selecteer de ingesloten reeks in een van de zones.
   1. Klik het **Configure** (moersleutel) pictogram aan één van de ingebedde opeenvolgingen in de redacteur.
   1. Selecteer het kanaalpad als **zones** —> **Kanalen** —> **Ingesloten kanalen** —> **Zone1**, zoals in de onderstaande afbeelding wordt getoond.
   Op dezelfde manier voeg **Zone2** aan een andere ingebedde opeenvolgingscomponent in de redacteur toe.

   ![image](/help/user-guide/assets/multi-zone/multizone-3.png)

#### Het resultaat weergeven {#viewing-the-result}

Nadat u lay-outs met meerdere zones hebt geïmplementeerd met behulp van de voorgaande stappen, wordt de volgende uitvoer weergegeven, zoals in de onderstaande afbeelding wordt getoond.

De volgende uitvoer in de Speler van het Scherm toont de inhoud in drie verschillende streken. In de linker- en rechterzone (beide gebruiken ingesloten reeks als een component) wordt een reeks afbeeldingen weergegeven en in de zone eronder wordt een statische afbeelding weergegeven.

![new2-1](/help/user-guide/assets/multi-zone/screens-multi1.gif)


