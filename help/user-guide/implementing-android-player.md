---
title: Android&amp implementeren;trade; Player
description: Leer over de implementatie van Android&trade; Watchdog, een oplossing waarmee u de Android&amp kunt herstellen;trade; player van crashes.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 0%

---

# Android™ Player implementeren {#implementing-android-player}

>[!CAUTION]
>De in Android gebaseerde AEM Screens Player is officieel vervangen. Gebruikers wordt aangeraden te migreren naar een ander besturingssysteem dat door AEM Screens wordt ondersteund.

In deze sectie wordt beschreven hoe u de Android™-speler configureert. Het verstrekt informatie van het configuratiedossier en de beschikbare opties en aanbevelingen met betrekking tot welke montages voor ontwikkeling en het testen te gebruiken.

Ook, **Watchdog** is een oplossing om de speler van neerstortingen terug te krijgen. Een toepassing moet zich bij de waakhond dienst registreren en dan periodiek berichten naar de dienst verzenden dat het leeft. Als de waakhonddienst niet een bewaarde bericht binnen een bepaalde tijd ontvangt, probeert de dienst om het apparaat opnieuw op te starten. Dit gebeurt voor een schone terugwinning (als het de voldoende voorrechten heeft) of herstart de toepassing.

## Android™ Player installeren {#installing-android-player}

Installeer Android™ Player voor AEM Screens om Android™ Player voor AEM Screens te implementeren.

Bezoek [**AEM 6.5 de Downloads van de Speler** ](https://download.macromedia.com/screens/) pagina.

### De Milieu van de vestiging voor AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Stel een omgeving in voor de Android™-speler als u AEM Screens 6.5.5 Service Pack gebruikt.

Plaats het **attribuut SameSite voor de login-symbolische koekjes** van **Lax** aan **niets** van **de Configuratie van de Console van het Web van Adobe Experience Manager** op alle auteur van AEM en publiceer instanties.

Voer de onderstaande stappen uit:

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager** gebruikend `http://localhost:4502/system/console/configMgr`.

1. Onderzoek naar *Adobe Granite Token de Handler van de Authentificatie*.

1. Plaats het **attribuut SameSite voor de login-symbolische koekjes** van **Lax** aan **niets**.
   ![afbeelding](/help/user-guide/assets/granite-updates.png)

1. Klik **sparen**.


### Ad hoc-methode {#ad-hoc-method}

De ad hoc methode laat u de recentste Speler Android™ (*.exe*) installeren. Bezoek [**AEM 6.5 de Downloads van de Speler** ](https://download.macromedia.com/screens/) pagina.

Nadat u de toepassing hebt gedownload, voert u de stappen op de speler uit om de ad-hocinstallatie te voltooien:

1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
1. Navigeer aan **Configuratie** van het linkeractiemenu en ga de plaats (adres) van de instantie van AEM in u met wilt verbinden en **klikken sparen**.

1. Navigeer aan het **Apparaat** **verbinding van de Registratie** van het linkeractiemenu zodat kunt u de status van het proces van de apparatenregistratie controleren.

>[!NOTE]
>
>Als de **Staat** **GEREGISTREERD** is, kunt u zien dat het **identiteitskaart van het Apparaat** gebied bevolkt is.
>
>Als de **Staat** **ONGEREGISTREERD** is, kunt u het **Symbolische** gebruiken om het apparaat te registreren.

## Android™ Watchdog implementeren {#implementing-android-watchdog}

Vanwege de architectuur van Android™ vereist het opnieuw opstarten van het apparaat dat de toepassing systeemrechten heeft. Onderteken de apk met de ondertekeningssleutels van de fabrikant, anders kan de waakhond de spelertoepassing opnieuw starten en het apparaat niet opnieuw opstarten.

### Android™ ondertekenen `apks` met behulp van fabriekssleutels {#signage-of-android-apks-using-manufacturer-keys}

Om tot enkele bevoorrechte APIs van Android™, zoals *PowerManager* of *HDMIControlServices* toegang te hebben, teken Android™ `apk` gebruikend de sleutels van de fabrikant.

>[!CAUTION]
>
>Voorwaarden:
>
>U moet de Android™ SDK installeren voordat u de volgende stappen uitvoert.

Volg de onderstaande stappen om de Android™ apk te ondertekenen met de toetsen van de fabrikant:

1. Download apk van Google Play of van de [ downloadt van de Speler van AEM Screens ](https://download.macromedia.com/screens/) pagina
1. Verkrijg de platformsleutels van de fabrikant zodat kunt u a *pk8* en a *krijgen pem* dossier

1. Zoek het gereedschap `apksigner` in Android™ SDK met de zoekfunctie `~/Library/Android/sdk/build-tools -name "apksigner"`
1. `<pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk`
1. Het pad naar het gereedschap ZIP-uitlijning zoeken in de Android™ SDK
1. `<pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk`
1. Installeer ***aemscreensalign.apk*** gebruikend adb installeert aan het apparaat

## Android™ Watchdog Services {#android-watchdog-services}

De dwars-Android™ waakhond dienst wordt uitgevoerd als stop Cordova gebruikend *AlarmManager*.

Het volgende diagram toont de implementatie van de waakhonddienst:

![ chlimage_1-31 ](assets/chlimage_1-31.png)

**1. Initialisatie** - op het tijdstip van initialisatie van de insteekmodule Cordova, worden de toestemmingen gecontroleerd om te zien of hebt u systeemvoorrechten en zo Reboot toestemming. Als aan deze twee criteria wordt voldaan, wordt een hangende Intent voor Reboot gecreeerd, anders wordt een hangende Intent om de toepassing (die op zijn Activiteit van de Lancering wordt gebaseerd) opnieuw te beginnen gecreeerd.

**2. Levende Tijdopnemer van het Levensonderhoud** - een houdt levende tijdopnemer wordt gebruikt om een gebeurtenis om de 15 seconden teweeg te brengen. In dat geval annuleert u de bestaande in behandeling zijnde intent (om de app opnieuw op te starten of te starten) en registreert u in de toekomst een nieuwe in behandeling zijnde intent gedurende dezelfde 60 seconden (waarmee de reboot wordt uitgesteld).

>[!NOTE]
>
>In Android™, wordt *AlarmManager* gebruikt om *pendingIntents* te registreren die kan uitvoeren zelfs als app is vastgelopen en zijn alarmlevering is onnauwkeurig van API 19 (Kitkat). Behoud wat het uit elkaar plaatsen tussen het interval van de tijdopnemer en het ** alarm van AlarmManager in afwachting vanIntent *.*

**3. Toepassing loopt vast** - als er een crash is, wordt pendingIntent voor Reboot geregistreerd met AlarmManager niet meer teruggesteld. Daarom wordt de toepassing opnieuw opgestart of opnieuw opgestart (afhankelijk van de machtigingen die beschikbaar zijn op het moment dat de Cordova-plug-in wordt geïnitialiseerd).

## Bulkprovisioning van Android™ Player {#bulk-provision-android-player}

Wanneer u de Android™-speler bulksgewijs implementeert, moet u de speler de mogelijkheid bieden naar een AEM-instantie te verwijzen en andere eigenschappen te configureren zonder deze handmatig in te voeren in de beheerinterface.

>[!NOTE]
>Deze functie is beschikbaar in Android™ Player 42.0.372.

Volg de onderstaande stappen om bulkprovisioning in de Android™-speler toe te staan:

1. Maak een configuratie-JSON-bestand met de naam `player-config.default.json` .
Zie een [ Beleid JSON van het Voorbeeld ](#example-json) en een lijst die het gebruik van de diverse [ Attributen van het Beleid ](#policy-attributes) beschrijft.

1. Gebruik een MDM of ADB of Android™ Studio dossierontdekkingsreiziger om dit beleidJSON dossier aan de *sdcard* omslag op het Android™ apparaat te laten vallen.

1. Wanneer het dossier wordt opgesteld, gebruik MDM om de spelertoepassing te installeren.

1. Wanneer de spelertoepassing wordt gestart, wordt dit configuratiebestand gelezen en wordt het verwezen naar de AEM-server waarop het is geregistreerd en vervolgens wordt bestuurd.

   >[!NOTE]
   >Dit dossier is *leest slechts* de eerste keer dat de toepassing wordt gelanceerd en niet voor verdere configuraties kan worden gebruikt. Als de speler wordt gestart voordat het configuratiebestand wordt neergezet, verwijdert u de toepassing gewoon en installeert u deze opnieuw op het apparaat.

### Beleidskenmerken {#policy-attributes}

De volgende lijst vat de beleidsattributen met een voorbeeldbeleid JSON ter verwijzing samen:

| **Naam van het Beleid** | **Doel** |
|---|---|
| *server* | De URL naar de Adobe Experience Manager-server. |
| *resolutie* | De resolutie van het apparaat. |
| *rebootSchedule* | Het programma voor opnieuw opstarten is van toepassing op alle platforms. |
| *enableAdminUI* | Schakel de interface van Admin in om het apparaat op de site te configureren. Reeks aan *vals* zodra het volledig en in productie wordt gevormd. |
| *enableOSD* | Schakel de interface van de kanaalschakelaar voor gebruikers in om naar een ander kanaal op het apparaat te gaan. Overweeg het plaatsen van het aan *vals* nadat het volledig en in productie wordt gevormd. |
| *enableActivityUI* | Schakel deze optie in als u de voortgang van activiteiten, zoals downloaden en synchroniseren, wilt weergeven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
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
>Alle Android™-apparaten hebben een `*sdcard*` -map, ongeacht of een actuele `*sdcard*` is ingevoegd of niet. Dit bestand wordt tijdens de implementatie op hetzelfde niveau geplaatst als de map Downloads. Sommige MDMs, zoals Knox Samsung, kan deze *sdcard* omslagplaats als *Interne opslag* zien.

## Bulkprovisioning van Android™ Player met gebruik van Enterprise Mobility Management {#bulk-provisioning}

Wanneer u de Android™-speler bulksgewijs inzet, wordt het vervelend om elke speler handmatig bij AEM te registreren. Gebruik een EMM-oplossing (Enterprise Mobility Management), zoals [`VMWare Airwatch` ](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm) , MobileIron of Samsung Knox, zodat u uw implementatie op afstand kunt voorzien en beheren. AEM Screens Android™-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

## Namen van Android™ Player {#name-android}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Android™-speler toewijzen en zo de toegewezen apparaatnaam naar AEM (Adobe Experience Manager) verzenden. Met deze functie kunt u niet alleen uw Android™-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam in de Android™-speler te configureren:

1. Navigeer aan **montages** > **Ongeveer apparaat**
1. Geef uw apparatennaam uit en plaats uw Android™ speler te noemen

### Bulkprovisioning van Android™ Player implementeren met gebruik van Enterprise Mobility Management {#implementation}

Voer de onderstaande stappen uit om bulkprovisioning in Android™ Player toe te staan:

1. Zorg ervoor dat uw Android™-apparaat ondersteuning biedt voor Google Play-services.
1. Schrijf uw Android™-spelerapparaten in met uw favoriete EMM-oplossing die AppConfig ondersteunt.
1. Meld u aan bij uw EMM-console en haalt de AEM Screens Player-toepassing uit Google Play.
1. Klik op de beheerde configuratie of verwante optie.
1. Er wordt nu een lijst weergegeven met speleropties die kunnen worden geconfigureerd, zoals server- en bulkregistratiecode.
1. Vorm deze parameters, sparen, en stel het beleid aan de apparaten op.

   >[!NOTE]
   >De apparaten zouden de toepassing samen met de configuratie moeten ontvangen. De toepassing moet verwijzen naar de juiste AEM-server met de geselecteerde configuratie. Als u ervoor hebt gekozen de bulkregistratiecode te configureren en deze op dezelfde manier te handhaven als in AEM, kan de speler zichzelf automatisch registreren. Als u een standaardweergave hebt geconfigureerd, kan deze ook standaardinhoud downloaden en weergeven (die later naar wens kan worden gewijzigd).

Raadpleeg ook uw leverancier van EMM op AppConfig-ondersteuning. De populairste degenen zoals [`VMWare Airwatch` ](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [`Mobile Iron` ](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [`SOTI` ](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [`BlackBerry&reg; UEM` ](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [`IBM&reg; Maas360` ](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm), en [`Samsung Knox` ](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) onder anderen steunen deze industriestandaard.

### De afstandsbediening van Screens gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Leer meer over deze eigenschap hier: [ de Verre Controle van Screens ](implementing-remote-control.md)
