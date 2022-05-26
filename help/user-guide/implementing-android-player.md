---
title: Android-speler implementeren
seo-title: Implementation of Android Player
description: Volg deze pagina om de implementatie van Android Watchdog te leren, een oplossing om de speler te herstellen van vastlopen.
seo-description: Follow this page to learn implementation of Android Watchdog, a solution to recover the player from crashes.
uuid: 17edd093-f1b1-479e-9f25-28c64f1a7223
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 77fe9d4e-e1bb-42f7-b563-dc03e3af8a60
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: 8d4a7b2bc436d822c673a00437ee895c8ef5cb6f
workflow-type: tm+mt
source-wordcount: '1529'
ht-degree: 0%

---

# Android-speler implementeren {#implementing-android-player}

In deze sectie wordt beschreven hoe u de Android-speler configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

Daarnaast **Watchdog** is een oplossing om de speler te herstellen van vastlopen. Een toepassing moet zich bij de waakhond dienst registreren en dan periodiek berichten naar de dienst verzenden die het levend is. Als de waakhonddienst niet binnen een bepaalde tijd een bewaarde bericht ontvangt, probeert de dienst om het apparaat voor een schoon terugwinning (als het de voldoende voorrechten heeft) opnieuw op te starten of de toepassing opnieuw te beginnen.

## Android Player installeren {#installing-android-player}

Installeer Android Player voor AEM Screens om Android Player voor AEM Screens te implementeren.

Ga naar [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

### De Milieu van de vestiging voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>U moet een omgeving instellen voor Android Player als u AEM Screens 6.5.5 Service Pack gebruikt.

Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen** van **Configuratie Adobe Experience Manager-webconsole** op alle AEM auteur- en publicatieinstanties.

Voer de onderstaande stappen uit:

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** gebruiken `http://localhost:4502/system/console/configMgr`.

1. Zoeken naar *Adobe Granite Token Authentication Handler*.

1. Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klikken **Opslaan**.


### Ad hoc-methode {#ad-hoc-method}

Met de ad-hocmethode kunt u de nieuwste Android-speler installeren (*.exe*). Bezoek [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeren naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de AEM instantie in u wenst om met te verbinden en te klikken **Opslaan**.

1. Ga naar de **Apparaat** **Registratie** van het linkeractiemenu om de status van het proces van de apparatenregistratie te controleren.

>[!NOTE]
>
>Als de **Staat** is **GEREGISTREERD**, merkt u de **Apparaat-id** wordt ingevuld.
>
>Als de **Staat** is **ONGEREGISTREERD** kunt u de **Token** om het apparaat te registreren.

## Android Watchdog implementeren {#implementing-android-watchdog}

Vanwege de architectuur van Android vereist het opnieuw opstarten van het apparaat dat de toepassing systeemrechten heeft. Hiervoor moet u de apk ondertekenen met de ondertekeningssleutels van de fabrikant. Als dit niet het geval is, wordt de speler opnieuw gestart door de controlehond en wordt het apparaat niet opnieuw opgestart.

### Handtekening van Android-apks met behulp van fabriekssleutels {#signage-of-android-apks-using-manufacturer-keys}

Sommige geprivilegieerde API&#39;s van Android openen, zoals *PowerManager* of *HDMIControlServices*, moet u de android-apk ondertekenen met de toetsen van de fabrikant.

>[!CAUTION]
>
>Voorwaarden:
>
>U zou Android SDK moeten hebben geïnstalleerd, alvorens u de volgende stappen uitvoert.

Volg de onderstaande stappen om de android-apk te ondertekenen met de toetsen van de fabrikant:

1. Download de app van Google Play of van [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/) page
1. Vraag de platformtoetsen aan bij de fabrikant voor een *pk8* en *peperen* file

1. Zoek het hulpprogramma voor ondertekenaars in android-SDK met Zoeken ~/Library/Android/sdk/build-tools -name &quot;apksigner&quot;
1. &lt;pathto> /apksigner sign —key platform.pk8 —cert platform.x509.pem aemscreensplayer.apk
1. Het pad naar het gereedschap ZIP-uitlijning zoeken in android sdk
1. &lt;pathto> /zipalign-fv 4 aemscreensplayer.apk aemscreensalign.apk
1. Installeren ***aemscreensalign.apk*** adb-installatie gebruiken op het apparaat

## Android Watchdog Services {#android-watchdog-services}

De cross-Android-waakhond-service wordt geïmplementeerd als een cordova-plug-in met *AlarmManager*.

In het volgende diagram wordt de implementatie van waakhond-service getoond:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisatie** Op het moment van initialisatie van de cordova-insteekmodule worden de machtigingen gecontroleerd om te controleren of we over systeemrechten beschikken en dus of we de machtiging Opnieuw opstarten gebruiken. Als aan deze twee criteria wordt voldaan, wordt een hangende Intent voor Reboot gecreeerd, anders wordt een hangende Intent om de toepassing (die op zijn Activiteit van de Lancering wordt gebaseerd) opnieuw te beginnen gecreeerd.

**2. Alive Timer behouden** Een keep live timer wordt gebruikt om een gebeurtenis om de 15 seconden te activeren. In dat geval moet u de bestaande in behandeling zijnde intent annuleren (om de app opnieuw op te starten of te starten) en een nieuwe in behandeling zijnde intent in de toekomst voor dezelfde 60 seconden registreren (in feite om het opnieuw opstarten uit te stellen).

>[!NOTE]
>
>In Android worden de *AlarmManager* wordt gebruikt om de *pendingIntents* die kan worden uitgevoerd, zelfs als de app is vastgelopen en de alarmlevering niet exact is vastgelegd in API 19 (Kitkat). Behoud wat ruimte tussen het interval van de tijdopnemer en *AlarmManager&#39;s* *pendingIntent* alarm.

**3. Toepassing vastloopt** Als de toepassing vastloopt, wordt de in AlarmManager geregistreerde pendingIntent for Reboot niet meer opnieuw ingesteld en wordt de app opnieuw opgestart of opnieuw opgestart (afhankelijk van de machtigingen die beschikbaar zijn op het moment van initialisatie van de cordova-plug-in).

## Bulkprovisioning van Android Player {#bulk-provision-android-player}

Wanneer u de Android-speler bulksgewijs implementeert, moet u de speler de mogelijkheid bieden naar een AEM instantie te verwijzen en andere eigenschappen te configureren zonder deze handmatig in te voeren in de interface van Admin.

>[!NOTE]
>Deze functie is beschikbaar in Android Player 42.0.372.

Voer de onderstaande stappen uit om bulkprovisioning in de Android-speler toe te staan:

1. Een JSON-configuratiebestand met de naam maken `player-config.default.json`.
Zie een [Voorbeeld JSON-beleid](#example-json) alsmede een tabel waarin het gebruik van de verschillende [Beleidskenmerken](#policy-attributes).

1. Gebruik een MDM- of ADB- of Android Studio-bestandsverkenner om dit beleid-JSON-bestand naar de *sdcard* op het Android-apparaat.

1. Zodra het dossier wordt opgesteld, gebruik MDM om de spelertoepassing te installeren.

1. Wanneer de spelertoepassing begint, zal het dit configuratiedossier lezen en aan de toepasselijke AEM server richten waar het kan worden geregistreerd en later worden gecontroleerd.

   >[!NOTE]
   >Dit bestand is *alleen-lezen* de eerste keer dat de toepassing wordt gestart en niet kan worden gebruikt voor volgende configuraties. Als de speler wordt gestart voordat het configuratiebestand wordt neergezet, verwijdert u de toepassing gewoon en installeert u deze opnieuw op het apparaat.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:

| **Beleidsnaam** | **Doel** |
|---|---|
| *server* | De URL naar de Adobe Experience Manager-server. |
| *resolutie* | De resolutie van het apparaat. |
| *rebootSchedule* | Het programma voor opnieuw opstarten is van toepassing op alle platforms. |
| *enableAdminUI* | Schakel de interface van Admin in om het apparaat op de site te configureren. Instellen op *false* zodra het volledig is geconfigureerd en in productie is. |
| *enableOSD* | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Stel de instelling in op *false* zodra het volledig is geconfigureerd en in productie is. |
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
>Alle Android-apparaten hebben een *sdcard* map of een werkelijke map *sdcard* wordt ingevoegd of niet. Wanneer dit bestand wordt geïmplementeerd, bevindt het zich op hetzelfde niveau als de map Downloads. Sommige MDM&#39;s, zoals Samsung Knox, verwijzen mogelijk naar deze *sdcard* maplocatie als *Interne opslag*.

## Bulkprovisioning van Android Player via Enterprise Mobility Management {#bulk-provisioning}

Wanneer u de Android-speler bulksgewijs implementeert, wordt het vervelend om elke speler handmatig te registreren bij AEM. Het wordt ten zeerste aanbevolen om een EMM-oplossing (Enterprise Mobility Management), zoals VMWare Airwatch, MobileIron of Samsung Knox, te gebruiken om uw implementatie op afstand te voorzien en te beheren. AEM Screens Android-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

## Android-speler hernoemen {#name-android}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Android-speler toewijzen en daarbij de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen uw Android-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Player is geregistreerd, kan de Player-naam niet meer worden gewijzigd.

Voer de onderstaande stappen uit om de naam te configureren in Android-speler:

1. Navigeren naar **instellingen** —> **Apparaat**
1. De naam van uw apparaat bewerken en instellen als naam voor uw Android-speler

### Bulkprovisioning van Android Player implementeren met gebruik van Enterprise Mobility Management {#implementation}

Voer de onderstaande stappen uit om bulkprovisioning in Android Player toe te staan:

1. Zorg ervoor dat uw Android-apparaat Google Play-services ondersteunt.
1. U kunt uw Android-spelerapparaten inschrijven met uw favoriete EMM-oplossing die AppConfig ondersteunt.
1. Meld u aan bij uw EMM-console en haalt de AEM Screens Player-toepassing uit Google Play.
1. Selecteer beheerde configuratie of verwante optie.
1. Er wordt nu een lijst weergegeven met speleropties die kunnen worden geconfigureerd, zoals server- en bulkregistratiecode.
1. Vorm deze parameters, sparen, en stel het beleid aan de apparaten op.

   >[!NOTE]
   >De apparaten zouden de toepassing samen met de configuratie en punt aan de correcte AEM server met de geselecteerde configuratie moeten ontvangen. Als u ervoor hebt gekozen de bulkregistratiecode te configureren en deze op dezelfde wijze te handhaven als in AEM is geconfigureerd, moet de speler zichzelf automatisch kunnen registreren. Als u een standaardweergave had geconfigureerd, kan deze ook standaardinhoud downloaden en weergeven (die later naar wens kan worden gewijzigd).

Bovendien dient u contact op te nemen met uw EMM-leverancier op AppConfig-ondersteuning. Meest populaire zoals [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobiel ijzer](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) en [Samsung Knox](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) deze industriestandaard wordt onder meer ondersteund .

### De afstandsbediening voor schermen gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Meer informatie over deze functie vindt u hier: [Schermen afstandsbediening](implementing-remote-control.md)
