---
title: Opdrachtsynchronisatie gebruiken
seo-title: Using Command Sync
description: Volg deze pagina voor meer informatie over het gebruik van Command Sync.
seo-description: Follow this page to learn about how to use Command Sync.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3314e0b5-0001-4bce-8ec6-5a6ffbb20f7b
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# Opdrachtsynchronisatie {#command-sync}

Op de volgende pagina wordt beschreven hoe u Command Sync kunt gebruiken. Met Command Sync kunt u het afspelen tussen verschillende spelers synchroniseren. De spelers kunnen verschillende inhoud afspelen, maar elk element moet dezelfde duur hebben.

>[!IMPORTANT]
>
>Deze functie biedt geen ondersteuning voor ingesloten reeksen, dynamische ingesloten reeksen, toepassingskanalen of overgangen.

## Overzicht {#overview}

De digitale signaaloplossingen moeten videomuren en gesynchroniseerde playback steunen om scenario&#39;s zoals tellingen van Nieuwjaar of grote video te steunen die over veelvoudige schermen worden gesegmenteerd en dit is waar de Synchronisatie van het Bevel in spel komt.

Als u Command Sync wilt gebruiken, fungeert één speler als een *primair* en verzendt bevel en alle andere spelers handelen als *clients* en afspelen wanneer ze de opdracht ontvangen.

De *primair* verzendt een bevel naar alle geregistreerde cliënten wanneer het op het punt staat om playback van een punt te beginnen. De nuttige lading van dit kan de index van het te spelen punt en/of buitenste html van het te spelen element zijn.

## Opdrachtsynchronisatie implementeren {#using-command-sync}

In de volgende sectie wordt beschreven hoe u Command Sync in een AEM Screens-project kunt gebruiken.

>[!NOTE]
>
>Voor gesynchroniseerd afspelen is het vereist dat alle hardwareapparaten dezelfde hardwarespecificaties hebben en bij voorkeur hetzelfde besturingssysteem. Synchroniseren tussen verschillende hardware en besturingssystemen wordt afgeraden.

### Het project instellen {#setting-up}

Voordat u de functie Opdrachtsynchronisatie gebruikt, moet u een project en een kanaal met inhoud instellen voor uw project.

1. In het volgende voorbeeld ziet u een demo-project met de naam **CommandSyncDemo** en een sequentiekanaal **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het maken van een kanaal of het toevoegen van inhoud aan een kanaal naar [Kanalen maken en beheren](/help/user-guide/managing-channels.md)

   Het kanaal bevat de volgende inhoud, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Een locatie maken **Lobby** en vervolgens een display met de naam **LobbyDisplay** in de **Locaties** map, zoals weergegeven in de onderstaande afbeelding.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Wijs het kanaal toe. **ChannelLobby** aan uw **LobbyDisplay**. U kunt het toegewezen kanaal nu vanaf het weergavedashboard bekijken op de weergave.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het toewijzen van een kanaal aan een weergave naar [Weergaven maken en beheren](/help/user-guide/managing-displays.md).

1. Navigeren naar **Apparaten** map en klik op **Apparaatbeheer** op de actiebalk om de apparaten te registreren.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het registreren van een apparaat naar [Apparaatregistratie](/help/user-guide/device-registration.md)

1. In dit voorbeeld worden voor demo-doeleinden een chroom- en een Windows-speler weergegeven als twee aparte apparaten. Beide apparaten wijzen aan de zelfde vertoning.
   ![image1](assets/command-sync6.png)

### Kanaalinstellingen bijwerken

1. Navigeren naar **ChannelLobby** en klik op **Bewerken** in de actiebalk om de kanaalinstellingen bij te werken.

1. Selecteer het volledige kanaal zoals weergegeven in de onderstaande afbeelding.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klik op het moersleutelpictogram om het dialoogvenster **Pagina** in.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Voer de *gesynchroniseerd* trefwoord in het dialoogvenster **Strategie** veld.

   ![image1](assets/command-sync/command-sync9-1.png)


### Een primaire {#setting-up-primary}

1. Navigeren naar het weergavedashboard vanaf **CommandSyncDemo** > **Locaties**  > **Lobby** > **LobbyDisplay** en klik op **Dashboard** in de actiebalk.
U ziet de twee apparaten (chroom- en vensterspeler) in **APPARATEN** zoals weergegeven in de onderstaande afbeelding.
   ![image1](assets/command-sync/command-sync10-1.png)

1. Van de **APPARATEN** selecteert u het apparaat dat u als primair wilt instellen. In het volgende voorbeeld ziet u hoe u het Chrome-apparaat als primair apparaat instelt. Klikken op **Instellen als primair apparaat**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Voer het IP-adres in **Instellen als primair apparaat** en klik op **Opslaan**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>U kunt meerdere apparaten als primair instellen.

### Synchroniseren met primaire {#sync-up-primary}

1. Nadat u het Chrome-apparaat als primair hebt ingesteld, kunt u het andere apparaat (in dit geval de Windows-speler) synchroniseren met het primaire apparaat.
Selecteer het andere apparaat (in dit geval de Windows-speler) in het menu **APPARATEN** deelvenster en klik op **Synchroniseren met primair apparaat**, zoals weergegeven in onderstaande afbeelding.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Selecteer het apparaat in de lijst en klik op **Opslaan**.

   >[OPMERKING:]
   > De **Synchroniseren met primair apparaat** wordt de lijst met primaire apparaten weergegeven. U kunt de gewenste optie selecteren.

1. Nadat het apparaat (Windows-speler) is gesynchroniseerd met de primaire speler (Chrome-speler), wordt het apparaat gesynchroniseerd in het dialoogvenster **APPARATEN** deelvenster.

   ![image1](assets/command-sync/command-sync14-1.png)

### De-synchroniseren met de primaire {#desync-up-primary}

Nadat u een apparaat of apparaten hebt gesynchroniseerd met een primair apparaat, kunt u de synchronisatie van het apparaat ongedaan maken.

>[!NOTE]
>
>Als u de synchronisatie van een primair apparaat ongedaan maakt, worden ook alle clientapparaten die aan dat primaire apparaat zijn gekoppeld, ontkoppeld.

Volg onderstaande stappen om de synchronisatie van het primaire apparaat te verwijderen:

1. Ga naar de **APPARATEN** en selecteert u het apparaat.

1. Klikken op **Apparaat(en) desynchroniseren** om de synchronisatie van de client met het primaire apparaat ongedaan te maken.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klikken **Bevestigen** om de synchronisatie van het geselecteerde apparaat met het primaire apparaat ongedaan te maken.

   >[OPMERKING:]
   > Als u het primaire apparaat selecteert en de optie Niet-synchroniseren gebruikt, worden alle apparaten die op het primaire apparaat zijn aangesloten in één stap gedessynchroniseerd.
