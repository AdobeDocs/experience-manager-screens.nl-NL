---
title: Kanaaltoewijzing
seo-title: Kanaaltoewijzing
description: Volg deze pagina om over de Toewijzing van het Kanaal en Dagscheiding te leren.
seo-description: Volg deze pagina om over de Toewijzing van het Kanaal en Dagscheiding te leren.
uuid: fe429485-dcc9-4507-864c-b04393cedeee
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 212adcd1-835b-453d-9d3e-775366abf181
docset: aem65
translation-type: tm+mt
source-git-commit: bde770227dfbe72e96254d27ba14e7469eed1b5c

---


# Kanaaltoewijzing {#channel-assignment}

In deze sectie worden de volgende onderwerpen behandeld:

* **Een kanaal toewijzen**
* **Eigenschappen van het dialoogvenster Kanaaltoewijzing**
* **Dagscheiding**

Nadat u een weergave hebt gedefinieerd, moet u een kanaal aan een weergave toewijzen.

Op deze pagina ziet u hoe u kanaal toewijst aan uw weergaven.

**Voorwaarden**:

* [Schermen configureren en implementeren](configuring-screens-introduction.md)
* [Schermproject maken en beheren](creating-a-screens-project.md)
* [Kanalen maken en beheren](managing-channels.md)
* [Locaties maken en beheren](managing-locations.md)
* [Weergaven maken en beheren](managing-displays.md)

## Een kanaal toewijzen {#assign-a-channel}

Voer de onderstaande stappen uit om een kanaal toe te wijzen aan een weergave:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoProject** —> **Locaties** —> **SanJose** —> **StoreDisplay**.

   ![screen_shot_2018-08-23at25359pm](assets/screen_shot_2018-08-23at25359pm.png)

1. Tik/klik op Kanaal **** toewijzen op de actiebalk

   Of

   Tik/klik op **Dashboard** en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN** om het dialoogvenster **Kanaaltoewijzing** te openen.

   ![image](/help/user-guide/assets/channel-assign1.png)

   In de onderstaande sectie kunt u de volgende eigenschappen configureren vanuit het dialoogvenster **Kanaaltoewijzing** .

### Kanaaleigenschappen {#channel-properties}

#### Referentiekanaal {#ref-channel}

Met het referentiekanaal kunt u een verwijzing naar het gewenste kanaal opgeven, op kanaalnaam of op kanaalpad.

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

Als auteur van inhoud moet u kunnen opgeven wanneer een kanaal wordt onderbroken, zodat u niet-kritieke inhoud kunt uitschakelen, maar belangrijke inhoud volledig kunt laten afspelen voordat u het afspelen afsluit vanwege het plannen.
De volgende opties zijn beschikbaar om de methode van de onderbreking van de de dialoogdoos van de Toewijzing van het **Kanaal** te plaatsen:

* **Onmiddellijk**: wanneer de planning wordt geactiveerd of een update wordt ontvangen, wordt het afspelen onderbroken en wordt de nieuwe inhoud direct vernieuwd of afgespeeld
* **Aan het einde van het huidige item**: wanneer een nieuw programma activeert of een update wordt ontvangen, wachten wij op het huidige punt in de opeenvolging om te beëindigen speel, en slechts daarna verfrissen wij of spelen de nieuwe inhoud
   >[!NOTE]
   >Dit is de standaardoptie die wordt geselecteerd.
* **Aan het einde van de reeks**: wanneer een nieuw programma activeert of een update wordt ontvangen, wachten wij op de volledige opeenvolging om zijn eind te bereiken, en net alvorens wij terug naar het eerste element herhalen wij verfrissen of spelen de nieuwe inhoud

#### Schema {#schedule-channel}

In het schema kunt u een beschrijving in tekst opgeven wanneer het kanaal moet worden weergegeven. Ook kunt u een begindatum (**actief vanaf**) en een einddatum (**actief tot**) definiëren voor het kanaal dat moet worden weergegeven.

**Knopinfo** voor bijtrekken weergeven:

De knopinfo voor het weergeven van de aantrekkingskracht definieert of de knopinfo voor het aantrekken (&quot;*overal aanraken om te beginnen*&quot;) al dan niet moet worden weergegeven terwijl het kanaal wordt uitgevoerd.


### Dagscheiding {#dayparting}

De programma&#39;s wanneer gecombineerd met **Dagscheiding**, staan u toe om een globaal programma met veelvoudige kanalen te plaatsen die op specifieke tijden van de dag lopen, en hergebruik die opstelling voor al uw vertoningen in één keer.

DayParting verwijst naar als het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. Met AEM-rasters kunt u kanalen plannen voor overdag binnen een dag, week of maand volgens de vereisten.

In de volgende voorbeelden wordt het overschakelen tussen kanalen in drie verschillende scenario&#39;s uitgelegd:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant zomertijd gebruikt om het ontbijt-, lunch- en dinermenu te tonen.

Hier, zullen wij elke dag in drie verschillende tijdgroeven verdelen, zodat de kanaalinhoud zoals per de gespecificeerde tijd van de dag speelt:

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| Menu_A | Ontbijt |  | na 6:00 en vóór 11:00 |
| Menu_B | Lunch |  | na 11.00 uur en vóór 15.00 uur |
| Menu_C | Diner |  | na 15.00 uur en vóór 20.00 uur |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

In dit voorbeeld wordt getoond hoe de dag wordt bereikt in een casino, waar de livegebeurtenis elk weekend plaatsvindt van 8:00 tot 10:00 uur en er speciale menu&#39;s beschikbaar zijn voor het diner na 10:00 tot 13:00 uur.

<table>
 <tbody>
  <tr>
   <td><strong>Kanaal</strong></td>
   <td><strong>Rol</strong></td>
   <td><strong>Prioriteit</strong></td>
   <td><strong>Schema</strong></td>
  </tr>
  <tr>
   <td>LiveConcert</td>
   <td>Weekend</td>
   <td> </td>
   <td>21 okt 2017 - 22 okt 2017 <br /> na 20:00 vóór 22:00</td>
  </tr>
  <tr>
   <td>SpecialsDiner</td>
   <td>Weekend</td>
   <td> </td>
   <td>21 okt 2017 - 22 okt 2017 <br /> na 22:00 vóór 1:00</td>
  </tr>
 </tbody>
</table>

#### Inhoud afspelen voor een bepaalde maand/maanden {#playing-content-for-a-particular-month-months}

In dit voorbeeld ziet u de zomertijd voor een winkel waarin de zomerverzameling wordt weergegeven van de maanden juni tot augustus en de herfstcollectie van september tot eind oktober.

Hier, zult u dagparing zoals per maanden creëren, zodat de kanaalinhoud zoals per de gespecificeerde maanden van het jaar speelt.

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| SummerCollection | Zomer |  | 1 juni 2017 - 31 aug. 2017 |
| FallCollection | Herfst |  | 01 sep. 2017 - 30 okt. 2017 |

>[!NOTE]
>
>Bovendien kunt u ***Prioriteit*** voor elk van de kanalen bepalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

#### Inhoud afspelen voor kanalen met dezelfde prioriteit {#playing-content-for-channels-with-same-priority}

Dit voorbeeld toont de dag-parting voor een opslag die hun winterinzameling met het zelfde programma in de maand van December toont. Maar aangezien Kanaal B prioriteit heeft die als 2 wordt geplaatst, tijdens die week; kanaal B speelt zijn inhoud eerder dan kanaal A.

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| A | Winter | 1 | 01 dec. 2017 - 31 dec. 2017 |
| B | Kerstmis | 2 | 24 dec. 2017 - 31 dec. 2017 |

>[!IMPORTANT]
> Raadpleeg de volgende secties voor meer informatie over overdag:
>* [Herhaling van activa afhandelen](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling.html#handling-recurrence-in-assets)
>* [Herhaling van middelen in een kanaal afhandelen](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation.html#handling-recurrence-in-assets)


