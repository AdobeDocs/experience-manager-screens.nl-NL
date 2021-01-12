---
title: Android-speler implementeren
seo-title: Implementatie van Android Player
description: Volg deze pagina om de implementatie van Android Watchdog te leren, een oplossing om de speler te herstellen van vastlopen.
seo-description: Volg deze pagina om de implementatie van Android Watchdog te leren, een oplossing om de speler te herstellen van vastlopen.
uuid: 17edd093-f1b1-479e-9f25-28c64f1a7223
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 77fe9d4e-e1bb-42f7-b563-dc03e3af8a60
docset: aem65
translation-type: tm+mt
source-git-commit: 2b72d9a83735beb327f519a66e8b3c0e8bf04409
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 0%

---


# Android-speler {#implementing-android-player} implementeren

In deze sectie wordt beschreven hoe u de Android-speler configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

Daarnaast is **Watchdog** een oplossing om de speler te herstellen van vastlopen. Een toepassing moet zich bij de waakhond dienst registreren en dan periodiek berichten naar de dienst verzenden die het levend is. Als de waakhonddienst niet binnen een bepaalde tijd een bewaarde bericht ontvangt, probeert de dienst om het apparaat voor een schoon terugwinning (als het de voldoende voorrechten heeft) opnieuw op te starten of de toepassing opnieuw te beginnen.

## Android-speler {#installing-android-player} installeren

Installeer Android Player voor AEM Screens om Android Player voor AEM Screens te implementeren.

Bezoek de pagina [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/).

### Environment instellen voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>U moet een omgeving instellen voor Android Player als u AEM Screens 6.5.5 Service Pack gebruikt.

Stel het **SameSite-kenmerk voor de aanmeldings-token cookies** in van **Lax** naar **None** van **Adobe Experience Manager Web Console Configuration** op alle AEM auteur- en publicatieinstanties.

Voer de onderstaande stappen uit:

1. Navigeer naar **Adobe Experience Manager Web Console Configuration** met `http://localhost:4502/system/console/configMgr`.

1. Zoek naar *Adobe Granite Token Authentication Handler*.

1. Stel het **SameSite-kenmerk voor de cookies met inlognaam** in van **Lax** naar **None**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klik **Opslaan**.


### Ad hoc methode {#ad-hoc-method}

Met de ad-hocmethode kunt u de nieuwste Android-speler (*.exe*) installeren. Bezoek [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeer naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de AEM instantie in u wenst om met te verbinden en **sparen** te klikken.

1. Navigeer naar de **Device** **Registratie**-koppeling in het linkeractiemenu om de status van het registratieproces van het apparaat te controleren.

>[!NOTE]
>
>Als **State** **REGISTERED** is, zult u merken dat het **Device id** veld wordt gevuld.
>
>Als **State** **UNREGISTERED** is, kunt u **Token** gebruiken om het apparaat te registreren.

## Android Watchdog {#implementing-android-watchdog} implementeren

Vanwege de architectuur van Android vereist het opnieuw opstarten van het apparaat dat de toepassing systeemrechten heeft. Hiervoor moet u de apk ondertekenen met de ondertekeningssleutels van de fabrikant. Als dit niet het geval is, wordt de speler opnieuw gestart door de controlehond en wordt het apparaat niet opnieuw opgestart.

### Signering van Android-apparaten met behulp van fabriekssleutels {#signage-of-android-apks-using-manufacturer-keys}

Als u toegang wilt tot enkele geprivilegieerde API&#39;s van Android, zoals *PowerManager* of *HDMIControlServices*, moet u de android-app ondertekenen met de toetsen van de fabrikant.

>[!CAUTION]
>
>Voorwaarden:
>
>U zou Android SDK moeten hebben geïnstalleerd, alvorens u de volgende stappen uitvoert.

Volg de onderstaande stappen om de android-apk te ondertekenen met de toetsen van de fabrikant:

1. Download de app van Google Play of van de pagina [AEM Screens Player Downloads](https://download.macromedia.com/screens/)
1. Vraag de platformtoetsen van de fabrikant aan om een *pk8*- en een *pem*-bestand te verkrijgen

1. Zoek het hulpprogramma voor ondertekenaars in android-SDK met Zoeken ~/Library/Android/sdk/build-tools -name &quot;apksigner&quot;
1. &lt;pathto> /apksigner sign —key platform.pk8 —cert platform.x509.pem aemscreensplayer.apk
1. Het pad naar het gereedschap ZIP-uitlijning zoeken in android sdk
1. &lt;pathto> /zipalign-fv 4 aemscreensplayer.apk aemscreensalign.apk
1. ***aemscreensalign.apk*** installeren met adb-installatie op het apparaat

## Android Watchdog Services {#android-watchdog-services}

De cross-Android waakhond service wordt geïmplementeerd als een cordova-plug-in met *AlarmManager*.

In het volgende diagram wordt de implementatie van waakhond-service getoond:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisatie** Op het moment van initialisatie van de cordova-insteekmodule worden de machtigingen gecontroleerd om te zien of we over systeemrechten beschikken en dus over de machtiging Opnieuw opstarten. Als aan deze twee criteria wordt voldaan, wordt een hangende Intent voor Reboot gecreeerd, anders wordt een hangende Intent om de toepassing (die op zijn Activiteit van de Lancering wordt gebaseerd) opnieuw te beginnen gecreeerd.

**2. Levende Tijdopnemer** A houdt levend tijdopnemer wordt gebruikt om een gebeurtenis om de 15 seconden teweeg te brengen. In dat geval moet u de bestaande in behandeling zijnde intent annuleren (om de app opnieuw op te starten of te starten) en een nieuwe in behandeling zijnde intent in de toekomst voor dezelfde 60 seconden registreren (in feite om het opnieuw opstarten uit te stellen).

>[!NOTE]
>
>In Android wordt de *AlarmManager* gebruikt om de *pendingIntents* te registreren die ook kunnen worden uitgevoerd als de app is vastgelopen en de alarmlevering niet exact is via API 19 (Kitkat). Behoud wat ruimte tussen het interval van de tijdopnemer en *alarm* *pendingIntent* alarm.

**3. Toepassing crash** In het geval van een crash, wordt de pendingIntent voor Reboot geregistreerd met AlarmManager niet meer opnieuw ingesteld en wordt daarom een reboot of nieuw begin van app uitgevoerd (afhankelijk van toestemmingen beschikbaar op het tijdstip van initialisering van de cordova plugin).

## Bulkprovisioning van Android Player {#bulk-provision-android-player}

Wanneer u de Android-speler bulksgewijs implementeert, moet u de speler de mogelijkheid bieden naar een AEM instantie te verwijzen en andere eigenschappen te configureren zonder deze handmatig in te voeren in de interface van Admin.

>[!NOTE]
>Deze functie is beschikbaar in Android Player 42.0.372.

Voer de onderstaande stappen uit om bulkprovisioning in de Android-speler toe te staan:

1. Maak een configuratie-JSON-bestand met de naam `player-config.default.json`.
Verwijs naar [Voorbeeld JSON Beleid](#example-json) evenals een lijst die het gebruik van diverse [Beleidsattributen](#policy-attributes) beschrijft.

1. Gebruik een MDM of ADB of Android Studio dossierontdekkingsreiziger om dit beleidJSON dossier aan *sdcard* omslag op het Android apparaat te laten vallen.

1. Zodra het dossier wordt opgesteld, gebruik MDM om de spelertoepassing te installeren.

1. Wanneer de spelertoepassing begint, zal het dit configuratiedossier lezen en aan de toepasselijke AEM server richten waar het kan worden geregistreerd en later worden gecontroleerd.

   >[!NOTE]
   >Dit bestand is *alleen-lezen* de eerste keer dat de toepassing wordt gestart en kan niet worden gebruikt voor volgende configuraties. Als de speler wordt gestart voordat het configuratiebestand wordt neergezet, verwijdert u de toepassing gewoon en installeert u deze opnieuw op het apparaat.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:

| **Beleidsnaam** | **Doel** |
|---|---|
| *server* | De URL naar de Adobe Experience Manager-server. |
| *resolutie* | De resolutie van het apparaat. |
| *rebootSchedule* | Het programma voor opnieuw opstarten is van toepassing op alle platforms. |
| *enableAdminUI* | Schakel de interface van Admin in om het apparaat op de site te configureren. Stel in op *false* als deze volledig is geconfigureerd en in productie is. |
| *enableOSD* | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Overweeg het plaatsen aan *false* zodra het volledig en in productie wordt gevormd. |
| *enableActivityUI* | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| *enableNativeVideo* | Inschakelen om native hardwareversnelling te gebruiken voor het afspelen van video (alleen Android). |

### Voorbeeld JSON-beleid {#example-json}

```java
{
  "server": "https://author-screensdemo.adobecqms.net",
"device": "",
"user": "",
"password": "",
"resolution": "auto",
"rebootSchedule": "at 4:00 am",
"maxNumberOfLogFilesToKeep": 10,
"logLevel": 3,
"enableAdminUI": true,
"enableOSD": true,
"enableActivityUI": false,
"enableNativeVideo": false,
"enableAutoScreenshot": false,
"cloudMode": false,
"cloudUrl": "https://screens.adobeioruntime.net",
"cloudToken": "",
"enableDeveloperMode": true
}
```

>[!NOTE]
>Alle Android-apparaten hebben een *sdcard*-map, ongeacht of een werkelijke *sdcard* is ingevoegd of niet. Wanneer dit bestand wordt geïmplementeerd, bevindt het zich op hetzelfde niveau als de map Downloads. Sommige MDM&#39;s zoals Samsung Knox verwijzen mogelijk naar deze *sdcard* maplocatie als *Interne opslag*.