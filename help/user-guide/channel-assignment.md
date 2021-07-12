---
title: Kanaaltoewijzing
seo-title: Kanaaltoewijzing
description: Volg deze pagina voor meer informatie over Kanaaltoewijzing en Dagverdeling.
feature: Auteursschermen, Kanaaltoewijzing
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '1219'
ht-degree: 1%

---

# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>Deze sectie benadrukt de toewijzing van het Kanaal en het plannen van kanalen voor de pakken van de Eigenschap ouder dan AEM 6.5.5 de versie van het Scherm.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw scherm.

>[!NOTE]
>U kunt meerdere kanalen aan een weergave toewijzen.

## Een kanaal toewijzen {#assign-a-channel}

Voer de onderstaande stappen uit om een kanaal toe te wijzen aan een weergave:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoProject** —> **Locaties** —> **SanJose** —> **StoreDisplay**.

   ![afbeelding](assets/screen_shot_2018-08-23at25359pm.png)

1. Tik/klik **Kanaal toewijzen** in de actiebalk

   Of

   Tik/klik **Dashboard** en klik **+Wijs Kanaal** van **TOEGEWEZEN KANALEN** paneel toe om **Kanaaltoewijzing** dialoogdoos te openen.

   ![afbeelding](/help/user-guide/assets/channel-assign1.png)

   U kunt de eigenschappen van de **de dialoogdoos van de Toewijzing van het Kanaal** van de sectie hieronder vormen. Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.


## Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

### Referentiekanaal {#ref-channel}

Met het referentiekanaal kunt u een verwijzing naar het gewenste kanaal opgeven, op kanaalnaam of op kanaalpad.

* **per pad**: u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.

* **op naam**: U voert de naam in van het kanaal dat per context wordt omgezet in een daadwerkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met bijvoorbeeld de naam *gaat over de dag*, waarbij de werkelijke inhoud in twee steden anders zou zijn, maar u hebt nog steeds de rol van het normaal kanaal op alle weergaven.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt geplaatst als aantal (1 voor minimum) in **de dialoogdoos van de Toewijzing van het Kanaal**, zoals hierboven vermeld. Bovendien, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

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

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het dialoogvenster **Kanaaltoewijzing**:

* **Onmiddellijk**: wanneer het programma wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen
* **Aan het einde van het huidige item**: wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, hebt u de optie om te wachten tot het huidige item in de reeks klaar is met afspelen en pas daarna vernieuwt of afspeelt u de nieuwe inhoud
   >[!NOTE]
   >Deze optie is standaard geselecteerd.
* **Aan het einde van de reeks**: wanneer een nieuw programma activeert of een update wordt ontvangen, hebt u de optie om op de volledige opeenvolging te wachten om zijn eind te bereiken, en net vóór de gewenste opeenvolging, kunt u terugloop naar het eerste element, u vernieuwt of de nieuwe inhoud speelt

   >[!NOTE]
   >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden enigszins worden uitgesteld omdat de speler op het einde van het item of de reeks (na de opgegeven tijd) wacht voordat het item of de reeks wordt vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

### Schema {#schedule-channel}

In het schema kunt u een beschrijving in tekst opgeven wanneer het kanaal moet worden weergegeven. Het laat u ook een begindatum (**actief van**) en een einddatum (**actief tot**) voor het te tonen kanaal bepalen.

**Knopinfo** voor bijtrekken weergeven:

De knopinfo voor het weergeven van de aantrekkingskracht definieert of de knopinfo voor het aantrekken (&quot;*Aanraken op een willekeurige plaats om te beginnen*&quot;) moet worden weergegeven of niet terwijl het kanaal wordt uitgevoerd.

### DayParting {#dayparting}

Planningen wanneer gecombineerd met **DayParting**, staat u toe om een globaal programma met veelvoudige kanalen te plaatsen die op specifieke tijden van de dag lopen, en hergebruik die opstelling voor al uw vertoningen tegelijkertijd.

DayParting verwijst naar als het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. AEM Screens staat u toe om kanalen in termen van dag-parting binnen een dag, een week, of een maand volgens het vereiste te plannen.

De volgende voorbeelden verklaren dag-parting in kanalen in drie verschillende scenario&#39;s:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld wordt getoond hoe een restaurant gebruikmaakt van dagparting om het ontbijt-, lunch- en dinermenu te laten zien.

Hier, zullen wij elke dag in drie verschillende tijdgroeven verdelen, zodat de kanaalinhoud zoals per de gespecificeerde tijd van de dag speelt:

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| Menu_A | Ontbijt |  | na 6:00 en vóór 11:00 |
| Menu_B | Lunch |  | na 11.00 uur en vóór 15.00 uur |
| Menu_C | Diner |  | na 15.00 uur en vóór 20.00 uur |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

In dit voorbeeld wordt getoond welke dayParting is bereikt in een casino, waar de livegebeurtenis plaatsvindt elk weekend van 8:00 tot 10:00 uur en er speciale menu&#39;s beschikbaar zijn voor het diner na 10:00 tot 13:00 uur.

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
   <td>21 okt 2017 - 22 okt 2017 <br /> na 22:00 voor 1:00</td>
  </tr>
 </tbody>
</table>

#### Inhoud afspelen voor een bepaalde maand/maanden {#playing-content-for-a-particular-month-months}

Dit voorbeeld toont DayParting voor een opslag die hun zomerinzameling van de maanden van Juni tot Augustus en herinzameling van September tot eind Oktober toont.

Hier, zult u dag-parting zoals per maanden tot stand brengen, zodat de kanaalinhoud zoals per de gespecificeerde maanden van het jaar speelt.

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| SummerCollection | Zomer |  | 1 juni 2017 - 31 aug. 2017 |
| FallCollection | Herfst |  | 01 sep. 2017 - 30 okt. 2017 |

>[!NOTE]
>
>Daarnaast kunt u ***Prioriteit*** voor elk van de kanalen definiëren. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

#### Inhoud afspelen voor kanalen met dezelfde prioriteit {#playing-content-for-channels-with-same-priority}

Dit voorbeeld toont DayParting voor een opslag die hun winterinzameling met het zelfde programma in de maand van December toont. Maar aangezien Kanaal B prioriteit heeft die als 2 wordt geplaatst, tijdens die week; kanaal B speelt zijn inhoud eerder dan kanaal A.

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| A | Winter | 1 | 01 dec. 2017 - 31 dec. 2017 |
| B | Kerstmis | 2 | 24 dec. 2017 - 31 dec. 2017 |


>[!NOTE]
>
> Raadpleeg de volgende secties voor meer informatie over DayParting:
>
>* [Herhaling van activa afhandelen](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling.html#handling-recurrence-in-assets)
>* [Herhaling van middelen in een kanaal afhandelen](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation.html#handling-recurrence-in-assets)

