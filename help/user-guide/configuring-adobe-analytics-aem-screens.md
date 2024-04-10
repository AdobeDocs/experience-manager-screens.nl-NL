---
title: Adobe Analytics configureren met AEM Screens
description: Meer informatie over het rangschikken en verzenden van aangepaste gebeurtenissen via Offline Adobe Analytics.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: 4ecc1fb1-2437-449a-a085-66b2a85f4053
source-git-commit: c142830a37461a36baae15f543bd43b0ae8a62a7
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# Adobe Analytics configureren met AEM Screens {#configuring-adobe-analytics-with-aem-screens}

<!-- OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available if you have installed AEM 6.4.2 Feature Pack 2 and AEM 6.3.3 Feature Pack 4.
>
>To get access to either of these Feature Packs, you must contact Adobe Support and request access. Once you have permissions, download it from Package Share. -->

In deze sectie worden de volgende onderwerpen behandeld:

* **Sequentie in Adobe Analytics met AEM Screens**
* **Aangepaste gebeurtenissen verzenden met offline Adobe Analytics**

## Sequentie in Adobe Analytics met AEM Screens {#sequencing-in-adobe-analytics-with-aem-screens}

De ***volgordeproces*** begint met de gegevensopslagservice die de Adobe Analytics-service activeert. De inhoud van het kanaal verzendt de gebeurtenissen van Adobe Analytics met loonlijst, dat wil zeggen, de vangst van de gegevenstest aan Vensters I/O en de gebeurtenissen van het verblijf wordt teweeggebracht. De gebeurtenissen worden opgeslagen in de index-DB en vervolgens in de objectopslag geplaatst. Gebaseerd op het programma de beheerderreeksen, knipt het de gegevens van objecten opslag, en brengt het verder over in brokkenopslag. Er wordt geprobeerd een maximale hoeveelheid gegevens te verzenden wanneer verbinding wordt gemaakt.

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
   <td>GUID van gebeurtenis</td> 
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
   <td>Tijdstip van begindatum van gebeurtenis, als u dit niet hebt opgegeven, wordt de tijd van de gebeurtenis aangenomen als het tijdstip waarop deze door de server is ontvangen</td> 
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
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>Hoofdcategorie (DESKTOP, MOBILE, WEB, PROCESS, SDK, SERVICE, ECOSYSTEM) - Groepering van gebeurtenistypen - <strong>Speler verzonden</strong></td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Subcategorie</td> 
   <td>event.subcategory</td> 
   <td>aanbevolen</td> 
   <td>string</td> 
   <td> </td> 
   <td>Subcategorie - Sectie van een werkstroom, of Gebied van een scherm, etc. (Recente bestanden, CC-bestanden, mobiele ontwerpen enzovoort.)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Type gebeurtenis/actie</td> 
   <td>event.type</td> 
   <td>vereist</td> 
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
   <td>Subtype gebeurtenis (maken, bijwerken, verwijderen, publiceren, enzovoort) - Meer informatie over de actie van de gebruiker</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Off line</td> 
   <td>event.offline</td> 
   <td>optioneel</td> 
   <td>boolean</td> 
   <td> </td> 
   <td>Gebeurtenis gegenereerd tijdens offline/online actie (true/false)</td> 
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
   <td>Identificeert het Apparaat GUID (bijvoorbeeld, machine identiteitskaart of knoeiboel van IP adres + subnet masker + netwerk identiteitskaart + gebruikersagent) - hier wordt de gebruikersbenaming van de speler die bij registratietijd wordt geproduceerd verzonden.</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Aantal</td> 
   <td>event.count</td> 
   <td>optioneel</td> 
   <td>getal</td> 
   <td> </td> 
   <td>Aantal keren dat de gebeurtenis heeft plaatsgevonden - De videoduur wordt verzonden</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Waarde</td> 
   <td>event.value</td> 
   <td>optioneel</td> 
   <td>string</td> 
   <td> </td> 
   <td>Waarde van de gebeurtenis (bijvoorbeeld instellingen aan/uit)</td> 
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
   <td>Foutbeschrijving</td> 
   <td>event.error_description</td> 
   <td> </td> 
   <td>string</td> 
   <td> </td> 
   <td>Beschrijving fout<br /> </td> 
  </tr>
  <tr>
   <td><strong><em>Bron/oorsprong product</em></strong></td> 
   <td>Naam</td> 
   <td>source.name</td> 
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>Toepassingsnaam (AEM Screens)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Versie</td> 
   <td>source.version</td> 
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>Firmwareversie</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Platform</td> 
   <td>source.platform</td> 
   <td>vereist</td> 
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
   <td>Handeling</td> 
   <td>content.action</td> 
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element inclusief de vertoning die is afgespeeld</td> 
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
   <td>vereist</td> 
   <td>string</td> 
   <td>UUID</td> 
   <td>Unieke id die bij voorkeur voldoet aan UUID v4</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Productbeschrijving</td> 
   <td>trn.product</td> 
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>De URL naar het element (behalve uitvoering)</td> 
  </tr>
  <tr>
   <td> </td> 
   <td>Aantal</td> 
   <td>trn.quantity</td> 
   <td>vereist</td> 
   <td>string</td> 
   <td> </td> 
   <td>De afspeelduur</td> 
  </tr>
 </tbody>
</table>
