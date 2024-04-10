---
title: Kanaaltoewijzing - Laatste FP
description: Meer informatie over Kanaaltoewijzing en Dagverdeling.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 0%

---

# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>
>In deze sectie worden de kanaaltoewijzing en de planning van kanalen voor AEM 6.5.5-pakket met schermfuncties en hoger gemarkeerd.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw weergave, welke kanaaleigenschappen u kunt begrijpen en hoe u DayParting kunt uitvoeren.

>[!NOTE]
>
>U kunt meerdere kanalen aan een weergave toewijzen.


## Een kanaal toewijzen {#assign-a-channel-new-release}

Volg de onderstaande secties om een AEM Screens-project te maken en een kanaal toe te wijzen aan een weergave.

### AEM Screens-project en -kanalen maken {#creating-project}

Voer de onderstaande stappen uit om een project en een kanaal in te stellen:

1. Een AEM Screens-project maken met de naam **DemoScreens**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Zie [Projecten maken en beheren](creating-a-screens-project.md) om te leren hoe u een AEM Screens-project maakt.

1. Een volgnummer maken met de naam **Cafeteria** in de **Kanalen** map.

1. Selecteer het kanaal en selecteer vervolgens **Bewerken** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Bijvoorbeeld de **Cafeteria** in het kanaal worden nu de volgende afbeeldingen weergegeven:

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Een locatie maken met de naam **SanJose** en een weergave als **Lobby**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Kanaal toewijzen aan een weergave {#assigning-channel-to-display}

Wanneer de projectopstelling volledig is, moet u het kanaal aan een vertoning toewijzen om de inhoud te bekijken.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** > **Locaties** > **SanJose** > **Lobby**.

1. Tikken/klikken **Kanaal toewijzen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of,

   Tikken/klikken **Dashboard** op de actiebalk en klik op **+Kanaal toewijzen** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. De **Kanaaltoewijzing** wordt geopend.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Van de **Instellingen** kunt u het kanaal **op pad** of **op naam**, voert u de **Kanaalrol**, **Prioriteit**, **Ondersteunde gebeurtenissen**, en **Methoden voor onderbreking**. Ook kunt u de knopinfo voor aantrekken inschakelen vanuit dit dialoogvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Zie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Van de **Schema** selecteert u de optie **Activeringsvenster** en **Herhalingsschema**.
   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Zie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Klikken **Opslaan** zodra u uw voorkeuren hebt geconfigureerd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome-speler getoond. Nadat u het kanaal aan de weergave hebt toegewezen, moet u het apparaat registreren bij een speler.

Zie [Apparaatregistratie](device-registration.md) voor informatie over het registreren van een apparaat op een AEM Screens-speler.

U kunt de volgende uitvoer naar keuze van de speler weergeven:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Tijdlijnweergave {#timeline-view}

Nadat u een kanaal aan een weergave hebt toegewezen en een herhalingsschema hebt ingesteld, kunt u de tijdlijn vanuit de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

Ga als volgt te werk om naar de tijdlijnweergave te navigeren:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** > **Locaties** > **SanJose** > **Lobby**.

1. Tikken/klikken **Kanaal toewijzen** in de actiebalk.

   Of,

   Tikken/klikken **Dashboard** en klik op **Tijdlijn** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Kanaaleigenschappen van dialoogvenster Kanaaltoewijzing {#channel-properties}

De volgende eigenschappen worden ingesteld vanuit de **Instellingen** in de **Kanaaltoewijzing** in.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Een kanaal selecteren {#select-channel}

Als u een kanaal selecteert, kunt u een verwijzing naar het gewenste kanaal opgeven, op naam van kanaal of op pad naar kanaal.

* **Op pad** - U geeft een expliciete verwijzing op met het absolute pad van het kanaal.
* **Op naam** - Voer de naam in van het kanaal dat per context wordt omgezet in een werkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken, zodat u locatie-specifieke inhoud dynamisch kunt oplossen. Een kanaal met bijvoorbeeld een naam *dagblad*, waarbij de inhoud in feite in twee steden anders zou zijn, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor het minimum) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Ook, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting** - Laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Niet-actief scherm** - Wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Timer** - Moet worden vastgesteld wanneer een schema wordt verstrekt.
* **Gebruikersinteractie** - De speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie (aanraking) op het scherm plaatsvindt bij inactiviteit van het kanaal en wordt geladen wanneer het scherm wordt aangeraakt.

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
> Deze optie is alleen beschikbaar bij <!--AEM 6.4 Feature Pack 8 or-->AEM 6.5 Functiepakket 4.

Als auteur van inhoud kunt u opgeven wanneer een kanaal wordt onderbroken. Zo kunt u ervoor kiezen om niet-kritieke inhoud uit te knippen. Maar het geeft u ook de optie om belangrijke inhoud volledig terug te laten spelen alvorens het wegens planning kort te snijden.

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het menu **Kanaaltoewijzing** dialoogvenster:

* **Meteen** - Wanneer de planning wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen
* **Einde van het huidige item** - Wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, kunt u optioneel wachten tot het huidige item in de reeks is afgespeeld. Pas daarna kunt u de nieuwe inhoud vernieuwen of afspelen.

  >[!NOTE]
  >Deze optie is standaard ingeschakeld.

* **Aan het einde van de reeks** - Wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op de volledige opeenvolging wachten om zijn eind te bereiken. Vervolgens kunt u vlak voor de gewenste volgorde de nieuwe inhoud herhalen, vernieuwen of afspelen.

  >[!NOTE]
  >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden iets worden uitgesteld. De reden hiervoor is dat de speler wacht tot het einde van het item of de reeks (na de opgegeven tijd) is vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

De volgende eigenschappen worden ingesteld vanuit de **Schema** in de **Kanaaltoewijzing** in.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Activeringsvenster {#activation-window}

In het venster Activering kunt u een **Begindatum** en **Einddatum** om uw inhoud weer te geven.

### Herhalingsschema {#recurrence-schedule}

Met het schema Herhaling kunt u een terugkerend schema voor uw inhoud instellen. Selecteren **+ Plan toevoegen** om een terugkerend programma aan uw kanaal toe te voegen.

>[!NOTE]
>U kunt veelvoudige terugkomende programma&#39;s aan uw kanaal toevoegen.
>Herhalingsschema&#39;s worden geïntroduceerd *DayParting* Hiermee kunt u een algemeen schema instellen met meerdere kanalen die op specifieke tijdstippen van de dag worden uitgevoerd, en die instelling opnieuw gebruiken voor al uw beeldschermen tegelijk.

U kunt de volgende opties instellen:

* **Naam** - Titel van uw terugkerend schema.
* **Herhalen** - Kies of de planning wordt uitgevoerd **Dagelijks**, **Wekelijks**, **Maandelijks**, of **Jaarlijks**.
* **Start** - De begintijd voor uw schema.
* **Einde** - De eindtijd voor uw schema. U kunt de waarde instellen op tijd of duur.
   * **Tijd** - Het schema eindigt op een bepaald tijdstip.
   * **Duur** - Het schema loopt gedurende een bepaalde tijdsduur in uren of minuten.

### DayParting {#dayparting}

De Parting van de dag verwijst naar het opsplitsen van omhoog een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. Met AEM Screens kunt u kanalen plannen in termen van DayParting binnen een dag, week of maand volgens de vereiste.

De volgende voorbeelden verklaren DayParting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant Dagparting gebruikt om dagelijks het ontbijt, de lunch en het dinermenu te tonen.

Hier, wordt elke dag verdeeld in verschillende tijdgroeven, zodat de kanaalinhoud zoals per de gespecificeerde tijd van de dag speelt. Stel de volgende eigenschappen van het programma Herhaling voor uw kanaal in om de inhoud af te spelen volgens deze gebruiksaanwijzing.

| **Naam** | **Herhalingen** | **Start** | **Einde** |
|---|---|---|---|
| Ontbijt | Dagelijks | 06:00 | 11:00 |
| Lunch | Dagelijks | 11:00 | 15:00 |
| Diner | Dagelijks | 15:00 | 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

Dit voorbeeld toont DayParting die in een casino wordt uitgevoerd waar de levende gebeurtenis elk weekend van 8:00 p.m. tot 10:00 p.m. voorkomt en de specials zijn beschikbaar voor dinermenu na 10:00 p.m. tot 1:00 a.m.

| **Naam** | **Herhalingen** | **Start** | **Einde** |
|---|---|---|---|
| Weekend | Wekelijks: zaterdag en zondag | 20:00 | 22:00 |
| Specials | Dagelijks: van maandag tot vrijdag | 22:00 | 01:00 |

>[!NOTE]
>
>U kunt ook ***Prioriteit*** voor elk van de kanalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.
