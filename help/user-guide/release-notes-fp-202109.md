---
title: Opmerkingen bij de release voor Feature Pack 202109
description: Meer informatie over het AEM Screens Feature Pack 202109 dat op 23 september 2021 is uitgebracht.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). AEM Screens biedt onderhoudsondersteuning voor AEM 6.3-schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 9 uitgebracht.

U kunt het nieuwste functiepakket voor de AEM Screens 6.5.9-versie downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID. Navigeren naar **Adobe Experience Manager** tabblad en zoeken naar **Schermen** om het nieuwste functiepakket met de naam **AEM 6.5 Schermen FP9**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202109 is 23 september 2021.

### Wat is er nieuw? {#what-is-new}

* **Ondersteuning van miniaturen voor video&#39;s**

  Ondersteuning voor miniaturen voor video&#39;s die nu worden ondersteund in AEM Screens. Een auteur van inhoud definieert een miniatuur voor video&#39;s, zodat de afbeelding als plaatsaanduiding wordt gebruikt. Ook wordt het afspelen en activeren van inhoud op de juiste wijze getest, terwijl de video zelf door het juiste team wordt voltooid. De afbeelding kan ook worden gebruikt als het afspelen van de video mislukt.
Zie [Ondersteuning van miniaturen voor video&#39;s](/help/user-guide/thumbnail-support.md) voor meer informatie .

* **Standaardafspeelcontrole**

  AEM Screens ondersteunt nu elementaire afspeelcontrole. De speler rapporteert nu verschillende playbackmetriek met elk pingelt (gebrek aan 30 seconden). Op basis van de meetgegevens worden verschillende randgevallen gedetecteerd (geplakte ervaring, leeg scherm, planningsprobleem, enzovoort). Met deze functie kan het team op afstand controleren of een speler de inhoud correct afspeelt en de reactiviteit op lege schermen verbetert of de ervaringen in het veld verbroken zijn. Het vermindert ook het risico om een gebroken ervaring aan het eind - gebruiker te tonen.
Zie [Standaardafspeelcontrole](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/installing-screens-player#playback-monitoring) voor meer informatie .

* **Updates voor Rapport voor toewijzing van inhoud**

  Rapport voor toewijzing van inhoud is nu geoptimaliseerd en verbeterd dankzij verbeterde gebruikerservaring. In het downloadbare rapport worden verbeterde spelergerelateerde entiteiten zoals locaties, weergaven en apparaten op één spreadsheettabblad weergegeven en wordt informatie over de inhoudsprovider weergegeven, zoals kanalen en elementen op een ander tabblad.
Zie [Rapport Inhoudstoewijzing](/help/user-guide/content-assignment-report.md) voor meer informatie .

* **Aangepaste uitvoeringen**

  Met adaptieve uitvoeringen kunnen de apparaten automatisch op de beste uitvoering voor een apparaat klikken op basis van door de klant gedefinieerde regels.

  Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Zie [Adaptieve uitvoeringen: Overzicht van architectuur en configuraties](/help/user-guide/adaptive-renditions.md) voor meer informatie .

  Bovendien kunt u als AEM Screens Content Author uw middelen configureren voor het gebruik van Adaptieve uitvoeringen. U kunt uw apparaten ook migreren voor grote netwerken om deze functie in uw AEM Screens-kanalen te gebruiken. Zie [Adaptieve uitvoeringen gebruiken in AEM Screens](/help/user-guide/using-adaptive-renditions.md) voor meer informatie .

* **Ondersteuning voor V3-manifest**

  U kunt de Dispatcher nu configureren voor Manifest Version v3. Ga als volgt te werk om v3-manifest in te schakelen:

   * Wis alle taken met offline inhoud die in behandeling zijn, zowel in de auteur als gepubliceerd.

      * Navigeer naar CRXDE Lite in Auteur en Publiceer.

      * Klik op Opties > Query.

      * In de query gebruikt u `/jcr:root/var/eventing/jobs/assgined//element(*,slingevent:Job)[\@event.job.topic='screens/offline_content_update']`.

      * Hier worden alle taken met offlineinhoud weergegeven die momenteel worden uitgevoerd of in behandeling zijn in de wachtrij.

      * Wacht tot er geen off-line inhoudstaken meer van de vraag zijn teruggekeerd.

   * ContentSync uitschakelen in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`.

   * SmartSync inschakelen in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`.

   * Dispatcher bijwerken.

   * Aangepaste component bijwerken.


   * Zie [Dispatcher configureren voor manifestversie v3](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3) voor meer informatie .
   * Als u aangepaste componenten gebruikt als onderdeel van v3-manifesten, raadpleegt u [Sjabloon voor aangepaste handlers](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).


### Opgeloste problemen {#bug-fixes}

**Speler**

* Fouten met het in cache plaatsen van bestanden zijn opgelost door elementen te vervangen door uitvoeringen.

* De spelers stellen nu alleen elementen van uitvoeringen beschikbaar als er renditie-toewijzing is.

* Verbeterd pingelen om opnieuw te verifiëren als de reactie ongeldig JSON is.

* Numerieke kanaalnamen/rollen hebben een leeg scherm veroorzaakt.

* Download geoptimaliseerde uitvoeringen via SmartSync.

* De toewijzing is omgezet in een lijst met vertoningssleutels.

* Toegang tot `cmd.exe` en `reg.exe` in de Windows-speler.

* Een speler moet de laatste geslaagde afspeelgebeurtenis melden.

* Een speler moet de afspeelstatus melden.

* De speler downloadt geen Middelen opnieuw wanneer `ALL` Cache is gewist.

* Als Player-beheerder kunt u nu een spelernaam kiezen.

* Het verwijderen van kanaaltoewijzing uit de weergave wordt niet weerspiegeld in de speler.

* Als de speler opnieuw wordt geladen terwijl de kanaalupdate wordt gedownload, negeert de speler de update.

* De component Ingesloten pagina respecteert nu de aanraakgebeurtenis.

* Externe provisioning van Tizen Player wordt nu ondersteund.

**Server-zijde**

* Doelvideo wordt niet weergegeven
* Vervang weergavevoorwaarden voor het uitzenden van weergavegegevens naar volgende bewerkingen.

* Kanaalvoorvertoning werkt niet voor kanalen met video&#39;s.

* De modus Voorvertoning is leeg voor het gesplitste schermkanaal.

* Videominiaturen worden leeg weergegeven met ingeschakelde adaptieve uitvoeringen.

* Kanaalmanifest automatisch bijwerken als de pagina waarnaar wordt verwezen, wordt gepubliceerd.

* Verwijderde apparaten blokkeren nu de wachtrij voor schermreplicatie niet.

* Manifest bevatte geen doelinhoud of ingesloten sitepagina&#39;s. Dit is nu opgelost.

* De nieuwe component van het kernbeeld wordt nu toegevoegd aan kanaalmanifest.

* Het downloaden van geoptimaliseerde uitvoeringen via SmartSync wordt nu ondersteund.

* Geoptimaliseerde uitvoering afspelen voor alle elementen.

* Toegevoegde ondersteuning voor meerdere typen inhoudsproviders

* De ingesloten strategie voor het afspelen van reeksen is verbroken en deze is nu opgelost.

* Offline manifest die de verzoekparameter gebruikt `wcmmode` voor de vermelding van html, waardoor deze ontoegankelijk wordt.

* Lege, dynamische ingesloten reeks heeft soms een leeg scherm veroorzaakt.

* De speler rapporteert nu zijn playbackstatus.

* Video is afgespeeld in `Tiny mode` en wordt niet afgespeeld als video op een volledig scherm op het apparaat. Het probleem is nu opgelost.

### Uitgebrachte AEM Screens-spelers

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 9 van de Eigenschap:

* ChromeOS
* Windows
* Tizen
* Android™
* Linux®

#### Downloads voor AEM Screens Player

Als u de nieuwste AEM Screens-speler wilt downloaden en meer wilt weten over de opgeloste problemen, raadpleegt u **[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/index.html)**.
