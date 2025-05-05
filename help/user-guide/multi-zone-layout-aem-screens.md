---
title: Layout meerdere zones
description: Leer hoe u inhoud voor meerdere zones maakt en verschillende elementen gebruikt, zoals video's, afbeeldingen en tekst die in één scherm in AEM Screens worden gecombineerd.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 901ed50e-d3f0-4c85-ad79-6c4595382759
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Layout meerdere zones {#multi-zone-layout}

De volgende pagina beschrijft het gebruik van lay-out met meerdere zones en behandelt de volgende onderwerpen:

* Overzicht
* Lay-out met meerdere zones maken
* Vereisten
* Single Assets gebruiken in een of meer zones
* Gesegrafeerde inhoud gebruiken in een of meer zones

## Overzicht {#overview}

***Lay-out van meerdere zones*** laat u veelvoudige streekinhoud tot stand brengen en diverse activa zoals video&#39;s, beelden, en tekst gebruiken die in één enkel scherm kunnen worden gecombineerd. U kunt afbeeldingen, video&#39;s en tekst aan elkaar trekken, zodat deze allemaal kunnen overvloeien en een intuïtieve digitale ervaring ontstaat.

Zoals bij de projectvereisten, soms hebt u veelvoudige streken in een kanaal nodig en geeft hen uit als één uitvoerige eenheid. Bijvoorbeeld, een productopeenvolging met een verwante sociale media voer die in drie afzonderlijke streken op één enkel kanaal loopt.

>[!NOTE]
>In kanalen met meerdere zones wordt het plannen op middelenniveau niet aanbevolen vanwege potentiële conflicten en onbedoeld gedrag. Als een schema op middelenniveau noodzakelijk is, maakt u een afzonderlijk volgnummer en past u de planningslogica toe binnen dat kanaal. Sluit vervolgens het sequentiekanaal in het kanaal met meerdere zones in.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u de conceptuele kennis over:

* [ Creërend een Project van AEM Screens ](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project)
* [ Creërend een Vertoning ](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays)
* [Een kanaal toewijzen aan een weergave](/help/user-guide/channel-assignment.md)

## Lay-out met meerdere zones maken {#creating-multi-zone-layout}

Tijdens het maken van een kanaal kunt u verschillende sjablonen gebruiken om zones in uw kanaal te maken. U kunt één afbeelding, video of ingesloten kanaal toevoegen waarmee meerdere elementen in een reeks kunnen worden weergegeven.

**Creërend een Kanaal**

1. Klik de verbinding van Adobe Experience Manager (bovenkant links) en dan **Screens**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens` gaan.
1. Navigeer aan de **omslag van Kanalen** en klik **creeer** van de actiebar.

1. Klik **1x2 Gesplitste Kanaal van het Scherm** van **creeer** tovenaar.

1. Klik **daarna** en ga de **titel** als **MultiZone** in.

1. Klik **creëren** om de kanaalverwezenlijking te voltooien.

### Single Assets gebruiken in een of meer zones {#using-single-assets-in-one-or-more-zones}

U kunt afzonderlijke elementen, zoals een afbeelding of een video, in alle afzonderlijke zones gebruiken. Volg de onderstaande stappen voor implementatie:

1. **Toevoegend Inhoud aan het Kanaal**

   1. Navigeer aan **Gebieden** > **Kanalen** > **MultiZone**.
   1. Klik het **kanaal 0&rbrace; MultiZone &lbrace;en klik** uitgeven **van de actiebar.**

1. **Toevoegend Beelden aan het Kanaal**

   Als u één afbeelding of video in twee zones wilt afspelen, sleept u een afbeelding naar elke zone in de Kanaaleditor, zoals in de onderstaande afbeelding wordt getoond:

   ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Gesegrafeerde inhoud gebruiken in een of meer zones {#using-sequenced-content-in-one-or-more-zones}

Als u wilt dat in de zones een reeks afbeeldingen en een video in de verschillende zones wordt weergegeven, volgt u de onderstaande stappen voor meer informatie.

1. **Creërend een Omslag van het Kanaal**

   1. Navigeer aan **Gebieden** > **MultiZone** > **Kanalen** en klik **creeer** van de actiebar.
   1. Klik **Omslag van Kanalen** van **creëren** tovenaar en klik **daarna**.
   1. Ga de titel als **EmbeddedChannels** in en klik **creeer**.

   ![ screen_shot_2018-12-19at125428pm ](assets/screen_shot_2018-12-19at125428pm.png)

1. **Toevoegend twee meer kanalen aan de Omslag van het Kanaal**

   1. Navigeer aan **Gebieden** > **Kanalen** > **EmbeddedChannels** en klik **creeer** van de actiebar.
   1. Klik het Kanaal van de Opeenvolging **van** creëren **tovenaar om een kanaal tot stand te brengen dat als &#x200B;**`Zone1`**wordt genoemd.**
   1. Klik **`Zone1`** en klik **uitgeven** van de actiebar.
   1. Sleep een paar afbeeldingen naar dit kanaal.
   1. Op dezelfde manier creeer een ander opeenvolgingskanaal dat als **`Zone2`** in **wordt genoemd EmbeddedChannels** omslag.
   1. Sleep een video naar dit kanaal.

   De volgende afbeelding toont de kanalen **`Zone1`** en **`Zone2`** :

   ![ screen_shot_2018-12-19at125930pm ](assets/screen_shot_2018-12-19at125930pm.png)

   De afbeeldingen die worden toegevoegd aan de editor van het **`Zone1`** -sequentiekanaal, worden hieronder weergegeven:

   ![ screen_shot_2018-12-19at125930pm ](/help/user-guide/assets/multi-zone/multizone-img4.png)

   De video die is toegevoegd aan de editor van het **`Zone2`** reekskanaal, wordt hieronder weergegeven:

   ![ screen_shot_2018-12-19at125930pm ](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Toevoegend Ingesloten Reeksen (component) aan belangrijkste kanaal (MultiZone)**

   1. Navigeer aan **Gebieden** > **Kanalen** > **MultiZone**.
   1. Klik **uitgeven** van de actiebar.
   1. Sleep en laat vallen de **Ingebedde component van de Opeenvolging** aan beide streken.
   1. Klik op de ingesloten reeks in een van de zones.
   1. Klik **vormen** (moersleutel) pictogram aan één van de ingebedde opeenvolgingen in de redacteur.
   1. Klik de kanaalweg als **>** Kanalen **>** EmbeddedChannels **>**`Zone1`**, zoals aangetoond in het hieronder cijfer.**
   1. Voeg de **`Zone2`** ook toe aan een andere ingesloten reekscomponent in de editor.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-3.png)

### Een locatie en een weergave maken {#creating-location}

Maak een locatie en een weergave zodat u de inhoud in de AEM Screens Player kunt bekijken.

1. **Creërend een Plaats**

   1. Navigeer aan de **omslag van Grenzen** > **Plaats**.
   1. Klik de **omslag van Plaatsen** en klik **creëren** van de actiebar.
   1. Klik **Plaats** van **creëren** tovenaar en klik **daarna**.
   1. Ga de **Titel** als **SanJose** in en klik **creeer**.

1. **Creërend een Vertoning**

   1. Navigeer aan de **omslag van Grenzen** > **Plaats**.
   1. Klik **SanJose** plaats en klik **creëren** van de actiebar.
   1. Klik **Vertoning** van **creëren** tovenaar en klik **daarna**.
   1. Ga de **Titel** als **Lobby** in en klik **creeer**.

### Kanalen toewijzen aan de weergave {#channel-channel}

Wijs de kanalen aan de vertoning toe om de inhoud te bekijken. Voer de onderstaande stappen uit om het kanaal aan de weergave toe te wijzen.

1. **Toewijzend Kanaal aan de Vertoning**

   1. Navigeer aan **Gebieden** > **Plaatsen** > **SanJose**> **Lobby**.
   1. Klik de **vertoning 0&rbrace; Lobby &lbrace;en klik** toewijzen Kanaal **van de actiebar.**
   1. Ga de weg aan het **kanaal 0&rbrace; MultiZone &lbrace;in** Weg van het Kanaal **in.**
   1. Plaats de **Gesteunde Gebeurtenissen** als **Aanvankelijke Lading**, **het Niet-actieve Scherm**, en **Tijdopnemer**.
   1. Klik **sparen**.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Wijs op dezelfde manier de andere twee ingesloten kanalen (**`Zone1`** en **`Zone2`**) aan deze vertoning toe.
   1. Nadat u alle drie kanalen aan de **&#x200B;**&#x200B;vertoning Lobby toewijst, zou u de toegewezen kanalen van het vertoningsdashboard moeten kunnen bekijken.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img8.png)


      >[!IMPORTANT]
      >
      >Nadat u het belangrijkste kanaal (in dit geval, **MultiZone**) aan de vertoning toewijst, is het verplicht om de andere twee ingebedde kanalen **`Zone1`** en **`Zone2`** ook aan de zelfde vertoning toe te wijzen.

### Het apparaat registreren {#registering-device}

Wanneer u een locatie en een weergave hebt ingesteld, voert u de onderstaande stappen uit om het apparaat te registreren en de weergave aan het apparaat toe te wijzen.

1. **registrerend het Apparaat**

   1. Navigeer aan de **Gebieden** > **omslag van Apparaten**.
   1. Klik de **omslag van Apparaten** en klik **Manager van het Apparaat** van de actiebar.
   1. Klik **Registratie van het Apparaat** en klik het hangende apparaat van de lijst.

      >[!NOTE]
      > De titel van het apparaat moet het apparatenteken (**Symbolische** gebied) aanpassen dat in de **Registratie van het Apparaat** tabel wordt getoond.

   1. Als de titel het apparatenteken aanpast, dan klik het apparaat en klik **Apparaat van het Register** van de actiebar.
   1. Als de registratiecode de code in de speler van Screens **1&rbrace; tabel van de Registratie van het Apparaat aanpast, klik** bevestigt **van de actiebar.**

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Ga de **Titel** als **`Chrome-Device1`** in en klik **Register**.
   1. Klik **toewijzen Vertoning** en klik de weg aan het apparaat config.

   >[!NOTE]
   >Als u probeert om de inhoud in de speler van Screens te bekijken, zorg ervoor u **Offlineinhoud** van de Update van het kanaaldashboard voor elk van de kanalen klikt die aan de vertoning worden toegewezen.

### Het resultaat weergeven {#viewing-the-result}

Wanneer u lay-outs met meerdere zones implementeert met behulp van de voorgaande stappen, wordt de volgende uitvoer weergegeven.

Controleer de Screens-speler, zodat u de uitvoer kunt bekijken die de inhoud in twee verschillende zones weergeeft. De linker- en rechterzones (beide gebruiken een ingesloten reeks als een component).

De linkerzone is een reekskanaal en de rechterzone bevat een video.

![ new2-1 ](/help/user-guide/assets/multi-zone/Multi-gif.gif)
