---
title: Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
description: De pagina beschrijft Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 0%

---

# Mobiel netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#mobile-network-setup}

AEM Screens Players van de Adobe kan ook worden aangesloten gebruikend mobiele of cellulaire netwerken die minstens een 3G netwerk in werking stellen.

In AEM Screens wordt de vereiste inhoud fysiek gedownload naar de spelercontroller of -computer en correct opgeslagen in het onderliggende besturingssysteem. Daarom heeft de opgegeven bandbreedte alleen invloed op de eerste downloadtijden en de updates van de inhoud en niet op de prestaties van het regelmatig afspelen van beeldschermen.

Het voordeel van deze opstelling is dat de mobiele router in een geoptimaliseerde plaats kan worden geplaatst om de beste beschikbare netwerkdekking te verzekeren. Deze vlek bevindt zich gewoonlijk in een verhoogde en open positie, met zo weinig mogelijk omringende beton- of metaalconstructies.
Deze instelling biedt AEM schermgebruikers de flexibiliteit omdat er geen vaste lijn nodig is om verbinding te maken met AEM Screens. Het is ook interessant voor letterlijke of mobiele instellingen.

Het volgende diagram toont het Mobiele Netwerk met de Mobiele Router van Gegevens en de Actieve configuratie van de Componenten van het Netwerk. Het bevat een toegang van Internet van om het even welke controlemechanismen van AEM Screens door directe toegang van Internet gebruikend een eigen 3/4/5G Verbinding van Gegevens.

![](/help/using/assets/mobile-network-1.png)

## AEM Screens Player verbinden met mobiel netwerk met mobiele gegevensrouter en actieve netwerkcomponenten {#connecting-aem-screens-players}

Voer de onderstaande stappen uit om te zorgen voor een juiste verbinding tussen de AEM schermspelers in deze configuratie:

De configuratie wijst een toegang van Internet voor elke Controlemechanisme van AEM Screens door directe toegang van Internet toe gebruikend een specifieke 3/4/5G Verbinding van Gegevens.

1. Zorg ervoor dat de Mobiele Router van Gegevens behoorlijk met het Netwerk van Gegevens Cellular zoals die binnen het Werkende Systeem wordt vermeld wordt verbonden. En, zorg ervoor dat elk van de AEM spelers van het Scherm met het Netwerk van Routers wordt verbonden.
1. Test de verbinding van Internet door een URL in Browser van uw systeem te roepen.

   >[!NOTE]
   >Controleer de netwerkinstellingen als er een fout optreedt. Er zijn fundamenteel twee opties voor een juiste netwerkverbinding:
   >* DHCP
   >* Handmatige IP-configuratie

1. Zorg ervoor dat het plaatsen van de Adapter van het Netwerk uw Plaatsende Router aanpast.

1. Controleer of de Router behoorlijk met het Netwerk van het Gebied van Internet Service Provider (de Verbinding van Internet) wordt verbonden. U kunt het gebruiken van leiden van het Signaal op StandaardRouters controleren.
1. Als de URL-aanroep is gelukt, kunt u de AEM Screens blijven installeren en registreren. Start AEM Screens.

   >[!TIP]
   >Het kan voorkomen dat de AEM Screens-verbinding niet goed werkt. De verwachte inhoud wordt niet weergegeven. In dergelijke gevallen, controleer uw firewall van de Router van Internet als er om het even welke beperkingen betreffende `TCP/IP Port 80/443` zijn.


## Vestiging Mobiel Netwerk met de Mobiele Router van Gegevens en de Actieve Componenten van het Netwerk {#requirements-direct}

De netwerkOpstelling kan logisch gezien in twee blokken worden gescheiden:

* Mobiele internetverbinding

* Netwerk voor lokale gebieden

### Mobiele internetverbinding {#mobile-internet-connection}

De prestaties van de verbinding van Internet, naast reeds beschreven netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om AEM Screens inhoud uit te voeren downloadt regelmatig.

*Voldoende* hangt van het aantal aangesloten apparaten van AEM Screens af. Het hangt ook van het gebruik van andere consumenten binnen het netwerk, zoals Smartphones, Tablets, Cashiers, Computers, of de netwerken van WiFi van de Gast af.
Houd in mening dat alle apparaten een gezamenlijke toegang tot de verbinding van Internet hebben en de bandbreedte lineair vermindert terwijl het toevoegen van meer consumenten/computers aan het netwerk.
Naast de specifieke theoretische verbinding van het Netwerk, moet het worden gewaarborgd dat de dekking van de mobiele Router minstens *goed* is. Ook, moet het onderliggende Maandelijkse Plan genoeg Capaciteit van Gegevens en voldoende bandbreedte behandelen om alle verbonden cliënten binnen verbonden LAN te dienen.

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
>Voor het eerste uploaden van mediabestanden terwijl nieuwe spelers worden geïntegreerd, moet een hogere hoeveelheid gegevens en een hogere downloadtijd worden verwacht. Dit komt ook tot uiting in de bovenstaande aannames. Een netwerk 4G met *goede* dekking en onbeperkte Gegevens zouden de gemeenschappelijkste installaties in deze Opstelling van Netwerk moeten aanpassen.


### Netwerk voor lokale gebieden {#lan-connection}

De prestaties van LAN, naast reeds beschreven netwerkbereikbaarheid, moeten voldoende bandbreedte verstrekken om de inhoudsdownloads van AEM Screens regelmatig in werking te stellen. In deze dagen, past het LAN netwerk gewoonlijk minstens een netwerk 100-Mbps aan, zodat er voldoende bandbreedte zou moeten zijn om vele apparaten met goede prestaties aan het systeem te verbinden. Terwijl het gebruiken van andere Actieve Componenten van het Netwerk, is het verplicht dat alle die aan de vereisten van de netwerkbandbreedte aanpassen.

Bijvoorbeeld, zouden de Componenten van het Netwerk minstens de norm 100 Mbps moeten aanpassen en de bandbreedte aanpassen die door de de Toegang/specificatie van de Router van Internet wordt verstrekt.

Als een Wi-Fi-oplossing wordt overwogen om een scherm te verbinden met de Internet Link, is het raadzaam ten minste gebruik te maken van moderne Wi-Fi-standaarden, zoals IEEE `802.11g` . Deze standaard steunt verbindingen tot 54 Mbps. Om het even welk *nieuwere* Normen als `802.11h-n` zijn van betere kwaliteit. Als een Wi-Fi Repeater vereist is, raadt de Adobe aan om Wi-Fi Access-punttechnologieën zoals Google Nest Mesh Wi-Fi of vergelijkbare technologieën te gebruiken.

## Media en Assets downloaden {#download}

AEM Screens biedt een aanzienlijk voordeel voor gebruikers van digitale berichten. Het downloadt en bewaart plaatselijk alle noodzakelijke Dossiers van Media, zoals Beelden en Video. Wegens dit concept, komt het belangrijkste netwerkverkeer voor in het geval dat er nieuwe inhoud is die op een specifiek scherm moet worden getoond.
Voor de normale bewerking, met een gedefinieerde afspeellijst die niet vaak wordt bijgewerkt, biedt deze methode vrijwel netwerkonafhankelijke bewerkingen wanneer alle bestanden op de speler worden opgeslagen.
Wanneer er meer interacties zijn met sensoren of andere triggers en de inhoud dynamisch is, is een snelle en betrouwbare netwerkverbinding essentieel voor een directe reactie op het scherm. Dit zorgt voor de best mogelijke klantervaring.
De volgende lijsten bieden een goed overzicht van welke zeer belangrijke gegevens van de netwerkconnectiviteit voor de prestaties die en potentiële wachttijden kunnen worden verwacht.

>[!NOTE]
>
>Alle informatie verwijst naar het verbruik van elk apparaat in het netwerk dat een internetbron aanvraagt en downloadt. Elk van deze verzoeken voegt toe en breidt de Tijd van de Download uit.

![](/help/using/assets/mobile-router-download.png)
