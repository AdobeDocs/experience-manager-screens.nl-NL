---
title: Inleiding tot standaardnetwerkinstellingen
seo-title: Inleiding tot standaardnetwerkinstellingen
description: De pagina beschrijft Standaardnetwerkinstellingen
seo-description: De pagina beschrijft Standaardnetwerkinstellingen
translation-type: tm+mt
source-git-commit: 77cf87cbce39a00528b2690d9689861b91e61fc5
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---


# Netwerkverkeer beheren {#managing-network-traffic}

Een Opstelling van het Netwerk kan diverse structuren hebben. Deze sectie beschrijft de meest gebruikelijke netwerkmontages binnen de het netwerkopstelling van een organisatie.

Deze gids benadrukt een inleiding aan volmachtsservers die door de gevarieerde netwerkstructuren worden gevolgd die opstelling binnen verschillende organisaties zijn.

>[!NOTE]
>**AEM Screens netwerkvereisten **>De AEM Screens communiceert direct met AEM als Cloud Service, daarom is het noodzakelijk om een stabiele verbinding tussen de twee knopen te vestigen. De firewalls zijn absoluut verplicht voor commerciële toegang van Internet en als klant moet u begrijpen welke communicatie havens in firewalls en andere op IT-Veiligheid betrekking hebbende netwerkcomponenten moeten worden geopend.

## Overzicht van proxyservers {#proxy-servers}

Een verbinding van Internet baseert zich op het gebruik van een Server van de Volmacht. Een Server van de Volmacht is een specifieke computer of een softwaresysteem die op een computer lopen die als intermediair tussen een eindpuntapparaat, zoals een computer, en een andere server dienst doet waarvan een gebruiker of een cliënt om de dienst verzoekt. De proxyserver kan op dezelfde computer als een firewallserver bestaan of op een aparte server staan, die aanvragen doorstuurt via de firewall.

Een voordeel van een volmachtsserver is dat het geheime voorgeheugen alle gebruikers kan dienen. Als één of meerdere plaatsen van Internet vaak worden gevraagd, zullen deze waarschijnlijk in het geheime voorgeheugen van de volmacht zijn, verbetert het de tijd van de gebruikersreactie. Een volmacht kan zijn interactie ook registreren, die voor het oplossen van problemen wordt gebruikt.

## Werken met de standaardnetwerkinstellingen {#network-setups}

Om een netwerkOpstelling uit te voeren, moet u naar de volgende scenario&#39;s met hun sterke punten en plaatsingsdetails verwijzen.

Er zijn vier belangrijke types van de montages van het Netwerk:

1. [Direct Internet Network (bekabeld/draadloos)](/help/using/direct-internet-network.md)
1. [Direct mobiel netwerk](/help/using/mobile-network.md)
1. [Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk](/help/using/mobile-network-router.md)
1. [Enclosed Corporate Network (bekabeld/draadloos)](/help/using/enclosed-corporate-network.md)

De volgende lijst schetst de verschillende types van netwerkmontages met voor en nadelen:

<table>
 <tbody>
  <tr>
   <td><strong>Netwerkinstellingen</strong></td>
   <td><strong>Voordelen</strong></td>
   <td><strong>Nadelen</strong></td>
  </tr>
  <tr>
   <td><strong>Direct Internet Network (bekabeld/draadloos)</strong></td>
   <td>Gemakkelijk en recht door:sturen aan Opstelling<br>Goede keus voor middelgrote of grotere Installaties<br>Dedicated Netwerk kan worden Encapsulated<br>Weg Punten van mislukking<br>Relatief Ingekoste<br>Goede Schaalbaarheid</td>
   <td>Verplicht internetgegevensplan </td>
  </tr>
    <tr>
   <td><strong>Direct mobiel netwerk</strong></td>
   <td>Eenvoudig in te stellen<br>Goede keuze voor middelgrote of grotere installaties<br>Goede schaalbaarheid<br>ingekapselde schermen
</td>
   <td>Verplichte internetverbinding</td>
  </tr>
    <tr>
<tr>
   <td><strong>Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk</strong></td>
   <td>Gemakkelijk aan Opstelling<br>Goede Keuze voor Midden-grootte of Grotere Installaties<br>Dedicated Netwerk kan worden ingekapseld<br>Weinig Punten van Mislukking<br>Relatief goedkoop<br>Goede scalability</br></td>
   <td>Verplicht internetgegevensplan</td>
  </tr>
    <tr>

<td><strong>Enclosed Corporate Network (bekabeld/draadloos)</strong></td>
   <td>Hoge flexibiliteit en scalability<br>hoogst veilig toe te schrijven aan verschillende lijnen van defensie<br>Encapsulated Netwerken<br>Gemakkelijk om te controleren en te handhaven<br>betrouwbaar</td>
   <td>Gecompliceerde en dure<br>Aanbevolen voor de Specialisten van het Netwerk of Integrators van het Systeem</td>
  </tr>
  </tr>
 </tbody>
</table>


