---
title: Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
description: De pagina beschrijft Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
translation-type: tm+mt
source-git-commit: 5460e384e96553d9f0478113368e31cf266479a4
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 0%

---


# Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#mobile-network-setup}

Adobe AEM Screens Players kan ook worden aangesloten gebruikend Mobiele/Cellulaire Netwerken die minstens een 3G netwerk in werking stellen.
Binnen de AEM Screens wordt de benodigde inhoud fysiek gedownload naar de Player-controller/computer en correct opgeslagen in het onderliggende besturingssysteem. Hierdoor heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijd en de prestaties van de weergavesystemen worden helemaal niet beïnvloed.
Verbinding van AEM Screens Players met een Cellular 3/4/5G verbindt met uw Leverancier van de Gegevens van de Mobiele Dienst. Het voordeel van deze Opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare dekking van het Netwerk te verzekeren. Dit wordt gebruikt in een verhoogde en open positie met zo min mogelijk omringende beton- of metaalconstructie.
Met deze configuratie kunnen gebruikers van AEM-schermen heel flexibel werken, omdat er geen vaste lijn nodig is om AEM Screens te verbinden.

![](/help/using/assets/mobile-network-1.png)

## Verbinding maken tussen AEM Screens Player en Direct mobiel netwerk {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om verbinding te maken met AEM Screen-spelers in deze configuratie:

De configuratie bevat van een Toegang van Internet van om het even welke Controllers van AEM Screens door de directe Toegang van Internet gebruikend een eigen Gegevens 3/4/5G Verbinding.
De correcte verbinding van de spelers van het Scherm AEM in deze configuratie is eenvoudig:

1. Zorg ervoor dat de Mobiele Router van Gegevens behoorlijk met het cellulaire Netwerk van Gegevens zoals die binnen het Werkende Systeem wordt vermeld wordt verbonden.
1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden
1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.
   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk aan uw Plaatsing van de Router aanpast.
1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden dit kan gewoonlijk ook worden geïdentificeerd gebruikend een Signal leiden op StandaardRouters. Als dit niet O.K. kijkt, gelieve uw ISP Dienst te contacteren om uw Router ver te controleren.
iv. Als al hierboven correct wordt gevormd en een foutenmelding nog verschijnt, controleer uw actieve netwerkcomponenten zoals Schakelaars of extra Routers als er om het even welke beperking van de Haven is.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en overeenkomstig registreren. AEM Screens starten

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet correct verbinden en de verwachte inhoud niet tonen:
   >
   >1. Controleer in uw Firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443`.
   >1. Zorg ervoor dat alle benodigde Havens zijn toegestaan.



## Vereisten voor het instellen van een mobiele netwerkconfiguratie {#requirements-direct}

De netwerkOpstelling kan logisch gezien in twee blokken worden gescheiden:

* Mobiele internetverbinding

* Netwerk voor lokale gebieden

### Mobiele internetverbinding {#mobile-internet-connection}

De prestaties van de Verbinding van Internet hebben, naast reeds beschreven netwerkbereikbaarheid, om voldoende Bandwith te verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen. In detail, &quot;voldoende&quot;hangt van de hoeveelheid aangesloten AEM schermen en van het gebruik van andere consumenten binnen het netwerk, zoals Smartphones, Tablets, Cashiers, Computers of de netwerken van Gast Wifi af.
Houd in mening dat alle apparaten een gelijktijdige toegang tot de verbinding van Internet hebben en de Bandwith gewoonlijk lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.
Naast de specifieke theoretische verbinding van het Netwerk moet het worden gewaarborgd, dat de dekking van de mobiele Router minstens &quot;goed&quot;is (gelieve te verwijzen naar uw Mobiele Handboek van de Router). Ook moet het onderliggende Maandabonnement voldoende gegevenscapaciteit en voldoende bandbreedte dekken om alle verbonden cliënten binnen verbonden LAN te dienen.
De gegevensnetwerken verstrekken standaardBandwith ongeveer.. maximaal:
* 3Go 42 Mbit/sec・ 4Go 150Mbit/sec・ 5Go 1000Mbit/sec-10000Mbit/secWanneer wordt overwogen welk gegevensnetwerk moet worden gebruikt, wordt het aanbevolen de volgende vragen te beantwoorden:
・ Hoeveel cliënten worden verbonden met de Router?
・ Hoeveel inhoudwijzigingen verwacht ik en wat zijn die gemiddelde bestandsgrootten?
Als follow-up moet het vereiste gegevenspakket ten minste zijn:
   `Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`
Controleer of er voldoende buffer is.
Let op: Voor het eerste uploaden van mediabestanden, bijvoorbeeld door het integreren van nieuwe spelers, moet een hogere hoeveelheid gegevens en een hogere downloadtijd worden verwacht en in bovenstaande veronderstellingen worden weerspiegeld.


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van LAN hebben, behalve aan reeds beschreven netwerkbereikbaarheid, om voldoende Bandwith te verstrekken om AEM Screens behoorlijk en regelmatig te werken. In deze dagen past het LAN netwerk gewoonlijk minstens een netwerk 100MBit/sec aan, zodat er voldoende Bandmet zou moeten zijn om vele apparaten met goede prestaties aan het systeem aan te sluiten. Terwijl het gebruiken van andere actieve Component van het Netwerk is het verplicht dat alle die met de netwerkbandwith vereisten aanpassen. Bijvoorbeeld de Componenten van het Netwerk zouden minstens 100Mbit/s norm moeten aanpassen en de Bandwith aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.
Als een WiFI-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, is het raadzaam om minimaal gebruik te maken van moderne WIFI-standaarden, zoals IEEE 802.11g. Deze standaard ondersteunt verbindingen tot 54 Mbit. Alle &quot;nieuwere&quot; standaarden zoals 802.11h-n zijn van betere kwaliteit. Als een Wifi Repeater vereist is, raden we Mesh Wifi Accesspoint-technologie zoals Google Nest Mesh Wifi of dergelijke sterk aan.
Andere WiFi herhalende technologieën leiden tot een enorm verlies van Bandwith in het algemene netwerk.

## Media en middelen downloaden {#download}

AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale werking, bijvoorbeeld wanneer u een afspeellijst hebt gedefinieerd die niet vaak tijdens de dag wordt gewijzigd, biedt dit een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.
De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële weglatingstijden kunnen worden verwacht.
Alle informatie moet worden gezien als het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Dus elk van deze aanvragen voegt de downloadtijd toe en verlengt deze.

![](/help/using/assets/mobile-router-download.png)



