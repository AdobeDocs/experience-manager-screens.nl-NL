---
title: Spraakherkenning in AEM Screens
description: De pagina bevat een beschrijving van de functie voor spraakherkenning in AEM Screens.
translation-type: tm+mt
source-git-commit: c46cd26f5067468aadf80a822fffce1d5f0b5d9a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---


# Spraakherkenning in AEM Screens {#voice-recognition}

## Overzicht {#overview}

De eigenschap van de Erkenning van de Stem staat inhoudsverandering in een kanaal van AEM Screens toe dat door steminteractie wordt gedreven.

Een inhoudauteur kan een vertoning vormen om toegelaten stem te zijn. Hierdoor kunnen alle spelers die tegen het scherm zijn geregistreerd, spraak begrijpen. U moet de stemerkenning voor de Vertoning toelaten en elk kanaal associëren met een unieke markering om een kanaalovergang teweeg te brengen.

>[!NOTE]
>De spelerhardware moet audio-invoer, zoals een microfoon, ondersteunen.

>[!IMPORTANT]
> De functie voor spraakherkenning is alleen beschikbaar voor Chrome- en Electron-spelers.

## Spraakherkenning implementeren {#implementing}

De volgende sectie beschrijft hoe u de eigenschap van de Erkenning van de Stem in een project van AEM Screens kunt toelaten en gebruiken.

### Het project instellen {#setting-up}

Alvorens u de eigenschap van de Erkenning van de Stem gebruikt, zorg ervoor u een project en een kanaal met inhoud hebt opstelling voor uw project.

1. Het volgende voorbeeld toont een demoproject genoemd **VoiceDemo** en drie opeenvolgingskanalen **Hoofd**, **ColdDrinks**, en **HotDrinks**, zoals aangetoond in het hieronder cijfer.

   >[!NOTE]
   >
   >Raadpleeg Kanalen [maken en beheren voor meer informatie over het maken van een kanaal of het toevoegen van inhoud aan een kanaal](/help/user-guide/managing-channels.md)

1. Navigeer naar elk kanaal en voeg inhoud toe. Navigeer bijvoorbeeld naar **VoiceDemo** —> **Kanalen** —> **Hoofd** en selecteer het kanaal. Klik op **Bewerken** op de actiebalk om de editor te openen en naar wens inhoud (afbeeldingen/video&#39;s) toe te voegen. Voeg op dezelfde manier inhoud toe aan zowel **ColdDrinks** als het **HotDrinks** -kanaal.

   De kanalen bevatten nu de volgende inhoud, zoals in de onderstaande afbeeldingen wordt getoond.

   **Hoofd**:

   **ColdDrinks**:

   **HotDrinks**:

### Labels instellen voor kanalen {#setting-tags}

Nadat u inhoud aan uw kanalen hebt toegevoegd, moet u naar elk kanaal navigeren en de juiste tags toevoegen die de spraakherkenning zouden activeren.

Voer de onderstaande stappen uit om codes aan uw kanaal toe te voegen:

1. Navigeer naar elk kanaal en voeg inhoud toe. Navigeer bijvoorbeeld naar **VoiceDemo** —> **Kanalen** —> **Hoofd** en selecteer het kanaal.

1. Klik op **Eigenschappen** op de actiebalk.

1. Navigeer naar het tabblad **Basisbeginselen** en selecteer een bestaand label in het veld **Codes** of maak een nieuw label.

1. Klik op **Opslaan en sluiten** als u klaar bent.


### Kanaal toewijzen aan een weergave {#channel-assignment}

1. Maak een weergave in de map **Locations** , zoals in de onderstaande afbeelding wordt getoond.

   >[!NOTE]
   >
   >Leer hoe te om een kanaal aan een vertoning toe te wijzen, verwijs naar het [Creëren van en het Leiden Vertoningen](/help/user-guide/managing-displays.md).

1. Wijs de kanalen **Main**, **ColdDrinks**, en **HotDrinks** aan uw **LobbyDisplay** toe.


1. Stel de volgende eigenschappen in voor elk kanaal.

   >[!NOTE]
   >
   >Leer hoe te om een kanaal aan een vertoning toe te wijzen, verwijs naar het [Creëren van en het Leiden Vertoningen](/help/user-guide/managing-displays.md).

1. Nadat u kanalen aan een weergave hebt toegewezen, navigeert u naar **LobbyDisplay** en selecteert u de weergave. Selecteer **Eigenschappen** op de actiebalk.

1. Navigeer naar het tabblad **Weergave** en schakel de optie **Voice ingeschakeld** in onder **Inhoud**.

   >[!NOTE]
   >Het is verplicht om de functie voor spraakherkenning vanuit de weergave in te schakelen.

## De inhoud weergeven in de Chrome Player {#viewing-content}

Wanneer de voorgaande stappen zijn voltooid, kunt u het chroomapparaat registreren en de uitvoer bekijken.

Voer de onderstaande stappen uit:

1. Navigeer naar de map **Apparaten** en klik op **Apparaatbeheer** op de actiebalk om de apparaten te registreren.







