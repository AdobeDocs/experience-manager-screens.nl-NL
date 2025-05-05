---
title: Veelgestelde vragen over AEM Screens
description: Lees antwoorden op veelgestelde vragen over een AEM Screens-project.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 0%

---

# Veelgestelde vragen over AEM Screens {#aem-screens-faqs}

Dit onderwerp verstrekt antwoorden aan algemeen gestelde FAQs met betrekking tot een project van AEM Screens.

## Probleem met leeg scherm {#blank-screen}

>[!NOTE]
>De vermelde verplichte controles die primaire ondersteuning of klantenondersteuning moeten proberen voordat een probleem wordt aangekaart.

### 1. Wat zouden de het oplossen van problemenstappen van de Eerste hulp voor om het even welke klant moeten zijn die een zwart scherm of het niet spelen van inhoud onder ogen zien? {#troubleshooting-blank-screen}

* Controleer of de voorvertoning van het kanaal werkt.
* Controleren of de voorvertoning werkt
* Registreer de speler als een browserextensie op uw systeem naar hetzelfde scherm en controleer of deze werkt.
* Blader naar `http://localhost:24502` terwijl de speler op uw systeem wordt uitgevoerd. Controleer of alle inhoud correct is gedownload.
* Controleer de elementen zodat u zeker weet dat de juiste uitvoeringen zijn gemaakt en dat de juiste vertoning wordt afgespeeld.
* Controleer of de geplande inhoud aanwezig is en of de tijden correct zijn. Controleer of de in de speler ingestelde tijd juist is.
* Inspect de spelerconsole registreert en controleert om het even welke fouten. Klik en inspecteer met de rechtermuisknop om de consolelogboeken te zien. Als u de Speler van Vensters gebruikt, druk `CTRL + ALT +I` om dev console omhoog te brengen om de logboeken te bekijken.

### 2. Hoe kan het probleem met grijswaardenschermen in AEM Screens worden opgelost door een standaardkanaal of -schema te maken?

Als u de lege of grijze schermen in het veld wilt vermijden, maakt u een standaard algemeen kanaal of schema, toegewezen aan elke weergave met de minste prioriteit 1. Als er iets mis gaat met het bijwerken van de inhoud omdat de spelers deze inhoud al in de cache hebben opgeslagen op de schijf. Het zou fijn moeten spelen en de grijze schermen vermijden.

Alle andere inhoud, zoals kanalen of programma&#39;s, prioriteit groter dan 1, zodat neemt de andere inhoud prioriteit en globale kanaal of planningsinhoud (met prioriteit 1) slechts als reserve optie.

## Kanaalbeheer {#channel-management}

### 1. Wat is het verschil tussen een online en een offline kanaal? {#what-is-the-difference-between-an-online-and-an-offline-channel}

Een ***Online Kanaal*** toont de bijgewerkte inhoud in het milieu in real time terwijl een ***Off-line Kanaal*** de caching inhoud toont.

### 2. Hoe maak ik online een kanaal? {#how-do-i-make-a-channel-online}

Klik op het kanaal en navigeer vanuit de actiebalk naar kanaaleigenschappen. De wijze van de Ontwikkelaar van de controle **(dwingend kanaal om online te zijn)** onder **Kanaal** tabel om het kanaal online te maken.

### 3. Wat is het gebruik van het veld Kanaalrol? {#what-is-the-use-of-the-channel-role-field}

De rol van het Kanaal is de abstractie van het daadwerkelijke kanaal dat wordt in werking gesteld zodat de auteur zich op de generische ervaring kan direct concentreren. U kunt het zien als een soort tag die het kanaal op unieke wijze identificeert in zijn context (weergave of schema).

### 4. Hoe verloopt de eigenlijke kanaaloplossing? {#how-does-actual-channel-resolution-happen}

Voor *statische verwijzingen*, volgt de resolutie enkel de weg die wordt gespecificeerd.

Voor *dynamische verwijzingen*, komt de resolutie voor zodra het kanaal aan de vertoning (niet het programma) wordt toegewezen. Het weergavepad wordt de context voor het kanaal en de resolutie gebeurt als volgt (hoogste naar laagste prioriteit):

1. De weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De weergave heeft een knooppunt op hetzelfde niveau dat overeenkomt met de naam van het kanaal waarnaar wordt verwezen
1. De bovenliggende locatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen
1. De bovenliggende hoofdlocatie van de weergave heeft een onderliggende node die overeenkomt met de kanaalnaam waarnaar wordt verwezen

En zo verder, totdat u de locatiemap bereikt. Stop daar momenteel (zodat u niet naar een kanaal kunt verwijzen dat in de kanaalomslag zou zijn, bijvoorbeeld, slechts kanalen in de plaatssubboom).

### 5. Hoe stelt u een aangepaste clientlib-offlineconfiguratie in in AEM Screens Channel?

Wanneer u een geïntegreerde aangepaste code aan de clientzijde `clientlib` in een AEM Screens-kanaal gebruikt, zijn de volgende stappen nodig. De stappen zorgen ervoor dat de `clientlib` dossiers met succes in het kanaal (`manifest.json`) worden geladen en de weg van `clientlib` bevatten.

Voer de onderstaande stappen uit vanuit de kanaaleditor:

1. Klik een kanaal, dan klik **uitgeven** van de actiebar.
1. Klik op de component waaraan u de aangepaste tekst `clientlib` wilt toevoegen.
1. Klik op de knop Configureren (het moersleutelpictogram).
1. Navigeer aan het **Off-line lusje Config** en voeg de weg aan uw douane clientlib in **cliënt-kant Bibliotheken** toe.

## Apparaatregistratie {#device-registration}

### 1. Als ik eindpunten zoals verzoeken om apparaat aan boord te nemen en registratie ontdekt, kan ik vele apparaten scripten en deze apparaten registreren. Is het mogelijk om deze verzoeken te beveiligen, naast het vergrendelen van de aanvraag voor een vertakking Wi-Fi? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Registratie is momenteel alleen mogelijk op de auteurinstantie. Hoewel de registratieservice niet is geverifieerd, wordt alleen een apparaat in AEM gemaakt dat in behandeling is en wordt het apparaat niet daadwerkelijk geregistreerd en wordt er geen weergave toegewezen.

Als u een apparaat wilt registreren (en een gebruiker voor het apparaat in AEM maakt), moet u zich verifiëren bij AEM en de registratiewizard handmatig volgen om de registratie te voltooien. In theorie kan een kwaadwillige gebruiker meerdere apparaten in behandeling maken, maar kan geen apparaten registreren als deze geen AEM aanmeldingsgegevens hebben.

### 2. Is er een manier om de verzoeken van HTTP GET in de POST van HTTP met één of andere vorm van authentificatie om te zetten? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

De registratieaanvraag is een aanvraag van een POST.

Het wordt aanbevolen de apparaat-id op te halen uit de sessie in plaats van deze als parameter door te geven. Als u dit doet, worden de serverlogboeken, de cache van de browser enzovoort opgeschoond. Het is geen veiligheidskwestie. Semantisch. GET wordt gebruikt wanneer er geen staatsverandering op de server is en de POST wordt gebruikt wanneer er een staatsverandering is.

### 3. Is er een manier om een verzoek tot registratie van een apparaat af te wijzen? {#is-there-a-way-to-decline-a-device-registration-request}

Je kunt de registratieaanvragen niet afwijzen. In plaats daarvan moeten de registratieaanvragen verlopen na een time-out die is geconfigureerd in `Adobe Experience Manager Web Console` . Deze waarde wordt standaard ingesteld op één dag en wordt opgeslagen in een geheugencache.

## Apparaatbewaking en statusrapporten {#device-monitoring-and-health-reports}

### 1. Hoe los ik problemen op als mijn AEM Screens Player een leeg scherm weergeeft?

Controleer op de volgende mogelijkheden om het probleem met het lege scherm op te lossen:

* AEM kan de offline inhoud niet verschuiven
* Het kanaal heeft geen inhoud
* Geen van de elementen wordt tijdens de huidige tijd weergegeven

### 2. Wat doe ik als de AEM Screens Player zich niet kan registreren en de status ervan als mislukt wordt weergegeven?

Schakel het filter Apache Sling Reference Filter Allow Empty in. Vereist voor een optimale werking van het controleprotocol tussen AEM Screens Player en AEM Screens Server.

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager**
1. Controleer **allow.empty** optie.
1. Klik **sparen**.

### 3. Hoe problemen op te lossen als tijdens het registreren van een Speler van AEM Screens, het apparaat MISLUKT toont en de consolelogboeken een fout ENAME_NOT_FOUND tonen?

Dit probleem kan optreden als de speler de AEM Screens Server DNS niet kan vinden. U kunt proberen gebruikend het IP adres om te verbinden. Om IP van de server te verkrijgen, gebruik: *arp &lt;server_dns_name>*.

### 4. beveelt AMS aan een Android™ Watchdog op alle apparaten te implementeren? Maakt de Watchdog (Cordova)-plug-in deel uit van de APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

Een Android™-waakhond die alleen Android™-API&#39;s gebruikt, maakt al deel uit van de apk. Er is geen extra software nodig. Afhankelijk van het apparaat dat u gebruikt, kunt u de apk echter opnieuw ondertekenen om zo nodig systeemrechten voor een volledige stroomcyclus (`Powermanager` api) te verkrijgen. Als het niet wordt verlaten gebruikend de fabriekstoetsen, sluit het en begint de toepassing opnieuw, maar aandrijft geen cyclus.

Voor meer informatie over hoe te om de Speler van Android™ uit te voeren, zie [**Uitvoerend Android™ Speler**](implementing-android-player.md).

### 5. Welke externe bewakings- en alarmeringsprogramma&#39;s (software) beveelt Adobe/AMS aan om elk apparaat te controleren? {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Afhankelijk van wat u uit de controle en het alarm wenst, meldt een nieuwe eigenschap de dienst van de Meldingen van AEM Screens u als een apparaat niet in een tijd heeft gepingeld. De hulpmiddelen van derden zijn afhankelijk van uw besturingssysteem, de mogelijkheden ervan en de specifieke behoeften van de klant.

Voor meer informatie over waar u apparatenactiviteit kunt controleren, zie [**AEM de Dienst van Berichten van het Scherm**](screens-notifications-service.md).

## AEM Screens Player

### 1. Hoe kan ik ChromeOS-speler installeren als Chrome-browserplug-in? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

De ChromeOS-speler kan worden geïnstalleerd als een Chrome-browserplug-in in de modus voor ontwikkelaars zonder dat een echt Chrome Player-apparaat nodig is. Volg onderstaande stappen voor installatie:

1. Klik [ hier ](https://download.macromedia.com/screens/) om de recentste Speler van Chrome te downloaden.
1. Pak het uit en sla het op de schijf op.
1. Open browser van Chrome en klik **Uitbreidingen** van het menu of navigeer direct aan ***chrome://extensions***.
1. Schakelaar op de **wijze van de Ontwikkelaar** van de top-juiste hoek.
1. Klik **Lading Onverpakte** van de hoogste-linkerhoek en lading unzipped Speler van Chrome.
1. Als beschikbaar in de lijst van uitbreidingen, controleer de **1&rbrace; stop van de Speler van AEM Screens Chrome**.
1. Open een nieuw lusje en klik **Apps** pictogram van de top-linkerhoek, of navigeer direct aan ***chrome://apps***.
1. Klik de **Insteekmodule van AEM Screens**. Standaard wordt de speler gestart in de modus Volledig scherm. Pers **Esc** om volledige het schermwijze weg te gaan.

### 2. Hoe kan ik problemen oplossen als Screens Player niet kan worden geverifieerd via een publicatie-instantie met een aangepaste fouthandler?

Wanneer de Speler van AEM Screens begint, doet het een verzoek aan ***/content/screens/svc.ping.json***, wanneer de speler een fout 404 krijgt. De speler start een verificatieaanvraag om te verifiëren op basis van de publicatieinstantie. Als er een manager van de douanefout in publiceer instantie is, zorg ervoor dat u de 404 statuscode voor een anonieme gebruiker op ***/content/screens/svc.ping.json*** terugkeert.

### 3. Hoe kunt u instellen dat het scherm van het apparaat blijft ingeschakeld in een Android™ Player? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Volg de onderstaande stappen om Op elke Android™-speler actief blijven in te schakelen:

1. Navigeer aan de spelermontages van Android™ > **Ongeveer**.
1. Tik zeven keer op het bouwstijlaantal zodat kunt u **Opties van de Ontwikkelaar** in **Montages** toelaten.
1. Navigeer aan **Opties van de Ontwikkelaar**.
1. Laat **Waakzaam** toe.

### 4. Hoe te om vensterwijze voor de Speler van Vensters toe te laten?{#enable-player}

Windows Player bevat geen venstermodus. De modus is altijd volledig scherm.

### 5. Hoe kan ik problemen oplossen als een AEM Screens Player voortdurend aanmeldingsaanvragen verzendt?

Voer de onderstaande stappen uit om problemen op te lossen met een AEM Screens Player die aanvragen doorlopend naar `/content/screens/svc.json` en `/libs/granite/core/content/login.validate/j_security_check` verzendt:

1. Wanneer AEM Screens Player wordt gestart, wordt `/content/screens/svc.json` aangeroepen. Wanneer de speler een 404 statuscode in de reactie krijgt, stelt het een authentificatieverzoek in door `/libs/granite/core/content/login.validate/j_security_check` tegen *te gebruiken publiceert* instantie. Als er een manager van de douanefout in *is publiceer* instantie, zorg ervoor om de 404 statuscode voor anonieme gebruiker op `/content/screens/svc.json` of `/content/screens/svc.ping.json` terug te keren.

1. Controleer of uw Dispatcher-configuratie deze aanvragen toestaat in de `/filters` .

   Zie [ Vormend de Filters van Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#step-configure-screens-filters) voor meer details.

1. Controleer of uw Dispatcher-herschrijfregels schermpaden herschrijven naar een ander pad.

1. Controle als u `/etc/map` regels op de *auteur* hebt of *publiceer* instantie en de schermwegen worden aangepast aan `sling:match` en intern opnieuw gericht aan een verschillende weg. Het oplossen van nauwkeurige url in `/system/console/jcrresolver` helpt in het identificeren als *publiceert* instantie deze URLs aan een andere weg herschrijft.

1. Controleer of de configuratie van de Apache Sling Resource Resolver Factory interne herschrijvingen veroorzaakt.

### 6. Hoe haalt u de details van het scherm en het apparaat op van de speler-API?

U kunt de details van de weergave en het apparaat ophalen door:

* **een interne JS API**
* **een opslag ContextHub**: Drie opslag ContextHub wordt bepaald in `/libs/screens/clientlibs/contexthub` om kanalen, apparaat en, vertoningsinfo bloot te stellen.

  Volg de stappen hieronder om deze ContentHub opslagwaarden te gebruiken:

   * Bewerk de kanaaleigenschappen en stel het pad ContextHub op het tabblad voor personalisatie in op de waarde (zoals hierboven vermeld)
   * In het kanaal JS, kunt u gebruiken:

     ```shell
        ContextHub.getStore('screens-device');
        ContextHub.getStore('screens-display');
        ContextHub.getStore('screens-channels');
     ```

## Algemene tips voor probleemoplossing {#general-troubleshooting-tips}

### 1. Hoe kan ik LiveCycle uitschakelen om een A/P Screens-fout te voorkomen?

Schakel Livefyre uit om logfouten te voorkomen door het volgende te doen.

1. ***maak Bibliotheekbundel onbruikbaar:***

   * Navigeer naar `https://<host>:<port>/system/console/bundles` .
   * Zoeken naar de AEM Livefyre-bundel: `com.adobe.cq.social.cq-social-livefyre`.
   * Klik **Einde**.

1. ***maak Livefyre poller onbruikbaar:***

   * Navigeer in CRXDE Lite naar `/etc/importers/polling/livefyre-poller/jcr:content` .
   * Voeg toe een bezit *toegelaten* type *Van Boole*.
   * Plaats **Toegelaten bezit** om **vals** te zijn.

### 2. Hoe kan ik Oak Index-gegevens toevoegen? {#add-oak-index-info}

AEM Screens maakt indexdefinities voor de query&#39;s die door het product worden gebruikt.
Als er om het even welk *Traversal WARNs van de Vraag* in `error.log` zijn, creeer een douaneindex voor uw vraag. Zie [ Vormend de Indexen ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#configuring-the-indexes) voor meer details.

U kunt ook een extra middel op [ Documentatie van Oak ](https://jackrabbit.apache.org/oak/docs/query/lucene.html) zien.


### 3. Wat is vereist om v3-manifest te configureren? {#configure-v3}

Ga als volgt te werk om v3-manifest in te schakelen:

* Dispatcher bijwerken.
Zie [ het Vormen Dispatcher voor Duidelijke Versie v3 ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3) voor meer details.

* Aangepaste component bijwerken.
Zie [ Malplaatje voor de Handlers van de Douane ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers) voor meer details.

* Schakel ContentSync uit in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` .

* SmartSync inschakelen in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl` .

* Bewerken `channel/experience fragment/page components` .

* Navigeer aan **Offline Config** tabel.

* Ga `clientlibs ` en omslagen voor statische dossiers in die aan manifest moeten worden toegevoegd.

### 4. Wat moet u doen als, na het pakket screens-cloud-ams-pkg-0.0.20, screens-cloud-ams-pkg-0.0.16 en de schermen core bundles geïnstalleerd maar niet actief zijn?

Installeer een minimale versie van AEM 6.5-functiepakket 8 voor de AMS-aansluiting. Zie [ Beschikbaarheid ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202105#availability) zodat kunt u de minimumversie van het Pak van de Eigenschap van AEM Screens krijgen.

### 5. Hoe te om de dienst van Externalzer van de Verbinding van CQ in Screens te vormen?

De dienst wordt gebruikt om openbare hostname voor de auteur te bepalen en instanties te publiceren, en de waarden worden dan gebruikt om de apparatenserver URLs en ook voor het richten ContextHub bij te werken.

De dienst van Externalzer van de Verbinding van CQ in Screens kan op de volgende manier worden gevormd:

1. Navigeren naar `http://localhost:4502/system/console/configMgr`
1. Day CQ Link ExternalAlizer
1. Wijzig zo nodig de hostnaam voor de `author/publish` -items