---
title: Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics
seo-title: Embedding a REACT application using the AEM SPA Editor and Integrating with AEM Screens Analytics
description: Volg deze pagina om te leren hoe te om een interactieve enige paginatoepassing in te bedden gebruikend REACT (of Angular) gebruikend de redacteur van de SPA van de AEM die door bedrijfsberoeps in AEM kunnen worden gevormd en ook hoe te om uw interactieve toepassing met off-line Adobe Analytics te integreren.
seo-description: Follow this page to learn how to embed an interactive single page application using REACT (or Angular) using the AEM SPA editor that can be configured by business professionals in AEM and also how to integrate your interactive application with offline Adobe Analytics.
uuid: fb56ede0-7b36-4f47-b9e5-d806c9a3c707
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: e4ecc179-e421-4687-854c-14d31bed031d
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 7dc7d07e-cd94-4ce1-a106-98669be62046
source-git-commit: ffc44dbf1822ff4d0e875ef693d48dece248d555
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics {#embedding-a-react-application-using-the-aem-spa-editor-and-integrating-with-aem-screens-analytics}

In deze sectie wordt beschreven hoe u een interactieve toepassing van één pagina insluit met REACT (of Angular) met behulp van de AEM SPA-editor die door professionals in AEM kan worden geconfigureerd en hoe u uw interactieve toepassing kunt integreren met offline Adobe Analytics.

## De AEM SPA Editor gebruiken {#using-the-aem-spa-editor}

Voer de onderstaande stappen uit om de AEM SPA Editor te gebruiken:

1. De AEM SPA Editor-reactie klonen op [https://github.com/adobe/aem-spa-project-archetype.](https://github.com/adobe/aem-spa-project-archetype)

   >[!NOTE]
   >
   >Dit archetype leidt tot een minimaal project van Adobe Experience Manager als uitgangspunt voor uw eigen SPA projecten. De eigenschappen die moeten worden verstrekt wanneer het gebruiken van dit archetype staat toe om als gewenst alle delen van dit project te noemen.

1. Volg de readme instructies om een AEM redacteursarchetype project tot stand te brengen SPA:

   ```
   mvn clean install archetype:update-local-catalog
   mvn archetype:crawl
   
   mvn archetype:generate \
   -DarchetypeCatalog=internal \
   -DarchetypeGroupId=com.adobe.cq.spa.archetypes \
   -DarchetypeArtifactId=aem-spa-project-archetype \
   -DarchetypeVersion=1.0.3-SNAPSHOT \
   ```

   >[!NOTE]
   >
   >We gebruiken de **GroupId** als ***com.adobe.aem.screens*** en de **ArtifactId** als ***Mijn SPA*** (de standaardinstellingen). U kunt zo nodig uw eigen keuze maken.

1. Zodra het project wordt gecreeerd, of gebruik winde of redacteur van uw keus en voer het geproduceerde Geweven project in.
1. Distribueren naar uw lokale AEM met de opdracht ***mvn clean install -PautoInstallPackage***.

### Inhoud bewerken in de REACT-app {#editing-content-in-the-react-app}

De inhoud in de REACT-app bewerken:

1. Navigeren naar `https://localhost:4502/editor.html/content/mysamplespa/en/home.html` (vervang de hostnaam, poort en projectnaam, indien van toepassing).
1. U zou de tekst moeten kunnen uitgeven die in de Hello wereldtoepassing wordt getoond.

### De interactieve REACT-app toevoegen aan AEM Screens {#adding-the-interactive-react-app-to-aem-screens}

Voer de onderstaande stappen uit om de interactieve REACT-app aan AEM Screens toe te voegen:

1. Maak een nieuw AEM Screens-project. Zie [Projecten maken en beheren](creating-a-screens-project.md) voor meer informatie .

1. Een nieuwe **Toepassingskanaal** (bij voorkeur) (of 1x1-sjabloon of multikanaalskanaal) in het dialoogvenster **Kanalen** map van uw project Screens.

   >[!NOTE]
   >**Volgkanalen** worden afgeraden voor dit gebruik omdat ze inherent een diapresentatielogica hebben die conflicteert met de interactieve aard van de ervaring
   >Zie [Kanalen maken en beheren](managing-channels.md) voor meer informatie .


1. Bewerk een willekeurig volgnummer en sleep en zet een ingesloten pagina-component neer.

   Zie [Componenten toevoegen aan een kanaal](adding-components-to-a-channel.md) voor meer informatie .

   >[!NOTE]
   >
   >Voeg de gebruikersinteractiegebeurtenis toe wanneer u het kanaal toewijst aan de weergave.

1. Klikken op **Bewerken** in de actiebalk om de eigenschappen van het kanaal te bewerken.

   ![screen_shot_2019-02-15at100555am](assets/screen_shot_2019-02-15at100555am.png)

1. Sleep de **Ingesloten pagina** of hergebruik de bestaande component in een toepassingskanaal en selecteer bijvoorbeeld de startpagina onder de mysamplespa-toepassing, ***/content/mysamplespa/nl/home***.

   ![screen_shot_2019-02-15at101104am](assets/screen_shot_2019-02-15at101104am.png)

1. Wijs het kanaal toe aan een weergave.

   >[!NOTE]
   >Voeg de gebruikersinteractiegebeurtenis toe wanneer u het kanaal toewijst aan de weergave.

1. Registreer een speler tegen dit project en wijs het aan de vertoning toe. U moet nu uw interactieve toepassing kunnen zien uitvoeren op AEM Screens.

   Zie [Apparaatregistratie](device-registration.md) voor meer informatie over het registreren van een apparaat.

## De SPA integreren met Adobe Analytics met offlinemogelijkheden via AEM Screens {#integrating-the-spa-with-adobe-analytics-with-offline-capability-through-aem-screens}

Volg de onderstaande stappen om de SPA met Adobe Analytics te integreren met offline mogelijkheden via AEM Screens:

1. Configureer Adobe Analytics in AEM Screens.

   Zie [Adobe Analytics configureren met AEM Screens](configuring-adobe-analytics-aem-screens.md) voor meer informatie over het uitvoeren van reeksen in Adobe Analytics met AEM Screens en het verzenden van aangepaste gebeurtenissen met behulp van offline Adobe Analytics.

1. Bewerk uw reactie-app in de IDE/editor van uw keuze (met name de tekstcomponent of andere component die u wilt gebruiken om gebeurtenissen uit te zenden).
1. Voeg bij de klikgebeurtenis of andere gebeurtenis die u voor uw component wilt vastleggen de analysegegevens toe met behulp van het standaardgegevensmodel.

   Zie [Adobe Analytics configureren met AEM Screens](configuring-adobe-analytics-aem-screens.md)Zie voor meer informatie.

1. Roep de AEM Screens Analytics API aan om de gebeurtenis offline op te slaan en in bursts naar Adobe Analytics te verzenden.

   Bijvoorbeeld,

   ```
   handleClick() {
       if ((window.parent) && (window.parent.CQ) && (window.parent.CQ.screens) && (window.parent.CQ.screens.analytics))
       {
           var analyticsEvent = {};
           analyticsEvent['event.type'] = 'play'; // Type of event
    analyticsEvent['event.coll_dts'] = new Date().toISOString(); // Start of collecting the event
    analyticsEvent['event.dts_start'] = new Date().toISOString(); // Event start
    analyticsEvent['content.type'] = 'Washing machine'; // Mime Type or product category
    analyticsEvent['content.action'] = 'Path to the washing machine asset in AEM'; // Path in AEM to relevant asset
    analyticsEvent['trn.product'] = 'Washing machine Model number'; // Product being explored
    analyticsEvent['trn.amount'] = 1000; // Product pricing or other numeric value or weight
    analyticsEvent['event.dts_end'] = new Date().toISOString(); // Event end
    analyticsEvent['event.count'] = 100; // Numeric value that may count a number of clicks or keystrokes or wait time in seconds for example
    analyticsEvent['event.value'] = 'My favorite analytics event';
           analyticsEvent['trn.quantity'] = 10; // Quantity of product selection
    analyticsEvent['event.subtype'] = 'end'; // Event subtype if applicable
    window.parent.CQ.screens.analytics.sendTrackingEvent(analyticsEvent);
       }
   }
   ```

   >[!NOTE]
   >
   >De spelerfirmware voegt automatisch meer informatie over de speler en de bijbehorende runtimeomgeving toe aan de aangepaste analysegegevens die u verzendt. Daarom hoeft u wellicht geen informatie op laag niveau over het besturingssysteem en het apparaat op te nemen, tenzij dit absoluut noodzakelijk is. U hoeft zich alleen te richten op de bedrijfsanalysegegevens.
