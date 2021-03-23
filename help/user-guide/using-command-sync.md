---
title: Opdrachtsynchronisatie gebruiken
seo-title: Opdrachtsynchronisatie gebruiken
description: Volg deze pagina voor meer informatie over het gebruik van Command Sync.
seo-description: Volg deze pagina voor meer informatie over het gebruik van Command Sync.
feature: Ontwerpschermen
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---


# Command Sync {#command-sync}

Op de volgende pagina wordt beschreven hoe u Command Sync kunt gebruiken. Met Command Sync kunt u het afspelen tussen verschillende spelers synchroniseren. De spelers kunnen verschillende inhoud afspelen, maar elk element moet dezelfde duur hebben.

>[!IMPORTANT]
>
>Deze functie ondersteunt geen ingesloten reeksen, dynamische ingesloten reeksen, toepassingskanalen of overgangen.

## Overzicht {#overview}

De digitale signaaloplossingen moeten videomuren en gesynchroniseerde playback steunen om scenario&#39;s zoals tellingen van Nieuwjaar of grote video te steunen die over veelvoudige schermen worden gesegmenteerd en dit is waar de Synchronisatie van het Bevel in spel komt.

Om de Synchronisatie van het Bevel te gebruiken, doet één speler dienst als *master* en verzendt bevel en alle andere spelers handelen als *cliënten* en spelen wanneer zij het bevel ontvangen.

De *master* verzendt een bevel naar alle geregistreerde cliënten wanneer het op het punt staat om playback van een punt te beginnen. De nuttige lading van dit kan de index van het te spelen punt en/of buitenste html van het te spelen element zijn.

## Opdrachtsync {#using-command-sync} implementeren

In de volgende sectie wordt beschreven hoe u Command Sync in een AEM Screens-project kunt gebruiken.

>[!NOTE]
>
>Voor gesynchroniseerd afspelen is het vereist dat alle hardwareapparaten dezelfde hardwarespecificaties hebben en bij voorkeur hetzelfde besturingssysteem. Synchroniseren tussen verschillende hardware en besturingssystemen wordt afgeraden.

### Het project {#setting-up} instellen

Voordat u de functie Opdrachtsynchronisatie gebruikt, moet u een project en een kanaal met inhoud instellen voor uw project.

1. In het volgende voorbeeld ziet u een demoproject met de naam **CommandSyncDemo** en een sequentiekanaal **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >Meer informatie over het maken van een kanaal of het toevoegen van inhoud aan een kanaal vindt u in [Kanalen maken en beheren](/help/user-guide/managing-channels.md)

   Het kanaal bevat de volgende inhoud, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Maak een locatie **Lobby** en zorg vervolgens voor een weergave met de naam **LobbyDisplay** in de map **Locations**, zoals in de onderstaande afbeelding wordt getoond.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Wijs het kanaal, **ChannelLobby** aan uw **LobbyDisplay** toe. U kunt het toegewezen kanaal nu vanaf het weergavedashboard bekijken op de weergave.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Leer hoe te om een kanaal aan een vertoning toe te wijzen, verwijs naar [Creërend en het Leiden Vertoningen](/help/user-guide/managing-displays.md).

1. Navigeer naar de map **Apparaten** en klik op **Apparaatbeheer** op de actiebalk om de apparaten te registreren.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Raadpleeg [Apparaatregistratie](/help/user-guide/device-registration.md) voor meer informatie over het registreren van een apparaat

1. In dit voorbeeld worden voor demo-doeleinden een chroom- en een Windows-speler weergegeven als twee aparte apparaten. Beide apparaten wijzen aan de zelfde vertoning.
   ![image1](assets/command-sync6.png)

### Kanaalinstellingen bijwerken

1. Navigeer naar **ChannelLobby** en klik **Bewerken** op de actiebalk om de kanaalinstellingen bij te werken.

1. Selecteer het volledige kanaal zoals weergegeven in de onderstaande afbeelding.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klik op het moersleutelpictogram om het dialoogvenster **Pagina** te openen.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Typ het trefwoord *gesynchroniseerd* in het veld **Strategie**.

   ![image1](assets/command-sync/command-sync9-1.png)


### Een master {#setting-up-master} instellen

1. Navigeer van **CommandSyncDemo** —> **Locations** —> **Lobby** —> **LobbyDisplay** naar het weergavedashboard en klik op **Dashboard** op de actiebalk.
De twee apparaten (chroom- en vensterspeler) worden weergegeven in het deelvenster **DEVICES**, zoals in de onderstaande afbeelding wordt getoond.
   ![image1](assets/command-sync/command-sync10-1.png)

1. Selecteer in het deelvenster **APPARATEN** het apparaat dat u als master wilt instellen. In het volgende voorbeeld ziet u hoe u het Chrome-apparaat instelt als het master apparaat. Klik op **Instellen als master apparaat**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Voer het IP-adres in **Instellen als master apparaat** in en klik op **Opslaan**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>U kunt meerdere apparaten instellen als master.

### Synchroniseren met Master {#sync-up-master}

1. Nadat u het Chrome-apparaat hebt ingesteld op master, kunt u het andere apparaat (in dit geval de Windows-speler) synchroniseren met het master apparaat.
Selecteer het andere apparaat (in dit geval de vensterspeler) in het **deelvenster DEVICES** en klik op **Synchroniseren met master apparaat**, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Selecteer het apparaat in de lijst en klik op **Opslaan**.

   >[OPMERKING:]
   > In het dialoogvenster **Synchroniseren met master apparaat** wordt de lijst met master apparaten weergegeven. U kunt de gewenste optie selecteren.

1. Nadat het apparaat (Windows-speler) is gesynchroniseerd met de master speler (Chrome-speler), wordt het apparaat gesynchroniseerd in het deelvenster **DEVICES**.

   ![image1](assets/command-sync/command-sync14-1.png)

### De-synchroniseren met Master {#desync-up-master}

Nadat u een apparaat of apparaten hebt gesynchroniseerd met een master apparaat, kunt u de synchronisatie van dat apparaat ongedaan maken.

>[!NOTE]
>
>Als u de synchronisatie van een master apparaat ongedaan maakt, worden ook alle clientapparaten die aan dat master apparaat zijn gekoppeld, ontkoppeld.

Volg onderstaande stappen om de synchronisatie van het master apparaat te verwijderen:

1. Navigeer naar het **deelvenster DEVICES** en selecteer het apparaat.

1. Klik op **Apparaat(en)** desync om de synchronisatie van de client met het master apparaat ongedaan te maken.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klik **Bevestig** om de synchronisatie van het geselecteerde apparaat met het master apparaat ongedaan te maken.

   >[OPMERKING:]
   > Als u het master apparaat selecteert en de optie Niet-synchroniseren gebruikt, worden alle apparaten die zijn aangesloten op het master apparaat in één stap gedessynchroniseerd.
