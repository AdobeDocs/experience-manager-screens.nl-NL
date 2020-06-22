---
title: Mobiel netwerk instellen
description: De pagina beschrijft de Mobiele Opstelling van het Netwerk
translation-type: tm+mt
source-git-commit: 6a0460fd6c62fd6408d3c7665b626818929351d9
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---


# Mobiele netwerkinstellingen {#mobile-network-setup}

Adobe AEM Screens Players kan ook worden aangesloten gebruikend Mobiele/Cellulaire Netwerken die minstens een 3G netwerk in werking stellen.
Binnen de AEM Screens wordt de benodigde inhoud fysiek gedownload naar de Player-controller/computer en correct opgeslagen in het onderliggende besturingssysteem. Hierdoor heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijd en de prestaties van de weergavesystemen worden helemaal niet beïnvloed.
Verbinding van AEM Screens Players met een Cellular 3/4/5G verbindt met uw Leverancier van de Gegevens van de Mobiele Dienst. Het voordeel van deze Opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare dekking van het Netwerk te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie met zo min mogelijk omringende beton- of metaalconstructie.
Met deze configuratie kunnen gebruikers van AEM-schermen heel flexibel werken, omdat er geen vaste lijn nodig is om AEM Screens te verbinden.


## Vereisten voor het opzetten van een netwerk voor directe toegang {#requirements-direct}

De netwerkopstelling zoals die in 5.5 wordt beschreven kan logisch gezien in drie blok worden gescheiden. Het WAN/Buitenwereld/het Blok van de Verbinding van Internet (hier mobiele Verbinding van Gegevens), het interne LAN/Netwerk van het Lokale Gebied en facultatieve subsecties van LAN die door Actieve Componenten van het Netwerk worden gescheiden.
Om de best mogelijke prestaties te kunnen leveren, moet ervoor worden gezorgd dat beide onderdelen voldoen aan de aanbevolen minimumnormen.
Wat betekent &quot;goede prestaties&quot;in het Milieu van AEM Screens?
AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale werking, bijvoorbeeld wanneer u een afspeellijst hebt gedefinieerd die niet vaak tijdens de dag wordt gewijzigd, biedt dit een vrijwel netwerkonafhankelijke bewerking, zodra alle bestanden op de speler zijn opgeslagen.
Voor die gebruiksgevallen waarin er meer interacties met sensoren of andere triggers zijn en de inhoud zeer dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.
De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële weglatingstijden kunnen worden verwacht.
Alle informatie moet worden gezien als het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Dus elk van deze aanvragen voegt de downloadtijd toe en verlengt deze.


### WAN-/internetverbinding {#wan-connection}

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


### LAN-verbinding {#lan-connection}

De prestaties van LAN hebben, behalve aan reeds beschreven netwerkbereikbaarheid, om voldoende bandbreedte te verstrekken om AEM Screens behoorlijk en regelmatig in werking te stellen. In deze dagen past het LAN netwerk gewoonlijk minstens een netwerk 100MBit/sec aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem aan te sluiten. Wanneer u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte. Bijvoorbeeld de Componenten van het Netwerk zouden minstens 100Mbit/s norm moeten aanpassen en de bandbreedte aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.
Als een WiFI-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, is het raadzaam ten minste gebruik te maken van moderne WIFI-standaarden zoals IEEE 802.11g. Deze standaard ondersteunt verbindingen tot 54 Mbit. Alle &quot;nieuwere&quot; standaarden zoals 802.11h-n zijn van betere kwaliteit. Als een Wifi Repeater wordt vereist adviseren wij sterk de technologieën van het Punt van de Toegang van het Netwerk Wifi zoals het Net van Google Net Wifi of gelijkaardig.
Andere WiFi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het totale netwerk.
