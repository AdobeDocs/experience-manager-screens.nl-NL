---
title: Netwerkverkeer beheren
description: De pagina beschrijft Standaardnetwerkinstellingen en hoe u het netwerkverkeer kunt beheren.
exl-id: b6d8f4a3-fca2-4556-9455-b9e27b138154
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# Netwerkverkeer beheren {#managing-network-traffic}

Een Opstelling van het Netwerk kan diverse structuren hebben. In deze sectie worden de meest gebruikelijke netwerkinstellingen en algemene benaderingen beschreven die binnen een organisatie worden gevolgd.

Deze gids benadrukt een inleiding aan volmachtsservers die door de gevarieerde netwerkstructuren worden gevolgd die opstelling binnen verschillende organisaties zijn.

>[!NOTE]
>**AEM Screens-netwerkvereisten**
>AEM Screens communiceert rechtstreeks met de as a Cloud Service AEM en moet daarom een stabiele verbinding tussen de twee knooppunten tot stand brengen. De firewalls zijn verplicht voor commerciële toegang tot Internet. Als klant, begrijp welke communicatie havens in deze firewalls en andere op IT-Veiligheid betrekking hebbende netwerkcomponenten moeten worden geopend.

## Overzicht van proxyservers {#proxy-servers}

Een verbinding van Internet baseert zich op het gebruik van een Server van de Volmacht. Een Proxyserver is een toegewijde computer of een softwaresysteem dat op een computer wordt uitgevoerd. Het doet dienst als intermediair tussen een eindpuntapparaat, zoals een computer, en een andere server waarvan een gebruiker of een cliënt de dienst aanvraagt. De proxyserver kan op dezelfde computer als een firewallserver bestaan of op een aparte server staan, die aanvragen doorstuurt via de firewall.

Een voordeel van een proxyserver is dat de cache van deze server alle gebruikers kan bedienen. Als één of meerdere plaatsen van Internet vaak worden gevraagd, zullen deze waarschijnlijk in het geheime voorgeheugen van de volmacht zijn, en dit verbetert verder de tijd van de gebruikersreactie. Een volmacht kan zijn interactie ook registreren, die voor het oplossen van problemen kan worden gebruikt.

Wanneer een volmachtsserver een verzoek om een middel van Internet (zoals een Web-pagina ontvangt of terwijl het verbinden met een Uitgever van de AEM), scant het zijn lokaal geheime voorgeheugen van eerder geroepen urls. Als het de pagina vindt, keert het het aan de gebruiker terug zonder het verzoek aan Internet door:sturen. Als de pagina niet in het geheime voorgeheugen is, handelt de volmachtsserver (als cliënt) namens de gebruiker en verzoekt de pagina van de server in Internet. Wanneer de inhoud wordt geretourneerd, koppelt de proxyserver het aan de oorspronkelijke aanvraag en stuurt het door naar de gebruiker.

## De standaardnetwerkinstellingen {#network-setups}

Om een netwerkOpstelling uit te voeren, zie de volgende scenario&#39;s met hun sterke punten en plaatsingsdetails.

Deze gids benadrukt vier verschillende soorten de Montages van het Netwerk binnen een Organisatie:

* **[Direct Internet Network (bekabeld/draadloos)](/help/using/direct-internet-network.md)**
* **[Direct mobiel netwerk](/help/using/mobile-network.md)**
* **[Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk](/help/using/mobile-network-router.md)**
* **[Enclosed Corporate Network (bekabeld/draadloos)](/help/using/enclosed-corporate-network.md)**

De volgende lijst schetst de verschillende types van netwerkmontages met voor en nadelen:

| Netwerkinstellingen | Voordelen | Nadelen |
|--- |--- |--- |
| **Direct Internet Network (bekabeld/draadloos)** | Eenvoudig en recht vooruit naar SetUp<br>Goede keuze voor middelgrote of grotere installaties<br>Het specifieke Netwerk kan worden ingekapseld<br>Enkele foutpunten<br>Relatief goedkoop<br>Goede schaalbaarheid | Verplicht internetgegevensplan |
| **Direct mobiel netwerk** | Eenvoudig in te stellen<br>Goede keuze voor middelgrote of grotere installaties<br>Goede schaalbaarheid<br>Ingekapselde schermen | Verplichte internetverbinding |
| **Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk** | Eenvoudig in te stellen<br>Goede keuze voor middelgrote of grotere installaties<br>Het specifieke Netwerk kan worden ingekapseld<br>Enkele foutpunten<br>Relatief goedkoop<br>Goede schaalbaarheid | Verplicht internetgegevensplan |
| **Enclosed Corporate Network (bekabeld/draadloos)** | Hoge flexibiliteit en schaalbaarheid<br>Zeer veilig vanwege verschillende regels van defensie<br>Encapsulated Networks<br>Eenvoudig te bewaken en te onderhouden<br>Betrouwbaar | Gecompliceerd en duur<br>Aanbevolen voor de Specialisten van het Netwerk of de Integrators van het Systeem |
