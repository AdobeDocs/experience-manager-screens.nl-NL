---
title: Direct mobiel netwerk
description: De pagina beschrijft Direct Mobile Network Setup
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---


# Direct mobiel netwerk {#mobile-network-setup}

AEM Screens Players kunnen ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

In AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijd en op de updates van de inhoud. De bandbreedte heeft geen invloed op de prestaties van het regelmatig afspelen van beeldschermen.

Het voordeel om AEM Screens Players over Cellular 3/4/5G met uw Mobiele Leverancier van de Gegevens van de Dienst te verbinden is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare netwerkdekking te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie met zo weinig mogelijk omringende beton- of metaalconstructie.

Deze instelling biedt AEM schermgebruikers een grote flexibiliteit omdat er geen vaste verbinding vereist is om verbinding te maken met AEM Screens. Dit is vooral interessant voor letterlijke of mobiele instellingen.

Het volgende diagram toont de Directe Mobiele Opstelling van het Netwerk en bestaat uit één enkel segment van de netwerkverbinding en de verbinding van elke speler aan het mobiele of cellulaire gegevensnetwerk.

![](/help/using/assets/direct-mobile-1.png)

## AEM Screens Player verbinden met Direct mobiel netwerk {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

1. Zorg ervoor dat elk van de AEM spelers van het Scherm met het Netwerk van de Router wordt verbonden.

1. Test de internetverbinding door een URL aan te roepen in uw systeembrowser.

   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen en controleert u of er een voldoende netwerkkoppeling is en de firewall van het besturingssysteem is geconfigureerd om netwerktoegang toe te staan met behulp van de geconfigureerde AEM Screens-communicatiepoorten.

1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

## Direct mobiel netwerk instellen {#requirements-direct}

De netwerkOpstelling kan logisch gezien in twee blokken worden gescheiden:

* Mobiele internetverbinding

* Netwerk voor lokale gebieden

### Mobiele internetverbinding {#mobile-internet-connection}

De prestaties van de verbinding van Internet naast netwerkbereikbaarheid verstrekken voldoende bandbreedte om AEM Screens regelmatig in werking te stellen.

In het Directe Mobiele Netwerk, wordt elke Speler verbonden met één enkele Mobiele Kaart van Gegevens aan het netwerk van leveranciersgegevens.

De volgende lijst benadrukt de gegevensnetwerken met hun standaardbandbreedte:

| Gegevensnetwerk | Bandbreedte |
|--- |--- |
| 3G | 42 Mbps |
| 4G | 150 Mbps |
| 5 G | 1000 - 10000 Mbps |

Wanneer het overwegen van welk Netwerk van Gegevens zou moeten worden gebruikt wordt het geadviseerd om de volgende vragen te beantwoorden:

De beschikbare netwerksnelheid is afhankelijk van het specifieke plan voor de provider van mobiele gegevens en van de beschikbare dekking die wordt bereikt op de locatie van de AEM Screens-controller.
Na deze installatie moet er ook rekening mee worden gehouden dat, naast de beschikbare bandbreedte, in sommige plannen voor de provider van mobiele gegevens de beschikbare hoeveelheid gegevens die binnen een bepaalde periode via de verbinding wordt verzonden, wordt beperkt. Er moet voor worden gezorgd dat er voldoende capaciteit is in de hoeveelheid gegevens en bandbreedte.
Als follow-up moet het vereiste gegevenspakket ten minste zijn:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Voor het eerste uploaden van mediabestanden, bijvoorbeeld door het integreren van nieuwe spelers, moet een hogere hoeveelheid gegevens en een hogere downloadtijd worden verwacht en in bovenstaande veronderstellingen worden weerspiegeld. Een 4G-netwerk met *goede*-dekking en *onbeperkt*-gegevens moeten overeenkomen met de meest gangbare installaties in deze netwerkinstelling.

>[!NOTE]
>Een minimaal 3G-plan met een goede netwerkdekking moet leiden tot acceptabele downloadprestaties voor een AEM Screens-speler. Als er slechts eerlijke dekking beschikbaar op een specifieke plaats is moet het in overweging nemen om de algemene Opstelling van het Netwerk aan [Mobiel Netwerk met de Mobiele Router van Gegevens en Actieve Componenten van het Netwerk ](/help/using/mobile-network-router.md) te schakelen.


### Netwerk {#lan-connection} voor lokale gebieden

De prestatieszorgen van het Netwerk van het Lokale Gebied (LAN), naast de netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens regelmatig te werken. De aanbeveling voor de LAN netwerksnelheden moet bij netwerken 100 Mbps minstens beginnen, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem te verbinden.

Wanneer u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte. Bijvoorbeeld, zouden de netwerkcomponenten minstens 100 norm moeten aanpassen Mbps en de bandbreedte aanpassen die door de toegang van Internet of de specificatie van de Router wordt verstrekt. Anders zal de totale bandbreedte door de zwakste verbinding in de netwerkketen worden beperkt.

## Media en elementen downloaden {#download}

AEM Screens biedt een groot voordeel voor Digital Signage-gebruikers. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld een gedefinieerde afspeellijst die regelmatig wordt bijgewerkt - biedt een vrijwel netwerkonafhankelijke bewerking aan zodra alle bestanden op de speler zijn opgeslagen.

Voor scenario&#39;s, waar er meer interactie met sensoren of trekkers en dynamische inhoud zijn, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe het schermreactie om optimale klantenervaring te verzekeren.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>
>Alle informatie heeft betrekking op het gebruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/download-times-mobile.png)



