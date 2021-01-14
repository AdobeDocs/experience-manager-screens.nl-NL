---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
translation-type: tm+mt
source-git-commit: c1ddb5f458831025bdcd1481bcdc198616f5bb47
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 1%

---


# Tizen Player {#tizen-player} implementeren

## Tizen Player {#installing-tizen-player} installeren

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [AEM Screens Player Downloads](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het bestand *(.zip)* van de lokale computer.

## Gebruikersagenten vrijstellen met het Samesite Cookie-probleem {#exempting-user-agents}

>[!IMPORTANT]
>**Dit punt is van toepassing op Adobe Experience Manager (AEM) 6.5.5 tot en met AEM 6.5.7**
>Sommige browserengines zijn niet compatibel met het kenmerk *SameSite=None* dat wordt gebruikt in het aanmeldingstoken dat wordt uitgegeven door AEM 6.5 tot AEM 6.7. In de meeste gevallen kan het probleem worden opgelost door de browser naar de nieuwste beschikbare versie te upgraden. In sommige gevallen zijn dergelijke upgrades mogelijk niet mogelijk, zoals bij slimme beeldschermen, instellen van bovenste vakken of andere apparaten met ingesloten bladerprogramma&#39;s.

Voer de onderstaande stappen uit om deze niet-compatibele clients vrij te stellen wanneer u *SameSite=None* gebruikt:

1. Upgrade naar Adobe Experience Manager (AEM) Service Pack 6.5.8.

   >[!NOTE]
   >Als u AEM 6.5.8 installeert, kunt u de volgende stappen 2 &amp; 3 overslaan.

1. Navigeer naar `/system/console/bundles` in AEM en klik op de knop `install/update`.

1. Installeer het jar-bestand `crx-auth-token`. U moet mogelijk AEM afsluiten en opnieuw starten nadat u deze pot hebt geïnstalleerd, omdat deze gerelateerd is aan verificatie.

1. Nadat AEM opnieuw begint, ga naar `/system/console/configMgr` en onderzoek naar **de Handler van de Authentificatie van het Symbolische Symbolie van de Adobe.** Stel de waarde voor de waarde **SameSite** in op **None**.

1. U zou een nieuwe optie *Gebruikersagenten moeten zien om van zelfde attributen worden vrijgesteld*. Vul deze met een regex die overeenkomt met de gebruikersagent(s) die niet compatibel is (zijn) met het *SameSite=None*-kenmerk.
   >[!NOTE]
   >Zie [SameSite=None: Bekende Niet-compatibele Clients](https://www.chromium.org/updates/same-site/incompatible-clients) voor meer informatie. Gebruik voor de Tizen-speler de regex: `(.*)Tizen(.*)`.

1. Registreer de Tizen-speler tegen AEM 6.5.5 en hoger en registreer de inhoud normaal.


## De lokale server instellen en ZIP-bestanden uitpakken {#setting-local-server}

Voer de onderstaande stappen uit:

1. Kopieer de twee geëxtraheerde bestanden, zoals `AEMScreensPlayer.wgt` en `sssp_config.xml`, naar de hoofdmap van uw lokale Apache-webserver.

   >[!NOTE]
   >De `AEMScreensPlayer.wgt`is de werkelijke Tizen Player-toepassing en `sssp_config.xml` bevat informatie over deze kaart die u helpt deze te installeren op een Tizen-apparaat.

1. Hiermee wordt de IP of URL van uw lokale HTTP-server opgehaald (en wordt het pad naar de map met de geëxtraheerde bestanden in stap 2 aangegeven als deze worden uitgepakt naar een submap en niet naar de hoofdmap)

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

### Updates configureren op het Samsung-apparaat {#config-updates}

Volg de onderstaande stappen op het Samsung-apparaat om de installatie van de AEM Screens-speler op het apparaat te voltooien:

1. Navigeer naar het Samsung-apparaat en schakel het in.

1. Klik op de knop **MENU** van de afstandsbediening van het apparaat en schuif omlaag naar **Systeem** vanaf de linkernavigatiebalk.

1. Schuif omlaag en selecteer de optie **Afspelen via** en wijzig deze in **URL-opstarter**.
   ![afbeelding](/help/user-guide/assets/tizen/rms-2.png)

1. Zodra de Lanceerinrichting URL wordt geplaatst, druk **Huis** knoop van uw ver.

1. Navigeer naar **URL Launcher Settings** en voer het IP-adres van uw localhost-server in en klik op **Done**.
   >[!NOTE]
   >De Tizen-speler moet verbinding kunnen maken met de http-server.

1. De AEM Screens Player moet nu automatisch worden geïnstalleerd en gestart op uw Samsung-apparaat.

   >[!NOTE]
   >Zowel het apparaat Tizen als de `http`-server moeten verbinding met elkaar kunnen maken. De server moet dus bereikbaar zijn voor de Tizen-speler.

## Bulkprovisioning van tizen Player {#bulk-provisioning-tizen-player}

>[!NOTE]
>Het kan een vervelende inspanning zijn om het adres van uw AEM server in admin UI van elk en elk apparaat voor een groot aantal apparaten manueel in te gaan. Het wordt aanbevolen de Samsung Remote Management (RMS)-oplossing te gebruiken voor het implementeren en beheren van grotere oplossingen. Raadpleeg [Het Tizen-apparaat inschrijven bij de Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm) voor meer informatie.

Voer de onderstaande stappen uit om een bulkbepaling in de toepassing op te nemen die naar de AEM-auteur verwijst wanneer deze wordt gestart:

1. Download en installeer de [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download).
1. Open het `wgt`-bestand met gebruik van de Tizen-studio.
1. Open het bestand `firmware-platform.js` en zoek naar `DEFAULT_PREFERENCES` en wijzig de URL van de server in de URL van de AEM auteur en sla deze op.
1. Bouw het nieuwe `wgt` dossier.

   >[!NOTE]
   >Mogelijk moet u een ondertekeningscertificaat maken of instellen.

1. Implementeer dit nieuwe `wgt`-bestand RMS. Wanneer de speler start, moet deze automatisch naar de server verwijzen, zodat u het bestand niet handmatig voor elk apparaat hoeft in te voeren.

### Het Tizen-apparaat aanmelden bij de Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en de URL Launcher op afstand te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Navigeer naar **Menu** -> **Netwerk** -> **Servernetwerkinstellingen** en druk op **Enter**.

   >[!NOTE]
   >Controleer of het scherm is ingesteld op Afspelen via URL Launcher.
   >![afbeelding](/help/user-guide/assets/tizen/rms-2.png)

1. Navigeer naar het serveradres en typ in de MagicInfo URL-toegang en druk op **Done**.

1. Indien nodig TLS instellen. Navigeer naar de poort en selecteer het poortnummer van de server en klik op **Opslaan**.

1. Navigeer naar het **Apparaat** lusje en controleer het apparaat u enkel vormde. Nadat een apparaat is gevonden, klikt u op het selectievakje en selecteert u **Goedkeuren**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-3.png)

1. Vul de vereiste informatie in en selecteer een apparaatgroep. Klik op **OK** om het goedkeuringsproces te voltooien.

   >![afbeelding](/help/user-guide/assets/tizen/rms-7.png)

1. Zodra het Apparaat wordt goedgekeurd, zou het op de Lijst van het Apparaat moeten verschijnen. Klik op de *Information* knoop op uw apparatendoos, die **i** is, zoals aangetoond in het hieronder cijfer.

   >![afbeelding](/help/user-guide/assets/tizen/rms-6.png)

1. Het dialoogvenster Apparaatinformatie wordt weergegeven. Selecteer het tabblad **Apparaatgegevens** en klik op **Bewerken**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-5.png)

1. Bewerk de apparaatopties en selecteer het tabblad **Setup**. Navigeer naar de sectie **URL Launcher** en voer de URL in die als host fungeert voor de widget en `SSSP config file` om een `SSSP`-toepassing te installeren, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/tizen/rms-9.png)

1. Klik op **Opslaan** om de wijzigingen weer te geven op het scherm.




