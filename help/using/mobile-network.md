---
title: Direct mobiel netwerk
description: De pagina beschrijft Direct Mobile Network Setup
translation-type: tm+mt
source-git-commit: 8e62b3fc4ce324e02aaec6fca9df79b1aaf94d72
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---


# Direct mobiel netwerk {#mobile-network-setup}

AEM Screens Players kunnen ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

Binnen de AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom beïnvloedt de gegeven bandbreedte slechts aanvankelijke downloadtijden en beïnvloedt niet de prestaties van Vertoningen.

De verbinding van de Players van AEM Screens met een Cellular 3/4/5G verbindt met uw Leverancier van de Gegevens van de Mobiele Dienst. Het voordeel van deze Opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare netwerkdekking te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie met een zo optimaal mogelijke omringende beton- of metaalconstructie.

Met deze configuratie kunnen gebruikers van AEM-schermen heel flexibel werken omdat er geen vaste verbinding is vereist om verbinding te maken met AEM Screens.

Het volgende diagram toont de Directe Mobiele Opstelling van het Netwerk en bestaat uit één enkel segment van de netwerkverbinding, de verbinding van elke speler aan het mobiele/cellulaire gegevensnetwerk.

![](/help/using/assets/direct-mobile-1.png)

## Verbinding maken tussen AEM Screens Player en Direct mobiel netwerk {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om AEM Screens-spelers in deze configuratie te verbinden:

1. Zorg ervoor dat elk van de spelers van het Scherm AEM met het Netwerk van Routers wordt verbonden.

1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het Plaatsen van de Adapter van het Netwerk aan uw Router plaatsen aanpast.

1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden dit kan ook worden geïdentificeerd gebruikend Signal leiden op Standaard Routers.

1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

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

De prestaties van de Verbinding van Internet naast netwerkbereikbaarheid verstrekken voldoende bandbreedte om AEM Screens regelmatig in werking te stellen.

*Voldoende* is afhankelijk van de hoeveelheid aangesloten AEM-schermen en van het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, cashiers, computers of WIFI-netwerken van gasten.

>[!NOTE]
>Alle apparaten hebben een gezamenlijke toegang tot de verbinding van Internet en de bandbreedte lineair vermindert terwijl het toevoegen van meer consumenten of computers aan het netwerk.

De netwerken van Gegevens verstrekken standaardbandbreedte van:

**3G**
* 42 Mbps

**4G**
* 150 Mbps

**5G**
* 1000 Mbps - 10000 Mbps

Wanneer het overwegen van welk Netwerk van Gegevens zou moeten worden gebruikt wordt het geadviseerd om de volgende vragen te beantwoorden:

* Hoeveel cliënten worden verbonden met de Router?

* Hoeveel inhoudswijzigingen worden verwacht en wat zijn die gemiddelde bestandsgrootten?

>[!NOTE]
>Het benodigde gegevenspakket moet ten minste:
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>Controleer of er voldoende buffer is.
>Voor de eerste upload van de Dossiers van Media, bijvoorbeeld terwijl het integreren van nieuwe spelers, moet een hogere hoeveelheid Gegevens en een verhoogde Tijd van de Download worden verwacht en die in de bovengenoemde veronderstellingen worden weerspiegeld.Een netwerk 4G met *goede* dekking en *onbeperkte* gegevens zou de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen.


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN) naast de netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens regelmatig in werking te stellen. Het LAN netwerk is gewoonlijk minstens een netwerk 100 Mbps, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem te verbinden.

Wanneer u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte. Bijvoorbeeld, zouden de netwerkcomponenten minstens 100 norm moeten aanpassen Mbps en de bandbreedte aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.

## Media en middelen downloaden {#download}

AEM Screens bieden een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Dit, komt het belangrijkste netwerkverkeer voor voor het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale bewerking, bijvoorbeeld, biedt een gedefinieerde afspeellijst die niet vaak tijdens de dag wordt bijgewerkt, een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.

De volgende lijst verstrekt een overzicht van zeer belangrijke gegevens van de netwerkconnectiviteit verantwoordelijk voor de prestaties die en potentiële wachttijden kunnen worden verwacht.

>[!NOTE]
>Alle informatie heeft betrekking op het gebruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/download-times-mobile.png)



