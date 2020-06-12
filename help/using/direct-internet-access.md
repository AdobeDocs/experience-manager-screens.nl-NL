---
title: Directe internettoegang
description: Directe internettoegang
translation-type: tm+mt
source-git-commit: 3527dd38898399e692e114edb492825b18b28f86
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---


# Directe internettoegang {#direct-internet-access}

De Directe Opstelling van de Toegang van Internet bevat een toegangspunt van de ingang voor de toegang van Internet om de AEM cloud services te bereiken die de AEM Screens moeten verbinden met.

De standaardhavens voor de mededeling van AEM Screens zijn:
* `http (TCP Port 80)`
Of
* `ssl-secured https (TCP Port 443)`

De havens kunnen door configuratie van uw specifieke configuratie variëren AEM. Binnen deze SetUp, worden alle apparaten direct verbonden met uw Internet router zoals aangetoond in het hieronder cijfer.

![](/help/assets/direct-access-2.png)

De configuratie omvat ook een Toegang van Internet door om het even welke dienstverlener van Internet en het is de Lijn van Internet. De meeste ISP&#39;s bieden wel een internetrouter die de internetmodem, netwerkswitch, WIFI-toegangspunt, firewall en andere netwerkfuncties (afhankelijk van fabrikant en model) bestrijkt.

>[!NOTE]
>**Tip voor probleemoplossing **>Als AEM Screens niet correct verbinden en de verwachte inhoud tonen:
>
>1. Controleer in uw Firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443`.
>1. Controleer of alle benodigde poorten zijn toegestaan en probeer het opnieuw.


## Vereisten voor het opzetten van een netwerk voor directe toegang {#requirements-direct}

De Directe Opstelling van het Netwerk van de Toegang kan logisch gezien in twee blok worden gescheiden. Het WAN/Buitenste World/Internet Connection Block en het interne LAN/Local Area Network.

### WAN-/internetverbinding {#wan-connection}

De prestaties van de Verbinding van Internet hebben, naast reeds beschreven netwerkbereikbaarheid, om voldoende bandbreedte te verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen. In detail, &quot;voldoende&quot;hangt van de hoeveelheid aangesloten AEM schermen en van het gebruik van andere consumenten binnen het netwerk, zoals Smartphones, Tablets, Cashiers, Computers of de netwerken van de WIFI van de Gast af.
Houd in mening dat alle apparaten een gezamenlijke toegang tot de verbinding van Internet hebben en de bandbreedte gewoonlijk lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.

### LAN-verbinding {#lan-connection}

De prestaties van LAN hebben, behalve aan reeds beschreven netwerkbereikbaarheid, om voldoende bandbreedte te verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen. In deze dagen past het LAN netwerk gewoonlijk minstens een netwerk 100MBit/sec aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem aan te sluiten.
Als een WIFI-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, wordt het aanbevolen om minimaal gebruik te maken van moderne WIFI-standaarden zoals IEEE 802.11g. Deze standaard ondersteunt verbindingen tot 54 Mbit. Alle *nieuwere* standaarden zoals 802.11h-n zijn van betere kwaliteit. Als er een WIFI Repeater vereist is, raden we Mesh WIFI Access-point-technologieën zoals Google Nest Mesh WIFI of een vergelijkbare technologie aan.
Andere WiFi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het totale netwerk.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Alle benodigde mediabestanden, zoals afbeeldingen en video&#39;s, worden gedownload en lokaal opgeslagen. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Als u bijvoorbeeld een afspeellijst hebt gedefinieerd die niet vaak overdag wordt gewijzigd, is dit vrijwel gelijk aan een netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interactie is met sensoren of andere triggers en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit:

![](/help/assets/direct-access-1.png)

>[!NOTE]
>Met deze informatie kunt u het verbruik bekijken van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Dus elk van deze aanvragen voegt de downloadtijd toe en verlengt deze.