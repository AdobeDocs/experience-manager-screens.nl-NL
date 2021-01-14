---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
translation-type: tm+mt
source-git-commit: 1ec3e3541755550f719dbe53e83326d9796de14f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---


# Tizen Player {#tizen-player} implementeren

## Tizen Player {#installing-tizen-player} installeren

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het bestand *(.zip)* van de lokale computer.

## De lokale server instellen en ZIP-bestanden uitpakken {#setting-local-server}

Voer de onderstaande stappen uit om de lokale server in te stellen en de geëxtraheerde bestanden te kopiëren:

1. IP-adres van uw lokale computer ophalen.
   >[!NOTE]
   >Raadpleeg de officiële documentatie voor informatie over het inschakelen van de lokale server op uw platform.

1. Navigeer in de Terminal naar dezelfde map in de map met uitgevouwen installatieprogramma en controleer of de localhost werkt.

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

1. Kopieer de twee geëxtraheerde bestanden, zoals `AEMScreensPlayer.wgt` en `sssp_config.xml`, naar de hoofdmap van uw lokale Apache-webserver.

   >[!NOTE]
   >De `AEMScreensPlayer.wgt`is de werkelijke Tizen Player-toepassing en `sssp_config.xml` bevat informatie over deze kaart die u helpt deze te installeren op een Tizen-apparaat.

### Updates configureren op het Samsung-apparaat {#config-updates}

Volg de onderstaande stappen op het Samsung-apparaat om de installatie van de AEM Screens-speler op het apparaat te voltooien:

1. Navigeer naar het Samsung-apparaat en schakel het in.

1. Klik op de knop **MENU** van de afstandsbediening van het apparaat en schuif omlaag naar **Systeem** vanaf de linkernavigatiebalk.

1. Schuif omlaag en selecteer de optie **Afspelen via URL Launcher**.
   ![afbeelding](/help/user-guide/assets/tizen/url-launcher.png)

1. Druk **Home** knoop van uw ver.

1. Voer het IP-adres van uw localhost-server in.

1. Selecteer **Extern** in de **Modus Ontwikkelaar**.

1. Klik op de knop **Home** op de afstandsbediening van het apparaat en selecteer **URL Launcher**.

1. De AEM Screens Player moet nu automatisch worden geïnstalleerd en gestart op uw Samsung-apparaat.

## Bulkprovisioning van tizen Player {#bulk-provisioning-tizen-player}

>[!NOTE]
>Het kan een vervelende inspanning zijn om het adres van uw AEM server in admin UI van elk en elk apparaat voor een groot aantal apparaten manueel in te gaan. Het wordt aanbevolen de Samsung Remote Management (RMS)-oplossing te gebruiken voor de implementatie en het beheer van de oplossing. Raadpleeg [Het Tizen-apparaat inschrijven bij de Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm) voor meer informatie.

Voer de onderstaande stappen uit om een bulkbepaling in de toepassing op te nemen die naar de AEM-auteur verwijst wanneer deze wordt gestart:

1. Download en installeer de [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download).
1. Open het `wgt`-bestand met gebruik van de Tizen-studio.
1. Open het bestand `firmware-platform.js` en zoek naar `DEFAULT_PREFERENCES` en wijzig de URL van de server in de URL van de AEM auteur en sla deze op.
1. Bouw het nieuwe `wgt` dossier.

   >[!NOTE]
   >Mogelijk moet u een ondertekeningscertificaat maken of instellen.

1. Implementeer dit nieuwe `wgt`-bestand RMS. Wanneer de speler start, moet deze automatisch naar de server verwijzen, zodat u het bestand niet handmatig voor elk apparaat hoeft in te voeren.

### Het Tizen-apparaat aanmelden bij de Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en op afstand URL Launcher te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Druk Menu op uw ver en ga Systeem en druk dan binnen op Spel Via.

   >[!NOTE]
   >Controleren of het scherm is ingesteld op Afspelen via URL Launcher
1. Navigeer naar **Menu** -> **Netwerk** -> **Servernetwerkinstellingen** en druk op **Enter**.

1. Navigeer aan het Adres van de Server en typ in de toegang MagicInfo URL en druk Gedaan.

1. Navigeer naar het tabblad Apparaat wanneer u bent aangemeld bij MIS
1. Zoek het apparaat u enkel gevormd door het IP adres en/of zijn Adres van MAC te bekijken.
1. Nadat een apparaat is gevonden, klikt u op het selectievakje en selecteert u Goedkeuren
1. Controleer of het scherm is ingesteld op Afspelen via URL Launcher
1. Druk op Menu op de afstandsbediening en ga naar Systeem en druk vervolgens op Enter op Play Via
1. Ga naar Menu -> Netwerk -> De Montages van het Netwerk van de Server en druk binnengaan
1. Ga naar het Adres van de Server en typ in de toegang van MagicInfo URL en druk Gedaan
1. Afhankelijk van het geval TLS instellen op Gebruik of Niet gebruiken
1. Ga naar poort en selecteer het poortnummer van de server.
1. Druk op Opslaan als de opties gereed zijn.



