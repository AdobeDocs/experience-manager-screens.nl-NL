---
title: Layout meerdere zones
description: Leer hoe u inhoud voor meerdere zones maakt en verschillende elementen gebruikt, zoals video's, afbeeldingen en tekst die in AEM Screens in één scherm kunnen worden gecombineerd.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 901ed50e-d3f0-4c85-ad79-6c4595382759
source-git-commit: c440527b80a3899fd45ec2d20d8cb48ffe85f6f3
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 0%

---

# Layout meerdere zones {#multi-zone-layout}

De volgende pagina beschrijft het gebruik van lay-out met meerdere zones en behandelt de volgende onderwerpen:

* Overzicht
* Lay-out met meerdere zones maken
* Vereisten
* Enkelvoudige elementen in een of meer zones gebruiken
* Gesegrafeerde inhoud gebruiken in een of meer zones

## Overzicht {#overview}

***Layout meerdere zones*** Hiermee kunt u inhoud met meerdere zones maken en verschillende elementen gebruiken, zoals video&#39;s, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. U kunt afbeeldingen, video&#39;s en tekst aan elkaar trekken, zodat deze allemaal kunnen overvloeien en een intuïtieve digitale ervaring ontstaat.

Zoals bij de projectvereisten, soms hebt u veelvoudige streken in een kanaal nodig en geeft hen uit als één uitvoerige eenheid. Bijvoorbeeld, een productopeenvolging met een verwante sociale media voer die in drie afzonderlijke streken op één enkel kanaal loopt.

>[!NOTE]
>In kanalen met meerdere zones wordt het plannen op middelenniveau niet aanbevolen vanwege potentiële conflicten en onbedoeld gedrag. Als de activa-niveau planning noodzakelijk is, adviseert het om een afzonderlijk opeenvolgingskanaal tot stand te brengen en het plannen logica binnen dat kanaal toe te passen. Sluit vervolgens het sequentiekanaal in het kanaal met meerdere zones in.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u de conceptuele kennis over:

* [Een AEM Screens-project maken](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project)
* [Weergave maken](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays)
* [Een kanaal toewijzen aan een weergave](/help/user-guide/channel-assignment.md)

## Lay-out met meerdere zones maken {#creating-multi-zone-layout}

Tijdens het maken van een kanaal kunt u verschillende sjablonen gebruiken om zones in uw kanaal te maken. U kunt één afbeelding, video of ingesloten kanaal toevoegen waarmee meerdere elementen in een reeks kunnen worden weergegeven.

**Een kanaal maken**

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en **Schermen**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens`.
1. Navigeren naar **Kanalen** map en klik op **Maken** in de actiebalk.

1. Selecteren **1 x 2 gesplitst schermkanaal** van de **Maken** wizard.

1. Klikken **Volgende** en voert u de **titel** als **MultiZone**.

1. Klikken **Maken** om het maken van het kanaal te voltooien.

### Enkelvoudige elementen in een of meer zones gebruiken {#using-single-assets-in-one-or-more-zones}

U kunt afzonderlijke elementen, zoals een afbeelding of een video, in alle afzonderlijke zones gebruiken. Volg de onderstaande stappen voor implementatie:

1. **Inhoud toevoegen aan het kanaal**

   1. Navigeren naar **Zones** > **Kanalen**> **MultiZone**.
   1. Selecteer de **MultiZone** kanaal en klik **Bewerken** in de actiebalk.

1. **Afbeeldingen toevoegen aan het kanaal**

   Als u één afbeelding of video in twee zones wilt afspelen, sleept u een afbeelding naar elke zone in de Kanaaleditor, zoals in de onderstaande afbeelding wordt getoond:

   ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Gesegrafeerde inhoud gebruiken in een of meer zones {#using-sequenced-content-in-one-or-more-zones}

Als u wilt dat in de zones een reeks afbeeldingen en een video in de verschillende zones wordt weergegeven, volgt u onderstaande stappen voor meer informatie.

1. **Een kanaalmap maken**

   1. Navigeren naar **Zones** > **MultiZone** > **Kanalen** en klik op **Maken** in de actiebalk.
   1. Selecteren **Map Kanalen** van de **Maken** wizard en klik op **Volgende**.
   1. Voer de titel in als **Ingesloten kanalen** en klik op **Maken**.

   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Twee kanalen toevoegen aan de kanaalmap**

   1. Navigeren naar **Zones** > **Kanalen** > **Ingesloten kanalen** en klik op **Maken** in de actiebalk.
   1. Selecteren **Volgekanaal** van de **Maken** wizard om een kanaal te maken met de naam **`Zone1`**.
   1. Selecteren **`Zone1`** en klik op **Bewerken** in de actiebalk.
   1. Sleep enkele afbeeldingen naar dit kanaal.
   1. Maak op dezelfde manier een ander volgnummer met de naam **`Zone2`** in **Ingesloten kanalen** map.
   1. Sleep een video naar dit kanaal.

   De volgende afbeelding toont de kanalen **`Zone1`** en **`Zone2`**:

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   De afbeeldingen die zijn toegevoegd aan de editor van **`Zone1`** volgordekanaal wordt hieronder weergegeven:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   De video die is toegevoegd aan de editor van **`Zone2`** volgordekanaal wordt hieronder weergegeven:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Ingesloten reeksen (component) toevoegen aan hoofdkanaal (MultiZone)**

   1. Navigeren naar **Zones** > **Kanalen** > **MultiZone**.
   1. Klikken **Bewerken** in de actiebalk.
   1. Sleep de **Ingesloten reeks** aan beide zones.
   1. Selecteer de ingesloten reeks in een van de zones.
   1. Klik op de knop **Configureren** (moersleutel) naar een van de ingesloten reeksen in de editor.
   1. Kanaalpad selecteren als **Zones** > **Kanalen** > **Ingesloten kanalen** > **`Zone1`**, zoals weergegeven in onderstaande afbeelding.
   1. Voeg op dezelfde manier de **`Zone2`** naar een andere ingesloten reekscomponent in de editor.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-3.png)

### Een locatie en een weergave maken {#creating-location}

Maak een locatie en een weergave zodat u de inhoud in de AEM Screens-speler kunt bekijken.

1. **Een locatie maken**

   1. Navigeren naar **Zones** > **Locaties** map.
   1. Selecteer de **Locaties** map en selecteer **Maken** in de actiebalk.
   1. Selecteren **Locatie** van de **Maken** wizard en selecteert u **Volgende**.
   1. Voer de **Titel** als **SanJose** en selecteert u **Maken**.

1. **Weergave maken**

   1. Navigeren naar **Zones** > **Locaties** map.
   1. Selecteer de **SanJose** locatie en selecteer **Maken** in de actiebalk.
   1. Selecteren **Weergave** van de **Maken** wizard en selecteert u **Volgende**.
   1. Voer de **Titel** als **Lobby** en selecteert u **Maken**.

### Kanalen toewijzen aan de weergave {#channel-channel}

Wijs de kanalen aan de vertoning toe om de inhoud te bekijken. Voer de onderstaande stappen uit om het kanaal aan de weergave toe te wijzen.

1. **Kanaal toewijzen aan de weergave**

   1. Navigeren naar **Zones** > **Locaties** > **SanJose**> **Lobby**.
   1. Selecteer de **Lobby** weergeven en selecteren **Kanaal toewijzen** in de actiebalk.
   1. Voer het pad naar het **MultiZone** kanaal in **Kanaalpad**.
   1. Stel de **Ondersteunde gebeurtenissen** als **Oorspronkelijke belasting**, **Niet-actief scherm**, en **Timer**.
   1. Selecteren **Opslaan**.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. U moet ook de andere twee ingesloten kanalen toewijzen (**`Zone1`** en **`Zone2`**) op dit scherm.
   1. Nadat u alle drie de kanalen aan **Lobby** weergegeven, kunt u de toegewezen kanalen weergeven vanaf het weergavedashboard.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img8.png)


      >[!IMPORTANT]
      >
      >Nadat u het hoofdkanaal hebt toegewezen (in dit geval **MultiZone**) aan het scherm toe te wijzen, is het verplicht de andere twee ingesloten kanalen toe te wijzen **`Zone1`** en **`Zone2`** ook op hetzelfde scherm.

### Het apparaat registreren {#registering-device}

Wanneer u een locatie en een weergave hebt ingesteld, voert u de onderstaande stappen uit om het apparaat te registreren en de weergave aan het apparaat toe te wijzen.

1. **Het apparaat registreren**

   1. Navigeren naar **Zones** > **Apparaten** map.
   1. Selecteer de **Apparaten** map en selecteer **Apparaatbeheer** in de actiebalk.
   1. Selecteren **Apparaatregistratie** en selecteer het apparaat in behandeling in de lijst.

      >[!NOTE]
      > De titel van het apparaat moet overeenkomen met het apparaattoken (**Token** veld) weergegeven in het dialoogvenster **Apparaatregistratie** tab.

   1. Als de titel overeenkomt met het apparaattoken, selecteert u het apparaat en selecteert u **Apparaat registreren** in de actiebalk.
   1. Als de registratiecode overeenkomt met de code in de Schermspeler **Apparaatregistratie** tab, selecteert u **Valideren** in de actiebalk.
      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Voer de **Titel** als **`Chrome-Device1`** en selecteert u **Registreren**.
   1. Selecteren **Weergave toewijzen** en selecteer het pad naar de apparaatconfiguratie.

   >[!NOTE]
   >Als u de inhoud probeert weer te geven in de Schermspeler, moet u **Offline inhoud bijwerken** van het kanaaldashboard voor elk van de kanalen die aan de vertoning worden toegewezen.

### Het resultaat weergeven {#viewing-the-result}

Wanneer u lay-outs met meerdere zones implementeert met behulp van de voorgaande stappen, wordt de volgende uitvoer weergegeven.

Controleer de schermspeler zodat u de uitvoer kunt bekijken die de inhoud in twee verschillende zones weergeeft. De linker- en rechterzones (beide gebruiken een ingesloten reeks als een component).

De linkerzone is een reekskanaal en de rechterzone bevat een video.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)
