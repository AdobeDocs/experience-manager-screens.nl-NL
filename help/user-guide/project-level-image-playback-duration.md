---
title: Tijdsduur afspeelafbeelding op projectniveau
description: Leer hoe u de duur van het afspelen van afbeeldingen definieert op projectniveau.
contentOwner: jsyal
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---


# Tijdsduur afspeelafbeelding op projectniveau {#project-level-image-playback}

## Overzicht {#overview}

Met deze functie kunt u de afspeelduur van afbeeldingen op projectniveau definiëren. In alle afbeeldingen wordt deze afspeelduur standaard overgenomen. Als geen duur op het projectniveau wordt bepaald, blijft het standaardplayback van 8 seconden verdergaan.

### Vereisten {#prerequisites}

Voordat u deze functie kunt gebruiken, moet u een project instellen als een voorwaarde voor het implementeren van deze functie. Bijvoorbeeld:

1. Creeer een project van AEM Screens (in dit voorbeeld, **ProjectLevelPlayback**).
1. Creeer een opeenvolgingskanaal als **PlayBackChannel** onder de **omslag van Kanalen**.
1. Voeg inhoud aan **PlayBackChannel** toe.

   ![ activa ](assets/image_playback1.png)

   Bijvoorbeeld, toont het volgende beeld de beelden die aan de **** redacteur worden toegevoegd PlayBackChannel:

   ![ activa ](assets/image_playback2.png)

## Tijdsduur afbeelding afspelen op projectniveau bewerken {#editing-project-level-image-playback-duration-assignment}

In de onderstaande sectie wordt uitgelegd hoe u de afspeelduur van inhoud in een AEM Screens-project kunt bewerken.

### De afspeelduur voor afbeeldingen bijwerken op projectniveau {#updating-the-playback-duration-for-images-in-a-project}


>[!NOTE]
>
>Als u een beeld of de duur van de kanaalplayback wilt bijwerken, zie {de Duur van de Afbeelding van het Niveau van het 0} Kanaal ](channel-level-image-playback.md).[

Volg de onderstaande stappen om te leren hoe u de duur van het afspelen van afbeeldingen op projectniveau kunt bijwerken:

1. Navigeer aan uw project **ProjectLevelPlayback** en klik **Eigenschappen** van de actiebar.
   ![ activa ](assets/image_playback3.png)

1. Klik op alle afbeeldingen in het kanaal en klik op het moersleutelpictogram linksboven (zoals in de onderstaande afbeelding), zodat u het dialoogvenster Kanaalniveau configureren kunt openen.

   ![ screen_shot_2019-06-25at95945am ](assets/screen_shot_2019-06-25at95945am.png)

1. Het **de dialoogvakje van de Pagina** opent.

   >[!NOTE]
   >
   >De afbeeldingen in een kanaal worden standaard ingesteld op een afspeelduur van 8 seconden en de video&#39;s worden op de standaardduur afgespeeld.

   ![ screen_shot_2019-06-25at100343am ](assets/screen_shot_2019-06-25at100343am.png)

   Bewerk de **Duur** van 8000 (milliseconden) aan 3000 (milliseconden), namelijk 3 seconden. Selecteer het vinkje op het hoogste recht van de **de dialoogdoos van de Pagina** zodat worden uw veranderingen bewaard.

   ![ screen_shot_2019-06-25at101527am ](assets/screen_shot_2019-06-25at101527am.png)

### Het resultaat weergeven {#viewing-the-result}

Nadat u de afspeelduur van het kanaal hebt bijgewerkt (in dit voorbeeld worden alle drie de afbeeldingen weergegeven), worden de afbeeldingen nu 3 seconden afgespeeld in plaats van 8 seconden (de standaardwaarde).

![ channel_preview ](assets/channel_preview.gif)

