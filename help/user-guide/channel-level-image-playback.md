---
title: Duur van afspelen van bulkafbeelding op kanaalniveau
seo-title: Duur van afspelen van bulkafbeelding op kanaalniveau
description: Op deze pagina wordt beschreven hoe u de afspeelduur van een bepaalde afbeeldingscomponent kunt bewerken.
seo-description: Op deze pagina wordt beschreven hoe u de afspeelduur van een bepaalde afbeeldingscomponent kunt bewerken.
uuid: 4ebb00a9-b04d-4dfe-9fee-2348a2e2c142
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: df3cf999-0c8d-4754-8b58-5c6ced2c8ca5
docset: aem65
feature: Ontwerpschermen
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---


# Duur van afspelen van bulkafbeelding op kanaalniveau {#channel-level-bulk-image-playback-duration}

## Overzicht {#overview}

Nadat u een volgnummer hebt gemaakt en er afbeeldingen aan hebt toegevoegd, nemen alle afbeeldingen standaard de afspeelduur over die is gedefinieerd in de kanaalconfiguratie. Elke afzonderlijke afbeelding kan nog steeds de standaardinstelling overschrijven en een andere afspeelduur hebben. Dit gebeurt door de afspeelduur van de specifieke afbeeldingscomponent te bewerken.

### Vereisten {#prerequisites}

Voordat u deze functionaliteit gaat implementeren, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van deze functionaliteit. Bijvoorbeeld,

1. Maak een AEM Screens-projectvoorbeeld **ChannelLevelPlayback**.

1. Creeer een opeenvolgingskanaal als **PlaybackChannel** onder **Kanalen** omslag.

1. Voeg inhoud toe aan **PlaybackChannel**.

## Tijdsduur afspeelafbeelding op kanaalniveau bewerken {#editing-channel-level-image-playback-duration-assignment}

In de onderstaande sectie wordt uitgelegd hoe u de afspeelduur van inhoud in een AEM Screens-kanaal kunt bewerken.

### De afspeelduur bijwerken voor afbeeldingen in een kanaal {#updating-the-playback-duration-for-images-in-a-channel}

Voer de volgende stappen uit om te leren hoe u de toewijzing Afbeeldingsniveau op kanaalniveau tijdens het afspelen van de afbeelding kunt bijwerken:

1. Navigeer naar het volgordekanaal **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Klik **Bewerken** van de actiebar om de redacteur te openen.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Voeg twee of meer afbeeldingen toe in de kanaaleditor, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Selecteer alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding) om het dialoogvenster Kanaalniveau configureren te openen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. **Het** dialoogvenster Pagina wordt geopend.

   >[!NOTE]
   >Standaard worden de afbeeldingen in een kanaal ingesteld op een afspeelduur van 8 seconden.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (ms) tot 3000 (ms), dat wil zeggen 3 seconden. Klik op het vinkje rechtsboven in het dialoogvenster **Pagina** om de wijzigingen op te slaan.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Resultaat {#viewing-the-result} weergeven

Nadat u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld worden alle drie de afbeeldingen weergegeven), worden de afbeeldingen nu 3 seconden afgespeeld in plaats van 8 seconden (standaardwaarde).

![channel_preview](assets/channel_preview.gif)

