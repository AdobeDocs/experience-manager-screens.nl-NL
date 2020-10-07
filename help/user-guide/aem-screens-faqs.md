---
title: Veelgestelde vragen over AEM Screens
seo-title: Veelgestelde vragen over AEM Screens
description: Volg deze pagina om antwoorden te krijgen op veelgestelde vragen over een AEM Screens-project.
seo-description: Volg deze pagina om antwoorden te krijgen op veelgestelde vragen over een AEM Screens-project.
uuid: 62e58f3b-0c0a-4006-b6d5-42d2090f47b5
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 7f897f969e7ca9c9c478b885cf716303bbbe5049
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 0%

---


# Veelgestelde vragen over AEM Screens {#aem-screens-faqs}

In de volgende sectie worden antwoorden gegeven op een aantal veelgestelde vragen over een AEM Screens-project.

## Kanaalbeheer {#channel-management}

### 1. Wat is het verschil tussen een online en een off-line kanaal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Met een ***onlinekanaal*** wordt de bijgewerkte inhoud weergegeven in de real-time omgeving, terwijl met een ***offlinekanaal*** de inhoud in de cache wordt weergegeven.

### 2. Hoe maak ik online een kanaal? {#how-do-i-make-a-channel-online}

Selecteer het kanaal en navigeer naar kanaaleigenschappen in de actiebalk. Schakel de modus **Ontwikkelaar in (forceer dat het kanaal online moet zijn)** onder het tabblad **Kanaal** om het kanaal online te maken.

### 3. Wat is het gebruik van het gebied van de Rol van het Kanaal? {#what-is-the-use-of-the-channel-role-field}

De rol van het Kanaal, is de abstractie van het daadwerkelijke kanaal dat wordt in werking gesteld zodat de auteur zich op de generische ervaring kan direct concentreren. U kunt het zien als een soort tag die het kanaal op unieke wijze identificeert in zijn context (weergave of schema).

### 4. Hoe gebeurt de werkelijke kanaalresolutie? {#how-does-actual-channel-resolution-happen}

Voor *statische verwijzingen* volgt de resolutie alleen het opgegeven pad.

Voor *dynamische verwijzingen* vindt de resolutie plaats zodra het kanaal is toegewezen aan de weergave (niet het schema). Het weergavepad wordt de context voor het kanaal en de resolutie gebeurt als volgt (hoogste naar laagste prioriteit):

1. De weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De weergave heeft een knooppunt op hetzelfde niveau dat overeenkomt met de naam van het kanaal waarnaar wordt verwezen
1. De bovenliggende locatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De bovenliggende hoofdlocatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen

En zo verder, tot u de plaatsingsomslag bereikt en daar tegenhoudt op het ogenblik (zodat kunt u niet naar een kanaal verwijzen dat in de kanaalomslag bijvoorbeeld, slechts kanalen in de plaatssubboom zou zijn).

## Apparaatregistratie {#device-registration}

### 1. Als ik eindpunten zoals verzoeken om apparaat het in- en uitstappen ontdekt, kan ik een groot aantal apparaten in een script opnemen en deze apparaten registreren. Is het mogelijk om deze verzoeken te beveiligen, naast het vergrendelen van dit aan een tak Wi-Fi? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Registratie is momenteel alleen mogelijk op de instantie van de auteur. Hoewel de registratiedienst niet voor authentiek verklaard is, zal het slechts tot een hangend apparaat in AEM leiden en zal eigenlijk niet het apparaat registreren of om het even welke vertoning toewijzen.

Als u een apparaat wilt registreren (wat betekent dat u een gebruiker voor het apparaat in AEM maakt), moet u nog steeds AEM verifiëren en de registratiewizard momenteel handmatig volgen om de registratie te voltooien. In theorie kan een kwaadwillige gebruiker meerdere apparaten in behandeling maken, maar zonder AEM aanmeldingsnaam kunnen geen apparaten worden geregistreerd.

### 2. Is er een manier om HTTP- GET- verzoeken in de POST van HTTP met één of andere vorm van authentificatie om te zetten? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

De registratieaanvraag is een aanvraag van een POST.

Het wordt aanbevolen de apparaat-id op te halen uit de sessie in plaats van deze als parameter door te geven. Hierdoor zouden de serverlogboeken, browsercache enzovoort worden opgeschoond. Het is momenteel geen veiligheidskwestie. Houd er rekening mee dat semantisch GET wordt gebruikt wanneer er geen statuswijziging op de server plaatsvindt en dat POST wordt gebruikt wanneer er een statuswijziging plaatsvindt.

### 3. Is er een manier om een verzoek tot registratie van een apparaat af te wijzen? {#is-there-a-way-to-decline-a-device-registration-request}

Je kunt de registratieaanvragen niet afwijzen. In plaats daarvan zouden de registratieverzoeken na een onderbreking moeten verlopen die in de Console [van het Web van](https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.registration.impl.RegistrationServiceImpl)Adobe Experience Manager wordt gevormd. Deze waarde wordt standaard ingesteld op één dag en wordt opgeslagen in een geheugencache.

## Apparaatbewaking en statusrapporten {#device-monitoring-and-health-reports}

### 1. Hoe los ik problemen op als mijn AEM Screens-speler een leeg scherm weergeeft? {#how-do-i-troubleshoot-if-my-aem-screens-player-shows-blank-screen}

Controleer de volgende mogelijkheden om het probleem met het lege scherm op te lossen:

* AEM kan de offline inhoud niet verschuiven
* Kanaal heeft geen inhoud
* Geen van de elementen wordt op het huidige tijdstip weergegeven

### 2. Wat moet ik doen als AEM Screens Player zich niet kan registreren en de status ervan als mislukt wordt weergegeven? {#what-do-i-do-if-aem-screens-player-cannot-register-and-its-state-is-displayed-as-failure}

U moet het filter Apache Sling Reference Filter Allow Empty inschakelen. Dit is vereist voor een optimale werking van het controleprotocol tussen AEM Screens Player en de AEM Screens-server.

1. Ga naar **Adobe Experience Manager Web Console Configuration**
1. Schakel de optie **allow.empty** in.
1. Click **Save**.

### 3. Hoe problemen op te lossen als tijdens het registreren van een speler van AEM Screens, het apparaat FAILURE en de console logboeken de fout ENAME_NOT_FOUND tonen? {#how-to-troubleshoot-if-while-registering-an-aem-screens-player-device-shows-failure-and-the-console-logs-display-ename-not-found-error}

Dit probleem kan optreden als de speler de AEM Screens Server DNS niet kan vinden. U kunt proberen gebruikend het IP adres om te verbinden. Om IP van server te verkrijgen, gebruik: *arp &lt;server_dns_name>*.

### 4. ADT AMS het implementeren van een Android Watchdog op alle apparaten? Maakt de Watchdog (Cordova)-plug-in deel uit van de APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Een Android-controlehond die alleen Android-API&#39;s gebruikt, maakt al deel uit van de apk. Er is geen extra software nodig, maar afhankelijk van het apparaat dat u gebruikt, moet u mogelijk de apk opnieuw ondertekenen om systeemrechten te verkrijgen voor een volledige energiecyclus (PowerManager-API). Als de toepassing niet opnieuw wordt ondertekend met de toetsen van de fabrikant, wordt de toepassing afgesloten en opnieuw gestart, maar niet met de energiecyclus.

Raadpleeg [**Android Player**](implementing-android-player.md) implementeren voor meer informatie over het implementeren van Android Player.

### 5. Welke externe controle- en waarschuwingsprogramma&#39;s (software) van derden beveelt Adobe/AMS aan om elk apparaat te controleren?  {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Afhankelijk van wat u uit de controle en het alarm wenst, meldt een nieuwe eigenschap de dienst van de Meldingen van AEM Screens u als een apparaat niet in een tijd heeft gepingeld. De hulpmiddelen van derden zijn afhankelijk van uw besturingssysteem, de mogelijkheden en de specifieke behoeften van de klant.

Raadpleeg [**AEM Screens Notifications Service**](screens-notifications-service.md) voor meer informatie over waar u de apparaatactiviteiten kunt controleren.

## AEM Screens Player {#aem-screens-player}

### 1. Hoe installeert u ChromeOS-speler als Chrome Browser Plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

De ChromeOS-speler kan als Chrome Browser-insteekmodule worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een daadwerkelijk chrome speler-apparaat nodig is. Volg onderstaande stappen voor installatie:

1. Klik [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.
1. Pak het uit en sla het op de schijf op.
1. Open Chrome-browser en selecteer **Extensies** in het menu of navigeer rechtstreeks naar ***chrome://extensions***.
1. Schakel de modus **Ontwikkelaar** in de rechterbovenhoek in.
1. Klik op **Niet-verpakt** laden in de linkerbovenhoek en laad niet-gecomprimeerde Chrome Player.
1. Controleer de **AEM Screens Chrome Player** -insteekmodule als deze beschikbaar is in de lijst met extensies.
1. Open een nieuw tabblad en klik op het pictogram **Apps** linksboven of navigeer rechtstreeks naar ***chrome://apps***.
1. Klik op **AEM Screens** -insteekmodule om Chrome Player te starten. Standaard wordt de speler gestart in de modus Volledig scherm. Druk op **esc** om de modus Volledig scherm af te sluiten.

### 2. Hoe te om problemen op te lossen als de speler van de Schermen niet door te verifiëren instantie met douanefoutenmanager kan verifiëren? {#how-to-troubleshoot-if-screens-player-is-unable-to-authenticate-through-publish-instance-with-custom-error-handler}

Wanneer de AEM Screens-speler wordt gestart, wordt een aanvraag gedaan naar ***/content/screens/svc.ping.json*** wanneer de speler een fout van 404 krijgt. De speler start een verificatieaanvraag om te verifiëren op basis van de publicatie-instantie. Als er een aangepaste fouthandler is in de publicatieversie, moet u de 404-statuscode voor anonieme gebruiker retourneren op ***/content/screens/svc.ping.json***.

### 3. Hoe kunt u instellen dat het scherm van het apparaat blijft ingeschakeld in een Android-speler? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Voer de onderstaande stappen uit om Op een Android-speler actief blijven in te schakelen:

1. Navigeren naar de instellingen van de Android-speler —> **Info**
1. Tik 7 keer op het buildnummer om **Developer Options** in **Settings in te schakelen**
1. Navigeren naar opties voor **ontwikkelaars**
1. Schakel **Wachten inschakelen in**

### 4. Hoe te om vensterwijze voor de speler van Vensters toe te laten?{#enable-player}

Er is geen venstermodus in Windows Player. Dit is altijd de modus Volledig scherm.

### 5. Hoe kan ik problemen oplossen als een AEM Screens-speler voortdurend aanmeldingsaanvragen verzendt?{#requests-login}

Voer de onderstaande stappen uit om problemen op te lossen bij een AEM Screens-speler die aanvragen doorlopend verzendt naar `/content/screens/svc.json` en `/libs/granite/core/content/login.validate/j_security_check`:

1. Wanneer de AEM Screens-speler start, vraagt deze om `/content/screens/svc.json`, wanneer de speler een 404-statuscode in het antwoord krijgt, een verificatieaanvraag te starten om deze te verifiëren met `/libs/granite/core/content/login.validate/j_security_check` behulp van de *publicatie* -instantie. Als er een manager van de douanefout in publiceer instantie is, zorg ervoor dat u de 404 statuscode voor anonieme gebruiker op `/content/screens/svc.json` of `/content/screens/svc.ping.json`terugkeert.

1. Controleer of deze aanvragen in de `/filters` sectie zijn toegestaan in de configuratie van de verzender.
Zie [Schermfilters](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html#step-configuring-screens-filters) configureren voor meer informatie.

1. Controleer of de regels voor het herschrijven van de verzender een van de rasterpaden naar een ander pad herschrijven.

1. Controleer of u `/etc/map` regels voor de *auteur* of *publiceer* instantie hebt en of de rasterpaden overeenkomen met `sling:match` en intern worden omgeleid naar een ander pad. Het oplossen van de nauwkeurige url in `/system/console/jcrresolver` helpt bij het identificeren als de *publicatie* instantie deze urls aan een ander weg herschrijft.

1. Controleer of de configuratie van Apache Sling Resource Resolver Factory interne herschrijvingen veroorzaakt.

## Algemene tips voor probleemoplossing {#general-troubleshooting-tips}

### 1. Hoe te om Livefyre onbruikbaar te maken om Fout A/P van de Schermen te vermijden? {#how-to-disable-livefyre-to-avoid-a-p-screens-error}

Om Livefyre onbruikbaar te maken om logboekfouten te vermijden:

1. ***Livefyre-bundel uitschakelen:***

   * Ga naar `https://&lt;host&gt;:&lt;port&gt;/system/console/bundles`
   * Zoeken naar de AEM Livefyre-bundel: `com.adobe.cq.social.cq-social-livefyre`
   * Klik op **Stoppen**

1. ***Livefyre-poller uitschakelen:***

   * Navigeer in CRXDE Lite naar `/etc/importers/polling/livefyre-poller/jcr:content`
   * Een nieuwe eigenschap van het *ingeschakelde* type *Boolean toevoegen*
   * Ingeschakelde eigenschap **** instellen op **false**

