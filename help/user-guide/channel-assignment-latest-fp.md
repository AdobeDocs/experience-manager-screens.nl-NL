---
title: Kanaaltoewijzing - Laatste FP
seo-title: Kanaaltoewijzing - Laatste FP
description: Volg deze pagina voor meer informatie over Kanaaltoewijzing en Dagverdeling.
translation-type: tm+mt
source-git-commit: 4ce9bd954a30282d94e30a6868d269b4df0a0f5e
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 1%

---


# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>In deze sectie worden de kanaaltoewijzing en de planning van kanalen voor AEM 6.5.5-pakket met schermfuncties en hoger gemarkeerd.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan de weergave, hoe u de kanaaleigenschappen begrijpt en hoe u de pagina kunt parseren.

>[!NOTE]
>U kunt meerdere kanalen aan een weergave toewijzen.


## Een kanaal toewijzen {#assign-a-channel-new-release}

Volg de onderstaande secties om een AEM Screens-project te maken en een kanaal toe te wijzen aan een weergave.

### AEM Screens-project en -kanalen maken {#creating-project}

Voer de onderstaande stappen uit om een project en een kanaal in te stellen:

1. Maak een AEM Screens-project met de naam **DemoScreens**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Raadpleeg [Projecten](creating-a-screens-project.md) maken en beheren voor meer informatie over het maken van een AEM Screens-project.

1. Maak een volgnummer met de naam **Cafeteria** in de map **Kanalen** .

1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om inhoud aan het kanaal toe te voegen.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Het kanaal **Cafeteria** geeft bijvoorbeeld nu de volgende afbeeldingen weer:

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Maak een locatie met de naam **SanJose** en een weergave als **Lobby**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Kanaal toewijzen aan een weergave {#assigning-channel-to-display}

Zodra de projectopstelling volledig is, moet u het kanaal aan een vertoning toewijzen om de inhoud te bekijken.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locations** —> **SanJose** —> **Lobby**.

1. Tik/klik op Kanaal **** toewijzen op de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of

   Tik/klik op **Dashboard** op de actiebalk en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Het dialoogvenster **Kanaaltoewijzing** wordt geopend.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Van de optie van **Montages** , kunt u het kanaal **door weg** of **door naam** kiezen, de Rol **van het** Kanaal, de **Prioriteit**********, de Methoden van ElementenSupportedEvents, en de Methoden van de Onderbreking ingaan. Bovendien kunt u de knopinfo voor aantrekken inschakelen vanuit dit dialoogvenster.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Selecteer bij de optie **Schema** de optie **Activeringsvenster** en **Herhalingsschema**.
   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over de eigenschappen van kanaaltoewijzingen.

1. Klik op **Opslaan** als u de voorkeuren hebt geconfigureerd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome-speler getoond. Nadat u het kanaal aan de weergave hebt toegewezen, moet u het apparaat registreren bij een speler.

Raadpleeg [Apparaatregistratie](device-registration.md) voor informatie over het registreren van een apparaat bij een AEM Screens-speler.

U geeft de volgende uitvoer weer naar keuze van de speler:

![new1](assets/channel-assignment/channel-assign-output.gif)

## Tijdlijnweergave {#timeline-view}

Nadat u een kanaal hebt toegewezen aan een weergave en een herhalingsschema hebt ingesteld, kunt u de tijdlijn weergeven vanuit het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

Ga als volgt te werk om naar de tijdlijnweergave te navigeren:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locations** —> **SanJose** —> **Lobby**.

1. Tik/klik op Kanaal **** toewijzen op de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of

   Tik/klik op **dashboard** en klik op **Tijdlijn** in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

1. Afbeeldingen in behandeling (vast te stellen)

## Kanaaleigenschappen van dialoogvenster Kanaaltoewijzing {#channel-properties}

De volgende eigenschappen worden ingesteld met de optie **Instellingen** in het dialoogvenster **Kanaaltoewijzing** .

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Een kanaal selecteren {#select-channel}

Als u een kanaal selecteert, kunt u een verwijzing naar het gewenste kanaal opgeven, hetzij op de kanaalnaam, hetzij op het kanaalpad.

* **per pad**: u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.

* **op naam**: U voert de naam in van het kanaal dat per context wordt omgezet in een daadwerkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met een naam *gaat bijvoorbeeld over de dag*, waar de inhoud in feite anders zou zijn in twee steden, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Priority {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor minimaal) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Bovendien, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting**: laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Niet-actief scherm**: wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Timer**: moet worden vastgesteld wanneer een schema wordt verstrekt
* **Gebruikersinteractie**: de speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie op het scherm is (aanraking) in een niet-actief kanaal en wordt geladen wanneer het scherm wordt aangeraakt

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Deze optie is alleen beschikbaar bij AEM 6.4 Feature Pack 8 of AEM 6.5 Feature Pack 4.

Als auteur van inhoud moet u kunnen opgeven wanneer een kanaal wordt onderbroken, zodat u niet-kritieke inhoud kunt uitschakelen, maar belangrijke inhoud volledig kunt laten afspelen voordat u het afspelen afsluit vanwege het plannen.

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het dialoogvenster **Kanaaltoewijzing** :

* **Onmiddellijk**: wanneer het programma wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen
* **Aan het einde van het huidige item**: wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, hebt u de optie om te wachten tot het huidige item in de reeks klaar is met afspelen en pas daarna vernieuwt of afspeelt u de nieuwe inhoud
   >[!NOTE]
   >Deze optie is standaard geselecteerd.
* **Aan het einde van de reeks**: wanneer een nieuw programma activeert of een update wordt ontvangen, hebt u de optie om op de volledige opeenvolging te wachten om zijn eind te bereiken, en net vóór de gewenste opeenvolging, kunt u terugloop naar het eerste element, u vernieuwt of de nieuwe inhoud speelt

   >[!NOTE]
   >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden enigszins worden uitgesteld omdat de speler op het einde van het item of de reeks (na de opgegeven tijd) wacht voordat het item of de reeks wordt vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.


De volgende eigenschappen worden ingesteld met de optie **Schema** in het dialoogvenster **Kanaaltoewijzing** .

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Activeringsvenster {#activation-window}

In het venster Activering kunt u een **begindatum** en een **einddatum** selecteren om uw inhoud weer te geven.

### Herhalingsschema {#recurrence-schedule}

Met het schema Herhaling kunt u een terugkerend schema voor uw inhoud instellen. Klik op **+ Plan** toevoegen om een terugkerend programma aan uw kanaal toe te voegen.

>[!NOTE]
>U kunt veelvoudige terugkomende programma&#39;s aan uw kanaal toevoegen.
>De Planningen van de herhaling introduceren *dag-parting*, die u toestaat om een globaal programma met veelvoudige kanalen te plaatsen die op specifieke tijden van de dag lopen, en hergebruik die opstelling voor al uw vertoningen in één keer.

U kunt de volgende opties instellen:

* **Naam**: Titel van uw terugkerend schema.
* **Herhalen**: Kies of de planning **Dagelijks**, **Wekelijks**, **Maandelijks**, of **Jaarlijks** loopt.
* **Begin**: De begintijd voor uw schema.
* **Einde**: De eindtijd voor uw schema. U kunt de achtergrondkleur instellen op tijd of duur.
   * **Tijd**: Het programma eindigt op een bepaald tijdstip.
   * **Duur**: Het schema loopt gedurende een bepaalde tijdsduur in uren of minuten.

### Dagverdeling {#dayparting}

Dagpartering wordt het splitsen van een dag in tijdsleuven genoemd en het opgeven van welke inhoud op het gewenste tijdstip wordt afgespeeld. AEM Screens staat u toe om kanalen in termen van dag-parting binnen een dag, een week, of een maand volgens het vereiste te plannen.

De volgende voorbeelden verklaren dag-parting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant dagelijks parten gebruikt om dagelijks zijn ontbijt-, lunch- en dinermenu te laten zien.

Hier, zullen wij elke dag in verschillende tijdgroeven verdelen, zodat de kanaalinhoud op de gespecificeerde tijd van de dag speelt. Stel de volgende eigenschappen van het programma Herhaling voor uw kanaal in om de inhoud af te spelen volgens deze gebruiksaanwijzing.

| **Naam** | **Herhalen** | **Begin** | **End** |
|---|---|---|---|
| Ontbijt | Dagelijks | 06:00 | 11:00 |
| Lunch | Dagelijks | 11:00 | 15:00 |
| Diner | Dagelijks | 15:00 | 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

In dit voorbeeld wordt getoond hoe de dag wordt geparseerd in een casino, waar elke weekendgebeurtenis plaatsvindt van 8:00 uur tot 10:00 uur en specials beschikbaar zijn voor het dinermenu na 22:00 uur tot 13:00 uur.

| **Naam** | **Herhalen** | **Begin** | **End** |
|---|---|---|---|
| Weekend | Wekelijks: zaterdag, zondag | 20:00 | 22:00 |
| Specials | Dagelijks: Maandag - vrijdag | 22:00 | 01:00 |

>[!NOTE]
>
>Bovendien kunt u ***Prioriteit*** voor elk van de kanalen bepalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

