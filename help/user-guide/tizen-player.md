---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
translation-type: tm+mt
source-git-commit: baefade9fa013bc77ed1f112d0ad2098c992dde5
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Tizen Player implementeren {#tizen-player}

## Tizen Player installeren {#installing-tizen-player}

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het zip-bestand (Tizen Player) van de lokale computer.

1. IP-adres van uw lokale computer ophalen.

   >[!NOTE]
   >In de Terminal van uw machine typ de volgende bevelen voor:
   >**Mac** -opdracht `ifconfig`
   >**Windows**, opdracht gebruiken `ipconfig`

1. Navigeer in de Terminal naar dezelfde map in de map met uitgevouwen installatieprogramma en controleer of de localhost werkt.

   >[!NOTE]
   >Typ voor **Mac**`http://localhost` en controleer of de `http` server actief is.

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

1. Kopieer de twee geëxtraheerde bestanden `AEMScreensPlayer.wgt` en `sssp_config.xml` naar `/Library/WebServer/Documents`.

### Configuratie-updates op het SamSung-apparaat {#config-updates}

Volg de onderstaande stappen op het Samsung-apparaat om de installatie van de AEM Screens-speler op het apparaat te voltooien:

1. Klik op de knop **Home** op de Samsung Remote.
1. Selecteer **URL Launcher** in de **Instellingen**.
1. Selecteer **Extern** in de modus Ontwikkelaar.
1. Installeer Web App en voer het IP-adres van uw computer in.
De AEM Screens Player moet automatisch op het Samsung-apparaat worden geïnstalleerd.


