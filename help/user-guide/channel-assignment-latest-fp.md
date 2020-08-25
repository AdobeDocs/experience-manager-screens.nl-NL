---
title: Kanaaltoewijzing - Laatste FP
seo-title: Kanaaltoewijzing - Laatste FP
description: Volg deze pagina voor meer informatie over Kanaaltoewijzing en Dagverdeling.
translation-type: tm+mt
source-git-commit: c022e583a52d68e20d7916a8f02341905bb957b6
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 1%

---


# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>In deze sectie worden de kanaaltoewijzing en de planning van kanalen voor AEM 6.5.5-beeldschermfuncties (Functiepakket) en hoger gemarkeerd.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw scherm.

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

Nadat u de projectinstelling hebt voltooid, moet u het kanaal toewijzen aan een weergave om de inhoud weer te geven.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locations** —> **SanJose** —> **Lobby**.

1. Tik/klik op Kanaal **** toewijzen op de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of

   Tik/klik op **dashboard** en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Het dialoogvenster **Kanaaltoewijzing** wordt geopend.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Met de optie **Instellingen** kunt u het kanaal kiezen op pad of op naam, de kanaalrol, prioriteit, ondersteunde gebeurtenissen en onderbreekmethoden invoeren. Bovendien kunt u de optie voor het aantrekken van knopinfo vanuit dit dialoogvenster inschakelen.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.

1. Selecteer bij **Planningen** de optie Tijdzone **** referentie, Venster **** activering en **Herhalingsschema**.
   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.

1. Klik op **Opslaan** als u de voorkeuren hebt geconfigureerd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

In dit voorbeeld wordt de uitvoer op een Chrome-speler getoond. Nadat u het kanaal aan de weergave hebt toegewezen, moet u het apparaat registreren bij een speler.

Raadpleeg [Apparaatregistratie](device-registration.md) voor informatie over het registreren van een apparaat bij een AEM Screens-speler.

U geeft de volgende uitvoer weer naar keuze van de speler:

### Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

De volgende eigenschappen worden ingesteld met de optie **Instellingen** in het dialoogvenster **Kanaaltoewijzing** .

![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

#### Een kanaal selecteren {#select-channel}

Als u een kanaal selecteert, kunt u een verwijzing naar het gewenste kanaal opgeven, hetzij op de kanaalnaam, hetzij op het kanaalpad.

* **per pad**: u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.

* **op naam**: U voert de naam in van het kanaal dat per context wordt omgezet in een daadwerkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met een naam *gaat bijvoorbeeld over de dag*, waar de inhoud in feite anders zou zijn in twee steden, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

#### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

#### Priority {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor minimaal) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Bovendien, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

#### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting**: laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Niet-actief scherm**: wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Timer**: moet worden vastgesteld wanneer een schema wordt verstrekt
* **Gebruikersinteractie**: de speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie op het scherm is (aanraking) in een niet-actief kanaal en wordt geladen wanneer het scherm wordt aangeraakt

#### Onderbrekingsmethode {#interruption-method-channel}

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

#### Referentie tijdzone {#reference-timezone}

Met de tijdzone Referentie kunt u de tijdzone voor de weergave van inhoud selecteren.

#### Activeringsvenster {#activation-window}

In het venster Activering kunt u een **begindatum** en een **einddatum** selecteren om uw inhoud weer te geven.

#### Herhalingsschema {#recurrence-schedule}

Met het schema Herhaling kunt u een terugkerend schema voor uw inhoud instellen. Klik op **+ Plan** toevoegen om een terugkerend programma aan uw kanaal toe te voegen.

>[!NOTE]
>U kunt veelvoudige terugkomende programma&#39;s aan uw kanaal toevoegen.
>De Planningen van de herhaling introduceren *DayParting*, die u toestaat om een globaal programma met veelvoudige kanalen te plaatsen die op specifieke tijden van de dag lopen, en hergebruik die opstelling voor al uw vertoningen in één keer.

U kunt de volgende opties instellen:

* **Naam**: Titel van uw terugkerend schema.
* **Herhalen**: Kies of de planning **Dagelijks**, **Wekelijks**, **Maandelijks**, of **Jaarlijks** loopt.
* **Begin**: De begintijd voor uw schema.
* **Einde**: De eindtijd voor uw schema. U kunt het plaatsen door:
* **Tijd**: Het programma eindigt op een bepaald tijdstip.
* **Duur**: Het schema loopt gedurende een bepaalde tijdsduur in uren of minuten.

### DayParting {#dayparting}

DayParting verwijst naar als het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. AEM Screens staat u toe om kanalen in termen van DayParting binnen een dag, een week, of een maand volgens het vereiste te plannen.

De volgende voorbeelden verklaren DayParting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant Dagparting gebruikt om dagelijks het ontbijt-, lunch- en dinermenu te laten zien.

Hier, zullen wij elke dag in drie verschillende tijdgroeven verdelen, zodat de kanaalinhoud zoals per de gespecificeerde tijd van de dag speelt. De URL stelt de volgende eigenschappen van het programma Herhaling in om de inhoud af te spelen op basis van dit gebruiksgeval.

| **Naam** | **Herhalen** | **Begin** | **End** |
|---|---|---|---|
| Ontbijt | Dagelijks | 06:00 | 11:00 |
| Ontbijt | Dagelijks | 11:02 | 15:00 |
| Ontbijt | Dagelijks | 15:01 | 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

In dit voorbeeld ziet u hoe DayParting is bereikt in een casino, waar de livegebeurtenis elk weekend plaatsvindt van 8:00 tot 10:00 uur en er speciale menu&#39;s beschikbaar zijn voor het diner na 10:00 tot 13:00 uur.


#### Inhoud afspelen voor een bepaalde maand/maanden {#playing-content-for-a-particular-month-months}

Dit voorbeeld toont DayParting voor een opslag die hun zomerinzameling van de maanden van Juni tot Augustus en herinzameling van September tot eind Oktober toont.

Hier, zult u DayParting zoals per maanden creëren, zodat de kanaalinhoud zoals per de gespecificeerde maanden van het jaar speelt.


>[!NOTE]
>
>Bovendien kunt u ***Prioriteit*** voor elk van de kanalen bepalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

#### Inhoud afspelen voor kanalen met dezelfde prioriteit {#playing-content-for-channels-with-same-priority}

Dit voorbeeld toont DayParting voor een opslag die hun winterinzameling met het zelfde programma in de maand van December toont. Maar aangezien Kanaal B prioriteit heeft die als 2 wordt geplaatst, tijdens die week; kanaal B speelt zijn inhoud eerder dan kanaal A.




