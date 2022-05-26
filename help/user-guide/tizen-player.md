---
title: Tizen Player
description: Deze pagina beschrijft de installatie en het werk van Speler Tizen.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
source-git-commit: 8d4a7b2bc436d822c673a00437ee895c8ef5cb6f
workflow-type: tm+mt
source-wordcount: '1242'
ht-degree: 0%

---

# Tizen Player implementeren {#tizen-player}

## Tizen Player installeren {#installing-tizen-player}

Voer de volgende stappen uit om Tizen Player voor AEM Screens te implementeren:

1. Ga naar de [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/) pagina om de Tizen Player te downloaden.

1. De Tizen-speler installeren *(.zip)* bestand van de lokale computer.

## De http-server instellen {#setting-local-server}

>[!NOTE]
> Extraheer het ZIP-bestand en stel de Tizen-speler beschikbaar via een `http server`. (De `http server` is niet vereist om een lokale of Apache-server te zijn).

Voer de onderstaande stappen uit:

1. Kopieer de twee geëxtraheerde bestanden, zoals `AEMScreensPlayer.wgt` en `sssp_config.xml` naar de hoofdmap van uw lokale Apache-webserver.

   >[!NOTE]
   >De `AEMScreensPlayer.wgt`is de werkelijke Tizen Player-toepassing en `sssp_config.xml` bevat informatie over deze kaart die u helpt deze op een apparaat met tizen te installeren.

1. Hiermee wordt de IP of URL van uw lokale HTTP-server opgehaald (en wordt het pad naar de map met de geëxtraheerde bestanden in stap 2 aangegeven als deze worden uitgepakt naar een submap en niet naar de hoofdmap)

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

### Naamgeving van Tizen Player {#name-tizen}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Tizen-speler toewijzen en daarbij de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de Tizen-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Player is geregistreerd, kan de Player-naam niet meer worden gewijzigd.

Voer de onderstaande stappen uit om de naam in de Tizen-speler te configureren:

1. Klik op de menuknop op de afstandsbediening.
1. Navigeren naar **netwerk** —> **Apparaatnaam** om een naam aan de speler toe te wijzen.

### Updates configureren op het Samsung-apparaat {#config-updates}

Volg de onderstaande stappen op het Samsung-apparaat om de installatie van de AEM Screens-speler op het apparaat te voltooien:

1. Navigeer naar het Samsung-apparaat en schakel het in.

1. Klik op de knop **MENU** van de afstandsbediening van het apparaat naar beneden schuiven **Systeem** in de linkernavigatiebalk.

1. Omlaag schuiven en de **Afspelen via** en wijzigen in **URL Launcher** optie.
   ![afbeelding](/help/user-guide/assets/tizen/rms-2.png)

1. Wanneer de URL Launcher is ingesteld, drukt u op de knop **Home** vanaf de afstandsbediening.

1. Ga naar de **Instellingen voor URL-opstart** en voer het IP-adres van uw localhost-server in en klik op **Gereed**.
   >[!NOTE]
   >De Tizen-speler moet verbinding kunnen maken met de http-server.

1. De AEM Screens Player moet nu automatisch worden geïnstalleerd en gestart op uw Samsung-apparaat.

   >[!NOTE]
   >Zowel het apparaat Tizen als het `http` De server moet verbinding met elkaar kunnen maken, dat wil zeggen dat de server bereikbaar moet zijn voor de Tizen-speler.


## Gebruikersagenten vrijstellen van het probleem SameSite Cookie {#exempting-user-agents}

>[!IMPORTANT]
>**Dit punt is van toepassing op Adobe Experience Manager (AEM) 6.5.5 tot en met AEM 6.5.7**
>Sommige browserengines zijn niet compatibel met de *SameSite=None* attribuut gebruikt in het login teken dat door AEM 6.5 tot AEM 6.7 wordt uitgegeven. Meestal kan het probleem worden opgelost door de browser naar de recentste beschikbare versie te upgraden. In sommige gevallen zijn dergelijke upgrades mogelijk niet mogelijk, zoals bij slimme beeldschermen, instellen van bovenste vakken of andere apparaten met ingesloten bladerprogramma&#39;s.

Voer de onderstaande stappen uit om deze niet-compatibele clients vrij te stellen bij het gebruik van *SameSite=None*:

1. Upgrade naar Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Ga na AEM start naar `/system/console/configMgr` en zoek naar **Adobe Granite Token Authentication Handler**. Stel de waarde in voor de **SameSite** waarde aan **Geen**.

1. Er moet een nieuwe optie worden weergegeven *Gebruikersagenten die van hetzelfde kenmerk moeten worden vrijgesteld*. Vul deze met een regex die overeenkomt met de gebruikersagent die niet compatibel is (zijn) met de *SameSite=None* kenmerk.
   >[!NOTE]
   >Zie [SameSite=Geen: Bekende niet-compatibele clients](https://www.chromium.org/updates/same-site/incompatible-clients) voor meer informatie . Gebruik voor de Tizen-speler de regex: `(.*)Tizen(.*)`.

1. Registreer de Tizen-speler tegen AEM 6.5.5 en hoger en registreer de inhoud normaal.

## De Tizen Player op afstand bevoorraden {#remote-provisioning}

Op afstand kunt u met de Tizen Player honderden of duizenden Samsung Tizen-beeldschermen zonder veel moeite implementeren. Het vermijdt de vervelende handmatige inspanning om elke speler met server URL en bulkregistratiecode, of andere parameters te vormen, en in het geval van Schermen as a Cloud Service om de wolkenwijze en wolkentoken te vormen.

Met deze functie kunt u Tizen Player op afstand configureren en deze configuraties indien nodig centraal bijwerken. Alles wat u nodig hebt, is de `HTTP` server die wordt gebruikt om de toepassing Tizen te hosten `(wgt and xml file)` en een teksteditor om de `config.json` met de juiste parameters.

Controleer of u het URL-startadres op het Tizen-apparaat hebt geconfigureerd, dat wil zeggen: Home Button —> URL Launcher-instellingen.
Op de `HTTP` server die als host fungeert voor de toepassing Tizen, plaatst u het bestand `config.json` op dezelfde locatie als `wgt` bestand. De bestandsnaam moet `config.json`.
De Tizen-speler wordt geïnstalleerd en bij het opstarten (en elke keer dat de computer opnieuw wordt opgestart) worden de instellingen in het dialoogvenster `config.json` bestand.

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

### Beleidskenmerken en Doel {#policy-attributes}

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
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals, zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Tizen-speler verbinding maakt met as a Cloud Service schermen. Ingesteld op false om verbinding te maken met AMS of on-Prem AEM. |
| cloudToken | Registratietoken voor registratie tegen as a Cloud Service schermen. |


## Het Tizen-apparaat inschrijven voor de Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en de URL Launcher op afstand te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Navigeren naar **Menu** -> **Netwerk** -> **Servernetwerkinstellingen** en drukken **Enter**.

1. Navigeer aan het adres van de Server en typ in de toegang MagicInfo URL en druk **Gereed**.

1. Indien nodig TLS instellen. Navigeer naar de poort en selecteer het poortnummer van de server en klik op **Opslaan**.

1. Ga naar de **Apparaat** en controleer het apparaat dat u net hebt geconfigureerd. Nadat een apparaat is gevonden, klikt u op het selectievakje en selecteert u **Goedkeuren**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-3.png)

1. Vul de vereiste informatie in en selecteer een apparaatgroep. Klikken op **OK** om het goedkeuringsproces te voltooien.

   >![afbeelding](/help/user-guide/assets/tizen/rms-7.png)

1. Zodra het Apparaat wordt goedgekeurd, zou het op de Lijst van het Apparaat moeten verschijnen. Klik op de knop *Informatie* op de doos van uw apparaat wordt gevestigd, dat **i**, zoals weergegeven in onderstaande afbeelding.

   >![afbeelding](/help/user-guide/assets/tizen/rms-6.png)

1. Het dialoogvenster Apparaatinformatie wordt weergegeven. Selecteer **Apparaatinfo** en klik op **Bewerken**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-5.png)

1. Bewerk de apparaatopties en selecteer de **Instellen** tab. Navigeren naar **URL Launcher** en voer de URL in die als host fungeert voor de widget en `SSSP config file` om een `SSSP` wordt toegepast, zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/tizen/rms-9.png)

1. Klikken op **Opslaan** voor de wijzigingen die op het weergavescherm worden weergegeven.

### De afstandsbediening voor schermen gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Meer informatie over deze functie vindt u hier: [Schermen afstandsbediening](implementing-remote-control.md)
