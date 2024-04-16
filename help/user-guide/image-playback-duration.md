---
title: Duur van afspeelafbeelding
description: Meer informatie over de afspeelduur van afbeeldingen in AEM Screens.
contentOwner: jsyal
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# Duur van afspeelafbeelding {#image-playback-duration}

## Overzicht {#overview}

Nadat u een opeenvolgingskanaal creeert en beelden aan het toevoegt, door gebrek, veronderstellen alle beelden de playbackduur die in de het niveauconfiguratie van het Kanaal wordt bepaald. Elke afzonderlijke afbeelding kan nog steeds de standaardinstelling overschrijven en een andere afspeelduur hebben. Dit gebeurt door de afspeelduur van de specifieke afbeeldingscomponent te bewerken.

### Vereisten {#prerequisites}

Voordat u deze functionaliteit implementeert, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van deze functionaliteit. Bijvoorbeeld:

1. Een AEM Screens-project maken (in dit voorbeeld: **ChannelLevelPlayback**)
1. Een volgnummer maken als **PlaybackChannel** krachtens **Kanalen** map
1. Inhoud toevoegen aan **PlaybackChannel**

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

1. Klik op alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding). Het dialoogvenster Kanaalniveau configureren wordt geopend.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. **Pagina** wordt geopend.

   >[!NOTE]
   >
   >Standaard worden de afbeeldingen in een kanaal ingesteld op een afspeelduur van 8 seconden.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (milliseconden) tot 3000 (milliseconden), dat wil zeggen, 3 seconden. Klik op het vinkje rechtsboven in het dialoogvenster **Pagina** zodat u uw wijzigingen kunt opslaan.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Het resultaat weergeven {#viewing-the-result}

Wanneer u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld zijn alle drie afbeeldingen), ziet u dat de afbeeldingen nu 3 seconden worden afgespeeld in plaats van 8 seconden (standaardwaarde).

![channel_preview](assets/channel_preview.gif)

