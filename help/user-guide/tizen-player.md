---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
translation-type: tm+mt
source-git-commit: 4c005ace7b1da94ed527164d6cfa09666d746273
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 0%

---


# Tizen Player {#tizen-player} implementeren

## Tizen Player {#installing-tizen-player} installeren

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het bestand *(.zip)* van de lokale computer.

## Gebruikersagenten vrijstellen met het Samesite Cookie-probleem {#exempting-user-agents}

>[!IMPORTANT]
>**Dit punt is van toepassing op AEM 6.5.5 tot en met AEM 6.5.7**
>Sommige browserengines zijn niet compatibel met het kenmerk *SameSite=None* dat wordt gebruikt in het aanmeldingstoken dat wordt uitgegeven door AEM 6.5 tot AEM 6.7. In de meeste gevallen kan het probleem worden opgelost door de browser naar de nieuwste beschikbare versie te upgraden. In sommige gevallen zijn dergelijke upgrades mogelijk niet mogelijk, zoals bij slimme beeldschermen, instellen van bovenste vakken of andere apparaten met ingesloten bladerprogramma&#39;s. Voer de volgende stappen uit om deze niet-compatibele clients vrij te stellen wanneer u SameSite=None gebruikt.

1. Download de patch *jar file* van `https://artifactory.corp.adobe.com/artifactory/maven-aem-release-local/com/adobe/granite/crx-auth-token/2.6.10/`.

1. Navigeer naar `/system/console/bundles` in AEM en klik op de knop `install/update`.

1. Installeer het jar-bestand `crx-auth-token`. U moet mogelijk AEM afsluiten en opnieuw starten nadat u deze pot hebt geïnstalleerd, omdat deze gerelateerd is aan verificatie.

1. Nadat AEM opnieuw begint, ga naar `/system/console/configMgr` en onderzoek naar **de Handler van de Authentificatie van het Symbolische Symbolie van de Adobe.** Stel de waarde voor de instelling SameSite in op Geen.

1. U zou een nieuwe optie *Gebruikersagenten moeten zien om van zelfde attributen worden vrijgesteld*. Vul deze met een regex die overeenkomt met de gebruikersagent(s) die niet compatibel is (zijn) met het *SameSite=None*-kenmerk.
   >[!NOTE]
   >Zie [SameSite=None: Bekende Niet-compatibele Clients](https://www.chromium.org/updates/same-site/incompatible-clients) voor meer informatie.

1. Gebruik voor de Tizen-speler de regex: `(.*)Tizen (4|5)(.*)` Registreer de Tizen-speler op uw AEM 6.5.5 en hoger en registreer de inhoud normaal.


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
   ![afbeelding](/help/user-guide/assets/tizen/rms-2.png)

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

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en de URL Launcher op afstand te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Navigeer naar **Menu** -> **Netwerk** -> **Servernetwerkinstellingen** en druk op **Enter**.

   >[!NOTE]
   >Controleer of het scherm is ingesteld op Afspelen via URL Launcher.
   >![afbeelding](/help/user-guide/assets/tizen/rms-2.png)

1. Navigeer aan het Adres van de Server en typ in de toegang MagicInfo URL en druk Gedaan.

1. Indien nodig TLS instellen. Navigeer naar de poort en selecteer het poortnummer van de server. Klik op **Opslaan**.

1. Navigeer naar het tabblad Apparaat en zoek naar het apparaat dat u net hebt geconfigureerd.

1. Nadat een apparaat is gevonden, klikt u op het selectievakje en selecteert u **Goedkeuren**.

1. Vul de vereiste informatie in en selecteer een apparaatgroep. Klik op **Ok** om het goedkeuringsproces te voltooien.

   >![afbeelding](/help/user-guide/assets/tizen/rms-7.png)

1. Zodra het Apparaat wordt goedgekeurd, zou het op de Lijst van het Apparaat moeten verschijnen. Klik op de *Informatieknop* in het apparaatvak **i**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-6.png)

1. Het dialoogvenster Apparaatinformatie wordt weergegeven. Selecteer het tabblad **Apparaatgegevens** en klik op **Bewerken**.

1. Bewerk apparaatopties en selecteer het tabblad **Setup**. Navigeer naar de sectie **URL Launcher** en voer de URL in die als host fungeert voor de widget en `SSSP config file` om een `SSSP`-toepassing te installeren, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/tizen/rms-9.png)

1. Klik op **Opslaan** om de wijzigingen weer te geven op het scherm.




