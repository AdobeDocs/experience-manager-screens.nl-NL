---
title: Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
description: De pagina beschrijft Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: 02929219a064e3b936440431e77e67e0bf511bf6
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 0%

---

# Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#mobile-network-setup}

AEM Screens Players van de Adobe kan ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

In AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijden en de updates van de inhoud en niet op de prestaties van het regelmatig afspelen van beeldschermen.

Het voordeel van deze opstelling is dat de Mobiele Router in een geoptimaliseerde plaats kan worden geplaatst om beste beschikbare netwerkdekking te verzekeren. Dit bevindt zich gewoonlijk in een verhoogde en open positie, met zo weinig mogelijk omringende beton- of metaalconstructies.
Deze instelling biedt AEM schermgebruikers de flexibiliteit omdat er geen vaste lijn nodig is om verbinding te maken met AEM Screens. Dit is interessant voor letterlijke of mobiele instellingen.

Het volgende diagram toont het Mobiele Netwerk met de Mobiele Router van Gegevens en de Actieve configuratie van de Componenten van het Netwerk. Het bevat een toegang van Internet van om het even welke controlemechanismen van AEM Screens door directe toegang van Internet gebruikend een eigen 3/4/5G Verbinding van Gegevens.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player verbinden met mobiel netwerk met mobiele gegevensrouter en actieve netwerkcomponenten {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

De configuratie wijst een Toegang van Internet voor elk Controlemechanisme van AEM Screens door de Directe Toegang van Internet toe gebruikend een specifieke 3/4/5G Verbinding van Gegevens.

1. Zorg ervoor dat de Mobiele Router van Gegevens behoorlijk wordt verbonden met het cellulaire Netwerk van Gegevens zoals die binnen het Werkende Systeem wordt vermeld en elk van de spelers van het AEM van het Scherm wordt aangesloten aan het Netwerk van Routers.
1. Test de internetverbinding door een URL aan te roepen in de browser van uw systeem.

   >[!NOTE]
   >Controleer de netwerkinstellingen als er een fout optreedt. Er zijn fundamenteel twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie

1. Zorg ervoor dat het plaatsen van de Adapter van het Netwerk uw Plaatsende Router aanpast.

1. Controleer of de Router behoorlijk met het Netwerk van het Gebied van Internet Service Provider (de Verbinding van Internet) wordt verbonden. Dit kan ook worden geïdentificeerd gebruikend Signal leiden op StandaardRouters.
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

*Voldoende* Afhankelijk van het aantal aangesloten AEM Screens-apparaten en het gebruik van andere gebruikers in het netwerk, zoals smartphones, tablets, Cashiers, Computers of gastWi-Fi-netwerken.
Houd in mening dat alle apparaten een gezamenlijke toegang tot de verbinding van Internet hebben en de bandbreedte lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.
Naast de specifieke theoretische verbinding van het Netwerk, moet worden gewaarborgd dat de dekking van de mobiele Router minstens &quot;goed&quot;is. Ook het onderliggende Maandelijkse Plan moet genoeg Capaciteit van Gegevens en voldoende bandbreedte behandelen om alle verbonden cliënten binnen verbonden LAN te dienen.

In de volgende tabel worden de gegevensnetwerken gemarkeerd met hun standaardbandbreedte:

| Gegevensnetwerk | Bandbreedte |
|--- |--- |
| 3G | 42 Mbps |
| 4G | 150 Mbps |
| 5 G | 1000 - 10000 Mbps |

Terwijl het overwegen van welk Netwerk van Gegevens zou moeten worden gebruikt, adviseert de Adobe dat u de volgende vragen beantwoordt:

* Hoeveel cliënten worden verbonden met de Router?
* Hoeveel inhoudswijzigingen worden verwacht en wat zijn die gemiddelde bestandsgrootten?

>[!NOTE]
>
>Het benodigde gegevenspakket moet ten minste:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>Voor het aanvankelijk uploaden van mediabestanden, bijvoorbeeld, terwijl nieuwe spelers worden geïntegreerd, moet een hogere hoeveelheid gegevens en een verhoogde downloadtijd worden verwacht en in de bovenstaande veronderstellingen worden weerspiegeld. Een 4G-netwerk met *goed* de dekking en de onbeperkte Gegevens zouden de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen.


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van LAN, naast reeds beschreven netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om de inhoudsdownloads van AEM Screens regelmatig in werking te stellen. In deze dagen, past het LAN netwerk gewoonlijk minstens een netwerk 100-Mbps aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem te verbinden. Wanneer u andere actieve netwerkcomponenten gebruikt, is het verplicht dat al deze wel voldoen aan de vereisten voor netwerkbandbreedte.

Bijvoorbeeld, zouden de Componenten van het Netwerk minstens norm 100 Mbps moeten aanpassen en de bandbreedte aanpassen die door de Toegang van Internet/de specificatie van de Router wordt verstrekt.

Als een Wi-Fi-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, is het raadzaam om moderne Wi-Fi-standaarden te gebruiken, zoals IEEE `802.11g` minimaal. Deze standaard steunt verbindingen tot 54 Mbps. Alle *nieuwer* Standaarden als `802.11h-n` van betere kwaliteit zijn. Als een Wi-Fi Repeater vereist is, raadt de Adobe aan om Wi-Fi Access-punttechnologieën zoals Google Nest Mesh Wi-Fi of vergelijkbare technologieën te gebruiken.

## Media en middelen downloaden {#download}

AEM Screens biedt een aanzienlijk voordeel voor gebruikers van digitale berichten. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept, komt het belangrijkste netwerkverkeer voor voor het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale werking, bijvoorbeeld, na bepaalde playlist die niet vaak tijdens de dag wordt bijgewerkt, biedt dit dichtbij netwerk-onafhankelijke verrichting aan wanneer alle dossiers op de speler worden bewaard.
Voor gebruiksgevallen waarin er meer interacties zijn met sensoren of andere triggers en de inhoud dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe schermreactie om een optimale gebruikerservaring te garanderen.
De volgende lijsten bieden een goed overzicht welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties betekenen die en potentiële wachttijden kunnen worden verwacht.

>[!NOTE]
>
>Alle informatie heeft betrekking op het gebruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van deze verzoeken voegt toe en breidt de Tijd van de Download uit.

![](/help/using/assets/mobile-router-download.png)
