---
title: Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
description: De pagina beschrijft Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: 707833ddd8ab2573abcac4e9a77ec88778624435
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 0%

---

# Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#mobile-network-setup}

Adobe AEM Screens Players kunnen ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

In AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijden en op de updates van de inhoud. De bandbreedte heeft geen invloed op de prestaties van het regelmatig afspelen van beeldschermen.

Het voordeel van deze opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare netwerkdekking te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie met zo weinig mogelijk omringende beton- of metaalconstructie.
Deze instelling biedt AEM schermgebruikers de flexibiliteit omdat er geen vaste lijn nodig is om verbinding te maken met AEM Screens. Dit is vooral interessant voor letterlijke of mobiele instellingen.

Het volgende diagram toont het Mobiele Netwerk met de Mobiele Configuratie van de Router van Gegevens en de Actieve Componenten van het Netwerk en bevat een toegang van Internet van om het even welke controlemechanismen van AEM Screens door directe toegang van Internet gebruikend een eigen Gegevens 3/4/5G.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player verbinden met mobiel netwerk met mobiele gegevensrouter en actieve netwerkcomponenten {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

De configuratie wijst een Toegang van Internet voor elk Controlemechanisme van AEM Screens door de Directe Toegang van Internet toe gebruikend een specifieke 3/4/5G Verbinding van Gegevens.

1. Zorg ervoor dat de Mobiele Router van Gegevens behoorlijk wordt verbonden met het cellulaire Netwerk van Gegevens zoals die binnen het Werkende Systeem wordt vermeld en elk van de spelers van het AEM van het Scherm wordt aangesloten aan het Netwerk van Routers.
1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.
   >[!NOTE]
   >Als er een fout optreedt, controleert u de netwerkinstellingen. Er zijn eigenlijk twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie


1. Zorg ervoor dat het plaatsen van de Adapter van het Netwerk uw Plaatsende Router aanpast.

1. Controle als de Router behoorlijk met het ISP Netwerk van het Gebied (de Verbinding van Internet) wordt verbonden dit kan ook worden geïdentificeerd gebruikend Signal leiden op Standaard Routers.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet behoorlijk verbindt en de verwachte inhoud niet getoond dan controleer uw firewall van de Router van Internet als er om het even welke beperkingen betreffende zijn `TCP/IP Port 80/443`.


## Vestiging Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#requirements-direct}

De netwerkOpstelling kan logisch gezien in twee blokken worden gescheiden:

* Mobiele internetverbinding

* Netwerk voor lokale gebieden

### Mobiele internetverbinding {#mobile-internet-connection}

De prestaties van de verbinding van Internet, naast reeds beschreven netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens inhoud uit te voeren downloadt regelmatig.

*Voldoende* is afhankelijk van de hoeveelheid aangesloten AEM en van het gebruik van andere consumenten in het netwerk, zoals smartphones, tablets, cashiers, computers of gastWi-Fi-netwerken.
Houd in mening dat alle apparaten een gezamenlijke toegang tot de verbinding van Internet hebben en de bandbreedte gewoonlijk lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.
Naast de specifieke theoretische verbinding van het Netwerk, moet worden gewaarborgd dat de dekking van de mobiele Router minstens &quot;goed&quot;is. Ook het onderliggende Maandelijkse Plan moet genoeg Capaciteit van Gegevens en voldoende bandbreedte behandelen om alle verbonden cliënten binnen verbonden LAN te dienen.

De volgende lijst benadrukt de gegevensnetwerken met hun standaardbandbreedte:

| Gegevensnetwerk | Bandbreedte |
|--- |--- |
| 3G | 42 Mbps |
| 4G | 150 Mbps |
| 5G | 1000 - 10000 Mbps |

Wanneer het overwegen van welk Netwerk van Gegevens zou moeten worden gebruikt wordt het geadviseerd om de volgende vragen te beantwoorden:

* Hoeveel cliënten worden verbonden met de Router?

* Hoeveel inhoudswijzigingen worden verwacht en wat zijn die gemiddelde bestandsgrootten?

>[!NOTE]
>
>Het benodigde gegevenspakket moet ten minste:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>Voor het aanvankelijk uploaden van mediabestanden, bijvoorbeeld, terwijl nieuwe spelers worden geïntegreerd, moet een hogere hoeveelheid gegevens en een verhoogde downloadtijd worden verwacht en in de bovenstaande veronderstellingen worden weerspiegeld. Een 4G-netwerk met *goed* De dekking en de onbeperkte Gegevens zouden de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen.


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van LAN, naast reeds beschreven netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om de inhoudsdownloads van AEM Screens regelmatig in werking te stellen. In deze dagen past het LAN netwerk gewoonlijk minstens een netwerk 100 Mbps aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem te verbinden. Bij het gebruik van andere actieve netwerkcomponenten is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte.

Bijvoorbeeld, zouden de Componenten van het Netwerk minstens norm 100 Mbps moeten aanpassen en de bandbreedte aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.

Als een Wi-Fi-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, is het raadzaam ten minste gebruik te maken van moderne Wi-Fi-standaarden, zoals IEEE 802.11g. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwer* Normen als 802.11h-n zijn van betere kwaliteit. Als u een Wi-Fi Repeater nodig hebt, raden we u sterk aan Wi-Fi Access-punttechnologieën zoals Google Nest Mesh Wi-Fi of een vergelijkbare technologie aan.

## Media en middelen downloaden {#download}

AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Als u bijvoorbeeld een afspeellijst hebt gedefinieerd die niet vaak tijdens de dag wordt bijgewerkt, is dit vrijwel gelijk aan een netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.
De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële wachttijden kunnen worden verwacht.

>[!NOTE]
>
>Alle informatie heeft betrekking op het gebruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/mobile-router-download.png)
