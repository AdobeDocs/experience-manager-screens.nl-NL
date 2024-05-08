---
title: Adobe Analytics-integratie met AEM Screens
description: Meer informatie over de out-of-the-box integratie van AEM Screens met Adobe Analytics en een bewijs van spel.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: 92c8c42b-7c1e-4d4a-8662-18c99666e9c6
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Adobe Analytics-integratie met AEM Screens {#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u een minimale versie van AEM 6.4.2 Feature Pack 2 of AEM 6.3.3 Feature Pack 4 hebt geïnstalleerd. Voor klanten van de AEM Screens Cloud-service neemt u contact op met uw Adobe Relationship Manager om Adobe Analytics in Screens Cloud in te schakelen.

>[!NOTE]
>
>Om toegang tot één van beiden van deze Packs van de Eigenschap te krijgen, contacteer de Steun van de Adobe en verzoek toegang. U kunt het nieuwste elementenpakket voor AEM Screens downloaden via het menu [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Architectuurgegevens**
* **Eigenschappen configureren**

## Overzicht {#overview}

***AEM Screens*** gebruikt Adobe Analytics, en daarmee kunt u iets uniek in de markt bereiken - kanaalanalyses die helpen inhoud correleren die op plaats met andere gegevensbronnen wordt getoond.

AEM Screens biedt een uitweg uit de box-integratie met Adobe Analytics en biedt u een bewijs van spel.

In deze sectie wordt de volgende functionaliteit beschreven die betrokken is bij het verbinden van een AEM Screens-project met Adobe Analytics:

* Staat voor bewijs van spel rapportering door apparaat toe
* Staat toe dat de verslaggeving van de play-out per actief wordt aangetoond
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen worden vastgelegd en voorzien van een tijdstempel
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen lokaal worden opgeslagen als het afspelen niet is verbonden met een netwerk
* Er kunnen feedback-lussen worden gemaakt die gebeurtenissen bijhouden die in de loop der tijd worden afgespeeld
* Hiermee kan het systeem inhoud en lay-outs bewerken op basis van succescriteria die zijn gedefinieerd door de Content Author

Adobe Analytics Integration with AEM Screens dwingt dus het volgende af *doelen*:

* ROI van de implementatie van de digitale handtekening inschakelen
* Analyses integreren als basis voor toekomstige mogelijkheden voor het verzamelen en analyseren van gebruiksinformatie

## Architectuurgegevens {#architectural-details}

Een AEM Screens-klant wil weten welke inhoud op welk moment en voor hoe lang (geaggregeerd) is weergegeven. Deze noodzaak is een gemeenschappelijk vermogen van een ondertekeningsoplossing. AEM Screens gebruikt Adobe Analytics in plaats van een aparte analysetoepassing te maken. Met deze combinatie kunnen we iets uniek bereiken op de markt - kanaaloverschrijdende analyses die helpen inhoud die op locatie wordt getoond, te correleren met andere gegevensbronnen.

In het volgende architectuurdiagram wordt de Adobe Analytics Integration met AEM Screens uitgelegd:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Adobe Analytics inschakelen in AEM Screens {#enabling-adobe-analytics-in-aem-screens}

De montages van Adobe Analytics kunnen van de console worden gevormd OSGi.

Navigeren naar **Configuratie Adobe Experience Manager-webconsole** zodat u Adobe Analytics for AEM Screens kunt configureren.

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Screens Analytics: Enablement Flow {#screens-analytics-enablement-flow}

>[!CAUTION]
>
>Alvorens u de eigenschappen vormt, contacteer uw Manager van de Verhouding van de Adobe om een kaartje tot stand te brengen om een **Sleutel Analytics API** en **Analyseproject** voor gebruik met AEM Screens.

### Eigenschappen configureren {#configuring-the-properties}

>[!CAUTION]
>
>Alvorens u de eigenschappen vormt, contacteer uw Manager van de Verhouding van de Adobe om een kaartje tot stand te brengen om een **Sleutel Analytics API** en **Analyseproject** voor gebruik met AEM Screens.

In de volgende tabel worden de eigenschappen gemarkeerd met hun beschrijving voor het configureren van Adobe Analytics voor AEM Screens:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong>URL voor analyse</strong></td>
   <td>URL om analysegegevens van de speler te posten. <br>
   Voor ontwikkeling/fase</em> - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>Voor productie</em> - https://cc-api-data.adobe.io/ingest/<br /> <br /></td>
  </tr>
  <tr>
   <td><strong>Sleutel Analytics API</strong></td>
   <td>API-sleutel voor verificatie bij de Adobe Analytics-server (meegeleverd door Accounts Manager).</td>
  </tr>
  <tr>
   <td><strong>Analyseproject</strong></td>
   <td>AEM Screens-project geconfigureerd voor uw analyse om gegevens te ontvangen (geleverd door de Accounts Manager).</td>
  </tr>
  <tr>
   <td><strong>Omgeving</strong></td>
   <td><p>Werkgebied of Productieomgeving (kies Werkgebied of Productie).</p></td>
  </tr>
  <tr>
   <td><strong>Verzendfrequentie voor analyse</strong></td>
   <td>Frequentie in minuten voor het verzenden van analysegegevens van de spelers. De standaardwaarde is 15 minuten.</td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Standaard worden de **Verzendfrequentie voor analyse** is 15 minuten.

#### Adobe Analytics Service gebruiken in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

Dit scenario haalt Analytics API door de vraag van het REST van een analysedienst in de ingebouwde programmatuur aan. Het instrumenteert ook AEM schermen-kern componenten om gebeurtenissen tot stand te brengen en te verzenden specifiek voor een bepaald gebruiksgeval. Al deze functionaliteit terwijl het toestaan van rekbaarheid waar om het even welk douanebericht naar Analytics van een douane-ontwikkeld kanaal kan worden verzonden.

Analytische gebeurtenissen worden offline opgeslagen in geïndexeerdeDB en later afgekapt en naar de cloud verzonden.

>[!NOTE]
>
>Meer informatie over de ***Sequentie*** en ***Standaardgegevensmodel voor gebeurtenissen***, zie **[Adobe Analytics voor AEM Screens configureren](configuring-adobe-analytics-aem-screens.md)**.
