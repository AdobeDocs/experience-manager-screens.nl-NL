---
title: Inleiding tot standaardnetwerkinstellingen
seo-title: Inleiding tot standaardnetwerkinstellingen
description: De pagina beschrijft Standaardnetwerkinstellingen
seo-description: De pagina beschrijft Standaardnetwerkinstellingen
translation-type: tm+mt
source-git-commit: ae7da9c48188c3f7567d05d0e9a5a6b72383d539
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Netwerkverkeer beheren {#managing-network-traffic}

Een Opstelling van het Netwerk kan diverse structuren hebben. Deze sectie verstrekt een overzicht van de netwerkstructuren die in een milieu worden opgesteld. Er zijn verschillende instellingen die soms helemaal opnieuw worden geïmplementeerd.

Deze sectie benadrukt een inleiding aan volmachtsservers die door de verschillende netwerkstructuren worden gevolgd die opstelling met verschillende organisaties zijn.

>[!NOTE]
>**AEM Screens netwerkvereisten **>De AEM Screens communiceert direct met de Cloud Service AEM, daarom is er behoefte om een stabiele verbinding tussen die twee knopen te vestigen. Firewalls zijn absoluut verplicht voor commerciële internettoegang en de klant moet weten welke communicatiepoorten moeten worden geopend in Firewalls en andere IT-beveiligingsgerelateerde netwerkonderdelen die onder de controle van de klant staan.

## Proxyservers {#proxy-servers}

Een volmachtsserver is een specifieke computer of een softwaresysteem die op een computer lopen die als intermediair tussen een eindpuntapparaat, zoals een computer, en een andere server dienst doet waarvan een gebruiker of een cliënt om de dienst verzoekt. De proxyserver kan op dezelfde computer als een firewallserver bestaan of op een aparte server staan, die aanvragen doorstuurt via de firewall.

Een voordeel van een volmachtsserver is dat het geheime voorgeheugen alle gebruikers kan dienen. Als er vaak om een of meer internetsites wordt gevraagd, bevinden deze zich waarschijnlijk in het cache van de proxy, waardoor de responstijd van de gebruiker wordt verbeterd. Een volmacht kan zijn interactie ook registreren, die voor het oplossen van problemen nuttig kan zijn.

## Werken met de standaardnetwerkinstellingen {#network-setups}

Om een netwerkOpstelling uit te voeren, moet u naar de volgende scenario&#39;s met sterke punten en plaatsingsdetails verwijzen.

Er zijn drie belangrijke types van de montages van het Netwerk:

1. [Directe internettoegang](/help/using/direct-internet-access.md)
1. [Direct mobiel netwerk](/help/using/mobile-network-setup.md)
1. [Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk](/help/using/mobile-network-setup-router.md)
1. [Engesloten bedrijfsnetwerk](/help/using/enclosed-corporate-network.md)

De volgende lijst schetst de verschillende types van netwerkmontages met voor en nadelen:

<table>
 <tbody>
  <tr>
   <td><strong>Netwerkinstellingen</strong></td>
   <td><strong>Voordelen</strong></td>
   <td><strong>Nadelen</strong></td>
  </tr>
  <tr>
   <td><strong>Directe internettoegang</strong></td>
   <td>Gemakkelijk en recht door:sturen aan Opstelling<br>Goede keus voor middelgrote of grotere Installaties<br>Dedicated Netwerk kan worden ingekapseld<br>Weinig Punten van mislukking<br>Relatief Schap<br>Goede scalability</td>
   <td>Geschikt internetgegevensplan verplicht</td>
  </tr>
    <tr>
   <td><strong>Direct mobiel netwerk</strong></td>
   <td>Eenvoudig en recht vooruit naar SetUp<br>Goede keuze voor middelgrote of grotere installaties<br>Goede schaalbaarheid<br>Encapsulated-schermen
</td>
   <td>Geschikte internetverbinding verplicht</td>
  </tr>
    <tr>
<tr>
   <td><strong>Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk</strong></td>
   <td>Gemakkelijk en recht door:sturen aan SetUp<br>Goede keus voor middelgrote of grotere installaties<br>Dedicated Netwerk kan worden ingekapseld<br>Weinig Punten van mislukking<br>Relatief Goedkope<br>scalability</br></td>
   <td>Geschikt internetgegevensplan verplicht</td>
  </tr>
    <tr>

<td><strong>Engesloten bedrijfsnetwerk</strong></td>
   <td>Hoge flexibiliteit en scalability<br>hoogst veilig toe te schrijven aan verschillende Lijnen van Defense<br>Encapsulated netwerken<br>Gemakkelijk om te controleren en te handhaven<br>Betrouwbaar</td>
   <td>De gecompliceerde en dure<br>specialisten van het Netwerk of de Integrator van het Systeem adviseerde</td>
  </tr>
  </tr>
 </tbody>
</table>


