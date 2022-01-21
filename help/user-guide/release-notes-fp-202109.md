---
title: Opmerkingen bij de release voor Feature Pack 202109
description: Volg deze pagina voor informatie over AEM Screens Feature Pack 202109, uitgebracht op 23 september 2021.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
source-git-commit: b56844c66bfa980013b610523842c7ac0c30f44d
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>We raden u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). Schermen bieden onderhoudsondersteuning voor AEM 6.3 Schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 9 uitgebracht.

U kunt het nieuwste functiepakket voor de AEM Screens 6.5.9-versie downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID. Navigeren naar **Adobe Experience Manager** tabblad en zoeken naar **Schermen** om het nieuwste functiepakket met de naam **AEM 6.5 Schermen FP9**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202109 is 23 september 2021.

### Wat is er nieuw? {#what-is-new}

* **Ondersteuning van miniaturen voor video&#39;s**

   Ondersteuning voor miniaturen voor video&#39;s die nu worden ondersteund in AEM Screens. Een inhoudauteur kan een duimnagel voor video&#39;s bepalen zodat het beeld als placeholder kan worden gebruikt en behoorlijk het playback en richten van inhoud testen, terwijl de daadwerkelijke video door het aangewezen team wordt gebeëindigd. De afbeelding kan ook worden gebruikt voor het geval dat het afspelen van de video mislukt.
Zie [Ondersteuning van miniaturen voor video&#39;s](/help/user-guide/thumbnail-support.md) voor meer informatie .

* **Standaardafspeelcontrole**

   AEM Screens ondersteunt nu elementaire afspeelcontrole. De speler zal nu diverse playbackmetriek met elk melden pingelt (gebrek aan 30 seconden). Op basis van de meetgegevens kunnen verschillende randgevallen worden gedetecteerd (geplakte ervaring, leeg scherm, planningsprobleem, enz.). Met deze functie kan het team op afstand controleren of een speler inhoud correct afspeelt, de reactiviteit verbetert tot lege schermen of gebroken ervaringen in het veld en het risico dat de eindgebruiker een verbroken ervaring krijgt verkleind.
Zie [Standaardafspeelcontrole](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/installing-screens-player.html?lang=en#playback-monitoring) voor meer informatie .

* **Updates voor Rapport voor toewijzing van inhoud**

   Rapport voor toewijzing van inhoud is nu geoptimaliseerd en verbeterd dankzij verbeterde gebruikerservaring. In het downloadbare rapport worden verbeterde entiteiten met betrekking tot de speler, zoals locaties, weergaven en apparaten, op één spreadsheettabblad weergegeven en wordt informatie over de inhoudsprovider weergegeven, zoals kanalen en elementen op een ander tabblad.
Zie [Rapport Inhoudstoewijzing](/help/user-guide/content-assignment-report.md) voor meer informatie .

* **Aangepaste uitvoeringen**

   De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd.

   Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Zie [Adaptieve uitvoeringen: Overzicht en configuraties van architectuur](/help/user-guide/adaptive-renditions.md) voor meer informatie .

   Bovendien kunt u als AEM Screens Content Author uw middelen configureren voor het gebruik van Aangepaste uitvoeringen en tevens uw apparaten migreren voor grote netwerken om deze functie te gebruiken, in uw AEM Screens-kanalen. Zie [Adaptieve uitvoeringen gebruiken in AEM Screens](/help/user-guide/using-adaptive-renditions.md) voor meer informatie .

* **Ondersteuning voor V3-manifest**

   U kunt Dispatcher nu configureren voor Manifest Version v3. Voor het inschakelen van v3-manifest moet u:

   * Wis om het even welke hangende off-line inhoudstaken in zowel auteur als gepubliceerd

      * Naar crx/de navigeren in auteur en publiceren

      * Klik op Gereedschappen —> Query uitvoeren

      * In het vraaggebruik `/jcr:root/var/eventing/jobs/assgined//element(*,slingevent:Job)[\@event.job.topic='screens/offline_content_update']`

      * Hiermee worden alle taken met offline inhoud vermeld die momenteel worden uitgevoerd of in behandeling zijn in de wachtrij

      * Wacht tot er geen off-line inhoudstaken meer van de vraag zijn teruggekeerd
   * ContentSync uitschakelen in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`

   * SmartSync inschakelen in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`

   * Verzender bijwerken

   * Aangepaste component bijwerken


   * Zie [Dispatcher configureren voor manifestversie v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=en#configuring-dispatcherv3) voor meer informatie .
   * Als u aangepaste componenten gebruikt als onderdeel van v3-manifesten, raadpleegt u [Sjabloon voor aangepaste handlers](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=en#custom-handlers).



### Opgeloste problemen {#bug-fixes}

**Player-zijde**

* Fouten met het in cache plaatsen van bestanden zijn opgelost door elementen te vervangen door uitvoeringen.

* De spelers stellen nu alleen elementen van uitvoeringen beschikbaar als er renditie-toewijzing is.

* Verbeterd pingelen om opnieuw voor authentiek te verklaren als de reactie ongeldig JSON is.

* Numerieke kanaalnamen/rollen hebben een leeg scherm veroorzaakt.

* Download geoptimaliseerde uitvoeringen via SmartSync.

* De toewijzing is omgezet in een lijst met vertoningssleutels.

* Verwijderde toegang tot `cmd.exe` en `reg.exe` in de Windows-speler.

* Een speler moet de laatste geslaagde afspeelgebeurtenis melden.

* Een speler moet zijn playbackstatus melden.

* Speler downloadt geen Middelen opnieuw wanneer `ALL` Cache is gewist.

* Als Player-beheerder kunt u nu een spelernaam kiezen.

* Het verwijderen van kanaaltoewijzing uit de weergave wordt niet weerspiegeld in de speler.

* Als de speler opnieuw wordt geladen terwijl de kanaalupdate wordt gedownload, negeert de speler de update.

* De component Ingesloten pagina respecteert nu de aanraakgebeurtenis.

* Externe provisioning van Tizen Player wordt nu ondersteund.

**Server-zijde**

* Doelvideo wordt niet weergegeven
* Voorwaarde bij het uitzenden van weergavegegevens verschuiven naar volgende waarden.

* Kanaalvoorvertoning werkt niet voor kanalen met video&#39;s.

* De modus Voorvertoning is leeg voor het gesplitste schermkanaal.

* Videominiaturen worden leeg gerenderd met ingeschakelde adaptieve uitvoeringen.

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

* Speler meldt nu zijn playbackstatus.

* Video is afgespeeld in `Tiny mode` en wordt niet afgespeeld als video op een volledig scherm op het apparaat. Het probleem is nu opgelost.

### Uitgebrachte AEM Screens-spelers {#released-aem-screens-players}

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 9 van de Eigenschap:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### Downloads voor AEM Screens Player  {#aem-screens-player-downloads}

Als u de nieuwste AEM Screens-speler wilt downloaden en meer wilt weten over de opgeloste problemen, raadpleegt u **[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/index.html)**.
