---
title: Een live kopie maken en beheren
description: Leer hoe u Live kopieën van kanalen maakt en beheert in AEM Screens.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 4a4b3a83-2b02-42a0-86a7-fce6bbf47c7d
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 0%

---

# Een live kopie maken en beheren {#creating-and-managing-a-live-copy}

Op deze pagina vindt u een beschrijving van het maken en beheren van Actieve exemplaren van kanalen.

A ***Live kopie*** is een kopie van specifieke site-inhoud waarvoor een live relatie met de oorspronkelijke bron behouden blijft. Met deze live relatie kan de live kopie inhoud en pagina-eigenschappen overnemen van de bron.

Deze pagina beschrijft het maken van een live kopie van een kanaal, het weergeven van eigenschappen, het controleren van de status en het doorgeven van wijzigingen van een kanaal naar de live kopie.


## Een actieve kopie maken {#creating-a-live-copy}

Voer de onderstaande stappen uit om een live kopie van een kanaal in uw projectmap te maken.

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en **Schermen**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens`.

1. Navigeer naar het project Screens en klik op **Kanalen**.
1. Klikken **Maken** en selecteert u **Live kopie** zodat u een live kopie van het kanaal kunt maken.
1. Selecteer het doel en klik op **Volgende**.
1. Selecteer de locatie waar de live kopie kan worden opgeslagen.
1. Voer de **Titel** en **Naam** in de **Live kopie maken** pagina.

1. Klikken **Openen** om de inhoud van een nieuwe live kopie te bekijken of **Gereed** om terug te keren naar de hoofdpagina.

U kunt ook de onderstaande stappen volgen voor een visuele weergave voor het maken van een nieuwe live kopie van een kanaal.

In het volgende voorbeeld wordt getoond hoe u een live kopie (***IdleLiveCopy***) voor ***Niet-actief kanaal*** met doelmap als ***Kanalen***.

![chlimage_1-2](assets/chlimage_1-2.gif)

## Inhoud van het kanaal Live kopie weergeven {#viewing-content-of-the-live-copy-channel}

Een actieve kopie is een kopie van een bestaand kanaal.

Zie de volgende stappen om de inhoud van uw live kopie weer te geven:

1. Navigeer naar het project Schermen en klik op de locatie waar u oorspronkelijk een live kopie hebt gemaakt, zoals in de bovenstaande sectie wordt getoond. (Hier is de locatie gekozen als **Kanalen** map)

   ![chlimage_1-18](assets/chlimage_1-18.png)

1. Klikken **Bewerken** in de actiebalk.

   ![chlimage_1-19](assets/chlimage_1-19.png)

   >[!NOTE]
   >
   >Wanneer u inhoud voor een actief kopieerkanaal weergeeft, ziet u een extra item in het menu als **Status van live kopiëren**. Zie de onderstaande sectie voor meer informatie.

### Eigenschappen van een actieve kopie weergeven {#viewing-properties-of-a-live-copy}

U kunt ook de eigenschappen van uw live-kopieerkanaal weergeven.

1. Ga naar uw livefkopie en klik op **Eigenschappen** in de actiebalk.

   ![chlimage_1-20](assets/chlimage_1-20.png)

1. Selecteer de **Live kopie** zodat u details van uw kanaal kunt bekijken.

   ![chlimage_1-21](assets/chlimage_1-21.png)

### Status van live kopiëren {#live-copy-status}

De modus **Status van live kopiëren** Zoals u in de onderstaande afbeelding ziet, kunt u de relatiestatus van alle elementen in het kanaal bekijken.

1. Klikken **Bewerken** zodat u de **Status van live kopiëren** en bekijk de koppeling van uw kanaalinhoud aan het oorspronkelijke kanaal (waaruit de live kopie wordt gegenereerd).

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Selecteren **Status van live kopiëren** zodat u de voorvertoningspagina kunt weergeven.

   Alle bronnen met een groene rand tonen aan dat de inhoud wordt overgenomen van het oorspronkelijke kanaal.

   ![chlimage_1-23](assets/chlimage_1-23.png)

### De overerving doorbreken {#breaking-the-inheritance}

U kunt de overerving van de live kopie ook annuleren, zodat de inhoud onafhankelijk wordt van de oorspronkelijke vertakking.

In het volgende voorbeeld ziet u dat u de afbeelding in de bewerkingsmodus selecteert en op het overervingssymbool annuleren rechtsboven klikt.

![chlimage_1-24](assets/chlimage_1-24.png)

### Wijzigingen doorgeven aan het kanaal van Live kopie {#propagating-changes-to-the-live-copy-channel}

Als u wijzigingen aanbrengt of wijzigingen aanbrengt in het oorspronkelijke kanaal, moet u deze wijzigingen ook doorgeven aan uw Live Copy-kanaal.

Voer de onderstaande stappen uit om ervoor te zorgen dat uw wijzigingen van het oorspronkelijke kanaal naar het actieve kopieerkanaal worden doorgegeven:

1. Het oorspronkelijke kanaal selecteren (***Niet-actief kanaal***) en selecteert u **Bewerken** in de actiebalk.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Bewerk de inhoud van dit kanaal. Verwijder bijvoorbeeld een afbeelding uit dit kanaal.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Selecteer de live kopie van het kanaal (***IdleLiveCopy***) en selecteert u **Bewerken** in de actiebalk. De afbeelding die u hebt verwijderd, wordt nog steeds weergegeven in de live kopie.

   Als u de wijzigingen wilt doorgeven, synchroniseert u het kanaal.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. Als u wijzigingen in het actieve kopieerkanaal wilt doorgeven, navigeert u naar het AEM dashboard en selecteert u het actieve kopieerkanaal en klikt u op **Eigenschappen** in de actiebalk.

   ![chlimage_1-28](assets/chlimage_1-28.png)

1. Selecteer de **Live kopie** en selecteert u **Synchroniseren** in de actiebalk.

   ![chlimage_1-29](assets/chlimage_1-29.png)

1. Selecteren **Sync** selecteert u vervolgens **Opslaan en sluiten** om terug naar het AEM dashboard te navigeren.

   ![chlimage_1-30](assets/chlimage_1-30.png)

   De afbeelding wordt nu ook verwijderd uit het live-kopieerkanaal.
