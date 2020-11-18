---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
translation-type: tm+mt
source-git-commit: 8f8973c4fda8d40f919e199be3df15ba42f0a6c6
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---


# Tizen Player implementeren {#tizen-player}

## Tizen Player installeren {#installing-tizen-player}

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het zip-bestand (Tizen Player) van de lokale computer.

## De lokale server instellen en ZIP-bestanden uitpakken {#setting-local-server}

Voer de onderstaande stappen uit om de lokale server in te stellen en de geëxtraheerde bestanden te kopiëren:

1. IP-adres van uw lokale computer ophalen.

   >[!NOTE]
   >U kunt het IP adres van de Terminal van uw machine krijgen door de volgende bevelen te typen:
   >* **Mac**: `ifconfig`
   >* **Windows**: `ipconfig`


1. Navigeer in de Terminal naar dezelfde map in de map met uitgevouwen installatieprogramma en controleer of de localhost werkt.

   >[!NOTE]
   >Typ voor **Mac**`http://localhost` en controleer of de `http` server actief is.

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

1. Kopieer de twee geëxtraheerde bestanden `AEMScreensPlayer.wgt` en `sssp_config.xml` naar `/Library/WebServer/Documents`.

### Updates configureren op het Samsung-apparaat {#config-updates}

Volg de onderstaande stappen op het Samsung-apparaat om de installatie van de AEM Screens-speler op het apparaat te voltooien:

1. Ga naar uw Samsung-apparaat en wijs dit naar uw localhost-server.
1. Selecteer **URL Launcher Settings** in de **Settings** en voer het IP-adres van uw localhost-server in.
1. Webtoepassing installeren.
1. Selecteer **Extern** in de **ontwikkelaarsmodus**.
1. De AEM Screens Player moet nu automatisch op uw Samsung-apparaat worden geïnstalleerd.


