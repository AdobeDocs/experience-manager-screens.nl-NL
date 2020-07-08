---
title: Adobe Analytics-integratie met AEM Screens
seo-title: Adobe Analytics-integratie met AEM Screens
description: Volg deze pagina voor meer informatie over de integratie van AEM Screens in de doos met Adobe Analytics. Hier ziet u een proefdruk van het programma.
seo-description: Volg deze pagina voor meer informatie over de integratie van AEM Screens in de doos met Adobe Analytics. Hier ziet u een proefdruk van het programma.
uuid: 80d61af7-bf4d-46ca-a026-99a666c2e1a0
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: b1a0e00e-0368-42c9-8bcd-5f00b4d0990c
docset: aem65
translation-type: tm+mt
source-git-commit: f25176be89424059b8c51296969f069687328536
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
>Als u toegang wilt krijgen tot een van deze functiepakketten, neemt u contact op met de ondersteuning van Adobe en vraagt u om toegang. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Architectuurafbeeldingen**
* **Eigenschappen configureren**

## Overzicht {#overview}

***AEM Screens*** maken gebruik van Adobe Analytics en daarmee kunt u een unieke markt bereiken - kanaalanalyse waarmee inhoud die op locatie wordt weergegeven, kan worden gecorreleerd met andere gegevensbronnen.

AEM Screens is niet meer in de verpakking geïntegreerd met Adobe Analytics en biedt een proefafdruk van het spel.

In deze sectie wordt de volgende functionaliteit beschreven die is betrokken bij het verbinden van een AEM Screens-project met Adobe Analytics:

* Staat voor bewijs van spel rapportering door apparaat toe
* Staat toe dat de verslaggeving van de play-out per actief wordt aangetoond
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen worden vastgelegd en voorzien van een tijdstempel
* Hiermee zorgt u ervoor dat alle spelergebeurtenissen lokaal worden opgeslagen als het afspelen niet is verbonden met een netwerk
* Hiermee kunnen feedbacklussen worden gemaakt die gebeurtenissen bijhouden
* Hiermee kan het systeem inhoud en lay-outs wijzigen op basis van succescriteria die door de auteur van de inhoud zijn gedefinieerd

De integratie van Adobe Analytics met AEM Screens handhaaft zo de volgende *doelstellingen*:

* ROI van de implementatie van de digitale handtekening inschakelen
* Analytics integreren als basis voor toekomstige mogelijkheden voor het verzamelen en analyseren van gebruiksinformatie

## Architectuurafbeeldingen {#architectural-details}

Een AEM Screens klanten wil begrijpen welke inhoud op welk ogenblik, en voor hoe lang (samengevoegd) werd getoond. Dit is gemeenschappelijk vermogen van signaleringsoplossing. In plaats van onze eigen analyses te maken, zullen AEM Screens Adobe Analytics gebruiken en daarmee kunnen we iets anders bereiken op de markt - kanaaloverschrijdende analyses die de inhoud die op locatie wordt weergegeven, helpen correleren met andere gegevensbronnen.

In het volgende architectuurdiagram wordt de integratie van Adobe Analytics met AEM Screens uitgelegd:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Adobe Analytics inschakelen in AEM Screens {#enabling-adobe-analytics-in-aem-screens}

De Adobe Analytics-instellingen kunnen worden geconfigureerd via de OSGi-console.

Navigeer naar de Configuratie **van de Console van het Web van de** Adobe Experience Manager om Adobe Analytics voor AEM Screens te vormen, zoals aangetoond in het hieronder cijfer:

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

## Schermen Analytics: Stroom inschakelen {#screens-analytics-enablement-flow}

>[!CAUTION]
>
>Voordat u de eigenschappen configureert, neemt u contact op met de Adobe-relatiebeheerder om een ticket te maken voor een **Analytics API Key** and **Anaytics Project** voor gebruik met AEM Screens.

![]()

### Eigenschappen configureren {#configuring-the-properties}

>[!CAUTION]
>
>Voordat u de eigenschappen configureert, neemt u contact op met de Adobe-relatiebeheerder om een ticket te maken voor een **Analytics API Key** and **Anaytics Project** voor gebruik met AEM Screens.

In de volgende tabel worden de eigenschappen gemarkeerd met hun beschrijving voor het configureren van Adobe Analytics voor AEM Screens:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong>Analytics URL</strong></td>
   <td>URL om analysegegevens van de speler te posten. <br>
   Voor ontwikkeling/fase</em> - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>For Production</em> - https://cc-api-data.adobe.io/ingest/</em><br /> <br /></td>
  </tr>
  <tr>
   <td><strong>Analytics API-sleutel</strong></td>
   <td>API-sleutel voor verificatie bij de Adobe Analytics-server (meegeleverd door Accounts Manager).</td>
  </tr>
  <tr>
   <td><strong>Analytics Project</strong></td>
   <td>AEM Screens project dat op uw analyses wordt gevormd om gegevens (die door de Manager van Rekeningen worden verstrekt) te ontvangen.</td>
  </tr>
  <tr>
   <td><strong>Omgeving</strong></td>
   <td><p>Werkgebied of Productieomgeving (kies Werkgebied of Productie).</p></td>
  </tr>
  <tr>
   <td><strong>Verzendfrequentie Analytics</strong></td>
   <td>Frequentie in minuten voor het verzenden van analysegegevens van de spelers. De standaardwaarde is 15 minuten.</td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Standaard is de verzendfrequentie **van** Analytics 15 minuten.

#### Adobe Analytics Service gebruiken in AEM Screens {#using-adobe-analytics-service-in-aem-screens}

Dit scenario roept Analytics API door REST vraag van een analysedienst in de ingebouwde programmatuur en instrument scherm-kern componenten aan om gebeurtenissen uitdrukkelijk tot stand te brengen en te verzenden specifiek voor een bepaald gebruiksgeval terwijl het toestaan van rekbaarheid waar om het even welk douanebericht van een douane ontwikkeld kanaal kan worden verzonden naar Analytics.

Analytics-gebeurtenissen worden offline opgeslagen in geïndexeerdeDB en later afgekapt en naar de cloud verzonden.

>[!NOTE]
>
>Raadpleeg ***Adobe Analytics*** configureren voor AEM Screens ***voor meer informatie over de reekscode*** en het **[standaardgegevensmodel voor gebeurtenissen](configuring-adobe-analytics-aem-screens.md)**.

