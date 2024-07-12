---
title: Direct mobiel netwerk
description: Meer informatie over Direct Mobile Network Setup in AEM Screens.
exl-id: 6775bd10-7625-422f-a7af-4f7b8793fa42
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---

# Direct mobiel netwerk {#mobile-network-setup}

AEM Screens Players kunnen ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

In AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijd en op de updates van de inhoud. De bandbreedte heeft geen invloed op de prestaties van het regelmatig afspelen van beeldschermen.

Het voordeel om AEM Screens Players over Cellular 3/4/5G met uw Mobiele Leverancier van de Gegevens van de Dienst te verbinden is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst. Dit verzekert de beste beschikbare netwerkdekking. Deze plaats bevindt zich gewoonlijk in een verhoogde en open positie met zo weinig mogelijk omringende beton- of metaalconstructies.

Deze instelling biedt AEM schermgebruikers grote flexibiliteit omdat er geen vaste verbinding is vereist om verbinding te maken met AEM Screens. Dit is interessant voor letterlijke of mobiele instellingen.

Het volgende diagram toont de Directe Mobiele Opstelling van het Netwerk. Het bestaat uit één enkel netwerkverbindingssegment en de verbinding van elke speler aan het mobiele of cellulaire gegevensnetwerk.

![](/help/using/assets/direct-mobile-1.png)

## AEM Screens Player verbinden met Direct mobiel netwerk

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

1. Zorg ervoor dat elk van de AEM spelers van het Scherm met het Netwerk van de Router wordt verbonden.

1. Test de verbinding van Internet door een URL in uw systeembrowser te roepen.

   >[!NOTE]
   >Als u een foutbericht krijgt, controleert u de netwerkinstellingen en controleert u of er voldoende netwerkkoppeling is. Controleer ook of de firewall van het besturingssysteem is geconfigureerd om netwerktoegang toe te staan terwijl de geconfigureerde AEM Screens-communicatiepoorten worden gebruikt.

1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

## Direct mobiel netwerk instellen {#requirements-direct}

De netwerkOpstelling kan logisch gezien in twee blokken worden gescheiden:

* Mobiele internetverbinding

* Netwerk voor lokale gebieden

### Mobiele internetverbinding {#mobile-internet-connection}

De prestaties van de verbinding van Internet naast netwerkbereikbaarheid verstrekken voldoende bandbreedte om AEM Screens regelmatig in werking te stellen.

In het directe mobiele netwerk, wordt elke speler verbonden met één enkele Mobiele Kaart van Gegevens aan het gegevensnetwerk van de leverancier.

In de volgende tabel worden de gegevensnetwerken gemarkeerd met hun standaardbandbreedte:

| Gegevensnetwerk | Bandbreedte |
|--- |--- |
| 3G | 42 Mbps |
| 4G | 150 Mbps |
| 5 G | 1000 - 10000 Mbps |

Overweeg bij het overwegen van welk gegevensnetwerk moet worden gebruikt het volgende:

De beschikbare netwerksnelheid is afhankelijk van het specifieke plan voor de provider van mobiele gegevens en van de beschikbare dekking die wordt bereikt op de locatie van de AEM Screens-controller.
Tijdens het volgen van deze opstelling, ben van mening dat naast de beschikbare bandbreedte, sommige Mobiele Plannen van de Leverancier van Gegevens de beschikbare hoeveelheid Gegevens beperken die over de verbinding binnen een specifieke tijd komen. Er moet voor worden gezorgd dat er voldoende capaciteit is in de gegevens- en bandbreedtehoeveelheden.
Als follow-up moet het benodigde gegevenspakket ten minste het volgende zijn:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>Voor het aanvankelijk uploaden van mediabestanden terwijl nieuwe spelers worden geïntegreerd, moet een hogere hoeveelheid gegevens en een hogere downloadtijd worden verwacht; dit wordt weerspiegeld in de bovenstaande veronderstellingen. Een netwerk 4G met *goede* dekking en *onbeperkt* gegevens zou de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen.

>[!NOTE]
>Een minimaal 3G-plan met een goede netwerkdekking moet leiden tot acceptabele downloadprestaties voor een AEM Screens Player. Als er slechts eerlijke dekking beschikbaar bij een specifieke plaats is, denk na omschakeling van de algemene Opstelling van het Netwerk aan [ Mobiel Netwerk met de Mobiele Router van Gegevens en Actieve Componenten van het Netwerk ](/help/using/mobile-network-router.md).


### Netwerk voor lokale gebieden {#lan-connection}

De prestatieszorgen van het Netwerk van het Lokale Gebied (LAN), naast de netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens regelmatig te werken. De aanbeveling voor de LAN netwerksnelheden moet bij netwerken 100-Mbps minstens beginnen, zodat er voldoende bandbreedte is om vele apparaten met goede prestaties aan het systeem te verbinden.

Wanneer u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte. Bijvoorbeeld, zouden de netwerkcomponenten minstens de norm 100 Mbps moeten aanpassen en de bandbreedte aanpassen die door de toegang van Internet of de specificatie van de Router wordt verstrekt. Anders, wordt de totale bandbreedte beperkt door de zwakste verbinding in de netwerkketen.

## Media en Assets downloaden {#download}

AEM Screens biedt een aanzienlijk voordeel voor gebruikers van digitale berichten. Het downloadt en bewaart plaatselijk alle noodzakelijke media dossiers, zoals beelden en video&#39;s. Het belangrijkste netwerkverkeer komt voor wanneer er nieuwe inhoud is die op een specifieke vertoning moet worden getoond.

Voor normale bewerkingen, bijvoorbeeld een gedefinieerde afspeellijst die regelmatig wordt bijgewerkt - biedt deze functie een vrijwel netwerkonafhankelijke bewerking nadat alle bestanden op de speler zijn opgeslagen.

Voor scenario&#39;s, waar er meer interactie met sensoren of trekkers en dynamische inhoud zijn, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe het schermreactie om de best mogelijke klantenervaring te verzekeren.

De volgende lijst verstrekt een overzicht over de zeer belangrijke gegevens van de netwerkconnectiviteit.

>[!NOTE]
>
>Alle informatie verwijst naar het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van die verzoeken voegt omhoog toe en breidt de Tijd van de Download uit.

![](/help/using/assets/download-times-mobile.png)
