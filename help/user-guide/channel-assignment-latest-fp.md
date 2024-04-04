---
title: Kanaaltoewijzing - Laatste FP
seo-title: Channel Assignment - Latest FP
description: Volg deze pagina om meer te weten te komen over Kanaaltoewijzing en DayParting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
source-git-commit: d1adadbab2cb13626dd8ce70deacced9f55aa4c9
workflow-type: tm+mt
source-wordcount: '1476'
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

1. Selecteer het kanaal en klik op **Bewerken** in de actiebalk om inhoud toe te voegen aan uw kanaal.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Bijvoorbeeld de **Cafeteria** in het kanaal worden nu de volgende afbeeldingen weergegeven:

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Een locatie maken met de naam **SanJose** en een weergave als **Lobby**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Kanaal toewijzen aan een weergave {#assigning-channel-to-display}

Zodra de projectopstelling volledig is, moet u het kanaal aan een vertoning toewijzen om de inhoud te bekijken.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locaties** —> **SanJose** —> **Lobby**.

1. Tikken/klikken **Kanaal toewijzen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of,

   Tikken/klikken **Dashboard** op de actiebalk en klik op **+Kanaal toewijzen** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. De **Kanaaltoewijzing** wordt geopend.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Van de **Instellingen** kunt u het kanaal **op pad** of **op naam**, voert u de **Kanaalrol**, **Prioriteit**, **Ondersteunde gebeurtenissen**, en **Methoden voor onderbreking**. Bovendien kunt u de knopinfo voor aantrekken inschakelen vanuit dit dialoogvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >Zie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Van de **Schema** Selecteer de optie **Activeringsvenster** en **Herhalingsschema**.
   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >Zie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Klikken **Opslaan** zodra u uw voorkeuren hebt geconfigureerd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome-speler getoond. Nadat u het kanaal aan de weergave hebt toegewezen, moet u het apparaat registreren bij een speler.

Zie [Apparaatregistratie](device-registration.md) voor informatie over het registreren van een apparaat op een AEM Screens-speler.

U geeft de volgende uitvoer weer naar keuze van de speler:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Tijdlijnweergave {#timeline-view}

Nadat u een kanaal aan een weergave hebt toegewezen en een herhalingsschema hebt ingesteld, kunt u de tijdlijn vanuit de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

Ga als volgt te werk om naar de tijdlijnweergave te navigeren:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locaties** —> **SanJose** —> **Lobby**.

1. Tikken/klikken **Kanaal toewijzen** in de actiebalk.

   Of,

   Tikken/klikken **Dashboard** en klik op **Tijdlijn** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Kanaaleigenschappen van dialoogvenster Kanaaltoewijzing {#channel-properties}

De volgende eigenschappen worden ingesteld vanuit de **Instellingen** in de **Kanaaltoewijzing** in.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Een kanaal selecteren {#select-channel}

Als u een kanaal selecteert, kunt u een verwijzing naar het gewenste kanaal opgeven, op naam van het kanaal of op pad naar het kanaal.

* **op pad**: u geeft een expliciete verwijzing op met het absolute pad van het kanaal.

* **op naam**: U voert de naam in van het kanaal dat per context wordt omgezet in een daadwerkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met bijvoorbeeld een naam *dagblad*, waarbij de inhoud in feite in twee steden anders zou zijn, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor het minimum) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Bovendien, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting**: laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Niet-actief scherm**: wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Timer**: moet worden vastgesteld wanneer een schema wordt verstrekt
* **Gebruikersinteractie**: de speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie op het scherm plaatsvindt (aanraking) in een niet-actief kanaal en wordt geladen wanneer het scherm wordt aangeraakt

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
> Deze optie is alleen beschikbaar bij AEM 6.4 Feature Pack 8 of AEM 6.5 Feature Pack 4.

Als auteur van inhoud moet u kunnen opgeven wanneer een kanaal wordt onderbroken, zodat u niet-kritieke inhoud kunt uitschakelen, maar belangrijke inhoud volledig kunt laten afspelen voordat u het afspelen afsluit vanwege het plannen.

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het menu **Kanaaltoewijzing** dialoogvenster:

* **Meteen**: wanneer de planning wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen
* **Aan het einde van het huidige item**: wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, hebt u de optie om te wachten tot het huidige item in de reeks klaar is met afspelen en pas daarna vernieuwt of speelt u de nieuwe inhoud af

  >[!NOTE]
  >Deze optie is standaard ingeschakeld.

* **Aan het einde van de reeks**: wanneer een nieuw programma activeert of een update wordt ontvangen, hebt u de optie om op de volledige opeenvolging te wachten om zijn eind te bereiken, en net vóór de gewenste opeenvolging, kunt u terugloop naar het eerste element, u vernieuwt of de nieuwe inhoud speelt

  >[!NOTE]
  >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden enigszins worden uitgesteld omdat de speler op het einde van het item of de reeks (na de opgegeven tijd) wacht voordat het item of de reeks wordt vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

De volgende eigenschappen worden ingesteld vanuit de **Schema** in de **Kanaaltoewijzing** in.

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Activeringsvenster {#activation-window}

In het venster Activering kunt u een **Begindatum** en **Einddatum** om uw inhoud weer te geven.

### Herhalingsschema {#recurrence-schedule}

Met het schema Herhaling kunt u een terugkerend schema voor uw inhoud instellen. Klikken op **+ Plan toevoegen** om een terugkerend programma aan uw kanaal toe te voegen.

>[!NOTE]
>U kunt veelvoudige terugkomende programma&#39;s aan uw kanaal toevoegen.
>Herhalingsschema&#39;s worden geïntroduceerd *DayParting*, waarmee u een algemeen schema kunt instellen met meerdere kanalen die op specifieke tijdstippen van de dag worden uitgevoerd, en die instelling voor al uw beeldschermen tegelijk opnieuw kunt gebruiken.

U kunt de volgende opties instellen:

* **Naam**: Titel van uw terugkerend schema.
* **Herhalen**: Kies of het schema wordt uitgevoerd **Dagelijks**, **Wekelijks**, **Maandelijks**, of **Jaarlijks**.
* **Start**: De begintijd voor uw schema.
* **Einde**: De eindtijd voor uw schema. U kunt de achtergrondkleur instellen op tijd of duur.
   * **Tijd**: Het schema eindigt op een bepaald tijdstip.
   * **Duur**: De planning loopt gedurende een bepaalde tijdsduur in uren of minuten.

### DayParting {#dayparting}

DayParting verwijst naar het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. AEM Screens staat u toe om kanalen in termen van DayParting binnen een dag, een week, of een maand volgens het vereiste te plannen.

De volgende voorbeelden verklaren DayParting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant Dagparting gebruikt om dagelijks zijn ontbijt-, lunch- en dinermenu te laten zien.

Hier, zullen wij elke dag in verschillende tijdgroeven verdelen, zodat de kanaalinhoud op de gespecificeerde tijd van de dag speelt. Stel de volgende eigenschappen van het programma Herhaling voor uw kanaal in om de inhoud af te spelen volgens deze gebruiksaanwijzing.

| **Naam** | **Herhalingen** | **Start** | **Einde** |
|---|---|---|---|
| Ontbijt | Dagelijks | 06:00 | 11:00 |
| Lunch | Dagelijks | 11:00 | 15:00 |
| Diner | Dagelijks | 15:00 | 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

In dit voorbeeld wordt getoond hoe DayParting wordt geïmplementeerd in een casino waar de livegebeurtenis plaatsvindt elk weekend van 8:00 uur tot 10:00 uur en er speciale menu&#39;s beschikbaar zijn voor het diner na 10:00 uur tot 13:00 uur

| **Naam** | **Herhalingen** | **Start** | **Einde** |
|---|---|---|---|
| Weekend | Wekelijks: zaterdag, zondag | 20:00 | 22:00 |
| Specials | Dagelijks: maandag t/m vrijdag | 22:00 | 01:00 |

>[!NOTE]
>
>Bovendien kunt u ***Prioriteit*** voor elk van de kanalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.
