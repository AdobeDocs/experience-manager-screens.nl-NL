---
title: Duur van afspelen van bulkafbeelding op kanaalniveau
description: Leer hoe u de afspeelduur van een bepaalde afbeeldingscomponent in AEM Screens kunt bewerken.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 95aa761a-1449-4e18-8115-3b151036dc54
source-git-commit: 8a914d4b0237c327b7954c936c84a2c1aa719603
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Duur van afspelen van bulkafbeelding op kanaalniveau {#channel-level-bulk-image-playback-duration}

## Overzicht {#overview}

Wanneer u een opeenvolgingskanaal creeert en beelden aan het toevoegt, door gebrek, veronderstellen alle beelden de playbackduur die in de het niveauconfiguratie van het Kanaal wordt bepaald. Elke afzonderlijke afbeelding kan nog steeds de standaardinstelling overschrijven en een andere afspeelduur hebben. Deze mogelijkheid wordt bereikt door de afspeelduur van de specifieke afbeeldingscomponent te bewerken.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van deze functionaliteit. Bijvoorbeeld:

1. Een AEM Screens-projectvoorbeeld maken **ChannelLevelPlayback**.

1. Een volgnummer maken als **PlaybackChannel** onder de **Kanalen** map.

1. Inhoud toevoegen aan **PlaybackChannel**.

## Tijdsduur afspeelafbeelding op kanaalniveau bewerken {#editing-channel-level-image-playback-duration-assignment}

In de onderstaande sectie wordt uitgelegd hoe u de afspeelduur van inhoud in een AEM Screens-kanaal kunt bewerken.

### De afspeelduur bijwerken voor afbeeldingen in een kanaal {#updating-the-playback-duration-for-images-in-a-channel}

Voer de volgende stappen uit om te leren hoe u de toewijzing Afbeeldingsniveau op kanaalniveau tijdens het afspelen van de afbeelding kunt bijwerken:

1. Navigeren naar het volgnummer **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Klikken **Bewerken** in de actiebalk.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Voeg twee of meer afbeeldingen toe in de kanaaleditor, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Klik op alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding), zodat u het dialoogvenster Kanaalniveau configureren kunt openen.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. De **Pagina** wordt geopend.

   >[!NOTE]
   >Standaard worden de afbeeldingen in een kanaal ingesteld op een afspeelduur van 8 seconden.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (milliseconden) tot 3000 (milliseconden), dat wil zeggen, 3 seconden. Klik op het vinkje rechtsboven in het dialoogvenster **Pagina** zodat u uw wijzigingen kunt opslaan.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Het resultaat weergeven {#viewing-the-result}

Nadat u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld worden alle drie de afbeeldingen weergegeven), worden de afbeeldingen nu 3 seconden afgespeeld in plaats van 8 seconden (de standaardwaarde).

![channel_preview](assets/channel_preview.gif)
