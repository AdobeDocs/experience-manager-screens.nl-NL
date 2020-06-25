---
title: Directe internettoegang
description: Directe internettoegang
translation-type: tm+mt
source-git-commit: d12de8de2b7bb29d85ebb0e046f2d1fd5051e928
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---


# Direct Internet Network (bekabeld/draadloos) {#direct-internet-access}

Het directe netwerk van Internet bevat een toegangspunt van de ingang voor de toegang van Internet om de AEM cloud services te bereiken die de AEM Screens moeten verbinden met.

De standaardhavens voor de mededeling van AEM Screens zijn:
* `http (TCP Port 80)`
   <br>Of</br>

* `ssl-secured https (TCP Port 443)`

De havens kunnen als gevolg van configuratie van uw specifieke opstelling van de configuratie variëren AEM. Binnen deze SetUp, worden alle apparaten direct verbonden met uw router van Internet zoals aangetoond in het hieronder cijfer.

![](/help/assets/direct-access-2.png)

De configuratie omvat ook een toegang van Internet door om het even welke Internet Service Provider (ISP) en het is de lijn van Internet. De meeste ISP&#39;s bieden een internetrouter voor de internetmodem, netwerkswitch, Wi-Fi-toegangspunt, firewall en andere netwerkfuncties (afhankelijk van fabrikant en model).

## Verbinding maken tussen AEM Screens Player en Direct Internet Access {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM-spelers op het scherm in deze configuratie:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.
1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als er een fout optreedt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk uw Montages van de Router aanpast en controleer als de maximumhoeveelheid beschikbare IP adressen in uw netwerk niet wordt bereikt.

1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden. Dit kan ook worden geïdentificeerd gebruikend Signal leiden op StandaardRouters.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet correct verbinden en de verwachte inhoud niet wordt getoond:
   >
   >1. Controleer in uw firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443`. zijn
   >1. Zorg ervoor dat alle vereiste Havens worden toegestaan.


## Netwerk voor directe toegang instellen {#requirements-direct}

Het directe netwerk van Internet wordt logisch gezien gescheiden in twee blokken:

* Breed gebiedsnetwerk

* Netwerk voor lokale gebieden

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de verbinding van Internet naast bereikbaarheid van het netwerk moeten voldoende bandbreedte verstrekken om AEM Screens in werking te stellen.

*Voldoende* is afhankelijk van het aantal aangesloten AEM-schermen en het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, cashiers, computers of gastWi-Fi-netwerken.

>[!NOTE]
>Alle hierboven genoemde apparaten, hebben een gezamenlijke toegang tot de verbinding van Internet en de bandbreedte vermindert lineair wanneer u meer consumenten of computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN), behalve de bereikbaarheid van het netwerk verstrekt voldoende bandbreedte om AEM Screens in werking te stellen.

Het LAN netwerk past gewoonlijk minstens een netwerk 100 Mbps aan, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem te verbinden.
Als een Wi-Fi-oplossing wordt overwogen om AEM Screens te verbinden met de Internet Link, is het raadzaam om ten minste gebruik te maken van moderne Wi-Fi-standaarden. `IEEE 802.11g` Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwere* standaarden zoals die `802.11h-n` zijn van betere kwaliteit.

>[!NOTE]
>Als een Wi-Fi Repeater vereist is, wordt dit sterk aanbevolen voor een Wi-Fi-toegangspunt voor Net, zoals Google Nest Mesh Wi-Fi of een vergelijkbaar toegangspunt. Andere Wi-Fi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het hele netwerk.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld een gedefinieerde afspeellijst die regelmatig wordt bijgewerkt - biedt een vrijwel netwerkonafhankelijke bewerking aan zodra alle bestanden op de speler zijn opgeslagen.

Voor scenario&#39;s, waar er meer interactie met sensoren of trekkers en dynamische inhoud zijn, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe het schermreactie om optimale klantenervaring te verzekeren.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>De informatie staat u toe om de consumptie van elk apparaat in het netwerk te bekijken die en een bron van Internet verzoeken te downloaden. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/assets/download-times-direct.png)

