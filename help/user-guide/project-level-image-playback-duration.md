---
title: Tijdsduur afspeelafbeelding op projectniveau
seo-title: Tijdsduur afspeelafbeelding op projectniveau
description: 'Met deze functionaliteit kunt u de afspeelduur van afbeeldingen op projectniveau definiëren. '
seo-description: 'Met deze functionaliteit kunt u de afspeelduur van afbeeldingen op projectniveau definiëren. '
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: ae1f7cab650f811ae03f0a2f3dfa49ec855997ee

---


# Tijdsduur afspeelafbeelding op projectniveau {#project-level-image-playback}

## Overzicht {#overview}

Met deze functies kunt u de afspeelduur van afbeeldingen op projectniveau definiëren. In alle afbeeldingen wordt deze afspeelduur standaard overgenomen. Als geen duur op het projectniveau wordt bepaald, zal het standaardplayback van 8 seconden verdergaan.

### Vereisten {#prerequisites}

Voordat u deze functie gebruikt, moet u eerst een project instellen als voorwaarde voor het implementeren van deze functie. Bijvoorbeeld:

1. Een AEM-schermproject maken (in dit voorbeeld **ProjectLevelPlayback**)

1. Een volgnummer maken als **PlayBackChannel** onder de map **Kanalen**

1. Inhoud toevoegen aan **PlayBackChannel**

   ![elementen](assets/image_playback1.png)

   In de volgende afbeelding ziet u bijvoorbeeld de afbeeldingen die zijn toegevoegd aan de **PlayBackChannel** -editor:

   ![elementen](assets/image_playback2.png)

## Tijdsduur afbeelding afspelen op projectniveau bewerken {#editing-project-level-image-playback-duration-assignment}

In de onderstaande sectie wordt uitgelegd hoe u de afspeelduur van inhoud in een AEM-rasterproject kunt bewerken.

### De afspeelduur voor afbeeldingen bijwerken op projectniveau {#updating-the-playback-duration-for-images-in-a-project}


>[!NOTE]
>Als u de afspeelduur op afbeeldings- of kanaalniveau wilt bijwerken, raadpleegt u de afspeelduur [op](channel-level-image-playback.md)kanaalniveau.

Volg de onderstaande stappen om te leren hoe u de duur van het afspelen van afbeeldingen op projectniveau kunt bijwerken:

1. Navigeer naar uw project **ProjectLevelPlayback** en klik **Eigenschappen** van de actiebar.
   ![elementen](assets/image_playback3.png)

1. Selecteer alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding) om het dialoogvenster Kanaalniveau configureren te openen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. **Het dialoogvenster Pagina** wordt geopend.

   >[!NOTE]
   >
   >De afbeeldingen in een kanaal worden standaard ingesteld op een afspeelduur van 8 seconden en de video&#39;s worden op de standaardduur afgespeeld.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (ms) tot 3000 (ms), dat wil zeggen 3 seconden. Klik op het vinkje rechtsboven in het dialoogvenster **Pagina** om de wijzigingen op te slaan.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Het resultaat weergeven {#viewing-the-result}

Nadat u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld worden alle drie de afbeeldingen weergegeven), worden de afbeeldingen nu 3 seconden afgespeeld in plaats van 8 seconden (standaardwaarde).

![channel_preview](assets/channel_preview.gif)

