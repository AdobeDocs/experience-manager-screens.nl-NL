---
title: Duur van afspeelafbeelding
seo-title: Duur van afspeelafbeelding
description: Volg deze pagina voor meer informatie over de afspeelduur van afbeeldingen.
seo-description: Volg deze pagina voor meer informatie over de afspeelduur van afbeeldingen.
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 69a40e437fa9b19e283bcf1a1322d18e17990a49

---


# Duur van afspeelafbeelding {#image-playback-duration}

## Overzicht {#overview}

Nadat u een volgnummer hebt gemaakt en er afbeeldingen aan hebt toegevoegd, nemen alle afbeeldingen standaard de afspeelduur over die is gedefinieerd in de kanaalconfiguratie. Elke afzonderlijke afbeelding kan nog steeds de standaardinstelling overschrijven en een andere afspeelduur hebben. Dit gebeurt door de afspeelduur van de specifieke afbeeldingscomponent te bewerken.

### Vereisten {#prerequisites}

Voordat u deze functionaliteit gaat implementeren, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van deze functionaliteit. Bijvoorbeeld:

1. Een AEM-schermproject maken (in dit voorbeeld **ChannelLevelPlayback**)

1. Een sequentiekanaal maken als **PlaybackChannel** onder de map **Kanalen**

1. Inhoud toevoegen aan **PlaybackChannel**

## Tijdsduur afspeelafbeelding op kanaalniveau bewerken {#editing-channel-level-image-playback-duration-assignment}

In de onderstaande sectie wordt uitgelegd hoe u de afspeelduur van inhoud in een AEM-rasterkanaal kunt bewerken.

### De afspeelduur bijwerken voor afbeeldingen in een kanaal {#updating-the-playback-duration-for-images-in-a-channel}

Voer de volgende stappen uit om te leren hoe u de toewijzing Afbeeldingsniveau op kanaalniveau tijdens het afspelen van de afbeelding kunt bijwerken:

1. Navigeer naar het **PlaybackChannel**-sequentiekanaal.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Klik op **Bewerken** op de actiebalk om de editor te openen.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Voeg twee of meer afbeeldingen toe in de kanaaleditor, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Selecteer alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding) om het dialoogvenster Kanaalniveau configureren te openen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. **Het dialoogvenster Pagina** wordt geopend.

   >[!NOTE]
   >
   >Standaard worden de afbeeldingen in een kanaal ingesteld op een afspeelduur van 8 seconden.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (ms) tot 3000 (ms), dat wil zeggen 3 seconden. Klik op het vinkje rechtsboven in het dialoogvenster **Pagina** om de wijzigingen op te slaan.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Het resultaat weergeven {#viewing-the-result}

Nadat u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld worden alle drie de afbeeldingen weergegeven), worden de afbeeldingen nu 3 seconden afgespeeld in plaats van 8 seconden (standaardwaarde).

![channel_preview](assets/channel_preview.gif)
