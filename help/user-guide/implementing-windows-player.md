---
title: Windows 10 Player implementeren
seo-title: Implementing Windows 10 Player
description: Volg deze pagina voor meer informatie over het configureren van AEM Screens Windows 10 Player.
seo-description: Follow this page to learn about configuring AEM Screens Windows 10 player.
uuid: da7e88bf-c251-481e-9029-f8fc4768b309
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 4228e8a1-9749-49a6-a1bb-365492bc2a3d
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 0%

---

# Windows 10 Player implementeren {#implementing-windows-player}

In deze sectie wordt beschreven hoe u AEM Screens Windows 10 Player configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

## Windows Player installeren {#installing-windows-player}

Installeer Windows Player voor AEM Screens om Windows Player voor AEM Screens te implementeren.

Ga naar [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

>[!NOTE]
>Er is geen venstermodus in Windows Player. Dit is altijd de modus Volledig scherm.

### De Milieu van de vestiging voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>U moet een omgeving instellen voor Windows Player als u AEM Screens 6.5.5 Service Pack gebruikt.

Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen** van **Configuratie Adobe Experience Manager-webconsole** op alle AEM auteur- en publicatieinstanties.

Voer de onderstaande stappen uit:

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** gebruiken `http://localhost:4502/system/console/configMgr`.

1. Zoeken naar *Adobe Granite Token Authentication Handler*.

1. Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klikken **Opslaan**.

### Ad hoc-methode {#ad-hoc-method}

Met de ad-hocmethode kunt u de nieuwste Windows Player installeren (*.exe*). Bezoek [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeren naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de AEM instantie in u wenst om met te verbinden en te klikken **Opslaan**.
1. Ga naar de **Apparaat** **Registratie** van het linkeractiemenu om de status van het proces van de apparatenregistratie te controleren.

>[!NOTE]
>
>Als de **Staat** is **GEREGISTREERD**, merkt u de **Apparaat-id** wordt ingevuld.
>
>Als de **Staat** is **ONGEREGISTREERD**, kunt u de **Token** om het apparaat te registreren.

## Namen van Windows Player {#name-windows}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Windows-speler toewijzen en daarbij de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de naam van uw Windows-speler opgeven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Player is geregistreerd, kan de Player-naam niet meer worden gewijzigd.

Voer de onderstaande stappen uit om de naam in Windows Player te configureren:

1. Klikken op **start** > **run**
1. Enter `system.cpl`
1. Gebruik het tabblad Naam van de computer om de hostnaam van de computer in te stellen

## De standaardopties wijzigen in Windows Installer {#changing-default-options}

Volg deze sectie om te leren hoe te om de standaardopties in de Installateur van Vensters en de lijst van beschikbare aanpassingen te veranderen.

## Installatie met CLI (PowerShell) {#install-powershell}

1. Een aangepaste locatie maken **toegewijd** voor Schermspeler, bijvoorbeeld:
   `C:\Users\User\screens-player`)
1. Installeren
   `aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\screens-player`
1. Openen
   `Start-Process C:\Users\User\screens-player\AEMScreensPlayer.exe`

**Voorbeeld**

```shell
C:\Users\User\Downloads> mkdir screens-player

C:\Users\User\Downloads> .\aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\Downloads\screens-player

C:\Users\User\Downloads> Start-Process C:\Users\User\Downloads\screens-player\AEMScreensPlayer.exe
```

## Bulkregistratie van Windows Player {#bulk-registration}

Wanneer u de venstersspeler implementeert, hoeft u niet elke speler handmatig te configureren. In plaats daarvan kunt u het JSON-configuratiebestand bijwerken nadat het is getest en klaar is voor implementatie.

De configuratie zal ervoor zorgen dat alle spelers de zelfde server pingelen die in het configuratiedossier wordt verstrekt. U moet elke speler nog steeds handmatig registreren.

Voer de onderstaande stappen uit om Windows 10 Player te configureren:

1. Windows Player installeren.
1. Het configuratiebestand zoeken onder ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Werk de configuratie-JSON bij met behulp van de onderstaande informatie en kopieer vervolgens dezelfde map naar alle systemen waar de speler zich bevindt.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:


| **Beleidsnaam** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals, zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Windows-speler verbinding maakt met as a Cloud Service schermen. Ingesteld op false om verbinding te maken met AMS of on-Prem AEM. |
| cloudToken | Registratietoken voor registratie tegen as a Cloud Service schermen. |

#### JSON-bestand met voorbeeldbeleid {#example-policy-json-file}

```
{
    "server": "https://localhost:4502",
    "resolution": "auto",
    "rebootSchedule": "at 4:00 am",
    "enableAdminUI": false,
    "enableOSD": false,
    "enableActivityUI": false
}
```

## Modus Kiosk inschakelen {#enabling-kiosk-mode}

Wanneer u de Windows-speler implementeert, is het belangrijk dat u de modus Kiosk inschakelt, zodat andere toepassingen of de taakbalk niet op het bureaublad van Windows worden weergegeven.

>[!CAUTION]
>
>Adobe raadt een oplossing voor apparaatbeheer aan om Kiosk voor Windows in te schakelen. Voer de onderstaande stappen uit als u geen oplossing voor apparaatbeheer hebt om de modus Kiosk in te schakelen. Deze methode gebruikt de eigenschap van de Lanceerinrichting van Shell beschikbaar in Vensters 10 onderneming en uitgeeft. Alle andere door Microsoft aanbevolen methoden voor toepassingen die geen UWP zijn, kunnen ook worden toegepast om Kiosk in te schakelen, met name in andere versies van Windows.

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

>[!NOTE]
>
>Voordat u de onderstaande stappen uitvoert, moet u ervoor zorgen dat u Windows 10 Enterprise of Education gebruikt.

1. Enable Shell Launcher.

   Zie sectie ***Shell Launcher configureren*** in **[Shell Launcher](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/shell-launcher)** pagina door Microsoft Windows voor aanvullende informatie.

1. Maak een niet-administratieve gebruiker (als u er al een hebt) die u voor Kiosk wilt gebruiken. Dit kan een lokale of domeingebruiker zijn.
1. Installeer de vensterspeler voor die Kiosk-gebruiker vanuit [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/) pagina.
1. Zie [De Lanceerinrichting van Shell van het gebruik om Vensters 10 kiosk te creëren](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shelllauncher) om uw manuscript PowerShell voor meer informatie te wijzigen.

   Wijzig het manuscript PowerShell om de gebruikersbenaming met te vervangen u creeerde. Controleer of het pad naar het uitvoerbare bestand van de toepassing juist is. Hierdoor wordt de aangepaste shell ingesteld als de toepassing voor de venstersspeler voor de gebruiker kiosk en wordt de standaardwaarde als explorer.exe voor andere gebruikers ingesteld.

1. Stel het manuscript PowerShell in werking als beheerder.
1. Start opnieuw op en meld u opnieuw aan als de Kiosk-gebruiker en de spelertoepassing meteen moeten starten.

### Problemen oplossen {#troubleshooting}

Als u een zwart scherm krijgt wanneer u zich aanmeldt als gebruiker van Kiosk, betekent dit dat u mogelijk het pad naar het uitvoerbare bestand van de vensterspeler onjuist hebt opgegeven. Meld u weer aan als beheerder en controleer het script en voer het opnieuw uit.

Het standaardinstallatiepad voor Windows Player is:

***C:\Users\&lt;your user=&quot;&quot;>\AppData\Local\Programs\@aem-screensscreens-player-electron\AEM Screens Player.exe***

Met het voorbeeldscript in de koppelingen wordt de aangepaste shell in- en uitgeschakeld. Daarom moet u het script mogelijk in tweeën splitsen en de onderstaande toepasselijke regels in- en uitschakelen:

>[!NOTE]
>
>In sommige venstermilieu&#39;s kunnen de manuscripten PowerShell door beleid (vooral niet ondertekende manuscripten) worden beperkt. Als u uw script wilt uitvoeren, moet u deze beperking mogelijk tijdelijk uitschakelen en opnieuw inschakelen om het script uit te voeren. Open een venster PowerShell en gebruik deze bevelen.
>
>*onbeperkt beleid voor instellen* - om beperkingen tijdelijk te verwijderen
>
>*beperkt beleid voor instellen* - beperking weer inschakelen nadat het script is uitgevoerd

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### De afstandsbediening voor schermen gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Meer informatie over deze functie vindt u hier: [Schermen afstandsbediening](implementing-remote-control.md)