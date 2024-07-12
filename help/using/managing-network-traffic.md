---
title: Netwerkverkeer beheren
description: De pagina beschrijft Standaardnetwerkinstellingen en hoe u het netwerkverkeer kunt beheren.
exl-id: b6d8f4a3-fca2-4556-9455-b9e27b138154
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Netwerkverkeer beheren {#managing-network-traffic}

Een Opstelling van het Netwerk kan diverse structuren hebben. In deze sectie worden de meest gebruikelijke netwerkinstellingen en algemene benaderingen beschreven die binnen een organisatie worden gevolgd.

Deze gids benadrukt een inleiding aan volmachtsservers die door de gevarieerde netwerkstructuren worden gevolgd die opstelling binnen verschillende organisaties zijn.

>[!NOTE]
>**Vereisten van het Netwerk van AEM Screens**
>AEM Screens communiceert rechtstreeks met de AEM as a Cloud Service en moet daarom een stabiele verbinding tot stand brengen tussen de twee knooppunten. De firewalls zijn verplicht voor commerciële toegang tot Internet. Als klant, begrijp welke communicatie havens in deze firewalls en andere op IT-Veiligheid betrekking hebbende netwerkcomponenten moeten worden geopend.

## Overzicht van proxyservers {#proxy-servers}

Een internetverbinding is afhankelijk van het gebruik van een proxyserver. Een proxyserver is een toegewijde computer of een softwaresysteem dat op een computer wordt uitgevoerd. Het doet dienst als intermediair tussen een eindpuntapparaat, zoals een computer, en een andere server waarvan een gebruiker of een cliënt de dienst aanvraagt. De proxyserver kan op dezelfde computer als een firewallserver bestaan of op een aparte server staan, die aanvragen doorstuurt via de firewall.

Een voordeel van een proxyserver is dat de cache van deze server alle gebruikers kan bedienen. Als er vaak om een of meer internetsites wordt gevraagd, bevinden deze sites zich waarschijnlijk in de cache van de proxy. Een dergelijke caching verbetert de reactietijd van de gebruiker verder. Een volmacht kan zijn interactie ook registreren, die voor het oplossen van problemen kan worden gebruikt.

Wanneer een volmachtsserver een verzoek om een middel van Internet (zoals een Web-pagina ontvangt of terwijl het verbinden met een Uitgever van de AEM), scant het zijn lokaal geheime voorgeheugen van eerder geroepen urls. Als het de pagina vindt, keert het het aan de gebruiker terug zonder het verzoek aan Internet door:sturen. Als de pagina niet in het geheime voorgeheugen is, handelt de volmachtsserver als cliënt namens de gebruiker en verzoekt de pagina van de server in Internet. Wanneer de inhoud wordt geretourneerd, koppelt de proxyserver het aan de oorspronkelijke aanvraag en stuurt het door naar de gebruiker.

## De standaardnetwerkinstellingen {#network-setups}

Om een Opstelling van het Netwerk uit te voeren, zie de volgende scenario&#39;s met hun sterke punten en plaatsingsdetails.

Deze gids benadrukt vier verschillende soorten de Montages van het Netwerk binnen een Organisatie:

* **[Direct Netwerk van Internet (Getelegrafeerd/Draadloos)](/help/using/direct-internet-network.md)**
* **[Direct Mobiel Netwerk](/help/using/mobile-network.md)**
* **[Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk](/help/using/mobile-network-router.md)**
* **[Enclosed Collectief Netwerk (Getelegrafeerd/Draadloos)](/help/using/enclosed-corporate-network.md)**

De volgende lijst schetst de verschillende types van netwerkmontages met voor en nadelen:

| Netwerkinstellingen | Voordelen | Nadelen |
|--- |--- |--- |
| **Direct Netwerk van Internet (Getelegrafeerd/Draadloos)** | Gemakkelijk en recht door:sturen aan <br> Goede keus SetUp voor middelgrote of grotere Installaties <br> Dedicated Netwerk kan <br> Weinigen Punten van mislukking <br> Relatief goedkoop <br> Goede Scalability worden ingekapseld | Verplicht internetgegevensplan |
| **Direct Mobiel Netwerk** | Gemakkelijk om <br> Goede Keuze voor Midden-grootte of Grotere Installaties <br> Goede Scalability <br> Encapsulated Screens te plaatsen | Verplichte internetverbinding |
| **Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk** | Gemakkelijk om <br> Goede Keuze voor Midden-grootte of Grotere Installaties <br> Dedicated Netwerk te plaatsen kan <br> Weg punten van Verval <br> Relatief goedkoop <br> Goed scalability worden ingekapseld | Verplicht internetgegevensplan |
| **Enclosed Collectief Netwerk (Getelegrafeerd/Draadloos)** | De hoge flexibiliteit en scalability <br> hoogst veilig toe te schrijven aan Verschillende lijnen van de Verdediging <br> Encapsulated Netwerken <br> Gemakkelijk om <br> Betrouwbaar te controleren en te handhaven | Gecompliceerde en Uitzonderlijke <br> geadviseerd voor de Specialisten van het Netwerk of Integrators van het Systeem |
