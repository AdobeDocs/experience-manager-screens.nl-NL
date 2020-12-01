---
title: Kickstart Guide
seo-title: Kickstart Guide
description: Volg deze pagina om een demo AEM Screens-project te maken. Hiermee kunt u een digitale handtekening maken die begint bij de installatie en het instellen van een nieuw project voor het weergeven van uw inhoud in AEM Screens Player.
translation-type: tm+mt
source-git-commit: 77c81b84631b090333db0095986f634fa99c8223
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 1%

---


# Kickstart Guide {#kickstart-guide}

De kickstart naar AEM Screens laat zien hoe u een AEM Screens-project kunt opzetten en uitvoeren. Het begeleidt u door het instellen van een eenvoudige digitale handtekening en het toevoegen van inhoud, zoals elementen en/of video&#39;s, aan elk kanaal en het verder publiceren van de inhoud naar een AEM Screens-speler.

>[!NOTE]
>Voordat u aan de projectdetails gaat werken, moet u eerst het nieuwste Feature Pack voor AEM Screens hebben geïnstalleerd. U kunt het recentste eigenschapspakket van [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID.

## Vereisten {#prerequisites}

Voer de onderstaande stappen uit om een voorbeeldproject voor AEM Screens te maken en inhoud verder te publiceren naar de Schermspeler.

>[!NOTE]
>In de volgende zelfstudie wordt het afspelen van de inhoud van uw kanaal in Chrome OS Player geïllustreerd.

>[!IMPORTANT]
>**OSGi-configuratie-instellingen**
>U moet de lege referentie inschakelen zodat het apparaat gegevens op de server kan plaatsen. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen. Momenteel zijn enkele van deze functies alleen beschikbaar als het filter Lege waarden toestaan van Apache-verwijzing is ingeschakeld in de OSGi-configuratie. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.
>Voer de onderstaande stappen uit om het filter ***Leeg toestaan van paginaverwijzing van Apache in te schakelen***:


## Lege verwijzingsverzoeken {#allow-empty-referrer-requests} toestaan

1. Navigeer naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Adobe Experience Manager Web Console** Configuration wordt geopend. Zoeken naar de referentie van de sling.

   Voor het zoeken van het bezit van de lijstverwijzer, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

1. Schakel de optie **Lege waarden toestaan** in, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](assets/config/empty-ref2.png)

1. Klik op **Opslaan** om het filter Leeg toestaan van paginaverwijzing in te schakelen.

## Een digitale signaalervaring maken in 5 minuten {#creating-a-digital-signage-experience-in-minutes}

### AEM Screens-project {#creating-project} maken

De eerste stap is het maken van een AEM Screens-project.

1. Navigeer naar de Adobe Experience Manager-instantie (AEM) en klik op **Screens**. U kunt ook rechtstreeks navigeren vanuit `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Klik **Schermproject maken** om een nieuw schermproject te maken. Voer de titel in als **DemoScreens** en klik op **Save**.

   ![afbeelding](assets/kickstart/demo-1.png)

   >[!NOTE]
   >Zodra u het project creeert, brengt het u terug naar de homepage van het Project van de Schermen. U kunt nu uw project selecteren. In een project, zijn er vijf verschillende omslagen genoemd **Toepassingen**, **Kanalen**, **Apparaten**, **Plaatsen**, en **Planningen**.

### Een kanaal {#creating-channel} maken

Nadat u een AEM Screens-project hebt gemaakt, moet u een nieuw kanaal maken waarin u de inhoud beheert.

Ga als volgt te werk om een nieuw kanaal voor uw project te maken:

1. Zodra u een project creeert, selecteer **DemoScreens** project en selecteer **Kanalen** omslag, zoals aangetoond in het hieronder cijfer. Klik **+ creëren** van de actiebar.

   ![afbeelding](assets/kickstart/demo-2.png)

1. Kies **Volgkanaal** van de tovenaar en klik **Volgende**.
   ![afbeelding](assets/kickstart/demo-3.png)

1. Voer de **Titel** in als **TestChannel** en klik op **Create**.

   ![afbeelding](assets/kickstart/demo-4.png)

   De **TestChannel** wordt nu toegevoegd aan uw kanaalomslag, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](assets/kickstart/demo-5.png)

### Inhoud toevoegen aan een kanaal {#adding-content}

Wanneer u uw kanaal hebt ingesteld, moet u inhoud aan uw kanaal toevoegen die in AEM Screens Player wordt weergegeven.

Voer de onderstaande stappen uit om inhoud aan het kanaal (**TestChannel**) in uw project toe te voegen:

1. Navigeer naar **DemoProject** u creeerde en selecteer **TestChannel** van **Kanalen** omslag.

1. Klik op **Bewerken** op de actiebalk (zie de onderstaande afbeelding). De redacteur voor **TestChannel** opent.

   ![afbeelding](assets/kickstart/demo-6.png)

1. Klik op het pictogram dat het zijpaneel links van de actiebalk in- en uitschakelt om de elementen en componenten te openen.

1. Sleep de componenten die u aan het kanaal wilt toevoegen en zet deze neer.

   ![afbeelding](assets/kickstart/demo-7.png)

### Een locatie maken {#creating-location}

Als u het kanaal eenmaal hebt ingesteld, moet u een locatie maken.

>[!NOTE]
>***Locaties*** maken gebruik van een compartimentering voor verschillende digitale signalen en bevatten de configuraties van de displays, afhankelijk van de locatie van de verschillende schermen.

Ga als volgt te werk om een nieuwe locatie voor uw project te maken:

1. Navigeer naar **DemoProject** u creeerde en selecteer **Locations** omslag.

1. Klik **+ creëren** van de actiebar.

1. Selecteer **Locatie** van de tovenaar en klik **Volgende**.

1. Voer de **Naam** voor uw locatie in (voer de titel in als **Testlocatie**) en klik op **Maken**.

De **TestLocation** wordt gecreeerd en aan uw **omslag van Plaatsen** toegevoegd.


### Weergave maken voor locatie {#creating-display}

Nadat u een locatie hebt gemaakt, moet u een nieuwe weergave voor uw locatie maken.

>[!NOTE]
>***Display*** vertegenwoordigt de digitale ervaring die op één of veelvoudige schermen loopt.

1. Navigeer naar **TestLocation** en selecteer het.

1. Klik **Maken** van de actiebar.

   ![afbeelding](assets/kickstart/demo-disp1.png)

1. Selecteer **Display** in de wizard **Maken** en klik op **Volgende**.

   ![afbeelding](assets/kickstart/demo-disp2.png)

1. Voer de **Titel** in als **LobbyDisplay** en klik op **Maken**.

   ![afbeelding](assets/kickstart/demo-disp3.png)

   Er wordt nu een nieuwe weergave met de naam **TestDisplay** toegevoegd aan uw locatie **TestLocation**, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](assets/kickstart/demo-disp4.png)

### Een kanaal {#assigning-channel} toewijzen

Zodra de projectopstelling volledig is, moet u het kanaal aan een vertoning toewijzen om de inhoud te bekijken.

1. Navigeer naar de vereiste weergave vanuit **DemoScreens** —> **Locaties** —> **TestLocation** —> **LobbyDisplay**.

1. Tik/klik **Kanaal toewijzen** vanuit de actiebalk.

   ![afbeelding](assets/kickstart/demo-assign1.png)

   Of

   Tik/klik op **Dashboard** in de actiebalk en klik op **+Kanaal toewijzen** in het **Toegewezen KANALEN &amp; SCHEDULES**-deelvenster.

   ![afbeelding](assets/kickstart/demo-assign2.png)

1. Het dialoogvenster **Kanaaltoewijzing** wordt geopend.

1. Kies bij de optie **Instellingen** het kanaal **op pad** en **Ondersteunde gebeurtenissen** als **Eerste lading** en **Niet actief scherm**.

   >[!NOTE]
   >
   >De **Kanaalrol**, **Prioriteit**, en **Methoden van de Onderbreking** zijn allen bevolkt door gebrek. Zie [Kanaaleigenschappen](/help/user-guide/channel-assignment-latest-fp.md#channel-properties) sectie voor meer informatie over kanaaltoewijzingseigenschappen.

   ![afbeelding](assets/kickstart/demo-assign3.png)

   Daarnaast kunt u **Activeringsvenster** en **Herhalingsschema** ook selecteren.

   >[!NOTE]
   >Met het *Herhalingsschema* kunt u een terugkerend schema voor uw kanaal instellen. U stelt meerdere herhalingsschema&#39;s voor een kanaal in.
   >Zie [Herhalingsschema](/help/user-guide/channel-assignment-latest-fp.md#recurrence-schedule) voor meer informatie.

1. Klik **Save** zodra u uw voorkeur hebt gevormd.

### Een apparaat registreren en apparaat toewijzen aan een beeldscherm {#registering-device}

U moet het apparaat registreren via het AEM dashboard.

>[!IMPORTANT]
>De Chrome OS-speler kan worden geïnstalleerd als Chrome Browser-insteekmodule in de ontwikkelaarsmodus zonder dat hiervoor een echt chrome speler-apparaat nodig is. Volg onderstaande stappen voor installatie:
>
>1. Klik [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.
>1. Pak het uit en sla het op de schijf op.
>1. Open Chrome browser en selecteer **Extensies** in het menu of navigeer direct naar ***chrome://extensions***.
>1. Schakel de **modus Ontwikkelaar** vanuit de rechterbovenhoek in.
>1. Klik op **Niet-verpakte** vanuit de linkerbovenhoek laden en niet-gecomprimeerde Chrome Player laden.
>1. Schakel **AEM Screens Chrome Player** insteekmodule in als deze beschikbaar is in de lijst met extensies.
>1. Open een nieuw tabblad en klik op het pictogram **Apps** in de linkerbovenhoek of navigeer rechtstreeks naar ***chrome://apps***.
>1. Klik op **AEM Screens** Insteekmodule om Chrome Player te starten. Standaard wordt de speler gestart in de modus Volledig scherm. Druk op **esc** om de modus Volledig scherm af te sluiten.


Wanneer uw Chrome OS-speler is ingeschakeld, voert u de onderstaande stappen uit om een Chrome-apparaat te registreren.

1. Navigeer aan **Apparaten** omslag van uw project van uw AEM instantie.

1. Tik/klik op **Apparaatbeheer** in de actiebalk.

   ![afbeelding](assets/kickstart/demo-register1.png)

1. Tik/klik op **Apparaatregistratie** rechtsboven.

1. Selecteer het vereiste apparaat en tik/klik **Apparaat registreren**.

   ![afbeelding](assets/kickstart/demo-register2.png)

1. Wacht op het apparaat om zijn registratiecode te verzenden en tegelijkertijd **Registratiecode** van uw apparaat van Chrome te controleren.
   ![afbeelding](assets/kickstart/demo-register3.png)

1. Als **Registratiecode** op beide computers hetzelfde is, tikt u op **Valideren** in AEM.

1. Stel de gewenste naam in als **ChromeDeviceforDemo** voor het apparaat en klik op **Register**.

   ![afbeelding](assets/kickstart/demo-register4.png)

1. Klik **Weergave toewijzen** in het dialoogvenster **Apparaatregistratie gelukt**.

   ![afbeelding](assets/kickstart/demo-register5.png)

1. Selecteer het pad naar uw beeldscherm als **DemoScreens** —> **Locaties** —> **TestLocation** —> **LobbyDisplay** en klik **Toewijzen**.

   ![afbeelding](assets/kickstart/demo-device6.png)

1. Nadat het apparaat is toegewezen, wordt de volgende bevestiging weergegeven.

   ![afbeelding](assets/kickstart/demo-register8.png)

1. Tik/klik **Voltooi** om het registratieproces te voltooien. U moet het geregistreerde apparaat kunnen bekijken vanaf het weergavedashboard.

   ![afbeelding](assets/kickstart/demo-register9.png)

### De inhoud weergeven in Chrome Player {#viewing-content-output}

Alle elementen in uw kanaal worden nu afgespeeld op uw Chrome OS-speler.

Gefeliciteerd, u speelt nu inhoud in een AEM Screens-kanaal af.

![afbeelding](assets/kickstart/demo-video-screens.gif)
