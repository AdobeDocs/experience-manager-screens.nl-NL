---
title: Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics
description: Leer hoe u een interactieve toepassing van één pagina insluit met REACT (of Angular) met de AEM SPA editor.
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: e4ecc179-e421-4687-854c-14d31bed031d
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 7dc7d07e-cd94-4ce1-a106-98669be62046
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 0%

---

# Een REACT-toepassing insluiten met de AEM SPA Editor en integreren met AEM Screens Analytics {#embedding-a-react-application-using-the-aem-spa-editor-and-integrating-with-aem-screens-analytics}

U kunt een interactieve toepassing van één pagina insluiten met REACT (of Angular). U doet dit door de AEM SPA redacteur te gebruiken die de bedrijfsberoeps in AEM vormen. U kunt ook leren hoe u uw interactieve toepassing kunt integreren met offline Adobe Analytics.

## De AEM SPA Editor gebruiken {#using-the-aem-spa-editor}

Voer de onderstaande stappen uit om de AEM SPA Editor te gebruiken:

1. Kloon de AEM SPA Reactie van de Redacteur in [ https://github.com/adobe/aem-spa-project-archetype.](https://github.com/adobe/aem-spa-project-archetype)

   >[!NOTE]
   >
   >Dit archetype leidt tot een minimaal project van Adobe Experience Manager als uitgangspunt voor uw eigen SPA projecten. Met de eigenschappen die moeten worden opgegeven bij het gebruik van dit archetype kunt u naar wens alle onderdelen van dit project benoemen.

1. Als u een archetype-project voor een AEM SPA editor wilt maken, volgt u de leesmij-instructies:

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
   >Deze documentatie gebruikt **GroupId** als ***com.adobe.aem.screens*** en **ArtifactId** als ***Mijn SPA van de Steekproef*** (die de gebreken zijn). U kunt zo nodig uw eigen keuze maken.

1. Nadat het project wordt gecreeerd, of gebruik winde of redacteur van uw keus en voer het geproduceerde Maven project in.
1. Stel aan uw lokale AEM instantie op gebruikend bevel ***mvn schone installatie -PautoInstallPackage***.

### Inhoud bewerken in de REACT-app {#editing-content-in-the-react-app}

De inhoud bewerken in de REACT-app:

1. Navigeer naar `https://localhost:4502/editor.html/content/mysamplespa/en/home.html` (vervang de hostnaam, poort en projectnaam, indien van toepassing).
1. De tekst die wordt weergegeven in de Hello World-toepassing kunnen bewerken.

### De interactieve REACT-app toevoegen aan AEM Screens {#adding-the-interactive-react-app-to-aem-screens}

Voer de onderstaande stappen uit om de interactieve REACT-app aan AEM Screens toe te voegen:

1. Maak een AEM Screens-project. Zie [ Creërend en het Leiden Projecten ](creating-a-screens-project.md) voor meer details.
1. Creeer een **Kanaal van de Toepassing** (bij voorkeur) (of 1x1 malplaatje, of multi-zone kanaal) in de **omslag van Kanalen** van uw project van AEM Screens.

   >[!NOTE]
   >{de Kanalen van de opeenvolging van 0} **worden ontmoedigd voor dit gebruiksgeval omdat zij inherent met een diapresentatielogica komen die met de interactieve aard van de ervaring strijdig is.**
   >Zie [ Creërend en het Leiden Kanalen ](managing-channels.md) voor meer details.

1. Bewerk een willekeurig volgnummer en sleep en zet een ingesloten pagina-component neer.

   Zie [ Toevoegend Componenten aan een Kanaal ](adding-components-to-a-channel.md) voor meer details.

   >[!NOTE]
   >
   >Voeg de gebruikersinteractiegebeurtenis toe wanneer u het kanaal toewijst aan de weergave.

1. Klik **uitgeven** van de actiebar zodat kunt u de eigenschappen van het kanaal uitgeven.

   ![ screen_shot_2019-02-15at100555am ](assets/screen_shot_2019-02-15at100555am.png)

1. Sleep en laat vallen de **Ingebedde component van de Pagina**, of hergebruik de bestaande component in een toepassingskanaal, en klik de homepage onder de mysamplespa toepassing, bijvoorbeeld, ***/content/mysamplespa/nl/home***.

   ![ screen_shot_2019-02-15at101104am ](assets/screen_shot_2019-02-15at101104am.png)

1. Wijs het kanaal toe aan een weergave.

   >[!NOTE]
   >Voeg de gebruikersinteractiegebeurtenis toe wanneer u het kanaal toewijst aan de weergave.

1. Registreer een speler tegen dit project en wijs het aan de vertoning toe. Uw interactieve toepassing wordt nu uitgevoerd op AEM Screens.

   Zie [ Registratie van het Apparaat ](device-registration.md) voor meer informatie over het registreren van een apparaat.

## De SPA integreren met Adobe Analytics met offlinemogelijkheden via AEM Screens {#integrating-the-spa-with-adobe-analytics-with-offline-capability-through-aem-screens}

Volg de onderstaande stappen om de SPA met Adobe Analytics te integreren met offline mogelijkheden via AEM Screens:

1. Adobe Analytics configureren in AEM Screens.

   Zie [ Vormend Adobe Analytics met AEM Screens ](configuring-adobe-analytics-aem-screens.md) voor meer informatie over hoe te het rangschikken in Adobe Analytics met AEM Screens uitvoeren en douanegebeurtenissen verzenden gebruikend off-line Adobe Analytics.

1. Bewerk uw reactie-app in de IDE/editor van uw keuze (met name de tekstcomponent of andere component waarmee u gebeurtenissen wilt gaan uitzenden).
1. Voeg bij de klikgebeurtenis of andere gebeurtenis die u voor de component wilt vastleggen de analysegegevens toe met behulp van het standaardgegevensmodel.

   Zie [ Vormend Adobe Analytics met AEM Screens ](configuring-adobe-analytics-aem-screens.md) voor meer details.

1. Roep de AEM Screens Analytics API aan, zodat u de gebeurtenis offline kunt opslaan en in bursts naar Adobe Analytics kunt verzenden.

   Bijvoorbeeld:

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
   >De spelerfirmware voegt automatisch meer informatie over de speler en de bijbehorende runtimeomgeving toe aan de aangepaste analysegegevens die u verzendt. Daarom moet u mogelijk, tenzij nodig, details van het besturingssysteem of het apparaat op laag niveau vastleggen. Focus op de bedrijfsanalysegegevens.
