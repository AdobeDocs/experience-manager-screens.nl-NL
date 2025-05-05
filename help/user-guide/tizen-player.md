---
title: Tizen-speler
description: Meer informatie over de installatie en het werken van de Tizen-speler.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 0%

---

# Tizen-speler implementeren {#tizen-player}

## Tizen-speler installeren {#installing-tizen-player}

Volg de onderstaande stappen om de Tizen-speler voor AEM Screens te implementeren:

1. Navigeer aan de [ pagina van de Downloads van de Speler van AEM Screens ](https://download.macromedia.com/screens/) zodat kunt u de speler downloaden Tizen.

1. Installeer het bestand Tizen Player *(.zip)* vanaf uw lokale computer.

## De http-server instellen {#setting-local-server}

>[!NOTE]
> Extraheer het ZIP-bestand en stel de Tizen-speler beschikbaar via een `http server` . (De `http server` hoeft geen lokale of Apache-server te zijn.)

Voer de onderstaande stappen uit:

1. Kopieer de twee geëxtraheerde bestanden, zoals `AEMScreensPlayer.wgt` en `sssp_config.xml` , naar de hoofdmap van uw lokale Apache-webserver.

   >[!NOTE]
   >`AEMScreensPlayer.wgt` is de daadwerkelijke de spelertoepassing van Tizen en `sssp_config.xml` bevat informatie over deze kaart die u helpt om het op apparaat te installeren Tizen.

1. Haal het IP- of URL-adres van uw lokale HTTP-server op (en het pad naar de map met de geëxtraheerde bestanden in stap 2 als u deze uitpakt naar een submap en niet naar een hoofdmap).

1. De Tizen-speler downloadt het installatieprogramma van de lokale server.

### Naamgeving van Tizen-speler {#name-tizen}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Tizen-speler toewijzen en zo de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de Tizen-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam in de Tizen-speler te configureren:

1. Klik op de menuknop op de afstandsbediening.
1. Navigeer aan **Netwerk** > **Naam van het Apparaat** zodat kunt u een naam aan de speler toewijzen.

### Updates configureren op het Samsung-apparaat {#config-updates}

Voer de onderstaande stappen uit op het Samsung-apparaat, zodat u de installatie van de AEM Screens Player op het apparaat kunt voltooien:

1. Navigeer naar het Samsung-apparaat en schakel het in.
1. Klik de **MENU** knoop van ver van het apparaat en rol neer aan **Systeem** van de linkernavigatiebar.
1. De rol neer en klikt het **Spel als** optie en verandert het in de **Optie van de Lanceerinrichting URL**.
   ![afbeelding](/help/user-guide/assets/tizen/rms-2.png)
1. Wanneer de Lanceerinrichting URL wordt geplaatst, druk de **1&rbrace; knoop van het Huis &lbrace;van uw ver.**
1. Navigeer aan de **Montages van de Lanceerinrichting URL** en ga het IP adres van uw localhost server in en klik **Gedaan**.

   >[!NOTE]
   >De Tizen-speler moet verbinding kunnen maken met de HTTP-server.

1. De AEM Screens Player wordt automatisch op uw Samsung-apparaat geïnstalleerd en gestart.

   >[!NOTE]
   >Zowel het apparaat Tizen als de `http` -server moeten verbinding met elkaar kunnen maken. De server moet dus bereikbaar zijn voor de Tizen-speler.


## Gebruikersagenten vrijstellen van het probleem SameSite Cookie {#exempting-user-agents}

>[!IMPORTANT]
>**deze sectie is op Adobe Experience Manager (AEM) 6.5.5 op AEM 6.5.7 van toepassing**
>
>Sommige browserengines zijn niet compatibel met het attribuut *`SameSite=None`* dat wordt gebruikt in de aanmeldingstoken die door AEM 6.5.5 tot en met AEM 6.5.7 wordt uitgegeven. Meestal kan het probleem worden opgelost door de browser naar de recentste beschikbare versie te upgraden. Soms zijn dergelijke upgrades mogelijk niet mogelijk, zoals bij slimme beeldschermen, set-top boxes of andere apparaten met ingesloten bladerengines.

Volg de stappen hieronder om deze onverenigbare cliënten vrij te stellen wanneer het gebruiken van *SameSite=None*:

1. Upgrade naar Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. Na AEM begin opnieuw, ga naar `/system/console/configMgr` en onderzoek naar **de Afhandeling van de Authentificatie van het Symbolische van de Adobe Granite**. Plaats de waarde voor de **&#x200B;**&#x200B;waarde SameSite aan **niets**.

1. Er wordt een nieuwe optie weergegeven *`User agents to be exempted from samesite attribute`* . Vul deze optie met een regex die aan de gebruikersagent beantwoordt die (zijn) onverenigbaar met *SameSite=None* attributen is.

   >[!NOTE]
   >
   >Zie [ SameSite=None: Bekende Incompatibele Clients ](https://www.chromium.org/updates/same-site/incompatible-clients) voor meer details. Gebruik voor de Tizen-speler de regex: `(.*)Tizen(.*)` .

1. Registreer de Tizen-speler tegen AEM 6.5.5 en hoger en registreer de inhoud normaal.

## De Tizen-speler op afstand voorzien {#remote-provisioning}

Op afstand kunt u met de Tizen-speler honderden en duizenden Samsung Tizen-beeldschermen zonder veel moeite implementeren. Het vermijdt de handmatige inspanning om elke speler met server URL en bulkregistratiecode, of andere parameters te vormen. En, als er AEM Screens as a Cloud Service is, om de wolkenwijze en wolkentoken te vormen.

Met deze functie kunt u Tizen Player op afstand configureren en deze configuraties indien nodig ook centraal bijwerken. U hebt alleen de `HTTP` -server nodig die als host voor de toepassing Tizen wordt gebruikt `(wgt and xml file)` en een teksteditor die de `config.json` met de juiste parameters opslaat.

Zorg ervoor u het adres van de Lanceerinrichting URL op het apparaat van het Bevel hebt gevormd. Klik op de knop Home > URL Launcher-instellingen.
Plaats het bestand `config.json` op dezelfde locatie als het `wgt` -bestand op de `HTTP` -server die als host fungeert voor de toepassing Tizen. De bestandsnaam moet `config.json` zijn.
De Tizen-speler wordt geïnstalleerd en bij het opstarten (en elke keer opnieuw opstarten) gecontroleerd en past de instellingen in het `config.json` -bestand toe.

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
>De beheerconfiguraties van het beleid van Admin UI van de speler worden strikt afgedwongen en worden niet manueel met voeten getreden. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in de beleidsconfiguratie.
>Als u bijvoorbeeld handmatige configuratie wilt toestaan voor het opnieuw opstarten, geeft u de sleutel `rebootSchedule` niet op in de beleidsconfiguratie. Beleidsconfiguraties worden telkens gelezen wanneer de speler opnieuw wordt geladen.

| **Naam van het Beleid** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om naar een ander kanaal op het apparaat te gaan. Denk na plaatsend aan vals, zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in zodat u de voortgang van activiteiten zoals downloaden en synchroniseren kunt weergeven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Tizen-speler verbinding maakt met Screens as a Cloud Service. Ingesteld op false om verbinding te maken met AMS of on-prem AEM. |
| cloudToken | Registertoken voor Screens as a Cloud Service. |


## Het Tizen-apparaat inschrijven voor de Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Voer de onderstaande stappen uit om het Tizen-apparaat in te schrijven bij de Samsung Remote Management Service (RMS) en de URL Launcher op afstand te configureren:

>[!NOTE]
>Controleer de netwerkinstellingen en de monitor.

1. Navigeer aan **Menu** -> **Netwerk** -> **de Montages van het Netwerk van de Server** en druk **binnengaan**.

1. Navigeer aan het adres en het type van de Server in de toegang MagicInfo URL en druk **Gedaan**.

1. Indien nodig TLS instellen. Navigeer aan de haven en klik het havenaantal van de server en klik **sparen**.

1. Navigeer aan het **Apparaat** lusje en controleer het apparaat dat u vormde. Wanneer een apparaat zijn gevonden, klik de controledoos, dan klik **goedkeuren**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-3.png)

1. Vul de vereiste gegevens in en klik op een apparaatgroep. Klik **OK**.

   >![afbeelding](/help/user-guide/assets/tizen/rms-7.png)

1. Wanneer het Apparaat wordt goedgekeurd, verschijnt het op de Lijst van het Apparaat. Klik *Informatie* op uw apparatendoos zoals aangetoond in het volgende.

   >![afbeelding](/help/user-guide/assets/tizen/rms-6.png)

1. Het dialoogvenster Apparaatinformatie wordt weergegeven. Klik het **lusje van Info van het Apparaat 0&rbrace; &lbrace;en klik** uitgeven **.**

   >![afbeelding](/help/user-guide/assets/tizen/rms-5.png)

1. Bewerk de apparatenopties en klik de **Opstelling** tabel. Navigeer aan **de sectie van de Lanceerinrichting URL** en ga URL in die het wgt en `SSSP config file` ontvangt zodat kunt u een `SSSP` toepassing installeren, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/tizen/rms-9.png)

1. Klik **sparen**.

### De afstandsbediening van Screens gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Leer meer over deze eigenschap hier: [ de Verre Controle van Screens ](implementing-remote-control.md)
