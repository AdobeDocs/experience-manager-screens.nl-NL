---
title: Directe internettoegang
description: Directe internettoegang
exl-id: a393ce2f-b774-4cd5-9001-c5cc24d445ae
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Direct Internet Network (bekabeld/draadloos) {#direct-internet-access}

Het directe netwerk van Internet bevat een toegangspunt van de ingang voor de toegang van Internet om de AEM Cloud Servicen te bereiken die AEM Screens met moet verbinden.

De standaardpoorten voor AEM Screens-communicatie zijn:

* `ssl-secured https (TCP Port 443)`
  <br>Of,</br>

* `http (TCP Port 80)`, als uw specifieke gebruikscase dat niveau van veiligheid niet vereist.

De havens kunnen als gevolg van de configuratie van uw specifieke AEM configuratieopstelling variëren. Binnen deze SetUp, worden alle apparaten direct verbonden met uw router van Internet zoals aangetoond in het hieronder cijfer.

![](/help/assets/direct-access-2.png)

De configuratie omvat ook de toegang van Internet door om het even welke Dienstverlener van Internet (ISP) en zijn lijn van Internet. De meeste ISP&#39;s bieden een internetrouter voor de internetmodem, netwerkswitch, Wi-Fi-toegangspunt, firewall en andere netwerkfuncties (afhankelijk van fabrikant en model).

## AEM Screens Player verbinden met Direct Internet Access

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

1. Zorg ervoor dat elk van de AEM spelers van het Scherm met het Netwerk van de router wordt verbonden.
1. Test de verbinding van Internet door een URL in browser van uw systeem te roepen.

   >[!NOTE]
   >Controleer de netwerkinstellingen als er een fout optreedt. Er zijn fundamenteel twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie

1. Zorg ervoor dat het plaatsen van de Adapter van het Netwerk uw routermontages aanpast; controleer als het maximumaantal beschikbare IP adressen in uw netwerk niet wordt bereikt.
1. Controle als de router behoorlijk met ISP groot-gebied-Netwerk (de Verbinding van Internet) wordt verbonden. Of, kan het ook worden geïdentificeerd gebruikend Signal leiden op Standaardrouters.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

   >[!NOTE]
   >**Tip voor probleemoplossing**
   >Als AEM Screens niet correct verbinding maakt en de verwachte inhoud niet wordt weergegeven:
   >
   >1. Controle in uw de routerfirewall van Internet als er om het even welke beperkingen betreffende zijn `TCP/IP Port 80/443`.
   >1. Zorg ervoor dat alle vereiste Havens worden toegestaan.

## Direct internetnetwerk instellen {#requirements-direct}

Het directe netwerk van Internet wordt logisch gezien gescheiden in twee blokken:

* Breed gebiedsnetwerk

* Netwerk voor lokale gebieden

### Breed gebiedsnetwerk {#wan-connection}

De prestaties van de verbinding van Internet, naast bereikbaarheid van het netwerk, moeten voldoende bandbreedte verstrekken om AEM Screens in werking te stellen.

*Voldoende* is afhankelijk van het aantal verbonden AEM Screens. Het hangt ook van het gebruik van andere consumenten binnen het netwerk, zoals smartphones, tablets, cashiers, computers, of gastnetwerken van WiFi af.

>[!NOTE]
>
>De hierboven vermelde apparaten hebben gelijktijdige toegang tot de verbinding van Internet en de bandbreedte vermindert lineair wanneer u meer consumenten of computers aan het netwerk toevoegt.

### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van het Netwerk van het Lokale Gebied (LAN), naast de bereikbaarheid van het netwerk, moeten voldoende bandbreedte verstrekken om AEM Screens in werking te stellen.

Het LAN netwerk past gewoonlijk minstens een netwerk 100-Mbps aan, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem te verbinden.
Als een Wi-Fi-oplossing wordt overwogen om AEM Screens te verbinden met de Internet Link, is het raadzaam om moderne Wi-Fi-standaarden te gebruiken, zoals `IEEE 802.11g` minimaal. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwer* Standaarden als `802.11h-n` van betere kwaliteit zijn.

>[!NOTE]
>
>Als een Wi-Fi Repeater vereist is, raadt de Adobe een Wi-Fi-toegangspunt van het Netwerk aan, zoals Google Nest Mesh Wi-Fi of een vergelijkbaar toegangspunt. Andere Wi-Fi herhalende technologieën leiden tot een enorm verlies van bandbreedte in het hele netwerk.

## Media en middelen downloaden {#download}

AEM Screens biedt een aanzienlijk voordeel voor gebruikers van digitale berichten. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld een gedefinieerde afspeellijst die regelmatig wordt bijgewerkt - biedt deze functie een vrijwel netwerkonafhankelijke bewerking nadat alle bestanden op de speler zijn opgeslagen.

Voor scenario&#39;s, waar er meer interactie met sensoren of trekkers en dynamische inhoud zijn, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe het schermreactie om de best mogelijke klantenervaring te verzekeren.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>
>De informatie laat u de consumptie van elk apparaat in het netwerk bekijken door om een bron van Internet te verzoeken en te downloaden. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/assets/download-times-direct.png)
