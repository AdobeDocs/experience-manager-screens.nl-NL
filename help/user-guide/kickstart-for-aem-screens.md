---
title: Kickstart Guide
seo-title: Kickstart Guide
description: Volg deze pagina om een demo AEM Screens-project te maken. Hiermee kunt u een digitale handtekening maken die begint bij de installatie en het instellen van een nieuw project voor het weergeven van uw inhoud in AEM Screens Player.
translation-type: tm+mt
source-git-commit: 78ddd2b45f39d69b66f740910327eef475bcdcac
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---


# Kickstart Guide {#kickstart-guide}

Deze sectie is een kickstart naar AEM Screens en laat zien hoe u een AEM Screens-project kunt instellen en uitvoeren. Het begeleidt u door het instellen van een eenvoudige digitale handtekening en het toevoegen van inhoud, zoals elementen en/of video&#39;s, aan elk kanaal en het verder publiceren van de inhoud naar een AEM Screens-speler.

>[!NOTE]
>Voordat u aan de projectdetails gaat werken, moet u eerst het nieuwste Feature Pack hebben geïnstalleerd. U kunt het nieuwste functiepakket voor AEM Screens 6.5.5 Release downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID.

## Een Digital Signage-ervaring maken in 5 minuten {#creating-a-digital-signage-experience-in-minutes}

Voer de onderstaande stappen uit om een voorbeeldproject voor AEM Screens te maken en inhoud verder te publiceren naar de Schermspeler.

>[!NOTE]
>In de volgende zelfstudie wordt het afspelen van de inhoud van uw kanaal in Chrome OS Player geïllustreerd.

>[!IMPORTANT]
>**OSGi-configuratie-instellingen**
>U moet de lege referentie inschakelen zodat het apparaat gegevens op de server kan plaatsen. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen. Momenteel zijn enkele van deze functies alleen beschikbaar als het filter Lege waarden toestaan van Apache-verwijzing is ingeschakeld in de OSGi-configuratie. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.
>Voer de onderstaande stappen uit om het filter ***Apache-schuifverwijzing leeg*** toestaan in te schakelen:


## Lege verwijzingsverzoeken toestaan {#allow-empty-referrer-requests}

1. Ga naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Configuratie** van Adobe Experience Manager-webconsole wordt geopend. Zoeken naar de referentie van de sling.

   Voor het zoeken van het het rangschikken verwijzend bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

1. Schakel de optie Lege **** waarden toestaan in, zoals in de onderstaande afbeelding.

   ![afbeelding](assets/config/empty-ref2.png)

1. Klik op **Opslaan** om het filter Leeg toestaan voor Apache-schuifverwijzing in te schakelen.


## Zelfstudie {#tutorial}

### Creating an AEM Screens Project {#creating-project}

De eerste stap is het maken van een nieuw AEM Screens-project.

1. Navigeer naar uw Adobe Experience Manager-exemplaar (AEM) en klik op **Schermen**. U kunt ook rechtstreeks navigeren vanuit `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Klik op Schermproject **** maken om een nieuw rasterproject te maken. Voer de titel in als **DemoScreens** en klik op **Opslaan**.

   ![afbeelding](assets/kickstart/demo-1.png)

   >[!NOTE]
   >Zodra u het project creeert, brengt het u terug naar de homepage van het Project van de Schermen. U kunt nu uw project selecteren. In een project zijn er vijf verschillende mappen met de naam **Toepassingen**, **Kanalen**, **Apparaten**, **Locaties** en **Planningen**.


### Een kanaal maken {#creating-channel}

Zodra u uw project op zijn plaats hebt, moet u een nieuw kanaal tot stand brengen waar u de inhoud beheert.

Ga als volgt te werk om een nieuw kanaal voor uw project te maken:

1. Zodra u een project creeert, selecteer het **project DemoScreens** en selecteer de omslag **van** Kanalen, zoals aangetoond in het hieronder cijfer. Klik op **+ Maken** op de actiebalk.

   ![afbeelding](assets/kickstart/demo-2.png)

1. Kies het kanaal **van de** Reeks van de tovenaar en klik **daarna**.
   ![afbeelding](assets/kickstart/demo-3.png)

1. Voer de **titel** in als *TestChannel* en klik op **Maken**.

   ![afbeelding](assets/kickstart/demo-4.png)

Het *bestand TestChannel* wordt gemaakt en aan de map met kanalen toegevoegd, zoals in de onderstaande afbeelding wordt getoond.

![afbeelding](assets/kickstart/demo-5.png)

### Inhoud toevoegen aan een kanaal {#adding-content}

Wanneer u uw kanaal hebt ingesteld, moet u inhoud aan uw kanaal toevoegen die de Schermspeler zal tonen.

Voer de onderstaande stappen uit om inhoud aan het kanaal (*TestChannel*) in uw project toe te voegen:

1. Navigeer naar het **DemoProject** dat u hebt gemaakt en selecteer de map **Kanalen** .

1. Klik op **Bewerken** op de actiebalk (zie de onderstaande afbeelding). De redacteur voor **TestChannel** opent.

   ![afbeelding](assets/kickstart/demo-6.png)

1. Klik op het pictogram dat het zijpaneel links van de actiebalk in- en uitschakelt om de elementen en componenten te openen.

1. Sleep de componenten die u aan het kanaal wilt toevoegen en zet deze neer.

   ![afbeelding](assets/kickstart/demo-7.png)

### Een locatie maken {#creating-location}

Als u het kanaal eenmaal hebt ingesteld, moet u een locatie maken.

>[!NOTE]
>***De plaatsen*** compartimenteren uw diverse digitale signaalervaringen en bevatten de configuraties van de vertoningen volgens waar de diverse schermen zijn.

Ga als volgt te werk om een nieuwe locatie voor uw project te maken:

1. Navigeer naar het **demoProject** dat u hebt gemaakt en selecteer de map **Locations** .

1. Klik op **+ Maken** op de actiebalk.

1. Selecteer **Locatie** in de wizard en klik op **Volgende**.

1. Voer de **naam** voor uw locatie in (voer de titel in als *TestLocation*) en klik op **Maken**.

De **testlocatie** wordt gemaakt en toegevoegd aan de map **Locations** .


### Weergave voor locatie maken {#creating-display}

Nadat u een locatie hebt gemaakt, moet u een nieuwe weergave voor uw locatie maken.

>[!NOTE]
>***De vertoningen*** vertegenwoordigen de digitale ervaring die op één of veelvoudige schermen loopt.

1. Navigeer naar **TestLocation** en selecteer het.

1. Klik op **Maken** op de actiebalk.

1. Selecteer **Weergave** in de wizard **Maken** en klik op **Volgende**.

1. Voer de **titel** in als **LobbyDisplay** en klik op **Maken**.

Een nieuwe vertoning genoemd als **TestDisplay** wordt nu toegevoegd aan uw plaats **TestLocation**, zoals aangetoond in hieronder figuur.

### Een kanaal toewijzen {#assigning-channel}

Zodra de projectopstelling volledig is, moet u het kanaal aan een vertoning toewijzen om de inhoud te bekijken.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locations** —> **TestLocation** —> **LobbyDisplay**.

1. Tik/klik op Kanaal **** toewijzen op de actiebalk.

   Of

   Tik/klik op **Dashboard** op de actiebalk en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

1. Het dialoogvenster **Kanaaltoewijzing** wordt geopend.

1. Van de optie van **Montages** , kunt u het kanaal **door weg** of **door naam** kiezen, de Rol **van het** Kanaal, de **Prioriteit**********, de Methoden van ElementenSupportedEvents, en de Methoden van de Onderbreking ingaan. Bovendien kunt u de knopinfo voor aantrekken inschakelen vanuit dit dialoogvenster.


   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](/help/user-guide/channel-assignment-latest-fp.md#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Selecteer bij de optie **Schema** de optie **Activeringsvenster** en **Herhalingsschema**.

1. Klik op **Opslaan** als u de voorkeuren hebt geconfigureerd.

### Een apparaat registreren {#registering-device}

U moet het apparaat registreren via het AEM dashboard.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome-speler getoond. Nadat u het kanaal aan de weergave hebt toegewezen, moet u het apparaat registreren bij een speler.



