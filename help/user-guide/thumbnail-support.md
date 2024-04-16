---
title: Ondersteuning voor miniaturen voor video's in AEM Screens
description: Leer hoe u ondersteuning voor miniaturen voor video's toevoegt in AEM Screens.
exl-id: d2d87807-1699-47e3-b241-07c5b7e56f15
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# Ondersteuning van miniaturen voor video&#39;s {#thumbnail-support-videos}

## Inleiding {#introduction}

Een inhoudauteur kan een duimnagel voor video&#39;s bepalen zodat het beeld als placeholder wordt gebruikt en behoorlijk het playback en richten van inhoud test, terwijl de daadwerkelijke video door het aangewezen team wordt voltooid. De afbeelding kan ook worden gebruikt als het afspelen van de video mislukt.

Door ondersteuning toe te voegen voor een miniatuurafbeelding op de video-component kan de klant op de juiste wijze een geldige component in het kanaal met werkelijke inhoud toevoegen en eventuele doelconfiguraties uitvoeren voordat de video wordt geleverd.

>[!NOTE]
>Als de miniatuurafbeelding op de video-component is ingesteld, wordt deze afgespeeld wanneer de video niet kan worden afgespeeld op de speler. Hierdoor kunt u het gewenste bericht aan het publiek afspelen (door inhoud af te spelen) in plaats van het volledig over te slaan.

Dankzij de ondersteuning voor miniaturen kunt u:

* Een kanaalervaring voorbereiden wanneer de video&#39;s nog niet klaar zijn of wanneer u niet per se een grote download van middelen op de spelers wilt testen

* Stel een fallback-mechanisme in voor het geval er afspeelproblemen optreden op het apparaat.

## Miniaturen in video&#39;s gebruiken {#using-thumbnails}

Voer de onderstaande stappen uit om miniaturen in video&#39;s te gebruiken:

1. Navigeer naar een bestaand AEM Screens-kanaal of maak een kanaal.

1. Klik op het kanaal en klik **Bewerken** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/thumbnails/thumbnail-1.png)

1. Voeg of geef een bestaande videocomponent, zoals aangetoond in hieronder figuur toe uit.

   ![afbeelding](/help/user-guide/assets/thumbnails/thumbnail-2.png)

1. Klik op de video en klik op de *moersleutel* pictogram.

   ![afbeelding](/help/user-guide/assets/thumbnails/thumbnail-3.png)

1. De **Video** wordt geopend waar u de **Miniatuur** dropzone.

   ![afbeelding](/help/user-guide/assets/thumbnails/thumbnail-4.png)

1. Sleep een afbeelding van de elementkiezer naar de **Miniatuur** zone neerzetten en klikken **Gereed**.

   ![afbeelding](/help/user-guide/assets/thumbnails/thumbnail-5.png)

1. Klikken **Voorvertoning**.

1. Als een video op de component wordt geplaatst, speelt de video. Als dat niet het geval is en de miniatuur is ingesteld, wordt de miniatuur afgespeeld. Anders, wordt de component beschouwd als niet gevormd en overgeslagen.

## Ondersteunde gevallen voor gebruik tijdens het gebruik van miniaturen in video&#39;s {#understand-use-case}

Miniatuur in video&#39;s biedt ondersteuning voor de volgende gebruiksscenario&#39;s:

* Een video-component zonder installatie wordt overgeslagen.

* De miniatuur wordt afgespeeld in een video-onderdeel met alleen de miniatuurset.

* De video wordt afgespeeld door een videocomponent met zowel de video (als de video de juiste uitvoering heeft) als de miniatuurset.

* Een video-component met de videoset speelt de miniatuur af, als er een afspeelfout optreedt, of slaat naar het volgende item over als de miniatuur niet is geconfigureerd.
