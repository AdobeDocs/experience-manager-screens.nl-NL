---
title: Een live kopie maken en beheren
seo-title: LiveCopy beheren
description: Op deze pagina vindt u een beschrijving van het maken en beheren van Actieve exemplaren van kanalen.
seo-description: Volg deze pagina om een live kopie van een kanaal te maken, eigenschappen weer te geven, de status te controleren en wijzigingen van een kanaal door te geven aan de live kopie.
uuid: 78ec7219-95ab-44d1-9514-1b97aded5bf4
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 84085a03-1798-4f1d-858c-6014a3f6aff6
feature: Ontwerpschermen
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---


# Een actieve kopie maken en beheren {#creating-and-managing-a-live-copy}

Op deze pagina vindt u een beschrijving van het maken en beheren van Actieve exemplaren van kanalen.

Een ***actieve kopie*** is een kopie van specifieke site-inhoud waarvoor een live relatie met de oorspronkelijke bron behouden blijft. Met deze live relatie kan de live kopie inhoud en pagina-eigenschappen overnemen van de bron.

Deze pagina beschrijft het maken van een live kopie van een kanaal, het weergeven van eigenschappen, het controleren van de status en het doorgeven van wijzigingen van een kanaal naar de live kopie.


## Een actieve kopie maken {#creating-a-live-copy}

Voer de onderstaande stappen uit om een live kopie van een kanaal in uw projectmap te maken.

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en **Screens**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens`.

1. Navigeer naar het schermproject en klik op **Kanalen**.
1. Klik **Maken** en selecteer **Live kopie** om een live kopie van het kanaal te maken.

1. Selecteer de bestemming en klik **Volgende**.
1. Selecteer de locatie waar de live kopie zich bevindt.
1. Typ de **Titel** en **Naam** op de pagina **Live kopie maken**.

1. Klik **Open** om de inhoud van nieuwe levende exemplaar te bekijken of **Done** om aan de belangrijkste pagina terug te keren.

U kunt ook de onderstaande stappen volgen voor een visuele weergave voor het maken van een nieuwe live kopie van een kanaal.

In het volgende voorbeeld ziet u hoe u een live kopie (***IdleLiveCopy***) maakt voor ***Niet-actief kanaal*** met doelmap als ***Kanalen***.

![chlimage_1-2](assets/chlimage_1-2.gif)

## Inhoud van het kanaal Live kopie weergeven {#viewing-content-of-the-live-copy-channel}

Een actieve kopie is een kopie van een kanaal dat al bestaat.

Zie de volgende stappen om de inhoud van uw live kopie weer te geven:

1. Navigeer naar het project Schermen en klik op de locatie waar u oorspronkelijk een live kopie hebt gemaakt, zoals in de bovenstaande sectie wordt getoond. (Hier, werd de plaats gekozen als **Kanalen** omslag)

   ![chlimage_1-18](assets/chlimage_1-18.png)

1. Klik op **Bewerken** op de actiebalk om de inhoud in het kanaal weer te geven.

   ![chlimage_1-19](assets/chlimage_1-19.png)

   >[!NOTE]
   >
   >Wanneer u inhoud voor een actief kopieerkanaal weergeeft, wordt een extra item in het menu weergegeven als **Live Copy-status**. Zie de onderstaande sectie voor meer informatie.

### Eigenschappen van een actieve kopie bekijken {#viewing-properties-of-a-live-copy}

Bovendien kunt u de eigenschappen van het kanaal van uw levende exemplaar bekijken.

1. Navigeer naar het kanaal voor live kopiëren en klik op **Eigenschappen** op de actiebalk.

   ![chlimage_1-20](assets/chlimage_1-20.png)

1. Selecteer het tabblad **Live kopie** om de details van uw kanaal weer te geven.

   ![chlimage_1-21](assets/chlimage_1-21.png)

### Live Copy-status {#live-copy-status}

In de modus **Live Copy-status**, zoals in de onderstaande afbeelding wordt getoond, kunt u de relatiestatus van alle elementen in het kanaal weergeven.

1. Klik op **Bewerken** om de **Live Copy-status** te kiezen en de koppeling van de kanaalinhoud aan het oorspronkelijke kanaal weer te geven (waaruit de live kopie wordt gegenereerd).

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Selecteer **Live Copy-status** om de voorvertoningspagina weer te geven.

   Alle bronnen met een groene rand tonen aan dat de inhoud wordt overgenomen van het oorspronkelijke kanaal.

   ![chlimage_1-23](assets/chlimage_1-23.png)

### Overerving {#breaking-the-inheritance} verbreken

U kunt ook de overerving van de livecopy annuleren, zodat de inhoud onafhankelijk wordt van de oorspronkelijke vertakking.

In het volgende voorbeeld ziet u dat u de afbeelding in de bewerkingsmodus selecteert en rechtsboven op het overervingssymbool Annuleren klikt.

![chlimage_1-24](assets/chlimage_1-24.png)

### Wijzigingen doorgeven aan het kanaal Live kopie {#propagating-changes-to-the-live-copy-channel}

Als u wijzigingen/updates aanbrengt in het oorspronkelijke kanaal, moet u deze wijzigingen ook doorgeven aan uw Live Copy-kanaal.

Voer de onderstaande stappen uit om ervoor te zorgen dat uw wijzigingen van het oorspronkelijke kanaal naar het actieve kopieerkanaal worden doorgegeven:

1. Selecteer het oorspronkelijke kanaal (***Niet-actief kanaal***) en klik **Bewerken** op de actiebalk.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Bewerk de inhoud van dit kanaal. Verwijder bijvoorbeeld een afbeelding uit dit kanaal.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Selecteer de live kopie van het kanaal (***IdleLiveCopy***) en klik op **Edit** op de actiebalk. U zult zien dat de afbeelding die u hebt verwijderd, nog steeds zichtbaar is in de live kopie.

   Als u de wijzigingen wilt doorgeven, moet u het kanaal synchroniseren.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. Als u wijzigingen in het actieve kopieerkanaal wilt doorgeven, navigeert u naar het AEM dashboard en selecteert u het actieve kopieerkanaal. Klik vervolgens op **Eigenschappen** op de actiebalk.

   ![chlimage_1-28](assets/chlimage_1-28.png)

1. Selecteer het tabblad **Live kopie** en klik op **Synchroniseren** op de actiebalk.

   ![chlimage_1-21](assets/chlimage_1-29.png)

1. Klik **Sync** om de wijzigingen te bevestigen. Klik **Opslaan en sluiten** om terug te navigeren naar het AEM dashboard.

   ![chlimage_1-30](assets/chlimage_1-30.png)

   U zult merken dat de afbeelding nu ook uit het live-kopieerkanaal wordt verwijderd.

