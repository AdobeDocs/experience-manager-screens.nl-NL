---
title: Android&trade implementeren; Player
description: Leer meer over de implementatie van Android&trade; Watchdog, een oplossing waarmee u de Android&trade kunt herstellen; speler tegen vastlopen.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1462'
ht-degree: 0%

---

# Android™-speler implementeren {#implementing-android-player}

In deze sectie wordt beschreven hoe u de Android™-speler configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

Ook, **Watchdog** is een oplossing om de speler te herstellen van vastlopen. Een toepassing moet zich bij de waakhond dienst registreren en dan periodiek berichten naar de dienst verzenden dat het leeft. Als de waakhonddienst niet binnen een bepaalde tijd een bewaarde bericht ontvangt, probeert de dienst om het apparaat voor een schoon terugwinning (als het de voldoende voorrechten heeft) opnieuw op te starten of de toepassing opnieuw te beginnen.

## Android™ Player installeren {#installing-android-player}

Installeer Android™ Player voor AEM Screens om Android™ Player voor AEM Screens te implementeren.

Ga naar [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

### De Milieu van de vestiging voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Stel een omgeving in voor Android™ Player als u AEM Screens 6.5.5 Service Pack gebruikt.

Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen** van **Configuratie Adobe Experience Manager-webconsole** op alle AEM auteur- en publicatieinstanties.

Voer de onderstaande stappen uit:

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** gebruiken `http://localhost:4502/system/console/configMgr`.

1. Zoeken naar *Adobe Granite Token Authentication Handler*.

1. Stel de **SameSite-kenmerk voor de cookies met het token** van **Lax** tot **Geen**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klikken **Opslaan**.


### Ad hoc-methode {#ad-hoc-method}

Met de ad-hocmethode kunt u de nieuwste Android™-speler installeren (*.exe*). Bezoek [**AEM 6.5 Player-downloads**](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeren naar **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de AEM instantie in u wenst om met te verbinden en te klikken **Opslaan**.

1. Ga naar de **Apparaat** **Registratie** van het linkeractiemenu zodat kunt u de status van het proces van de apparatenregistratie controleren.

>[!NOTE]
>
>Als de **Staat** is **GEREGISTREERD**, kunt u zien dat de **Apparaat-id** veld is gevuld.
>
>Als de **Staat** is **ONGEREGISTREERD**, kunt u de **Token** om het apparaat te registreren.

## Android™-waakhond implementeren {#implementing-android-watchdog}

Vanwege de architectuur van Android™ vereist het opnieuw opstarten van het apparaat dat de toepassing systeemrechten heeft. Om dit te doen, ondertekent u de apk met de ondertekeningssleutels van de fabrikant. Als dat niet het geval is, start waakhond de spelertoepassing opnieuw en wordt het apparaat niet opnieuw opgestart.

### Handtekening van Android™ `apks` met productiesleutels {#signage-of-android-apks-using-manufacturer-keys}

Sommige geprivilegieerde API&#39;s van Android™ openen, zoals *PowerManager* of *HDMIControlServices*, ondertekent u Android™ `apk` met de sleutels van de fabrikant.

>[!CAUTION]
>
>Voorwaarden:
>
>De SDK van Android™ moet geïnstalleerd zijn voordat u de volgende stappen uitvoert.

Volg de onderstaande stappen om de Android™-apk te ondertekenen met de toetsen van de fabrikant:

1. Download de apk van Google Play of van [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/) page
1. Vraag de platformtoetsen aan bij de fabrikant zodat u een *pk8* en *peperen* file

1. Zoek de `apksigner` -gereedschap in de Android™-SDK met behulp van zoeken `~/Library/Android/sdk/build-tools -name "apksigner"`
1. `<pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk`
1. Het pad naar het gereedschap ZIP-uitlijning zoeken in de Android™-SDK
1. `<pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk`
1. Installeren ***aemscreensalign.apk*** adb-installatie gebruiken op het apparaat

## Android™ Watchdog Services {#android-watchdog-services}

De cross-Android-waakhond-service wordt geïmplementeerd als een Cordova-plug-in met *AlarmManager*.

In het volgende diagram wordt de implementatie van waakhond-service getoond:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialisatie** - Op het moment van initialisatie van de Cordova-plug-in worden de machtigingen gecontroleerd om te controleren of u systeemrechten hebt en dus of u de machtiging Opnieuw opstarten hebt. Als aan deze twee criteria wordt voldaan, wordt een hangende Intent voor Reboot gecreeerd, anders wordt een hangende Intent om de toepassing (die op zijn Activiteit van de Lancering wordt gebaseerd) opnieuw te beginnen gecreeerd.

**2. Alive Timer behouden** - De timer &#39;keep live&#39; wordt gebruikt om een gebeurtenis om de 15 seconden te activeren. In dat geval annuleert u de bestaande in behandeling zijnde intent (om de app opnieuw op te starten of te starten) en registreert u in de toekomst een nieuwe in behandeling zijnde intent gedurende dezelfde 60 seconden (in feite om het opnieuw opstarten uit te stellen).

>[!NOTE]
>
>In Android™ *AlarmManager* wordt gebruikt om de *pendingIntents* die kan worden uitgevoerd, zelfs als de app is vastgelopen en de alarmlevering niet exact is vastgelegd in API 19 (Kitkat). Tussenruimte tussen het interval van de timer en het *AlarmManager&#39;s* *pendingIntent* alarm.

**3. Toepassing vastloopt** - Als er een crash optreedt, wordt de in AlarmManager geregistreerde pendingIntent voor Reboot niet meer opnieuw ingesteld. Daarom wordt de toepassing opnieuw opgestart of opnieuw opgestart (afhankelijk van de machtigingen die beschikbaar zijn op het moment dat de Cordova-plug-in wordt geïnitialiseerd).

## Bulkprovisioning van Android™ Player {#bulk-provision-android-player}

Wanneer u de Android™-speler bulksgewijs implementeert, moet u de speler de mogelijkheid bieden naar een AEM instantie te verwijzen en andere eigenschappen te configureren zonder deze handmatig in te voeren in de interface van Admin.

>[!NOTE]
>Deze functie is beschikbaar in Android™ Player 42.0.372.

Voer de onderstaande stappen uit om bulkprovisioning in de Android™-speler toe te staan:

1. Een JSON-configuratiebestand met de naam maken `player-config.default.json`.
Zie een [Voorbeeld JSON-beleid](#example-json) en een tabel waarin de verschillende [Beleidskenmerken](#policy-attributes).

1. Gebruik een MDM- of ADB- of Android™ Studio-bestandsverkenner om dit beleid-JSON-bestand naar de *sdcard* op het Android™-apparaat.

1. Wanneer het dossier wordt opgesteld, gebruik MDM om de spelertoepassing te installeren.

1. Wanneer de spelertoepassing begint, wordt dit configuratiedossier gelezen en richt aan de toepasselijke AEM server waar het wordt geregistreerd en dan gecontroleerd.

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
| *enableActivityUI* | Schakel deze optie in als u de voortgang wilt weergeven van activiteiten zoals downloaden en synchroniseren. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| *enableNativeVideo* | Schakel deze optie in als u native hardwareversnelling wilt gebruiken voor het afspelen van video (alleen Android™). |

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
>Alle Android™-apparaten hebben een `*sdcard*` map of een werkelijke map is `*sdcard*` wordt ingevoegd of niet. Dit bestand wordt tijdens de implementatie op hetzelfde niveau geplaatst als de map Downloads. Sommige MDM&#39;s, zoals Samsung Knox, kunnen dit zien *sdcard* maplocatie als *Interne opslag*.

## Bulkprovisioning van Android™ Player via Enterprise Mobility Management {#bulk-provisioning}

Wanneer u de Android™-speler bulksgewijs inzet, wordt het vervelend om elke speler handmatig te registreren bij AEM. Het wordt ten zeerste aanbevolen een EMM-oplossing (Enterprise Mobility Management) te gebruiken, zoals [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), MobileIron of Samsung Knox om uw implementatie op afstand te verzorgen en te beheren. AEM Screens Android™-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

## Android™-speler hernoemen {#name-android}

U kunt een gebruikersvriendelijke apparaatnaam toewijzen aan uw Android™-speler en zo de toegewezen apparaatnaam naar AEM (Adobe Experience Manager) verzenden. Met deze functie kunt u niet alleen uw Android™-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam in de Android™-speler te configureren:

1. Navigeren naar **instellingen** > **Apparaat**
1. De naam van uw apparaat bewerken en instellen als naam voor uw Android™-speler

### Bulkprovisioning van Android™ Player implementeren met behulp van Enterprise Mobility Management {#implementation}

Voer de onderstaande stappen uit om bulkprovisioning in Android™ Player toe te staan:

1. Zorg ervoor dat uw Android™-apparaat Google Play-services ondersteunt.
1. U kunt uw Android™-spelerapparaten inschrijven met uw favoriete EMM-oplossing die AppConfig ondersteunt.
1. Meld u aan bij uw EMM-console en haalt de AEM Screens Player-toepassing uit Google Play.
1. Klik beheerde configuratie of verwante optie.
1. Er wordt nu een lijst weergegeven met speleropties die kunnen worden geconfigureerd, zoals server- en bulkregistratiecode.
1. Vorm deze parameters, sparen, en stel het beleid aan de apparaten op.

   >[!NOTE]
   >De apparaten zouden de toepassing samen met de configuratie en punt aan de correcte AEM server met de geselecteerde configuratie moeten ontvangen. Als u ervoor hebt gekozen de bulkregistratiecode te configureren en deze op dezelfde wijze te handhaven als in AEM is geconfigureerd, moet de speler zichzelf automatisch kunnen registreren. Als u een standaardweergave hebt geconfigureerd, kan deze ook standaardinhoud downloaden en weergeven (die later naar wens kan worden gewijzigd).

Raadpleeg ook uw leverancier van EMM op AppConfig-ondersteuning. Meest populaire zoals [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [`Mobile Iron`](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [`SOTI`](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [`BlackBerry&reg; UEM`](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [`IBM&reg; Maas360`](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm), en [`Samsung Knox`](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) deze industriestandaard wordt onder meer ondersteund .

### De afstandsbediening voor schermen gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Meer informatie over deze functie vindt u hier: [Schermen afstandsbediening](implementing-remote-control.md)
