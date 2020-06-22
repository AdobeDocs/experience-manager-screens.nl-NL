---
title: Direct mobiel netwerk
description: De pagina beschrijft Direct Mobile Network Setup
translation-type: tm+mt
source-git-commit: 0b1106b3cf7f83857f83e43f773a0d19556cfec5
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 0%

---


# Direct mobiel netwerk {#mobile-network-setup}

AEM Screens Players kunnen ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

Binnen de AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Hierdoor heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijd en niet op de prestaties van beeldschermen.

Verbinding van AEM Screens Players met een Cellular 3/4/5G verbindt met uw Leverancier van de Gegevens van de Mobiele Dienst. Het voordeel van deze Opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare dekking van het Netwerk te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie met zo min mogelijk omringende beton- of metaalconstructie.

Met deze configuratie kunnen AEM-schermgebruikers heel flexibel werken omdat er geen vaste verbinding is vereist om AEM Screens te verbinden.

![](/help/using/assets/direct-mobile-1.png)

## Verbinding maken tussen AEM Screens Player en Direct mobiel netwerk {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om verbinding te maken met AEM Screen-spelers in deze configuratie:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.

1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk aan uw Plaatsing van de Router aanpast.
1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden dit kan gewoonlijk ook worden geïdentificeerd gebruikend een Signal leiden op StandaardRouters.
1. Als alles hierboven correct wordt gevormd en een foutenmelding nog verschijnt, controleer uw actieve netwerkcomponenten zoals Schakelaars of extra Routers als er om het even welke beperking van de Haven is.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en overeenkomstig registreren. Start AEM Screens.

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

De prestaties van de Verbinding van Internet hebben, naast reeds beschreven netwerkbereikbaarheid, om voldoende bandbreedte te verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen. In detail, &quot;voldoende&quot;hangt van de hoeveelheid aangesloten AEM schermen en van het gebruik van andere consumenten binnen het netwerk, zoals Smartphones, Tablets, Cashiers, Computers of de netwerken van Gast Wifi af.
Houd in mening dat alle apparaten een gezamenlijke toegang tot de verbinding van Internet hebben en de bandbreedte gewoonlijk lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.
Naast de specifieke theoretische verbinding van het Netwerk moet het worden gewaarborgd, dat de dekking van de mobiele Router minstens &quot;goed&quot;is (gelieve te verwijzen naar uw Mobiele Handboek van de Router). Ook het onderliggende Maandelijkse Plan moet genoeg Capaciteit van Gegevens en voldoende bandbreedte behandelen om alle verbonden cliënten binnen verbonden LAN te dienen.
De netwerken van Gegevens verstrekken standaardbandbreedte heeft ongeveer.. maximaal:
・ 3Go 42 Mbit/sec・ 4Go 150Mbit/sec・ 5Go 1000Mbit/sec-10000Mbit/secWanneer wordt overwogen welk gegevensnetwerk moet worden gebruikt, wordt het aanbevolen de volgende vragen te beantwoorden:
・ Hoeveel cliënten worden verbonden met de Router?
・ Hoeveel inhoudwijzigingen verwacht ik en wat zijn die gemiddelde bestandsgrootten?
Als follow-up moet het vereiste gegevenspakket ten minste zijn:
Capaciteit gegevenspakket = aantal clients * (# inhoudsbestanden * Gemiddelde bestandsgrootte)Controleer of er voldoende buffer is.
Let op: Voor het eerste uploaden van mediabestanden, bijvoorbeeld door het integreren van nieuwe spelers, moet een hogere hoeveelheid gegevens en een hogere downloadtijd worden verwacht en in bovenstaande veronderstellingen worden weerspiegeld.
Als duimregel, zou een netwerk 4G met &quot;goede&quot;dekking en onbeperkte Gegevens de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van LAN hebben, behalve aan reeds beschreven netwerkbereikbaarheid, om voldoende Bandwith te verstrekken om AEM Screens behoorlijk en regelmatig te werken. In deze dagen past het LAN netwerk gewoonlijk minstens een netwerk 100MBit/sec aan, zodat er voldoende Bandmet zou moeten zijn om vele apparaten met goede prestaties aan het systeem aan te sluiten. Terwijl het gebruiken van andere actieve Component van het Netwerk is het verplicht dat alle die met de netwerkbandwith vereisten aanpassen. Bijvoorbeeld de Componenten van het Netwerk zouden minstens 100Mbit/s norm moeten aanpassen en de Bandwith aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.

## Media en middelen downloaden {#download}

AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale werking, bijvoorbeeld wanneer u een afspeellijst hebt gedefinieerd die niet vaak tijdens de dag wordt gewijzigd, biedt dit een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.
De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële wachttijden kunnen worden verwacht.
Alle informatie moet worden gezien als het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Dus elk van deze aanvragen voegt de downloadtijd toe en verlengt deze.

![](/help/using/assets/download-times-mobile.png)



