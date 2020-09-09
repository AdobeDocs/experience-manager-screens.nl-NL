---
title: Adobe Analytics configureren met AEM Screens
seo-title: Adobe Analytics configureren met AEM Screens
description: 'Volg deze sectie voor meer informatie over het volgen en verzenden van aangepaste gebeurtenissen met gebruik van Offline Adobe Analytics '
seo-description: 'Volg deze sectie voor meer informatie over het volgen en verzenden van aangepaste gebeurtenissen met gebruik van Offline Adobe Analytics '
uuid: e685e553-c05b-4db4-8fa5-9ef45268b094
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: 3cec9266-4032-46b9-9c75-16da64bfea7d
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 8%

---


# Adobe Analytics configureren met AEM Screens {#configuring-adobe-analytics-with-aem-screens}

>[!CAUTION]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.4.2 Feature Pack 2 en AEM 6.3.3 Feature Pack 4 hebt geïnstalleerd.
>
>Om toegang tot één van beiden van deze Packs van de Eigenschap te krijgen, moet u de Steun van Adobe contacteren en toegang verzoeken. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

In deze sectie worden de volgende onderwerpen behandeld:

* **Sequentie in Adobe Analytics met AEM Screens**
* **Aangepaste gebeurtenissen verzenden met offline Adobe Analytics**

## Sequentie in Adobe Analytics met AEM Screens {#sequencing-in-adobe-analytics-with-aem-screens}

Het ***volgordeproces*** begint met de gegevensopslagservice die de Adobe Analytics-service activeert. De inhoud van het kanaal verzendt de gebeurtenissen van Adobe Analytics met loonlijst, dat wil zeggen, de vangst van de gegevenstest aan Vensters I/O en de gebeurtenissen van het verblijf wordt teweeggebracht. De gebeurtenissen worden opgeslagen in de index-DB en vervolgens in de objectopslag geplaatst. Gebaseerd op het programma, de beheerderreeksen, knipt het de gegevens van objecten opslag, en brengt het verder over in brokkenopslag. Er wordt geprobeerd maximale hoeveelheid gegevens te verzenden wanneer verbinding wordt gemaakt.

### Scheidingsdiagram {#sequencing-diagram}

In het volgende volgordediagram wordt de Adobe Analytics-integratie met AEM Screens uitgelegd:

![analytics_chunking](assets/analytics_chunking.png)

## Aangepaste gebeurtenissen verzenden met offline Adobe Analytics {#sending-custom-events-using-offline-adobe-analytics}

De volgende tabel geeft een overzicht van het standaardgegevensmodel voor gebeurtenissen. Hier worden alle velden weergegeven die naar Adobe Analytics zijn verzonden:

<table>
 <tbody>
  <tr>
   <td><strong>Sectie</strong></td> 
   <td><strong>Eigenschappenlabel</strong></td> 
   <td><strong>Eigenschapnaam/sleutel</strong></td> 
   <td><strong>Vereist</strong></td> 
   <td><strong>Gegevenstype</strong></td> 
   <td><strong>Type eigenschap</strong><br /> </td> 
   <td><strong>Beschrijving</strong></td> 
  </tr>
  <tr>
   <td><strong><em>Kern/gebeurtenis</em></strong></td> 
   <td>GUID gebeurtenis</td> 
   <td>event.guid</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td>UUID</td> 
   <td>Unieke id die de instantie van een gebeurtenis identificeert</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum waarop de gebeurtenis is verzameld</td> 
   <td>event.coll_dts</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Tijdstip van verzameling</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum van gebeurtenis (begin)</td> 
   <td>event.dts_start</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Begindatum van gebeurtenis, als u dit NIET opgeeft, wordt de tijd van de gebeurtenis aangenomen op het tijdstip dat deze door de server is ontvangen</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Datum van gebeurtenis (einde)</td> 
   <td>event.dts_end</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td>timestamp - UTC</td> 
   <td>Einddatum van gebeurtenis</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Workflow</td> 
   <td>event.workflow</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Werkstroomnaam (schermen)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Hoofdcategorie DMe</td> 
   <td>event.category</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Hoofdcategorie (BUREAUBLAD, MOBIEL, WEB, PROCESS, SDK, SERVICE, ECOSYSTEM) - Groepering van gebeurtenistypen - <strong>We sturen Player</strong></td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subcategorie</td> 
   <td>event.subcategory</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Subcategorie - Sectie van een workflow of gebied van een scherm, enz. (Recente bestanden, CC-bestanden, mobiele ontwerpen enzovoort.)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Type gebeurtenis/actie</td> 
   <td>event.type</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Type gebeurtenis (renderen, klikken, knijpen, zoomen) - Primaire gebruikershandeling</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subtype</td> 
   <td>event.subtype</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Subtype gebeurtenis (maken, bijwerken, verwijderen, publiceren, enz.) - Aanvullende details van de actie van de gebruiker</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Off line</td> 
   <td>event.offline</td> 
   <td>optioneel</td> 
   <td>boolean</td> 
   <td> </td> 
   <td>Gebeurtenis gegenereerd terwijl de handeling offline/online was (true/false)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Gebruikersagent</td> 
   <td>event.user_agent</td> 
   <td>Aanbevolen (westeigenschappen)</td> 
   <td>string</td> 
   <td> </td> 
   <td>Gebruikersagent</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Taal/landinstelling</td> 
   <td>event.language</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>De landinstelling van de gebruiker is een tekenreeks die is gebaseerd op de conventies voor taaltags van RFC 3066 (bijvoorbeeld en-US, fr-FR of es-ES)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Device GUID</td> 
   <td>event.device_guid</td> 
   <td>optioneel</td> 
   <td>string<br /> </td> 
   <td>UUID</td> 
   <td>Identificeert het Apparaat GUID (b.v. machine identiteitskaart of knoeiboel van IP adres + subnet masker + netwerk identiteitskaart + gebruikersagent) - hier zullen wij de gebruikersbenaming van de speler verzenden die bij registratietijd wordt geproduceerd.</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Count</td> 
   <td>event.count</td> 
   <td>optioneel</td> 
   <td>getal</td> 
   <td> </td> 
   <td>Aantal keer dat de gebeurtenis heeft plaatsgevonden - Hier wordt de videoduur verzonden</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Waarde</td> 
   <td>event.value</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>Waarde van de gebeurtenis (bijv. instellingen aan/uit)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Pagename</td> 
   <td>event.pagename</td> 
   <td>vereist voor AA</td> 
   <td>string</td> 
   <td> </td> 
   <td>Adobe Analytics-ondersteuning voor aangepaste paginanaam</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>URL</td> 
   <td>event.url</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>URL van de webeigenschap of het mobiele schema - moet volledig gekwalificeerde URL omvatten</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Foutcode</td> 
   <td>event.error_code</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Foutcode</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Fouttype</td> 
   <td>event.error_type</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Type fout</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Beschrijving van fout</td> 
   <td>event.error_description</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Beschrijving fout<br /> </td> 
  </tr>
  <tr>
   <td><strong><em>Bron/product van oorsprong</em></strong></td> 
   <td>Naam</td> 
   <td>source.name</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Toepassingsnaam (AEM Screens)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Versie</td> 
   <td>source.version</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>Firmwareversie</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Platform</td> 
   <td>source.platform</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>navigator.platform</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Apparaat</td> 
   <td>source.device</td> 
   <td>vereiste w/uitzonderingen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Naam speler</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Versie besturingssysteem</td> 
   <td>source.os_version</td> 
   <td>vereiste w/uitzonderingen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Versie besturingssysteem</td> 
  </tr>
  <tr>
   <td><strong><em>Inhoud</em></strong></td> 
   <td>Actie</td> 
   <td>content.action</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element inclusief de vertoning die daadwerkelijk is afgespeeld</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>MIME-type</td> 
   <td>content.mimetype</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>MIME-type van de inhoud</td> 
  </tr>
  <tr>
   <td><strong><em>Transactie</em></strong></td> 
   <td>Transactienummer</td> 
   <td>trn.number</td> 
   <td>required</td> 
   <td>string</td> 
   <td>UUID</td> 
   <td>Unieke id die bij voorkeur voldoet aan UUID v4</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Productbeschrijving</td> 
   <td>trn.product</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element (behalve uitvoering)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Aantal</td> 
   <td>trn.quantity</td> 
   <td>required</td> 
   <td>string</td> 
   <td> </td> 
   <td>De afspeelduur</td> 
  </tr>
 </tbody>
</table>

