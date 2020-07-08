---
title: Engesloten bedrijfsnetwerk
description: Engesloten bedrijfsnetwerk
translation-type: tm+mt
source-git-commit: f25176be89424059b8c51296969f069687328536
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---


# Enclosed Corporate Network (bekabeld/draadloos) {#enclosed-corporate-networks}

De Ingesloten Collectieve Opstelling van het Netwerk is toepasselijk op kleinere, grotere en ondernemingsondernemingen. Het kan theoretisch complexer zijn, en de logische opstelling wordt getoond in het hieronder cijfer.

![](/help/using/assets/enclosed-network-1.png)


## Verbinding maken tussen AEM Screens Player en Direct Internet Access {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM-spelers op het scherm in deze configuratie:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.
1. Test de internetverbinding door een URL op te roepen in uw systeembrowser.

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


## Ingesloten bedrijfsnetwerken instellen {#requirements-enclosed-networks}

De Ingesloten Collectieve Opstelling van het Netwerk kan logisch gezien in twee blokken worden gescheiden:

* Het Netwerk van het Brede Gebied (WAN)
* LAN (Internal Local Area Network).

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de verbinding van Internet, behalve de netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens inhoudsupdates regelmatig in werking te stellen.
*Voldoende bandbreedte* is afhankelijk van de hoeveelheid aangesloten AEM-schermen en het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, cashiers, computers of gastWi-Fi-netwerken.

>[!NOTE]
>
>Alle apparaten hebben een gelijktijdige toegang tot de internetverbinding en de bandbreedte neemt lineair af wanneer u meer consumenten of computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN), behalve de netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens inhoudsupdates regelmatig in werking te stellen.

Het LAN netwerk binnen collectieve organisaties is gewoonlijk minstens 1000 MBit/sec netwerk, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem aan te sluiten. Terwijl het gebruiken van andere actieve componenten van het Netwerk is het verplicht dat al die aan de bandbreedtevereisten van het Netwerk aanpassen.

Bijvoorbeeld, zouden de componenten van het Netwerk minstens 100 norm moeten aanpassen Mbps en de bandbreedte aanpassen die door de toegang van Internet/routerspecificatie wordt verstrekt.

### Andere BedrijfsNetwerken Specificaties {#other-networks}

De collectieve Netwerken hebben een aantal aangesloten apparaten, zijn gescheiden in diverse subnetwerken en hebben overtollige of multiplexen verbindingen van Internet om voldoende prestaties voor vele duizenden gezamenlijke toegang te verstrekken.
Dit schema is vereenvoudigd en past in de meeste gevallen bij de omgevingen die beschikbaar zijn voor de client.

Als een Wi-Fi-oplossing bedoeld is om schermen te verbinden met de Internet Link, wordt aanbevolen om ten minste de moderne Wi-Fi-standaarden te gebruiken. Dit geldt bijvoorbeeld `IEEE 802.11g` voor alle andere apparaten. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwere* standaarden zoals die `802.11h-n` zijn van betere kwaliteit. Als u een Wi-Fi Repeater nodig hebt, raden we u sterk aan om technologieën als Google Nest Mesh Wi-Fi of een vergelijkbare technologie voor toegangspunten van Mesh aan te bevelen.
Andere Wi-Fi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het hele netwerk.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld een gedefinieerde afspeellijst die regelmatig wordt bijgewerkt - biedt een vrijwel netwerkonafhankelijke bewerking aan zodra alle bestanden op de speler zijn opgeslagen.

Voor scenario&#39;s, waar er meer interactie met sensoren of trekkers en dynamische inhoud zijn, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe het schermreactie om optimale klantenervaring te verzekeren.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>
>De informatie staat u toe om de consumptie van elk apparaat in het netwerk te bekijken die en een bron van Internet verzoeken te downloaden. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/enclosed-network-download.png)
