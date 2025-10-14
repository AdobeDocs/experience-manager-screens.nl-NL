---
title: Kanaaltoewijzing - Laatste FP
description: Meer informatie over Kanaaltoewijzing en Dagverdeling.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: f7653d8b386c02f510eb7a770cf3cdc22c41a5fb
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 0%

---

# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>
>Deze sectie benadrukt de Toewijzing van het Kanaal en het plannen van kanalen voor AEM 6.5.5 het Pak van de Eigenschap van Screens en later.

Wanneer u een weergave hebt ingesteld, wijst u een kanaal toe aan een weergave om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw weergave, welke kanaaleigenschappen u kunt begrijpen en hoe u DayParting kunt uitvoeren.

>[!NOTE]
>
>U kunt meerdere kanalen aan een weergave toewijzen.


## Een kanaal toewijzen {#assign-a-channel-new-release}

Volg de onderstaande secties om een AEM Screens-project te maken en een kanaal toe te wijzen aan een weergave.

### AEM Screens-project en -kanalen maken {#creating-project}

Voer de onderstaande stappen uit om een project en een kanaal in te stellen:

1. Creeer een project van AEM Screens dat als **wordt genoemd DemoScreens**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Leren hoe te om een project van AEM Screens tot stand te brengen, zie [&#x200B; Creërend en het Leiden Projecten &#x200B;](creating-a-screens-project.md).

1. Creeer een opeenvolgingskanaal dat als **Cafeteria** in de **omslag van Kanalen** wordt genoemd.

1. Klik het kanaal, dan klik **uitgeven** van de actiebar.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Bijvoorbeeld, toont het **kanaal 0&rbrace; Cafeteria nu de volgende beelden:**

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Creeer een Plaats die als **wordt genoemd SanJose** en een vertoning als **Lobby**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Kanaal toewijzen aan een weergave {#assigning-channel-to-display}

Wanneer de projectopstelling volledig is, wijs het kanaal aan een vertoning toe om de inhoud te bekijken.

1. Navigeer aan de vereiste vertoning, bijvoorbeeld, **DemoScreens** > **Plaatsen** > **SanJose** > **Lobby**.

1. Klik **toewijzen Kanaal** van de actiebar.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of,

   Klik **Dashboard** van de actiebar en klik **+ wijs Kanaal** van **TOEGEWEZEN KANALEN &amp; SCHEDULES** paneel toe.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Het **de dialoogvakje van de Toewijzing van het Kanaal** opent.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Van de **optie van Montages**, kunt u het kanaal **door weg** of **door naam** kiezen, ga de **Rol van het Kanaal** in, **Prioriteit**, **Ondersteunde Gebeurtenissen**, en **Methoden van de Onderbreking**. Ook kunt u de knopinfo voor aantrekken inschakelen vanuit dit dialoogvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Meer over de eigenschappen van de Toewijzing van het Kanaal leren, zie de [&#128279;](#channel-properties) sectie van de Eigenschappen van het Kanaal 0&rbrace;.

1. Van de **optie van het Programma**, klik het **Venster van de Activering** en **Programma van de Herhaling**.
   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Meer over de eigenschappen van de Toewijzing van het Kanaal leren, zie de [&#128279;](#channel-properties) sectie van de Eigenschappen van het Kanaal 0&rbrace;.

1. Klik **sparen** zodra u uw voorkeur hebt gevormd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome Player weergegeven. Wanneer u het kanaal aan uw vertoning hebt toegewezen, registreer het apparaat aan een speler.

Leren hoe te om een apparaat op een Speler van AEM Screens te registreren, zie [&#x200B; Registratie van het Apparaat &#x200B;](device-registration.md).

U kunt de volgende uitvoer naar keuze van de speler weergeven:

![&#x200B; new1 &#x200B;](assets/channel-assignment/channel-assign-output.gif)

## Tijdlijnweergave {#timeline-view}

Wanneer u een kanaal aan een vertoning en opstelling een Programma van de Herhaling hebt toegewezen, kunt u de chronologie van het **TOEGEWEZEN KANALEN &amp; SCHADUWEN** paneel bekijken.

Ga als volgt te werk om naar de tijdlijnweergave te navigeren:

1. Navigeer aan de vereiste vertoning, bijvoorbeeld, **DemoScreens** > **Plaatsen** > **SanJose** > **Lobby**.

1. Klik **toewijzen Kanaal** van de actiebar.

   Of,

   Klik **Dashboard** en klik **Chronologie** van **TOEGEWEZEN KANALEN &amp; SCHEDULES** paneel.

   ![afbeelding](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Kanaaleigenschappen van dialoogvenster Kanaaltoewijzing {#channel-properties}

De volgende eigenschappen worden geplaatst van de **optie van Montages** in het **de dialoogvakje van de Toewijzing van het Kanaal**.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Een kanaal selecteren {#select-channel}

Als u een kanaal selecteert, kunt u een verwijzing naar het gewenste kanaal opgeven, op naam van kanaal of op pad naar kanaal.

* **door weg** - u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.
* **door naam** - u gaat de naam van het kanaal in dat aan een werkelijk kanaal door context oplost. Met deze functie kunt u een lokale versie van een kanaal maken, zodat u locatie-specifieke inhoud dynamisch kunt oplossen. Bijvoorbeeld, behandelt een kanaal met naam *de dag*, waar de daadwerkelijke inhoud in twee steden verschillend zou zijn, maar u hebt nog de rol van het netwerkkanaal op alle vertoningen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. Diverse acties richten zich op de rol. Het is onafhankelijk van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>
>De prioriteit voor een kanaal wordt geplaatst als aantal (1 voor minimum) in het **de dialoogvakje van de Toewijzing van het Kanaal 1&rbrace;, zoals hierboven vermeld.** Ook, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Aanvankelijke Lading** - Laadt het kanaal wanneer de speler is begonnen. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Niet-actief Scherm** - Laadt wanneer het scherm nutteloos is. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Tijdopnemer** - moet worden geplaatst wanneer een programma wordt verstrekt.
* **Interactie van de Gebruiker** - de spelerschakelaars aan het gespecificeerde kanaal als er een gebruikersinteractie op het scherm (aanraking) in een nutteloos kanaal is en laadt wanneer het scherm wordt geraakt.

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
> Deze optie is alleen beschikbaar bij <!--AEM 6.4 Feature Pack 8 or-->AEM 6.5 Feature Pack 4.

Als inhoudsauteur kunt u opgeven wanneer een kanaal wordt onderbroken. Zo kunt u ervoor kiezen om niet-kritieke inhoud uit te knippen. Maar het geeft u ook de optie om belangrijke inhoud volledig terug te laten spelen alvorens het wegens planning kort te snijden.

Selecteer van één van de volgende opties die beschikbaar zijn om de onderbrekingsmethode van het **de dialoogvakje van de Taak van het Kanaal** te plaatsen:

* **onmiddellijk** - wanneer het programma activeert of een update wordt ontvangen, kunt u de playback snijden en onmiddellijk de nieuwe inhoud verfrissen of spelen
* **Eind van het huidige punt** - wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op het huidige punt in de opeenvolging wachten te beëindigen speel. Pas daarna kunt u de nieuwe inhoud vernieuwen of afspelen.

  >[!NOTE]
  >Deze optie is standaard ingeschakeld.

* **aan het eind van de opeenvolging** - wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op de gehele opeenvolging wachten om zijn eind te bereiken. Vervolgens kunt u vlak voor de gewenste volgorde de nieuwe inhoud herhalen, vernieuwen of afspelen.

  >[!NOTE]
  >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden iets worden uitgesteld. De reden hiervoor is dat de speler wacht tot het einde van het item of de reeks (na de opgegeven tijd) is vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

De volgende eigenschappen worden geplaatst van de **optie van het Programma** in het **de dialoogvakje van de Toewijzing van het Kanaal**.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Activeringsvenster {#activation-window}

Het Venster van de Activering laat u de datum van het a **Begin** en een **Einddatum** selecteren om uw inhoud te tonen.

### Herhalingsschema {#recurrence-schedule}

Met het schema Herhaling kunt u een terugkerend schema voor uw inhoud instellen. Klik op **+ Plan toevoegen** om een herhalingsschema aan uw kanaal toe te voegen.

>[!NOTE]
>U kunt veelvoudige terugkomende programma&#39;s aan uw kanaal toevoegen.
>De Planningen van de herhaling introduceren *DayParting*. U stelt een globaal schema in met meerdere kanalen die op specifieke tijdstippen van de dag worden uitgevoerd, en gebruikt dat schema opnieuw voor al uw weergaven tegelijk.

U kunt de volgende opties instellen:

* **Naam** - Titel van uw Programma van de Herhaling.
* **Herhaal** - kies of de programma **Dagelijks**, **wekelijks**, **maandelijks**, of **jaarlijks** in werking stelt.
* **Begin** - de begintijd voor uw programma.
* **Eind** - de beëindigende tijd voor uw programma. U kunt de waarde instellen op tijd of duur.
   * **Tijd** - het programma beëindigt bij een gespecificeerde tijd.
   * **Duur** - de programmalooppas voor een bepaalde duur van tijd in uren of notulen.

### DayParting {#dayparting}

De Parting van de dag verwijst naar het opsplitsen van omhoog een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. Met AEM Screens kunt u kanalen plannen in termen van DayParting binnen een dag, week of maand volgens de vereiste.

De volgende voorbeelden verklaren DayParting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant Dagparting gebruikt om dagelijks het ontbijt, de lunch en het dinermenu te tonen.

Hier, wordt elke dag verdeeld in verschillende tijdgroeven, zodat de kanaalinhoud zoals per de gespecificeerde tijd van de dag speelt. Stel de volgende eigenschappen van het programma Herhaling voor uw kanaal in om de inhoud af te spelen volgens deze gebruiksaanwijzing.

| **Naam** | **herhaalt** | **Begin** | **Eind** |
|---|---|---|---|
| Ontbijt | Dagelijks | 06:00 | 11:00 |
| Lunch | Dagelijks | 11:00 | 15:00 |
| Diner | Dagelijks | 15:00 | 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

Dit voorbeeld toont DayParting die in een casino wordt uitgevoerd waar de levende gebeurtenis elk weekend van 8:00 p.m. tot 10:00 p.m. voorkomt en de specials zijn beschikbaar voor dinermenu na 10:00 p.m. tot 1:00 a.m.

| **Naam** | **herhaalt** | **Begin** | **Eind** |
|---|---|---|---|
| Weekend | Wekelijks: zaterdag en zondag | 20:00 | 22:00 |
| Specials | Dagelijks: van maandag tot vrijdag | 22:00 | 01:00 |

>[!NOTE]
>
>Ook, kunt u ***Prioriteit*** voor elk van de kanalen bepalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.
