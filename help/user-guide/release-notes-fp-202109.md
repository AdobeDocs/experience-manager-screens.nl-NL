---
title: Opmerkingen bij de release voor Feature Pack 202109
description: Volg deze pagina voor informatie over het AEM Screens Feature Pack 202105, uitgebracht op 23 september 2021.
feature: Feature Pack
role: Developer
level: Intermediate
source-git-commit: ec58cd9171e359b451eaad7015d42b41ef1bff3f
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>We raden u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). Schermen bieden onderhoudsondersteuning voor AEM 6.3 Schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 9 uitgebracht.

U kunt het recentste eigenschappak voor AEM Screens 6.5.9 Versie van [het Portaal van de Distributie van de Software](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer naar **Adobe Experience Manager** tab en zoek **Screens** om het nieuwste functiepakket met de naam **AEM 6.5 Screens FP9** te krijgen.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202109 is 23 september 2021.

### Wat is er nieuw? {#what-is-new}

* **Ondersteuning van miniaturen voor video&#39;s**

   Ondersteuning voor miniaturen voor video&#39;s die nu worden ondersteund in AEM Screens. Een inhoudauteur kan een duimnagel voor video&#39;s bepalen zodat het beeld als placeholder kan worden gebruikt en behoorlijk het playback en richten van inhoud testen, terwijl de daadwerkelijke video door het aangewezen team wordt gebeëindigd. De afbeelding kan ook worden gebruikt voor het geval dat het afspelen van de video mislukt.
Zie [Ondersteuning van miniaturen voor video&#39;s](/help/user-guide/thumbnail-support.md) voor meer informatie.

* **Standaardafspeelcontrole**

   AEM Screens ondersteunt nu elementaire afspeelcontrole. De speler zal nu diverse playbackmetriek met elk melden pingelt (gebrek aan 30 seconden). Op basis van de meetgegevens kunnen verschillende randgevallen worden gedetecteerd (geplakte ervaring, leeg scherm, planningsprobleem, enz.). Met deze functie kan het team op afstand controleren of een speler inhoud correct afspeelt, de reactiviteit verbetert tot lege schermen of gebroken ervaringen in het veld en het risico dat de eindgebruiker een verbroken ervaring krijgt verkleind.
Zie [Basic Playback Monitoring](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/installing-screens-player.html?lang=en#playback-monitoring) voor meer informatie.

* **Updates voor Rapport voor toewijzing van inhoud**

   Rapport voor toewijzing van inhoud is nu geoptimaliseerd en verbeterd dankzij verbeterde gebruikerservaring. In het downloadbare rapport worden verbeterde entiteiten met betrekking tot de speler, zoals locaties, weergaven en apparaten, op één spreadsheettabblad weergegeven en wordt informatie over de inhoudsprovider weergegeven, zoals kanalen en elementen op een ander tabblad.
Zie [Rapport Inhoudstoewijzing](/help/user-guide/content-assignment-report.md) voor meer informatie.

* **Aangepaste uitvoeringen**

   De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd.

   Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Zie [Aangepaste uitvoeringen: Overzicht van architectuur en configuraties](/help/user-guide/adaptive-renditions.md) voor meer informatie

   Bovendien kunt u als AEM Screens Content Author nu Adaptive Renditions gebruiken in uw AEM Screens-project en ook een migratiestrategie toepassen voor grote netwerken.

* **Ondersteuning voor V3-manifest**

   U kunt Dispatcher nu configureren voor Manifest Version v3. Raadpleeg [Dispatcher configureren voor manifestversie v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=en#configuring-dispatcherv3) voor meer informatie.
Bovendien, als u douanecomponenten als deel van v3 manifests gebruikt, zie [Malplaatje voor de Handlers van de Douane](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=en#custom-handlers).


### Opgeloste problemen {#bug-fixes}

**Player-zijde**

* Fouten met het in cache plaatsen van bestanden zijn opgelost door elementen te vervangen door uitvoeringen.

* De spelers stellen nu alleen elementen van uitvoeringen beschikbaar als er renditie-toewijzing is.

* Verbeterd pingelen om opnieuw voor authentiek te verklaren als de reactie ongeldig JSON is.

* Numerieke kanaalnamen/rollen hebben een leeg scherm veroorzaakt.

* Download geoptimaliseerde uitvoeringen via SmartSync.

* De toewijzing is omgezet in een lijst met vertoningssleutels.

* Toegang tot `cmd.exe` en `reg.exe` in de vensterspeler is verwijderd.

* Een speler moet de laatste geslaagde afspeelgebeurtenis melden.

* Een speler moet de afspeelstatus melden.

* De speler herdownloadt geen Middelen wanneer `ALL` Geheime voorgeheugen wordt ontruimd.

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

* Offline manifest die de verzoekparameter `wcmmode` voor HTML ingang gebruikt, die het oncacheable maakt.

* Lege, dynamische ingesloten reeks heeft soms een leeg scherm veroorzaakt.

* Speler meldt nu zijn playbackstatus.

* Video werd afgespeeld in `Tiny mode` en niet als video op volledig scherm op apparaat en het probleem is nu opgelost.

### Uitgebrachte AEM Screens-spelers {#released-aem-screens-players}

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 9 van de Eigenschap:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### Downloads voor AEM Screens Player  {#aem-screens-player-downloads}

Raadpleeg **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)** voor meer informatie over de opgeloste problemen.
