---
title: Opdrachtsynchronisatie gebruiken
description: Meer informatie over het gebruik van Command Sync in AEM Screens.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3314e0b5-0001-4bce-8ec6-5a6ffbb20f7b
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 0%

---

# Opdrachtsynchronisatie {#command-sync}

Op de volgende pagina wordt beschreven hoe u Command Sync kunt gebruiken. Met Command Sync kunt u het afspelen tussen verschillende spelers synchroniseren. De spelers kunnen verschillende inhoud afspelen, maar elk element moet dezelfde duur hebben.

>[!IMPORTANT]
>
>Deze functie biedt geen ondersteuning voor ingesloten reeksen, dynamische ingesloten reeksen, toepassingskanalen of overgangen.

## Overzicht {#overview}

Digitale signaaloplossingen moeten videomuren en gesynchroniseerd afspelen ondersteunen. Dit scenario is waar als u scenario&#39;s zoals de tellingen van het Nieuwjaar probeert te steunen of grote video die omhoog wordt gesegmenteerd om over veelvoudige schermen te spelen. Dergelijke scenario&#39;s zijn waar de Synchronisatie van het Bevel in spel komt.

Als u Command Sync wilt gebruiken, fungeert één speler als een *primair* en verzendt het bevel en alle andere spelers handelen zoals *clients* en afspelen wanneer ze de opdracht ontvangen.

De *primair* verzendt een bevel naar alle geregistreerde cliënten wanneer het op het punt staat om playback van een punt te beginnen. De nuttige lading van deze actie kan de index van het te spelen punt, of buitenste html van het te spelen element zijn, of allebei.

## Opdrachtsynchronisatie implementeren {#using-command-sync}

In de volgende sectie wordt beschreven hoe u Command Sync in een AEM Screens-project kunt gebruiken.

>[!NOTE]
>
>Voor gesynchroniseerd afspelen is het vereist dat alle hardwareapparaten dezelfde hardwarespecificaties hebben en bij voorkeur hetzelfde besturingssysteem. Synchroniseren tussen verschillende hardware en besturingssystemen wordt afgeraden.

### Het project instellen {#setting-up}

Alvorens u de eigenschap van de Synchronisatie van het Bevel gebruikt, zorg ervoor u een project en een kanaal met vastgestelde inhoud voor uw project hebt.

1. In het volgende voorbeeld ziet u een demo-project met de naam **CommandSyncDemo** en een sequentiekanaal **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het maken van een kanaal of het toevoegen van inhoud aan een kanaal naar [Kanalen maken en beheren](/help/user-guide/managing-channels.md)

   Het kanaal bevat de volgende inhoud, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Een locatie maken **Lobby** en dan een display met de naam **LobbyDisplay** in de **Locaties** map, zoals weergegeven in de onderstaande afbeelding.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Wijs het kanaal toe. **ChannelLobby** aan uw **LobbyDisplay**. U kunt het toegewezen kanaal nu vanaf het weergavedashboard bekijken op de weergave.
   ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het toewijzen van een kanaal aan een weergave naar [Weergaven maken en beheren](/help/user-guide/managing-displays.md).

1. Ga naar de **Apparaten** map.
1. Klikken **Apparaatbeheer** in de actiebalk.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het registreren van een apparaat naar [Apparaatregistratie](/help/user-guide/device-registration.md)

1. In dit voorbeeld worden voor demo&#39;s een Chrome-apparaat en een Windows Player weergegeven als twee aparte apparaten. Beide apparaten wijzen aan de zelfde vertoning.
   ![image1](assets/command-sync6.png)

### Kanaalinstellingen bijwerken

1. Navigeren naar **ChannelLobby**.
1. Klikken **Bewerken** in de actiebalk.
1. Klik op het volledige kanaal zoals in de onderstaande afbeelding wordt weergegeven.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Klik op het moersleutelpictogram.
   ![image1](assets/command-sync/command-sync8-1.png)

1. In de **Pagina** in, voert u de *gesynchroniseerd* trefwoord in het dialoogvenster **Strategie** veld.
   ![image1](assets/command-sync/command-sync9-1.png)


### Een primaire {#setting-up-primary}

1. Navigeren naar het weergavedashboard vanaf **CommandSyncDemo** > **Locaties**  > **Lobby** > **LobbyDisplay**. Klik vervolgens op **Dashboard** in de actiebalk.
Let op de twee apparaten (Chrome en Windows Player) in **APPARATEN** , zoals in het volgende voorbeeld:
   ![image1](assets/command-sync/command-sync10-1.png)

1. Van de **APPARATEN** klikt u op het apparaat dat u als primair wilt instellen. In het volgende voorbeeld ziet u hoe u het Chrome-apparaat instelt als het primaire apparaat. Klikken **Instellen als primair apparaat**.

   ![image1](assets/command-sync/command-sync11-1.png)

1. Voer het IP-adres in **Instellen als primair apparaat** en klik op **Opslaan**.

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>U kunt meerdere apparaten instellen als primaire apparaten.

### Synchroniseren met primaire {#sync-up-primary}

1. Nadat u het Chrome-apparaat als primair apparaat hebt ingesteld, synchroniseert u het andere apparaat (in dit geval de Windows Player) met het primaire apparaat.
Klik op het andere apparaat (in dit geval Windows Player) van de **APPARATEN** deelvenster en klik op **Synchroniseren met primair apparaat**.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Klik op het apparaat in de lijst en klik op **Opslaan**.

   >[OPMERKING:]
   > De **Synchroniseren met primair apparaat** wordt de lijst met primaire apparaten weergegeven. Selecteer de gewenste optie.

1. Wanneer het apparaat (Windows Player) is gesynchroniseerd met het primaire apparaat (Chrome Player), wordt het apparaat gesynchroniseerd in het dialoogvenster **APPARATEN** deelvenster.

   ![image1](assets/command-sync/command-sync14-1.png)

### De-synchroniseren met de primaire {#desync-up-primary}

Nadat u een apparaat of apparaten naar een primair apparaat hebt gesynchroniseerd, kunt u de toewijzing van dat apparaat desynchroniseren.

>[!NOTE]
>
>Als u de synchronisatie van een primair apparaat ongedaan maakt, worden ook alle clientapparaten die aan dat primaire apparaat zijn gekoppeld, ontkoppeld.

Volg onderstaande stappen om de synchronisatie van het primaire apparaat te verwijderen:

1. Ga naar de **APPARATEN** en klikt u op het apparaat.

1. Klikken **Apparaten synchroniseren** zodat u de synchronisatie van de client met het primaire apparaat ongedaan kunt maken.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Klikken **Bevestigen** om de synchronisatie van het geselecteerde apparaat met het primaire apparaat ongedaan te maken.

   >[OPMERKING:]
   > Als u op het primaire apparaat klikt en de optie Niet-synchroniseren gebruikt, worden alle apparaten die op het primaire apparaat zijn aangesloten in één stap gedesynchroniseerd.
