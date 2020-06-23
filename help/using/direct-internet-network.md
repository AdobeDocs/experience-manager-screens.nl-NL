---
title: Directe internettoegang
description: Directe internettoegang
translation-type: tm+mt
source-git-commit: 77cf87cbce39a00528b2690d9689861b91e61fc5
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 0%

---


# Direct Internet Network (bekabeld/draadloos) {#direct-internet-access}

Het directe netwerk van Internet bevat een toegangspunt van de ingang voor de toegang van Internet om aan AEM cloud services te bereiken die de AEM Screens moeten verbinden met.

De standaardhavens voor de mededeling van AEM Screens zijn:
* `http (TCP Port 80)`
Of
* `ssl-secured https (TCP Port 443)`

De havens kunnen als gevolg van configuratie van uw specifieke opstelling van de configuratie variëren AEM. Binnen deze SetUp, worden alle apparaten direct verbonden met uw router van Internet zoals aangetoond in het hieronder cijfer.

![](/help/assets/direct-access-2.png)

De configuratie omvat ook een toegang van Internet door om het even welke Internet Service Provider (ISP) en het is de lijn van Internet. De meeste ISP&#39;s voorzien een Router van Internet die de Modem van Internet, de Schakelaar van het Netwerk, het toegangspunt van WIFI, firewall en andere functionaliteit van het Netwerk (afhankelijk van fabrikant en model) behandelt.

## Verbinding maken tussen AEM Screens Player en Direct Internet Access {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om verbinding te maken met AEM Screen-spelers in deze configuratie:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.
1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als u een foutbericht ontvangt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk aan uw Plaatsing van de Router aanpast en controleert als de maximumhoeveelheid beschikbare IP adressen in uw netwerk niet wordt bereikt.

1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden. Dit kan ook worden geïdentificeerd gebruikend Signal leiden op StandaardRouters.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet correct verbinden en de verwachte inhoud niet tonen:
   >
   >1. Controleer in uw Firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443`.
   >1. Zorg ervoor dat alle benodigde Havens zijn toegestaan.


## Vereisten voor het opzetten van een netwerk voor directe toegang {#requirements-direct}

Het directe netwerk van Internet kan logisch gezien in twee blokken worden gescheiden:

* Breed gebiedsnetwerk

* Netwerk voor lokale gebieden

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de verbinding van Internet naast bereikbaarheid van het netwerk moeten voldoende bandbreedte verstrekken om AEM Screens in werking te stellen.

*Voldoende* is afhankelijk van de hoeveelheid aangesloten AEM-schermen en van het gebruik van andere consumenten binnen het netwerk, zoals smartphones, tablets, cashiers, computers of gastnetwerken van het WIFI.

>[!NOTE]
>Alle apparaten hebben een gezamenlijke toegang tot de verbinding van Internet en de bandbreedte vermindert lineair wanneer u meer consumenten of computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN), behalve de bereikbaarheid van het netwerk verstrekt voldoende bandbreedte om AEM Screens in werking te stellen.

Het LAN netwerk past gewoonlijk minstens een netwerk 100 Mbps aan, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem te verbinden.
Als een WIFI-oplossing wordt overwogen om AEM Screens aan de Verbinding van Internet te verbinden, wordt het geadviseerd om moderne normen van de WIFI als `IEEE 802.11g` minimum te gebruiken. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwere* standaarden zoals die `802.11h-n` zijn van betere kwaliteit.

>[!NOTE]
>Als er een WIFI Repeater vereist is, raden we Mesh WIFI Access-point-technologieën zoals Google Nest Mesh WIFI of een vergelijkbare technologie aan. Andere WiFi herhalende technologieën resulteren in een enorm verlies van bandbreedte in het totale netwerk.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld wanneer u een afspeellijst hebt gedefinieerd die regelmatig tijdens de dag wordt bijgewerkt, biedt dit een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.

Voor die gebruiksgevallen waar er meer interactie is met sensoren of andere triggers en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>Met deze informatie kunt u het verbruik bekijken van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/assets/download-times-direct.png)

