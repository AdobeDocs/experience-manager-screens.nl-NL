---
title: Windows 10 Player implementeren
seo-title: Windows 10 Player implementeren
description: Volg deze pagina voor meer informatie over het configureren van AEM Screens Windows 10 player.
seo-description: Volg deze pagina voor meer informatie over het configureren van AEM Screens Windows 10 player.
uuid: da7e88bf-c251-481e-9029-f8fc4768b309
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 4228e8a1-9749-49a6-a1bb-365492bc2a3d
docset: aem65
translation-type: tm+mt
source-git-commit: 9e7c4ec77265c1b6927a19e0d9d39770b64db0fb

---


# Windows 10 Player implementeren {#implementing-windows-player}

In deze sectie wordt beschreven hoe u AEM-schermen configureert voor de Windows 10-speler. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

## Windows Player installeren {#installing-windows-player}

Installeer Windows Player voor AEM-schermen om Windows Player voor AEM-schermen te implementeren.

Ga naar de pagina [**AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

### Ad hoc-methode {#ad-hoc-method}

Met de ad-hocmethode kunt u de nieuwste Windows Player (*.exe*) installeren. Bezoek de pagina [**AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeer naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de instantie AEM in u wenst om te verbinden met en klik **sparen**.
1. Navigeer vanuit het menu Actie links naar de koppeling **Apparaatregistratie** **registreren** om de status van het registratieproces van het apparaat te controleren.

>[!NOTE]
>
>Als de **status** is **GEREGISTREERD**, wordt het veld **Apparaat-id** ingevuld.
>
>Als de **staat** **NIET-GEREGISTREERD** is, kunt u het apparaat registreren met het **token** .

### Configuratie van bulkserver: Meerdere Windows 10-spelers registreren met één configuratie {#bulk-server-configuration-registering-multiple-windows-players-with-one-configuration}

Nadat u de Windows-speler hebt geïnstalleerd, kunt u meerdere spelers registreren met één configuratie.

>[!NOTE]
>
>**Bulkregistratie van Windows Player**
>
>Wanneer u de venstersspeler implementeert, hoeft u niet elke speler handmatig te configureren. In plaats daarvan kunt u het JSON-configuratiebestand bijwerken nadat het is getest en klaar is voor implementatie.
>
>De configuratie zal ervoor zorgen dat alle spelers de zelfde server pingelen die in het configuratiedossier wordt verstrekt. U moet elke speler nog steeds handmatig registreren.

Voer de onderstaande stappen uit om Windows 10 Player te configureren:

1. Installeer Windows Player.
1. Zoek het configuratiebestand onder ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Werk de configuratie-JSON bij met behulp van de onderstaande informatie en kopieer vervolgens dezelfde map naar alle systemen waar de speler zich bevindt.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:

| **Beleidsnaam** | **Doel** |
|---|---|
| server | De URL naar de AEM-server (Adobe Experience Manager). |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |

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
>Adobe raadt een oplossing voor apparaatbeheer aan om Kiosk voor Windows in te schakelen. Voer de onderstaande stappen uit als u geen oplossing voor apparaatbeheer hebt om de modus Kiosk in te schakelen. Deze methode gebruikt de eigenschap van de Lanceerinrichting van Shell beschikbaar in Vensters 10 onderneming en uitgeeft. Andere door Microsoft aanbevolen methoden voor toepassingen die geen UWP zijn, kunnen ook worden toegepast om Kiosk in te schakelen, met name in andere versies van Windows.

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

>[!NOTE]
>
>Voordat u de onderstaande stappen uitvoert, moet u ervoor zorgen dat u Windows 10 Enterprise of Education gebruikt.

1. Enable Shell Launcher.

   Verwijs naar sectie ***vormt de Lanceerinrichting*** van Shell in de pagina van de Lanceerinrichting **[van](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/shell-launcher)**Shell door de steun van Microsoft Windows voor extra informatie.

1. Maak een niet-administratieve gebruiker (als u er al een hebt) die u voor Kiosk wilt gebruiken. Dit kan een lokale of domeingebruiker zijn.
1. Installeer de Windows-speler voor die Kiosk-gebruiker vanaf de pagina Downloads [van](https://download.macromedia.com/screens/) AEM Screens Player.
1. Verwijs naar de Lanceerinrichting van Shell van het [Gebruik om Vensters 10 kiosk](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shelllauncher) tot stand te brengen om uw manuscript PowerShell voor meer informatie te wijzigen.

   Wijzig het manuscript PowerShell om de gebruikersbenaming met te vervangen u creeerde. Controleer of het pad naar het uitvoerbare bestand van de toepassing juist is. Hierdoor wordt de aangepaste shell ingesteld als de toepassing voor de venstersspeler voor de gebruiker kiosk en wordt de standaardwaarde als explorer.exe voor andere gebruikers ingesteld.

1. Stel het manuscript PowerShell in werking als beheerder.
1. Start opnieuw op en meld u opnieuw aan als de Kiosk-gebruiker en de spelertoepassing meteen moeten starten.

### Problemen oplossen {#troubleshooting}

Als u een zwart scherm krijgt wanneer u zich aanmeldt als gebruiker van Kiosk, betekent dit dat u mogelijk het pad naar het uitvoerbare bestand van de vensterspeler onjuist hebt opgegeven. Meld u weer aan als beheerder en controleer het script en voer het opnieuw uit.

Het standaardinstallatiepad voor Windows Player is:

***C:\Users\&amp;lt;your user>\AppData\Local\Programs\@aem-screensscreens-player-electron\AEM Screens Player.exe***

Met het voorbeeldscript in de koppelingen wordt de aangepaste shell in- en uitgeschakeld. Daarom moet u het script mogelijk in tweeën splitsen en de onderstaande toepasselijke regels in- en uitschakelen:

>[!NOTE]
>
>In sommige venstermilieu&#39;s kunnen de manuscripten PowerShell door beleid (vooral niet ondertekende manuscripten) worden beperkt. Als u uw script wilt uitvoeren, moet u deze beperking mogelijk tijdelijk uitschakelen en opnieuw inschakelen om het script uit te voeren. Open een venster PowerShell en gebruik deze bevelen.
>
>*onbeperkt* beleid instellen - beperkingen tijdelijk verwijderen
>
>*set-execute-policy beperkt* - om beperking opnieuw in te schakelen nadat het script is uitgevoerd

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

