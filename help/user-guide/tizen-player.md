---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
feature: Schermen, afspeelapparatuur beheren
role: Administrator
level: Intermediate
source-git-commit: e955838d33cbe74719b237e568fb0bfd1a6844a2
workflow-type: tm+mt
source-wordcount: '1209'
ht-degree: 0%

---


# Tizen Player {#tizen-player} implementeren

## Tizen Player {#installing-tizen-player} installeren

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Navigeer naar de pagina [AEM Screens Player Downloads](https://download.macromedia.com/screens/) om de Tizen Player te downloaden.

1. Installeer het bestand *(.zip)* van de lokale computer.

## De lokale server instellen en ZIP-bestanden uitpakken {#setting-local-server}

>[!NOTE]
> Extraheer het ZIP-bestand en stel de Tizen-speler beschikbaar via een `http server`. (De `http server` hoeft geen lokale of Apache-server te zijn.)

Voer de onderstaande stappen uit:

1. Kopieer de twee geëxtraheerde bestanden, zoals `AEMScreensPlayer.wgt` en `sssp_config.xml`, naar de hoofdmap van uw lokale Apache-webserver.

   >[!NOTE]
   >De `AEMScreensPlayer.wgt`is de werkelijke Tizen Player-toepassing en `sssp_config.xml` bevat informatie over deze kaart die u helpt deze te installeren op een Tizen-apparaat.

1. Hiermee wordt de IP of URL van uw lokale HTTP-server opgehaald (en wordt het pad naar de map met de geëxtraheerde bestanden in stap 2 aangegeven als deze worden uitgepakt naar een submap en niet naar de hoofdmap)

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

### Naamgeving van Tizen Player {#name-tizen}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Tizen-speler toewijzen en daarbij de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de Tizen-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

Voer de onderstaande stappen uit om de naam in de Tizen-speler te configureren:

1. Klik op de menuknop op de afstandsbediening.
1. Navigeer naar **netwerk** —> **Apparaatnaam** om een naam aan de speler toe te wijzen.

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


## Gebruikersagents met het probleem SameSite Cookie {#exempting-user-agents} vrijstellen

>[!IMPORTANT]
>**Dit punt is van toepassing op Adobe Experience Manager (AEM) 6.5.5 tot en met AEM 6.5.7**
>Sommige browserengines zijn niet compatibel met het kenmerk *SameSite=None* dat wordt gebruikt in het aanmeldingstoken dat wordt uitgegeven door AEM 6.5 tot AEM 6.7. In de meeste gevallen kan het probleem worden opgelost door de browser naar de nieuwste beschikbare versie te upgraden. In sommige gevallen zijn dergelijke upgrades mogelijk niet mogelijk, zoals bij slimme beeldschermen, instellen van bovenste vakken of andere apparaten met ingesloten bladerprogramma&#39;s.

Voer de onderstaande stappen uit om deze niet-compatibele clients vrij te stellen wanneer u *SameSite=None* gebruikt:

1. Upgrade naar Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Nadat AEM opnieuw begint, ga naar `/system/console/configMgr` en onderzoek naar **de Handler van de Authentificatie van het Symbolische Symbolie van de Adobe.** Stel de waarde voor de waarde **SameSite** in op **None**.

1. U zou een nieuwe optie *Gebruikersagenten moeten zien om van zelfde attributen worden vrijgesteld*. Vul deze met een regex die overeenkomt met de gebruikersagent(s) die niet compatibel is (zijn) met het *SameSite=None*-kenmerk.
   >[!NOTE]
   >Zie [SameSite=None: Bekende Niet-compatibele Clients](https://www.chromium.org/updates/same-site/incompatible-clients) voor meer informatie. Gebruik voor de Tizen-speler de regex: `(.*)Tizen(.*)`.

1. Registreer de Tizen-speler tegen AEM 6.5.5 en hoger en registreer de inhoud normaal.

## Op afstand de Tizen Player {#remote-provisioning} voorzien

Op afstand kunt u met de Tizen Player honderden of duizenden Samsung Tizen-beeldschermen zonder veel moeite implementeren. Het vermijdt de vervelende handmatige inspanning om elke speler met server URL en bulkregistratiecode, of andere parameters te vormen, en in het geval van Schermen als Cloud Service om de wolkenwijze en wolkentoken te vormen.

Met deze functie kunt u Tizen Player op afstand configureren en deze configuraties indien nodig centraal bijwerken. U hebt alleen de `HTTP`-server nodig die wordt gebruikt om de toepassing `(wgt and xml file)` voor lagen te hosten en een teksteditor om de `config.json` met de juiste parameters op te slaan.

Controleer of u het URL-startadres op het Tizen-apparaat hebt geconfigureerd, dat wil zeggen: Home Button —> URL Launcher-instellingen.
Plaats het bestand `config.json` op dezelfde locatie als het `HTTP`-bestand op de `wgt`-server die als host fungeert voor de toepassing Tizen. De bestandsnaam moet `config.json` zijn.
De Tizen-speler wordt geïnstalleerd en bij het opstarten (en elke keer dat de computer opnieuw wordt opgestart) worden de instellingen in het `config.json`-bestand gecontroleerd en toegepast.

### Voorbeeld JSON-beleid {#example-json}

```java
{
  "server":  "http://your-aem-instance.com:4502",
  "registrationKey": "AdobeRocks!!",
  "enableAdminUI": true,
  "enableOSD": true,
  "enableActivityUI": true
}
```

### Beleidskenmerken en doel {#policy-attributes}

In de volgende tabel wordt een overzicht gegeven van de beleidsfuncties.

>[!NOTE]
>De configuraties van het beleid worden strikt afgedwongen en worden niet manueel met voeten getreden bij Admin UI van de speler. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in de beleidsconfiguratie, bijvoorbeeld, als u handconfiguratie voor reboot programma wilt toestaan, specificeer niet de sleutel `rebootSchedule` in de beleidsconfiguratie. Beleidsconfiguraties worden telkens gelezen wanneer de speler opnieuw wordt geladen.

| **Beleidsnaam** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Tizen-speler als cloudservice verbinding maakt met schermen. false om verbinding te maken met AMS of onPrem AEM. |
| cloudToken | Registratietoken voor registratie tegen schermen als Cloud Service. |


## Het Tizen-apparaat aanmelden bij de Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en de URL Launcher op afstand te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Navigeer naar **Menu** -> **Netwerk** -> **Servernetwerkinstellingen** en druk op **Enter**.

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

