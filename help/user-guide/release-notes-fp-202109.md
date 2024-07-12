---
title: Opmerkingen bij de release voor Feature Pack 202109
description: Meer informatie over het AEM Screens Feature Pack 202109 dat op 23 september 2021 is uitgebracht.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). AEM Screens biedt onderhoudsondersteuning voor het AEM 6.3 Screens-platform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 9 uitgebracht.

U kunt het recentste Pak van de Eigenschap voor AEM Screens 6.5.9 Versie van het [ Portaal van de Distributie van de Software ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer aan het **Adobe Experience Manager** lusje en onderzoek naar **Screens** om het recentste Pak van de Eigenschap te krijgen dat als **wordt genoemd AEM 6.5 Screens FP9**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202109 is 23 september 2021.

### Wat is er nieuw? {#what-is-new}

* **Steun van de Duimnagel voor Video&#39;s**

  Ondersteuning voor miniaturen voor video&#39;s die nu worden ondersteund in AEM Screens. Een Content Author definieert een miniatuur voor video&#39;s, zodat de afbeelding als plaatsaanduiding wordt gebruikt. Ook wordt het afspelen en activeren van inhoud op de juiste wijze getest, terwijl het juiste team de werkelijke video voltooit. De afbeelding kan ook worden gebruikt als het afspelen van de video mislukt.
Zie [ Steun van de Duimnagel voor Video&#39;s ](/help/user-guide/thumbnail-support.md) voor meer details.

* **Basis Controle van de Playback**

  AEM Screens ondersteunt nu elementaire afspeelcontrole. De speler rapporteert nu verschillende playbackmetriek met elk pingelt (gebrek aan 30 seconden). Op basis van de meetgegevens worden verschillende randgevallen gedetecteerd (geplakte ervaring, leeg scherm, planningsprobleem, enzovoort). Met deze functie kan het team op afstand controleren of een speler de inhoud correct afspeelt en de reactiviteit op lege schermen verbetert of de ervaringen in het veld verbroken zijn. Het vermindert ook het risico om een gebroken ervaring aan het eind - gebruiker te tonen.
Zie [ Basis Controle van de Playback ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/installing-screens-player#playback-monitoring) voor meer details.

* **Updates aan het Rapport van de Toewijzing van de Inhoud**

  Rapport voor toewijzing van inhoud is nu geoptimaliseerd en verbeterd dankzij een verbeterde gebruikerservaring. Het downloadbare rapport geeft verbeterde entiteiten met betrekking tot spelers weer. Dergelijke entiteiten omvatten plaatsen, vertoningen, en apparaten in één spreadsheetlusje. Het omvat ook de informatie van de inhoudsleverancier zoals kanalen en activa in andere tabel.
Zie [ Rapport van de Toewijzing van de Inhoud ](/help/user-guide/content-assignment-report.md) voor meer details.

* **Aangepaste Vertoningen**

  Met adaptieve uitvoeringen kan het apparaat automatisch op de beste uitvoering voor een apparaat klikken op basis van door de klant gedefinieerde regels.

  Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Zie [ Aangepaste Vertoningen: Het Overzicht van de Architectuur en Configuraties ](/help/user-guide/adaptive-renditions.md) voor meer details.

  Bovendien kunt u als AEM Screens Content Author uw middelen configureren voor het gebruik van Adaptieve uitvoeringen. U kunt uw apparaten ook migreren voor grote netwerken om deze functie in uw AEM Screens-kanalen te gebruiken. Zie [ Gebruikend Aangepaste Vertoningen in AEM Screens ](/help/user-guide/using-adaptive-renditions.md) voor meer details.

* **Steun voor V3 Manifests**

  U kunt nu de Dispatcher for Manifest versie v3 configureren. Ga als volgt te werk om v3-manifest in te schakelen:

   * Wis alle taken met offline inhoud die in behandeling zijn, zowel in de auteur als gepubliceerd.

      * Navigeer naar CRXDE Lite in Auteur en Publish.

      * Klik op Opties > Query.

      * Gebruik `/jcr:root/var/eventing/jobs/assgined//element(*,slingevent:Job)[\@event.job.topic='screens/offline_content_update']` in de query.

      * Hier worden alle taken met offlineinhoud weergegeven die momenteel worden uitgevoerd of in behandeling zijn in de wachtrij.

      * Wacht tot er geen off-line inhoudstaken meer van de vraag zijn teruggekeerd.

   * Schakel ContentSync uit in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` .

   * SmartSync inschakelen in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl` .

   * Dispatcher bijwerken.

   * Werk de aangepaste component bij.


   * Zie [ het Vormen Dispatcher voor Duidelijke Versie v3 ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3) voor meer details.
   * Als u douanecomponenten als deel van v3 manifests gebruikt, zie [ Malplaatje voor de Handlers van de Douane ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).


### Opgeloste problemen {#bug-fixes}

**Kant van de Speler**

* Fouten met het in cache plaatsen van bestanden zijn opgelost door elementen te vervangen door uitvoeringen.

* De spelers stellen nu alleen elementen van uitvoeringen beschikbaar als er renditie-toewijzing is.

* Verbeterd pingelen om opnieuw te verifiëren als de reactie ongeldig JSON is.

* Numerieke kanaalnamen/rollen hebben een leeg scherm veroorzaakt.

* Gebruik SmartSync om geoptimaliseerde uitvoeringen te downloaden.

* De toewijzing is omgezet in een lijst met vertoningssleutels.

* De toegang tot `cmd.exe` en `reg.exe` is verwijderd in Windows Player.

* Een speler moet de laatste geslaagde afspeelgebeurtenis melden.

* Een speler moet de afspeelstatus melden.

* Assets wordt niet opnieuw gedownload wanneer de cache van `ALL` wordt gewist.

* Als Player-beheerder kunt u nu een spelernaam kiezen.

* Het verwijderen van kanaaltoewijzing uit de weergave wordt niet weerspiegeld in de speler.

* Als de speler opnieuw wordt geladen terwijl de kanaalupdate wordt gedownload, negeert de speler de update.

* De component Ingesloten pagina respecteert nu de aanraakgebeurtenis.

* Externe provisioning van de Tizen-speler wordt nu ondersteund.

**Zijde van de Server**

* Doelvideo wordt niet weergegeven
* Vervang weergavevoorwaarden voor het uitzenden van weergavegegevens naar volgende bewerkingen.

* Kanaalvoorvertoning werkt niet voor kanalen met video&#39;s.

* De modus Voorvertoning is leeg voor het gesplitste schermkanaal.

* Videominiaturen worden leeg weergegeven met ingeschakelde adaptieve uitvoeringen.

* Werk het kanaalmanifest automatisch bij als de pagina waarnaar wordt verwezen, wordt gepubliceerd.

* Verwijderde apparaten blokkeren nu de Screens-replicatiereeks niet.

* Het manifest bevatte geen gerichte inhoud of plaatsen ingebedde pagina&#39;s. Deze bug is nu opgelost.

* Er wordt nu een nieuwe kerncomponent voor de afbeelding toegevoegd aan het kanaalmanifest.

* Het downloaden van geoptimaliseerde uitvoeringen via SmartSync wordt nu ondersteund.

* Geoptimaliseerde uitvoering afspelen voor alle elementen.

* Toegevoegde ondersteuning voor meerdere typen inhoudsproviders

* De strategie voor het afspelen van de ingesloten reeks is verbroken en deze bug is nu opgelost.

* Offline manifest die de verzoekparameter `wcmmode` voor HTML- ingang gebruikt, die het oncacheable maakt.

* Lege, dynamische ingesloten reeks heeft soms een leeg scherm veroorzaakt.

* De speler rapporteert nu de afspeelstatus.

* Video werd afgespeeld in `Tiny mode` en niet als video op een volledig scherm op het apparaat en het probleem is nu opgelost.

### Uitgebrachte AEM Screens-spelers

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 9 van de Eigenschap:

* ChromeOS
* Windows
* Tizen
* Android™
* Linux®

#### Downloads voor AEM Screens Player

Om de recentste Speler van AEM Screens te downloaden en meer over de insectenmoeilijke situaties te leren, zie **[Downloads van de Speler van AEM Screens ](https://download.macromedia.com/screens/index.html)**.
