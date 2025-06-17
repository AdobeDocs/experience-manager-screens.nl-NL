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
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Een live kopie maken en beheren {#creating-and-managing-a-live-copy}

Op deze pagina vindt u een beschrijving van het maken en beheren van Actieve exemplaren van kanalen.

A ***Levende Exemplaar*** is een exemplaar van specifieke plaatsinhoud waarvoor een levende verhouding met de originele bron wordt gehandhaafd. Met deze live relatie kan de live kopie inhoud en pagina-eigenschappen overnemen van de bron.

Deze pagina beschrijft het maken van een live kopie van een kanaal, het weergeven van eigenschappen, het controleren van de status en het doorgeven van wijzigingen van een kanaal naar de live kopie.


## Een actieve kopie maken {#creating-a-live-copy}

Voer de onderstaande stappen uit om een live kopie van een kanaal in uw projectmap te maken.

1. Klik de verbinding van Adobe Experience Manager (bovenkant links) en dan **Screens**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens` gaan.

1. Navigeer aan het project van Screens en klik **Kanalen**.
1. Klik **creëren** en klik **Levend Exemplaar** zodat kunt u een levende kopie van het kanaal tot stand brengen.
1. Klik de bestemming en klik **daarna**.
1. Klik op de locatie waar de live kopie kan worden opgeslagen.
1. Ga de **Titel** in en **Naam** in **creeer Levende pagina van het Exemplaar**.

1. Klik **Open** om de inhoud van het nieuwe levende exemplaar te bekijken of **Gedaan** om op de belangrijkste pagina terug te keren.

U kunt ook de onderstaande stappen volgen voor een visuele weergave voor het maken van een nieuwe live kopie van een kanaal.

Het volgende voorbeeld toont de verwezenlijking van een levend exemplaar (***IdleLiveCopy***) voor ***Niet-actief Kanaal*** met de bestemmingsomslag als ***Kanalen***.

![ chlimage_1-2 ](assets/chlimage_1-2.gif)

## Inhoud van het kanaal Live kopie weergeven {#viewing-content-of-the-live-copy-channel}

Een live kopie is een kopie van een bestaand kanaal.

Zie de volgende stappen om de inhoud van uw live kopie weer te geven:

1. Navigeer naar het Screens-project en klik op de locatie waar u oorspronkelijk een live kopie hebt gemaakt, zoals in de bovenstaande sectie wordt getoond. (Hier, werd de plaats gekozen als **Kanalen** omslag)

   ![ chlimage_1-18 ](assets/chlimage_1-18.png)

1. Klik **uitgeven** van de actiebar.

   ![ chlimage_1-19 ](assets/chlimage_1-19.png)

   >[!NOTE]
   >
   >Wanneer het bekijken van inhoud voor een levend exemplaarkanaal, bekijkt u een extra punt in het menu als **Levende Status van het Exemplaar**. Zie de onderstaande sectie voor meer informatie.

### Eigenschappen van een actieve kopie weergeven {#viewing-properties-of-a-live-copy}

U kunt ook de eigenschappen van uw live-kopieerkanaal weergeven.

1. Navigeer aan uw levend exemplaarkanaal en klik **Eigenschappen** van de actiebar.

   ![ chlimage_1-20 ](assets/chlimage_1-20.png)

1. Klik het **Levende lusje van het Exemplaar** zodat kunt u details van uw kanaal bekijken.

   ![ chlimage_1-21 ](assets/chlimage_1-21.png)

### Status van live kopiëren {#live-copy-status}

De wijze **Levende Status van het Exemplaar**, zoals aangetoond in het hieronder cijfer, laat u de relatiestatus van alle activa in het kanaal bekijken.

1. Klik **uitgeven** zodat kunt u de **Levende Status van het Exemplaar** kiezen. U kunt ook de koppeling van de kanaalinhoud aan het oorspronkelijke kanaal bekijken waaruit de live kopie wordt gegenereerd.

   ![ chlimage_1-22 ](assets/chlimage_1-22.png)

1. Klik **Levende Status van het Exemplaar** zodat kunt u de voorproefpagina tonen.

   Alle bronnen met een groene rand tonen aan dat de inhoud wordt overgenomen van het oorspronkelijke kanaal.

   ![ chlimage_1-23 ](assets/chlimage_1-23.png)

### De overerving doorbreken {#breaking-the-inheritance}

U kunt de overerving van de live kopie ook annuleren, zodat de inhoud onafhankelijk wordt van de oorspronkelijke vertakking.

Het volgende voorbeeld toont aan dat u het beeld op uitgeeft wijze klikt en **annuleert Overerving** pictogram op het hoogste recht klikt.

![ chlimage_1-24 ](assets/chlimage_1-24.png)

### Wijzigingen doorgeven aan het kanaal van Live kopie {#propagating-changes-to-the-live-copy-channel}

Als u wijzigingen aanbrengt of wijzigingen aanbrengt in het oorspronkelijke kanaal, moet u die wijzigingen ook doorgeven aan uw live kopieerkanaal.

Voer de onderstaande stappen uit om ervoor te zorgen dat uw wijzigingen van het oorspronkelijke kanaal naar het actieve kopieerkanaal worden doorgegeven:

1. Klik het originele kanaal (***Niet-actief Kanaal***) en klik **uitgeven** van de actiebar.

   ![ chlimage_1-25 ](assets/chlimage_1-25.png)

1. Bewerk de inhoud van dit kanaal. Verwijder bijvoorbeeld een afbeelding uit dit kanaal.

   ![ chlimage_1-26 ](assets/chlimage_1-26.png)

1. Klik het levende exemplaar van het kanaal (***IdleLiveCopy***) en klik **uitgeven** van de actiebar. De afbeelding die u hebt verwijderd, wordt nog steeds weergegeven in de live kopie.

   Als u de wijzigingen wilt doorgeven, synchroniseert u het kanaal.

   ![ chlimage_1-27 ](assets/chlimage_1-27.png)

1. Om veranderingen in het levende exemplaarkanaal te verspreiden, navigeer aan het dashboard van AEM en klik het levende exemplaarkanaal en klik **Eigenschappen** van de actiebar.

   ![ chlimage_1-28 ](assets/chlimage_1-28.png)

1. Klik het **Levende lusje van het Exemplaar** en klik **synchroniseren** van de actiebar.

   ![ chlimage_1-29 ](assets/chlimage_1-29.png)

1. Klik **Synchronisatie**, dan klik **sparen &amp; sluit** om terug naar het dashboard van AEM te navigeren.

   ![ chlimage_1-30 ](assets/chlimage_1-30.png)

   De afbeelding wordt nu ook verwijderd uit het live-kopieerkanaal.
