---
title: Ondersteuning voor miniaturen voor video's in AEM Screens
description: In deze pagina wordt beschreven hoe u ondersteuning voor miniaturen voor video's in schermen kunt toevoegen.
index: false
source-git-commit: e1f46a908a10bdf08985c857fb9302d3e111e9a1
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Ondersteuning van miniaturen voor video&#39;s {#thumbnail-support-videos}

## Inleiding {#introduction}

Een inhoudauteur kan een duimnagel voor video&#39;s bepalen zodat het beeld als placeholder kan worden gebruikt en behoorlijk het playback en richten van inhoud testen, terwijl de daadwerkelijke video door het aangewezen team wordt gebeëindigd. De afbeelding kan ook worden gebruikt voor het geval dat het afspelen van de video mislukt.

Door ondersteuning toe te voegen voor een miniatuurafbeelding op de video-component kan de klant op de juiste wijze een geldige component in het kanaal met werkelijke inhoud toevoegen en eventuele doelconfiguraties uitvoeren voordat de video daadwerkelijk wordt geleverd.

>[!NOTE]
>Als de miniatuurafbeelding op de video-component is ingesteld, wordt deze afgespeeld als het afspelen van de video is mislukt. Hierdoor kunt u het gewenste bericht aan het publiek afspelen (door inhoud af te spelen) in plaats van het volledig over te slaan.

Dankzij de ondersteuning voor miniaturen kunt u:

* Een kanaalervaring voorbereiden wanneer de video&#39;s nog niet klaar zijn of wanneer u niet per se een grote download van middelen op de spelers wilt testen

* Stel een fallback-mechanisme in voor het geval er afspeelproblemen optreden op het apparaat.

## Miniaturen in video&#39;s gebruiken {#using-thumbnails}

Voer de onderstaande stappen uit om miniaturen in video&#39;s te gebruiken:

1. Navigeer naar een bestaand rasterkanaal of maak een nieuw kanaal.


1. Selecteer het kanaal en klik op **Edit** van de actiebar om de redacteur te openen.

1. Voeg of geef een bestaande videocomponent, zoals aangetoond in hieronder figuur toe uit.

1. Selecteer de video en klik op het *moersleutelpictogram* om de video-eigenschappen te openen.

1. Het dialoogvenster **Video** wordt geopend waar u de neerzetzone **Miniatuur** wilt weergeven.

1. Sleep een afbeelding van de elementenkiezer naar de neerzetzone **Miniatuur** en klik op **Done**.

1. Klik op **Voorvertoning**.

1. Als een video op de component wordt geplaatst, zal de video spelen. Als dat niet het geval is en de miniatuur is ingesteld, wordt de miniatuur afgespeeld. Anders wordt de component beschouwd als niet gevormd en zal worden overgeslagen.

## Ondersteunde gevallen voor gebruik tijdens het gebruik van miniaturen in video&#39;s {#understand-use-case}

Miniatuur in video&#39;s biedt ondersteuning voor de volgende gebruiksscenario&#39;s:

* Een video-onderdeel zonder installatie wordt overgeslagen.

* De miniatuur wordt afgespeeld in een video-onderdeel met alleen de miniatuurset.

* De video wordt afgespeeld met een video-component met zowel de video (als de video de juiste uitvoering heeft) als de miniatuurset.

* Een videocomponent met de videoreeks zal de duimnagel spelen, in het geval van een playbackfout, of zal enkel aan het volgende punt overslaan voor het geval dat de duimnagel niet wordt gevormd.
