---
title: Veelgestelde vragen over AEM Screens
seo-title: AEM Screens FAQs
description: Volg deze pagina om antwoorden te krijgen op veelgestelde vragen over een AEM Screens-project.
seo-description: Follow this page to get answers to FAQs related to an AEM Screens project.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '2168'
ht-degree: 0%

---

# Veelgestelde vragen over AEM Screens {#aem-screens-faqs}

In de volgende sectie worden antwoorden gegeven op een aantal veelgestelde vragen over een AEM Screens-project.

## Probleem met leeg scherm {#blank-screen}

>[!NOTE]
>De vermelde verplichte controles die door primaire ondersteuning of klantenondersteuning moeten worden geprobeerd voordat een probleem aan de orde wordt gesteld.

### 1. Wat zouden de het oplossen van problemenstappen van de Eerste hulp voor om het even welke klant moeten zijn die een zwart scherm of het niet spelen van inhoud onder ogen zien? {#troubleshooting-blank-screen}

* Controleer of de voorvertoning van het kanaal werkt.
* Controleren of de voorvertoning werkt
* Registreer de speler als browserextensie op uw systeem naar hetzelfde scherm en controleer of dit werkt.
* Met de speler die op uw systeem loopt, navigeer aan `http://localhost:24502`. Controleer of alle inhoud correct is gedownload.
* Controleer de elementen of de juiste uitvoeringen zijn gemaakt en of de juiste uitvoering wordt afgespeeld.
* Controleer of de geplande inhoud aanwezig is en of de tijden correct zijn. Controleer of de in de speler ingestelde tijd juist is.
* Inspect de spelerconsole registreert en controleert om het even welke fouten. Klik en inspecteer met de rechtermuisknop om de consolelogboeken te zien. Druk op `CTRL + ALT +I` om de dev-console op te roepen om de logbestanden te bekijken.

### 2. Hoe kan het probleem met grijswaardenschermen in AEM Screens worden opgelost door een standaardkanaal of -schema te maken?

Als u wilt voorkomen dat het veld leeg of grijs wordt weergegeven, maakt u een standaard globaal kanaal of schema, toegewezen aan elk scherm met de minste prioriteit 1. In het geval dat er iets mis gaat met inhoudsupdates (vanwege netwerk, speler, server of replicatie), omdat de spelers deze inhoud al in het cachegeheugen op de schijf hebben, die goed moet worden afgespeeld en de grijze schermen moeten worden vermeden.

Alle andere inhoud, zoals kanalen of programma&#39;s, krijgt prioriteit groter dan 1. De andere inhoud heeft dus prioriteit en de inhoud van het algemene kanaal of programma (met prioriteit 1) wordt alleen afgespeeld als een terugvaloptie.

## Kanaalbeheer {#channel-management}

### 1. Wat is het verschil tussen een online en een offline kanaal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

An ***Onlinekanaal*** wordt de bijgewerkte inhoud in de real-time omgeving weergegeven, terwijl een ***Offline kanaal*** wordt de inhoud in de cache weergegeven.

### 2. Hoe maak ik online een kanaal? {#how-do-i-make-a-channel-online}

Selecteer het kanaal en navigeer naar kanaaleigenschappen in de actiebalk. Controleren **Modus Ontwikkelaar (kanaal forceren om online te zijn)** krachtens **Kanaal** om het kanaal online te maken.

### 3. Wat is het gebruik van het veld Kanaalrol? {#what-is-the-use-of-the-channel-role-field}

De rol van het Kanaal, is de abstractie van het daadwerkelijke kanaal dat wordt in werking gesteld zodat de auteur zich op de generische ervaring kan direct concentreren. U kunt het zien als een soort tag die het kanaal op unieke wijze identificeert in zijn context (weergave of schema).

### 4. Hoe verloopt de eigenlijke kanaaloplossing? {#how-does-actual-channel-resolution-happen}

Voor *statische verwijzingen* De resolutie volgt alleen het opgegeven pad.

Voor *dynamische verwijzingen*, treedt de resolutie op zodra het kanaal is toegewezen aan de weergave (niet het schema). Het weergavepad wordt de context voor het kanaal en de resolutie gebeurt als volgt (hoogste naar laagste prioriteit):

1. De weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De weergave heeft een knooppunt op hetzelfde niveau dat overeenkomt met de naam van het kanaal waarnaar wordt verwezen
1. De bovenliggende locatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De bovenliggende hoofdlocatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen

En zo verder, tot u de plaatsingsomslag bereikt en daar tegenhoudt op het ogenblik (zodat kunt u niet naar een kanaal verwijzen dat in de kanaalomslag bijvoorbeeld, slechts kanalen in de plaatssubboom zou zijn).

### 5. Hoe kan ik een aangepaste clientlib-offlineconfiguratie instellen in AEM Screens Channel?

Wanneer u een geïntegreerde aangepaste code aan de clientzijde gebruikt `clientlib` in een AEM Screens-kanaal moeten de volgende stappen worden uitgevoerd om ervoor te zorgen dat de `clientlib` bestanden zijn geladen in het kanaal (`manifest.json`) en bevat het pad van de `clientlib`.

Voer de onderstaande stappen uit vanuit de kanaaleditor:

1. Selecteer een kanaal en klik op **Bewerken** in de actiebalk om de kanaaleditor te openen.
1. Selecteer de component waar u de aangepaste elementen wilt toevoegen `clientlib`.
1. Klik op de vormingsknoop (het moersleutelpictogram).
1. Ga naar de **Offline configuratie** en voeg het pad toe aan uw aangepaste clientlib in **Client-side bibliotheken**.

## Apparaatregistratie {#device-registration}

### 1. Als ik eindpunten zoals verzoeken om apparaat aan boord te nemen en registratie ontdekt, kan ik een groot aantal apparaten scripten en deze apparaten registreren. Is het mogelijk om deze verzoeken te beveiligen, naast het vergrendelen van dit aan een tak Wi-Fi? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Registratie is momenteel alleen mogelijk op de auteurinstantie. Hoewel de registratiedienst niet voor authentiek verklaard is, zal het slechts tot een hangend apparaat in AEM leiden en zal eigenlijk niet het apparaat registreren of om het even welke vertoning toewijzen.

Als u een apparaat wilt registreren (wat betekent dat u een gebruiker voor het apparaat in AEM maakt), moet u nog steeds AEM verifiëren en de registratiewizard momenteel handmatig volgen om de registratie te voltooien. In theorie kan een kwaadwillige gebruiker meerdere apparaten in behandeling maken, maar zonder AEM aanmeldingsnaam kunnen geen apparaten worden geregistreerd.

### 2. Is er een manier om de verzoeken van HTTP GET in de POST van HTTP met één of andere vorm van authentificatie om te zetten? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

De registratieaanvraag is een aanvraag van een POST.

Het wordt aanbevolen de apparaat-id op te halen uit de sessie in plaats van deze als parameter door te geven. Hierdoor zouden de serverlogboeken, browsercache enzovoort worden opgeschoond. Het is momenteel geen veiligheidskwestie. Houd er rekening mee dat semantisch GET wordt gebruikt wanneer er geen statuswijziging op de server plaatsvindt en dat POST wordt gebruikt wanneer er een statuswijziging plaatsvindt.

### 3. Is er een manier om een verzoek tot registratie van een apparaat af te wijzen? {#is-there-a-way-to-decline-a-device-registration-request}

Je kunt de registratieaanvragen niet afwijzen. In plaats daarvan zouden de registratieverzoeken na een onderbreking moeten verlopen die binnen wordt gevormd `Adobe Experience Manager Web Console`. Deze waarde wordt standaard ingesteld op één dag en wordt opgeslagen in een geheugencache.

## Apparaatbewaking en statusrapporten {#device-monitoring-and-health-reports}

### 1. Hoe los ik problemen op als mijn AEM Screens-speler een leeg scherm weergeeft? {#how-do-i-troubleshoot-if-my-aem-screens-player-shows-blank-screen}

Controleer de volgende mogelijkheden om het probleem met het lege scherm op te lossen:

* AEM kan de offline inhoud niet verschuiven
* Kanaal heeft geen inhoud
* Geen van de elementen wordt op het huidige tijdstip weergegeven

### 2. Wat moet ik doen als AEM Screens Player zich niet kan registreren en de status ervan als mislukt wordt weergegeven? {#what-do-i-do-if-aem-screens-player-cannot-register-and-its-state-is-displayed-as-failure}

U moet het filter Apache Sling Reference Filter Allow Empty inschakelen. Dit is vereist voor een optimale werking van het controleprotocol tussen AEM Screens Player en AEM Screens Server.

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole**
1. Controleer de **allow.empty** -optie.
1. Klikken **Opslaan**.

### 3. Hoe kan ik problemen oplossen als tijdens het registreren van een AEM Screens-speler, het apparaat MISLUKT weergeeft en de console-logboeken de fout ENAME_NOT_FOUND weergeven? {#how-to-troubleshoot-if-while-registering-an-aem-screens-player-device-shows-failure-and-the-console-logs-display-ename-not-found-error}

Dit probleem kan optreden als de speler de AEM Screens Server DNS niet kan vinden. U kunt proberen gebruikend het IP adres om te verbinden. Om IP van server te verkrijgen, gebruik: *arp &lt;server_dns_name>*.

### 4. beveelt AMS aan een Android Watchdog op alle apparaten te implementeren? Maakt de Watchdog (Cordova)-plug-in deel uit van de APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Een Android-controlehond die alleen Android-API&#39;s gebruikt, maakt al deel uit van de apk. Er is geen extra software nodig, maar afhankelijk van het apparaat dat u gebruikt, moet u mogelijk de apk opnieuw ondertekenen om systeemrechten te verkrijgen voor een volledige energiecyclus (PowerManager-API). Als de toepassing niet opnieuw wordt ondertekend met de toetsen van de fabrikant, wordt de toepassing afgesloten en opnieuw gestart, maar niet met de energiecyclus.

Voor meer informatie over het implementeren van Android Player raadpleegt u [**Android-speler implementeren**](implementing-android-player.md).

### 5. Welke externe bewakings- en alarmeringsprogramma&#39;s (software) beveelt Adobe/AMS aan om elk apparaat te controleren?  {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Afhankelijk van wat u uit de controle en het alarm wenst, meldt een nieuwe eigenschap de dienst van de Meldingen van AEM Screens u als een apparaat niet in een tijd heeft gepingeld. De hulpmiddelen van derden zijn afhankelijk van uw besturingssysteem, de mogelijkheden en de specifieke behoeften van de klant.

Voor meer informatie over waar u de apparaatactiviteit kunt controleren, raadpleegt u [**AEM Screens-berichtenservice**](screens-notifications-service.md).

## AEM Screens Player {#aem-screens-player}

### 1. Hoe installeer je ChromeOS-speler als Chrome Browser Plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

De ChromeOS-speler kan als Chrome Browser-insteekmodule worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een daadwerkelijk chrome speler-apparaat nodig is. Volg onderstaande stappen voor installatie:

1. Klikken [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.
1. Pak het uit en sla het op de schijf op.
1. Chrome openen en **Extensies** in het menu of rechtstreeks door ***chrome://extensions***.
1. Schakel de **Modus Ontwikkelaar** in de rechterbovenhoek.
1. Klikken op **Niet-verpakt laden** in de linkerbovenhoek en geladen niet-gecomprimeerde Chrome Player.
1. Controleren **AEM Screens Chrome Player** insteekmodule indien beschikbaar in de lijst met extensies.
1. Open een nieuw tabblad en klik op de knop **Apps** vanuit de linkerbovenhoek, of rechtstreeks naar ***chrome://apps***.
1. Klikken op **AEM Screens** Insteekmodule voor het starten van Chrome Player. Standaard wordt de speler gestart in de modus Volledig scherm. Druk **esc** om de modus Volledig scherm af te sluiten.

### 2. Hoe kan ik problemen oplossen als de schermspeler niet kan worden geverifieerd via een publicatie-instantie met een aangepaste fouthandler? {#how-to-troubleshoot-if-screens-player-is-unable-to-authenticate-through-publish-instance-with-custom-error-handler}

Wanneer AEM Screens Player wordt gestart, wordt het volgende gevraagd: ***/content/screens/svc.ping.json***, wanneer de speler een fout van 404 krijgt. De speler start een verificatieaanvraag om te verifiëren op basis van de publicatie-instantie. Als er een aangepaste fouthandler is in de publicatieversie, moet u de 404-statuscode voor anonieme gebruikers retourneren op ***/content/screens/svc.ping.json***.

### 3. Hoe kunt u instellen dat het scherm van het apparaat in een Android-speler blijft ingeschakeld? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Voer de onderstaande stappen uit om Op een Android-speler actief blijven in te schakelen:

1. Ga naar de instellingen voor de Android-speler > **Info**
1. Tik 7 keer op het buildnummer om in te schakelen **Opties voor ontwikkelaars** in **Instellingen**
1. Navigeren naar **Opties voor ontwikkelaars**
1. Inschakelen **Blijf wakker**

### 4. Hoe kan de venstermodus voor de Windows-speler worden ingeschakeld?{#enable-player}

Er is geen venstermodus in Windows Player. Dit is altijd de modus Volledig scherm.

### 5. Hoe kan ik problemen oplossen als een AEM Screens-speler voortdurend aanmeldingsaanvragen verzendt?{#requests-login}

Volg de onderstaande stappen om een AEM Screens-speler problemen op te lossen die voortdurend aanvragen verzendt naar `/content/screens/svc.json` en `/libs/granite/core/content/login.validate/j_security_check`:

1. Wanneer AEM Screens Player wordt gestart, wordt het volgende gevraagd: `/content/screens/svc.json`. Wanneer de speler een 404 statuscode in de reactie krijgt, initieert het een authentificatieverzoek gebruikend `/libs/granite/core/content/login.validate/j_security_check` tegen de *publish* -instantie. Als er een aangepaste fouthandler is in het dialoogvenster *publish* -instantie, zorg er dan voor dat u de 404-statuscode voor anonieme gebruikers op `/content/screens/svc.json` of `/content/screens/svc.ping.json`.

1. Controleer of deze aanvragen zijn toegestaan in de configuratie van de verzender `/filters`.

   Zie [Schermfilters configureren](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html#step-configuring-screens-filters) voor meer informatie .

1. Controleer of de regels voor het herschrijven van de verzender een van de rasterpaden naar een ander pad herschrijven.

1. Controleer of u `/etc/map` voorschriften inzake *auteur* of *publish* instantie- en rasterpaden komen overeen met `sling:match` en intern omgeleid naar een ander pad. De exacte URL oplossen in `/system/console/jcrresolver` helpt bij het vaststellen of de *publish* -instantie herschrijft deze URL&#39;s naar een ander pad.

1. Controleer of de configuratie van Apache Sling Resource Resolver Factory interne herschrijvingen veroorzaakt.

### 6. Hoe haalt u de details van het scherm en het apparaat op van de speler-API?

U kunt de details van de weergave en het apparaat ophalen via:

* **een interne JS API**
* **een ContextHub-archief**: Drie ContextHub-winkels zijn gedefinieerd in `/libs/screens/clientlibs/contexthub` om kanalen, apparaat en, vertoningsinfo bloot te stellen.

  Volg de stappen hieronder om deze ContentHub opslagwaarden te gebruiken:

   * Bewerk de kanaaleigenschappen en stel het pad ContextHub op het tabblad voor personalisatie in op de waarde (zoals hierboven vermeld)
   * In het kanaal JS, kunt u gebruiken:

     ```shell
        ContextHub.getStore('screens-device');
        ContextHub.getStore('screens-display');
        ContextHub.getStore('screens-channels');
     ```

## Algemene tips voor probleemoplossing {#general-troubleshooting-tips}

### 1. Hoe kan Livefyre worden uitgeschakeld om een A/P-schermfout te voorkomen? {#how-to-disable-livefyre-to-avoid-a-p-screens-error}

Om Livefyre onbruikbaar te maken om logboekfouten te vermijden:

1. ***Bibliotheekbundel uitschakelen:***

   * Navigeren naar `https://<host>:<port>/system/console/bundles`
   * Zoeken naar de AEM Livefyre-bundel: `com.adobe.cq.social.cq-social-livefyre`
   * Klikken **Stoppen**

1. ***Livefyre-poller uitschakelen:***

   * Ga in CRXDE Lite naar `/etc/importers/polling/livefyre-poller/jcr:content`
   * Een nieuwe eigenschap toevoegen *enabled* type *Boolean*
   * Set **enabled, eigenschap** tot **false**

### 2. Hoe wordt informatie over de eikenindex toegevoegd? {#add-oak-index-info}

AEM Screens maakt indexdefinities voor de query&#39;s die door het product worden gebruikt.
Als er *Query Traversal-WAARSCHUWINGEN* in de `error.log`, maakt u een aangepaste index voor uw query. Zie [De indexen configureren](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/queries-and-indexing.html?lang=en#configuring-the-indexes) voor meer informatie .

U kunt ook naar een extra bron verwijzen op [Oak-documentatie](https://jackrabbit.apache.org/oak/docs/query/lucene.html).


### 3. Wat is vereist om v3-manifest te configureren? {#configure-v3}

Voor het inschakelen van v3-manifest moet u:

* Dispatcher bijwerken.
Zie [Dispatcher configureren voor manifestversie v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=en#configuring-dispatcherv3) voor meer informatie .

* Aangepaste component bijwerken.
Zie [Sjabloon voor aangepaste handlers](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=en#custom-handlers) voor meer informatie .

* ContentSync uitschakelen in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`.

* SmartSync inschakelen in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`.

* Bewerken `channel/experience fragment/page components`.

* Ga naar de **Offline configuratie** tab.

* Enter `clientlibs `en mappen voor statische bestanden die aan het manifest moeten worden toegevoegd.

### 4. Wat moet u doen als, na het pakket screens-cloud-ams-pkg-0.0.20, screens-cloud-ams-pkg-0.0.16 en de schermen core bundles geïnstalleerd maar niet actief zijn?

De AMS-aansluiting werkt alleen als u een minimale versie van AEM 6.5 Feature Pack 8 installeert. Zie de [Beschikbaarheid](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202105.html?lang=en#availability) voor de minimale versie van het pakket met schermfuncties.

### 5. Hoe te om de dienst van Externalzer van de Verbinding van CQ in Schermen te vormen?

De dienst wordt gebruikt om openbare hostname voor de auteur te bepalen en instanties te publiceren, en de waarden worden dan gebruikt om de apparatenserver URLs en ook voor het richten ContextHub bij te werken.

De dienst van Externalzer van de Verbinding CQ in Schermen kan via worden gevormd:

1. Navigeren naar `http://localhost:4502/system/console/configMgr`
1. Day CQ Link ExternalAlizer
1. Wijzig de hostnaam voor de `author/publish` zo nodig ingangen