---
title: Engesloten bedrijfsnetwerk
description: Engesloten bedrijfsnetwerk
translation-type: tm+mt
source-git-commit: ed683a86b7e8c6ec06309577bd0a8690a9cc4684
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---


# Omsloten bedrijfsnetwerken (bekabeld/draadloos) {#enclosed-corporate-networks}

De Ingesloten Collectieve Opstelling van het Netwerk is toepasselijk op kleinere, grotere en ondernemingsondernemingen. Het kan theoretisch complexer zijn, maar de logische Opstelling wordt getoond in het hieronder cijfer.

![](/help/using/assets/enclosed-network-1.png)


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


## Vereisten voor het opzetten van besloten bedrijfsnetwerken {#requirements-enclosed-networks}

De Ingesloten Collectieve Opstelling van het Netwerk kan logisch gezien in twee blokken worden gescheiden:

* Het Netwerk van het Brede Gebied (WAN)
* LAN (Internal Local Area Network).

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de internetverbinding naast de netwerkbereikbaarheid moeten voldoende bandbreedte bieden om AEM Screens mooi en vloeiend te kunnen gebruiken.
*Voldoende bandbreedte* is afhankelijk van de hoeveelheid aangesloten AEM-schermen en het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, Cashiers, Computers of gastWi-Fi-netwerken.

>[!NOTE]
>Alle apparaten hebben een gelijktijdige toegang tot de internetverbinding en de bandbreedte neemt doorgaans lineair af wanneer u meer consumenten of computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN) hebben, behalve de netwerkbereikbaarheid, voldoende bandbreedte moeten verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen.

In deze dagen past het LAN netwerk binnen collectieve organisaties gewoonlijk minstens een netwerk 1000 MBit/sec aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem aan te sluiten. Als u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte.

Bijvoorbeeld, zouden de netwerkcomponenten minstens 1000 norm moeten aanpassen Mbps en de bandbreedte aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.

### Andere BedrijfsNetwerken Specificaties {#other-networks}

Gewoonlijk hebben de Collectieve Netwerken een lading van aangesloten apparaten, in diverse subnetwerken zouden kunnen worden gescheiden en de overtollige of multiplexen verbindingen van Internet zouden kunnen hebben om voldoende prestaties voor vele duizenden gezamenlijke toegang te verstrekken.
Dit schema is vereenvoudigd en past in de meeste gevallen bij de omgeving die beschikbaar is voor de client.

Als een Wi-Fi-oplossing wordt overwogen om een scherm te verbinden met de internetverbinding, wordt het aanbevolen om ten minste de moderne Wi-Fi-standaarden te gebruiken. Dit geldt bijvoorbeeld `IEEE 802.11g` voor de verbinding met internet. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwere* standaarden zoals die `802.11h-n` zijn van betere kwaliteit. Als u een Wi-Fi Repeater nodig hebt, raden we u sterk aan Wi-Fi Access-punttechnologieën zoals Google Nest Mesh Wi-Fi of vergelijkbare technologieën aan te bevelen.
Andere Wi-Fi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het hele netwerk.

## Media en middelen downloaden {#download}

AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale werking, bijvoorbeeld wanneer u een afspeellijst hebt gedefinieerd die niet vaak tijdens de dag wordt gewijzigd, biedt dit een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen. Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.

De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële wachttijden kunnen worden verwacht.

>[!NOTE]
>Alle informatie moet worden gezien als het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/enclosed-network-download.png)