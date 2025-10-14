---
title: Windows Player implementeren
description: Meer informatie over het configureren van Windows Player in AEM Screens.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 0%

---

# Windows Player implementeren {#implementing-windows-player}

In deze sectie wordt beschreven hoe u de Windows Player in AEM Screens configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

## Windows Player installeren {#installing-windows-player}

Installeer Windows Player voor AEM Screens om Windows Player voor AEM Screens te implementeren.

Bezoek [**AEM 6.5 de Downloads van de Speler** &#x200B;](https://download.macromedia.com/screens/) pagina.

>[!NOTE]
>Windows Player bevat geen venstermodus. De modus is altijd volledig scherm.

### De Milieu van de vestiging voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Stel een omgeving in voor Windows Player als u AEM Screens 6.5.5 Service Pack gebruikt.

Plaats het **attribuut SameSite voor de login-symbolische koekjes** van **Lax** aan **niets** van **Console van het Web van Adobe Experience Manager
Configuratie** op alle auteur en publiceer instanties van AEM.

Voer de onderstaande stappen uit:

1. Navigeer naar **Adobe Experience Manager Web Console
Configuratie** met `http://localhost:4502/system/console/configMgr` .

1. Onderzoek naar *Adobe Granite Token de Handler van de Authentificatie*.

1. Plaats het **attribuut SameSite voor de login-symbolische koekjes** van **Lax** aan **niets**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klik **sparen**.

### Ad hoc-methode {#ad-hoc-method}

De ad hoc methode laat u de recentste Speler van Vensters installeren (*.exe*). Bezoek [**AEM 6.5 de Downloads van de Speler** &#x200B;](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeer aan **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de instantie van AEM in u met wilt verbinden en **klikken sparen**.
1. Navigeer aan het **Apparaat** **verbinding van de Registratie** van het linkeractiemenu zodat kunt u de status van het proces van de apparatenregistratie controleren.

>[!NOTE]
>
>Als de **Staat** **GEREGISTREERD** is, merk op dat het **identiteitskaart van het Apparaat** gebied bevolkt is.
>
>Als de **Staat** **ONGEREGISTREERD** is, kunt u het **Symbolische** gebruiken om het apparaat te registreren.

## Namen van Windows Player {#name-windows}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Windows Player toewijzen en zo de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen uw Windows Player een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam in Windows Player te configureren:

1. Klik **begin** > **looppas**.
1. Voer `system.cpl` in.
1. Gebruik het tabblad Naam van de computer om de hostnaam van de computer in te stellen.

## De standaardopties wijzigen in Windows Installer {#changing-default-options}

Volg deze sectie zodat kunt u leren hoe te om de standaardopties in de Installateur van Vensters en de lijst van beschikbare aanpassingen te veranderen.

## Installatie met CLI (PowerShell) {#install-powershell}

1. Creeer een douaneplaats **gewijd** voor de Speler van Screens, bijvoorbeeld:
   `C:\Users\User\screens-player`
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

Wanneer het uitvoeren van de Speler van Vensters, te hoeven u niet manueel om elke speler te vormen. In plaats daarvan kunt u het JSON-configuratiebestand bijwerken nadat het is getest en klaar is voor implementatie.

De configuratie zorgt ervoor dat alle spelers de zelfde server pingelen die in het configuratiedossier wordt verstrekt. Registreer elke speler handmatig.

Voer de onderstaande stappen uit om Windows 10 Player te configureren:

1. Windows Player installeren.
1. Zoek het configuratiebestand onder ***%appdata%\com.adobe.aem.screens.player\config.json*** .
1. Werk de configuratie-JSON bij met behulp van de onderstaande informatie en kopieer vervolgens dezelfde map naar alle systemen waar de speler zich bevindt.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:


| **Naam van het Beleid** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om naar een ander kanaal op het apparaat te gaan. Overweeg het plaatsen van het aan vals zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in zodat u de voortgang van activiteiten, zoals downloaden en synchroniseren, kunt weergeven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Windows Player verbinding maakt met Screens as a Cloud Service. Ingesteld op false om verbinding te maken met AMS of on-prem AEM. |
| cloudToken | Registertoken voor Screens as a Cloud Service. |

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

Wanneer u de Speler van Vensters opstelt, is het belangrijk om een wijze van Kiosk toe te laten zodat andere toepassingen of taskbar niet op de Desktop van Vensters verschijnen.

>[!CAUTION]
>
>Adobe raadt een oplossing voor apparaatbeheer aan om Kiosk voor Windows in te schakelen. Voer de onderstaande stappen uit als u geen oplossing voor apparaatbeheer hebt om de modus Kiosk in te schakelen. Deze methode gebruikt de eigenschap van de Lanceerinrichting van Shell beschikbaar in Vensters 10 Onderneming en uitgeeft. Andere door Microsoft aanbevolen methoden voor toepassingen die geen UWP zijn, kunnen ook worden toegepast om Kiosk in te schakelen, vooral in andere versies van Windows.

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

>[!NOTE]
>
>Voordat u de onderstaande stappen uitvoert, moet u ervoor zorgen dat u Windows 10 Enterprise of Education gebruikt.

1. Enable Shell Launcher.

   Zie ***de Lanceerinrichting van Shell*** in **[Lanceerinrichting van Shell &#x200B;](https://learn.microsoft.com/en-us/windows/configuration/shell-launcher/)** pagina door Microsoft® de steun van Vensters voor extra informatie vormen.

1. Maak een niet-administratieve gebruiker (als u er al een hebt) die u voor Kiosk wilt gebruiken. Het kan een lokale of domeingebruiker zijn.
1. Installeer de Speler van Vensters voor die gebruiker van Kiosk van de [&#x200B; downloadt van de Speler van AEM Screens &#x200B;](https://download.macromedia.com/screens/) pagina.
1. Zie [&#x200B; Lanceerinrichting van Shell van het Gebruik om Vensters 10 kiosk &#x200B;](https://learn.microsoft.com/en-us/windows/configuration/shell-launcher/?tabs=intune) tot stand te brengen om uw manuscript PowerShell voor meer informatie te wijzigen.

   Wijzig het manuscript PowerShell zodat kunt u de gebruikersbenaming met vervangen u creeerde. Zorg ervoor dat het pad naar het uitvoerbare bestand van de toepassing juist is. Dit plaatst douane shell als toepassing van de Speler van Vensters voor de gebruiker van kiosk en plaatst het gebrek als explorer.exe voor andere gebruikers.

1. Stel het manuscript PowerShell in werking als beheerder.
1. Start opnieuw op en meld u opnieuw aan als de Kiosk-gebruiker en de spelertoepassing meteen moeten starten.

### Problemen oplossen {#troubleshooting}

Als u een zwart scherm krijgt nadat u zich hebt aangemeld als gebruiker van Kiosk, betekent dit dat u mogelijk het pad naar het uitvoerbare bestand van Windows Player onjuist hebt opgegeven. Meld u weer aan als beheerder en controleer het script en voer het opnieuw uit.

Het standaardinstallatiepad voor Windows Player is:

***C:\Users\&lt;your user>\AppData\Local\Programs\@aem-screensscreens-player-electron \ AEM Screens Player.exe***

Met het voorbeeldscript in de koppelingen kunt u de aangepaste shell in- en uitschakelen. Splits het script daarom in twee regels en schakel de onderstaande regels in/uit:

>[!NOTE]
>
>Sommige milieu&#39;s van Vensters beperken manuscripten PowerShell door beleid, vooral als de manuscripten unsigned zijn. Als u uw script wilt uitvoeren, schakelt u deze beperking tijdelijk uit en schakelt u deze opnieuw in om het script uit te voeren. Open een venster PowerShell en gebruik deze bevelen.
>
>*`set-executionpolicy unrestricted`* - om beperkingen tijdelijk te verwijderen.
>
>*`set-executionpolicy restricted`* - om beperking weer in te schakelen nadat het script is uitgevoerd.

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### De afstandsbediening van Screens gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Leer meer over deze eigenschap hier: [&#x200B; de Verre Controle van Screens &#x200B;](implementing-remote-control.md)