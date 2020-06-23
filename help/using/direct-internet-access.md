---
title: Directe internettoegang
description: Directe internettoegang
translation-type: tm+mt
source-git-commit: 70dddffd46ebf1bd83b25515be548bc442e45fea
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 0%

---


# Directe internettoegang {#direct-internet-access}

De Direct Internet Access SetUp bevat een toegangspunt voor toegang tot internet om de AEM cloud services te bereiken waarmee AEM Screens verbinding moeten maken.

De standaardhavens voor de mededeling van AEM Screens zijn:
* `http (TCP Port 80)`
Of
* `ssl-secured https (TCP Port 443)`

De havens kunnen als gevolg van configuratie van uw specifieke opstelling van de configuratie variëren AEM. Binnen deze SetUp, worden alle apparaten direct verbonden met uw Internet router zoals aangetoond in het hieronder cijfer.

![](/help/assets/direct-access-2.png)

De configuratie omvat ook een Toegang van Internet door om het even welke Internet Service Provider (ISP) en het is de Lijn van Internet. De meeste ISP&#39;s voorzien een Router van Internet die de Modem van Internet, de Schakelaar van het Netwerk, het toegangspunt van WIFI, Firewall en andere functionaliteit van het Netwerk (afhankelijk van fabrikant en model) behandelt.

## Verbinding maken tussen AEM Screens Player en Direct Internet Access {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om verbinding te maken met AEM Screen-spelers in deze configuratie:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.
1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk aan uw Plaatsing van de Router aanpast en controleert als de Maximale hoeveelheid beschikbare IP adressen in uw netwerk niet wordt bereikt.

1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden dit kan gewoonlijk ook worden geïdentificeerd gebruikend een Signal leiden op StandaardRouters.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en overeenkomstig registreren. Start AEM Screens.

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet correct verbinden en de verwachte inhoud niet tonen:
   >
   >1. Controleer in uw Firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443`.
   >1. Zorg ervoor dat alle benodigde Havens zijn toegestaan.


## Vereisten voor het opzetten van een netwerk voor directe toegang {#requirements-direct}

De Directe Opstelling van het Netwerk van de Toegang kan logisch gezien in twee blokken worden gescheiden:

* Breed gebiedsnetwerk

* Netwerk voor lokale gebieden

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de internetverbinding naast de netwerkbereikbaarheid moeten voldoende bandbreedte bieden om AEM Screens mooi en vloeiend te kunnen gebruiken.

*Voldoende* is afhankelijk van de hoeveelheid aangesloten AEM-schermen en van het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, cashiers, computers of WIFI-netwerken van gasten.

>[!NOTE]
>Alle apparaten hebben een gelijktijdige toegang tot de internetverbinding en de bandbreedte neemt gewoonlijk lineair af wanneer u meer consumenten/computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN), behalve de netwerkbereikbaarheid, verstrekt voldoende bandbreedte om AEM Screens behoorlijk en regelmatig in werking te stellen.

Het LAN netwerk past gewoonlijk minstens een netwerk 100 MBit/sec aan, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem aan te sluiten.
Als een WIFI-oplossing wordt overwogen om AEM Screens met de Internet Link te verbinden, wordt het aanbevolen om minimaal gebruik te maken van moderne WIFI-standaarden zoals IEEE 802.11g. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwere* standaarden zoals 802.11h-n zijn van betere kwaliteit.

>[!NOTE]
>Als er een WIFI Repeater vereist is, raden we Mesh WIFI Access-point-technologieën zoals Google Nest Mesh WIFI of een vergelijkbare technologie aan. Andere WiFi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het totale netwerk.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Wegens dit concept komt het belangrijkste netwerkverkeer voor wanneer er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Als u bijvoorbeeld een afspeellijst hebt gedefinieerd die niet vaak overdag wordt gewijzigd, is dit vrijwel gelijk aan een netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interactie is met sensoren of andere triggers en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>Met deze informatie kunt u het verbruik bekijken van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/assets/download-times-direct.png)

