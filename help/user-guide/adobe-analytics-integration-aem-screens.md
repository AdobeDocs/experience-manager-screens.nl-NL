---
title: Adobe Analytics-integratie met AEM Screens
seo-title: Adobe Analytics-integratie met AEM Screens
description: Volg deze pagina om meer te weten te komen over de integratie van AEM Screens met Adobe Analytics in de doos en geeft u een proefdruk van het spel.
seo-description: Volg deze pagina om meer te weten te komen over de integratie van AEM Screens met Adobe Analytics in de doos en geeft u een proefdruk van het spel.
uuid: 80d61af7-bf4d-46ca-a026-99a666c2e1a0
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: b1a0e00e-0368-42c9-8bcd-5f00b4d0990c
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---


# Adobe Analytics-integratie met AEM Screens {#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.4.2 Feature Pack 2 en AEM 6.3.3 Feature Pack 4 hebt geïnstalleerd.

>[!NOTE]
>
>Om toegang tot één van beiden van deze Packs van de Eigenschap te krijgen, moet u de Steun van Adobe contacteren en toegang verzoeken. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Architectuurafbeeldingen**
* **Eigenschappen configureren**

## Overzicht {#overview}

***AEM*** Screenshefboomwerkingen Adobe Analytics, en daarmee kunt u iets uniek in de markt - kanaalanalyses bereiken die helpen inhoud correleren die in plaats met andere gegevensbronnen wordt getoond.

AEM Screens biedt een uitweg uit de box-integratie met Adobe Analytics en biedt u een bewijs van spel.

In deze sectie wordt de volgende functionaliteit beschreven die betrokken is bij het verbinden van een AEM Screens-project met Adobe Analytics:

* Staat voor bewijs van spel rapportering door apparaat toe
* Staat toe dat de verslaggeving van de play-out per actief wordt aangetoond
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen worden vastgelegd en voorzien van een tijdstempel
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen lokaal worden opgeslagen als het afspelen niet is verbonden met een netwerk
* Hiermee kunnen feedbacklussen worden gemaakt die gebeurtenissen bijhouden
* Hiermee kan het systeem inhoud en lay-outs wijzigen op basis van succescriteria die door de auteur van de inhoud zijn gedefinieerd

Adobe Analytics Integration with AEM Screens dwingt dus de volgende *doelstellingen* af:

* ROI van de implementatie van de digitale handtekening inschakelen
* Analyses integreren als basis voor toekomstige mogelijkheden voor het verzamelen en analyseren van gebruiksinformatie

## Architectuurdetails {#architectural-details}

Een AEM Screens-klant wil weten welke inhoud op welk moment en voor hoe lang (geaggregeerd) is weergegeven. Dit is algemeen vermogen van signaleringsoplossing. In plaats van onze eigen analyses op te stellen, zal AEM Screens Adobe Analytics benutten en daarmee kunnen we iets anders bereiken op de markt - kanaaloverschrijdende analyses die de inhoud die op locatie wordt getoond, helpen correleren met andere gegevensbronnen.

In het volgende architectuurdiagram wordt de Adobe Analytics Integration met AEM Screens uitgelegd:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Adobe Analytics inschakelen in AEM Screens {#enabling-adobe-analytics-in-aem-screens}

De montages van Adobe Analytics kunnen van de console worden gevormd OSGi.

Navigeer naar **Adobe Experience Manager Web Console Configuration** om Adobe Analytics for AEM Screens te configureren, zoals in de onderstaande afbeelding wordt getoond:

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Schermanalyse: Stroom {#screens-analytics-enablement-flow} inschakelen

>[!CAUTION]
>
>Voordat u de eigenschappen configureert, neemt u contact op met de Adobe Relationship Manager om een ticket te maken voor een **Analytics API Key** en **Analytics Project** voor gebruik met AEM Screens.

![]()

### Eigenschappen {#configuring-the-properties} configureren

>[!CAUTION]
>
>Voordat u de eigenschappen configureert, neemt u contact op met de Adobe Relationship Manager om een ticket te maken voor een **Analytics API Key** en **Analytics Project** voor gebruik met AEM Screens.

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
   Voor ontwikkeling/fase</em>  - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>For Production</em> - https://cc-api-data.adobe.io/ingest/</em><br /> <br /></td>
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
>Standaard is de **Analytics Send Frequency** 15 minuten.

#### Adobe Analytics Service gebruiken in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

Dit scenario haalt Analytics API door de vraag van het HART van een analysedienst in de ingebouwde programmatuur en de apparaat scherm-kern componenten aan om gebeurtenissen uitdrukkelijk tot stand te brengen en te verzenden specifiek voor een bepaald gebruiksgeval terwijl het toestaan van rekbaarheid waar om het even welk douanebericht naar Analytics van een douane ontwikkeld kanaal kan worden verzonden.

Analytische gebeurtenissen worden offline opgeslagen in geïndexeerdeDB en later afgekapt en naar de cloud verzonden.

>[!NOTE]
>
>Voor meer informatie over ***Sequencing*** en ***Standaardgegevensmodel voor gebeurtenissen***, raadpleegt u **[Adobe Analytics configureren voor AEM Screens](configuring-adobe-analytics-aem-screens.md)**.

