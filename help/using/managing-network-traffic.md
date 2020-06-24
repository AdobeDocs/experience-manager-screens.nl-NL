---
title: Netwerkverkeer beheren
description: De pagina beschrijft Standaardnetwerkinstellingen en hoe u het netwerkverkeer kunt beheren.
translation-type: tm+mt
source-git-commit: d27abdfd92336279bf2c6abe4d2ae38b6e9077bf
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Netwerkverkeer beheren {#managing-network-traffic}

Een Opstelling van het Netwerk kan diverse structuren hebben. In deze sectie worden de meest gebruikelijke netwerkinstellingen en algemene benaderingen beschreven die binnen een organisatie worden gevolgd.

Deze gids benadrukt een inleiding aan volmachtsservers die door de gevarieerde netwerkstructuren worden gevolgd die opstelling binnen verschillende organisaties zijn.

>[!NOTE]
>
>**AEM Screens netwerkvereisten**
>
>De AEM Screens communiceert direct met AEM als Cloud Service, daarom is het vereist om een stabiele verbinding tussen de twee knopen te vestigen. De firewalls zijn absoluut verplicht voor commerciële toegang van Internet en als klant moet u begrijpen welke communicatie havens in deze firewalls en andere op IT-Veiligheid betrekking hebbende netwerkcomponenten moeten worden geopend.

## Overzicht van proxyservers {#proxy-servers}

Een verbinding van Internet baseert zich op het gebruik van een Server van de Volmacht. Een Server van de Volmacht is een specifieke computer of een softwaresysteem die op een computer lopen die als intermediair tussen een eindpuntapparaat, zoals een computer, en een andere server dienst doet waarvan een gebruiker of een cliënt om de dienst verzoekt. De proxyserver kan op dezelfde computer als een firewallserver bestaan of op een aparte server staan, die aanvragen doorstuurt via de firewall.

Een voordeel van een volmachtsserver is dat het geheime voorgeheugen alle gebruikers kan dienen. Als één of meerdere plaatsen van Internet vaak worden gevraagd, zullen deze waarschijnlijk in het geheime voorgeheugen van de volmacht zijn, en dit verbetert verder de tijd van de gebruikersreactie. Een volmacht kan zijn interactie ook registreren, die voor het oplossen van problemen kan worden gebruikt.

Wanneer een volmachtsserver een verzoek om een middel van Internet (zoals een Web-pagina ontvangt of terwijl het verbinden met een Uitgever AEM), scant het zijn lokaal geheime voorgeheugen van eerder geroepen urls. Als het de pagina vindt, keert het het aan de gebruiker terug zonder het verzoek aan Internet door:sturen. Als de pagina niet in het geheime voorgeheugen is, handelt de volmachtsserver (als cliënt) namens de gebruiker en verzoekt de pagina van de server in Internet. Wanneer de inhoud wordt geretourneerd, koppelt de proxyserver de inhoud aan de oorspronkelijke aanvraag en stuurt deze door naar de gebruiker.

## Werken met de standaardnetwerkinstellingen {#network-setups}

Om een netwerkOpstelling uit te voeren, moet u naar de volgende scenario&#39;s met hun sterke punten en plaatsingsdetails verwijzen.

Deze gids benadrukt vier verschillende soorten de Montages van het Netwerk binnen een Organisatie:

* **[Direct Internet Network (bekabeld/draadloos)](/help/using/direct-internet-network.md)**
* **[Direct mobiel netwerk](/help/using/mobile-network.md)**
* **[Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk](/help/using/mobile-network-router.md)**
* **[Enclosed Corporate Network (bekabeld/draadloos)](/help/using/enclosed-corporate-network.md)**

De volgende lijst schetst de verschillende types van netwerkmontages met voor en nadelen:

| Netwerkinstellingen | Voordelen | Nadelen |
|--- |--- |--- |
| **Direct Internet Network (bekabeld/draadloos)** | Gemakkelijk en recht door:sturen aan<br>SetUpGood keus voor middelgrote of grotere<br>InstallationsDedicated Netwerk kan<br>EncapsulatedWeinig Punten van<br>mislukkingRelatief<br>IndureGoede Scalability zijn | Verplicht internetgegevensplan |
| **Direct mobiel netwerk** | Eenvoudig in<br>SetUpGood keuze voor middelgrote of grotere<br>installatiesGoede<br>schaalbaarheidEncapsulated schermen | Verplichte internetverbinding |
| **Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk** | Gemakkelijk aan<br>Keuze SetUpGood voor Midden-grootte of Grotere<br>InstallationsDedicated Netwerk kan<br>EncapsulatedEnkele Punten van<br>MisluktRelatief<br>IndureGoede scalability zijn | Verplicht internetgegevensplan |
| **Enclosed Corporate Network (bekabeld/draadloos)** | Hoge flexibiliteit en<br>scalabilityZeer veilig toe te schrijven aan verschillende lijnen van<br>DefenseEncapsulated<br>NetworksEasy to Monitor and<br>MaintenanceReliable | Gecompliceerde en<br>ExpensiveRecommended voor de Specialisten van het Netwerk of Integrators van het Systeem |
