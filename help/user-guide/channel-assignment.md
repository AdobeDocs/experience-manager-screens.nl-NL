---
title: Kanaaltoewijzing
description: Meer informatie over Kanaaltoewijzing en Dagverdeling.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 0%

---

# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>In deze sectie worden de Kanaaltoewijzing en de planning van kanalen voor kenmerkpakketten die ouder zijn dan AEM 6.5.5 Screens-versie gemarkeerd.

Wanneer u een weergave hebt ingesteld, wijst u een kanaal toe aan een weergave om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw scherm.

>[!NOTE]
>U kunt meerdere kanalen aan een weergave toewijzen.

## Een kanaal toewijzen {#assign-a-channel}

Voer de onderstaande stappen uit om een kanaal toe te wijzen aan een weergave:

1. Navigeer aan de vereiste vertoning, bijvoorbeeld, **DemoProject** > **Plaatsen** > **SanJose** > **StoreDisplay**.

   ![afbeelding](assets/screen_shot_2018-08-23at25359pm.png)

1. Klik **toewijzen Kanaal** in de actiebar.

   of

   Klik **Dashboard** en klik **+ wijs Kanaal** van het **TOEGEWEZEN paneel van KANALEN** toe zodat kunt u het **7&rbrace; de dialoogvakje van de Toewijzing van het Kanaal openen.**

   ![afbeelding](/help/user-guide/assets/channel-assign1.png)

   U kunt de eigenschappen van het **de dialoogvakje van de Taak van het Kanaal** van de sectie hieronder vormen. Zie de [ sectie van de Eigenschappen van het Kanaal ](#channel-properties) voor meer informatie over kanaaleigenschappen.

## Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

### Referentiekanaal {#ref-channel}

Met een referentiekanaal kunt u een verwijzing naar het gewenste kanaal opgeven, op kanaalnaam of op kanaalpad.

* **door weg** - u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.

* **door naam** - u gaat de naam van het kanaal in dat aan een werkelijk kanaal door context oplost. Met deze functie kunt u een lokale versie van een kanaal maken, zodat u locatie-specifieke inhoud dynamisch kunt oplossen. Bijvoorbeeld, behandelt een kanaal met naam *de dag*, waar de daadwerkelijke inhoud in twee steden verschillend zou zijn, maar u hebt nog de rol van het netwerkkanaal op alle vertoningen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol is gericht op verschillende acties en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt geplaatst als aantal (1 voor minimum) in het **de dialoogvakje van de Toewijzing van het Kanaal 1&rbrace;, zoals hierboven vermeld.** Ook, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Aanvankelijke Lading** - Laadt het kanaal wanneer de speler is begonnen. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Niet-actief Scherm** - Laadt wanneer het scherm nutteloos is. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Tijdopnemer** - moet worden geplaatst wanneer een programma wordt verstrekt.
* **Interactie van de Gebruiker** - de spelerschakelaars aan het gespecificeerde kanaal als er een gebruikersinteractie op het scherm (aanraking) in een nutteloos kanaal is en laadt wanneer het scherm wordt geraakt.

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Deze optie is slechts beschikbaar met <!--AEM 6.4 Feature Pack 8 or --> AEM 6.5 Pak van de Eigenschap 4.

Geef als Inhoudsauteur op wanneer een kanaal wordt onderbroken. Als u dit doet, kunt u niet-kritieke inhoud desgewenst uitschakelen, maar belangrijke inhoud desgewenst eerst afspelen voordat de inhoud wordt afgespeeld vanwege planning.

Klik van één van de volgende opties die beschikbaar zijn om de onderbrekingsmethode van het **de dialoogvakje van de Taak van het Kanaal** te plaatsen:

* **onmiddellijk** - wanneer het programma activeert of een update wordt ontvangen, kunt u de playback snijden en onmiddellijk verfrissen of de nieuwe inhoud spelen.
* **Aan eind van huidig punt** - wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op het huidige punt in de opeenvolging wachten om te beëindigen speel. Alleen daarna kunt u de nieuwe inhoud vernieuwen of afspelen.

  >[!NOTE]
  >Deze optie is standaard ingeschakeld.
* **aan het eind van de opeenvolging** - wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op de gehele opeenvolging wachten om zijn eind te bereiken. Vervolgens kunt u vlak voor de gewenste volgorde de nieuwe inhoud herhalen, vernieuwen of afspelen.

  >[!NOTE]
  >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden iets worden uitgesteld. De reden hiervoor is dat de speler wacht tot het einde van het item of de reeks (na de opgegeven tijd) is vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

### Schema {#schedule-channel}

Met Planning kunt u een beschrijving in tekst opgeven wanneer het kanaal moet worden weergegeven. Het laat u ook een begindatum (**actief van**) en een einddatum (**actief tot**) voor het kanaal bepalen om worden getoond.

**toon Tooltip van de Aantrek**

Toon aantrekkingstooltip bepaalt als de aantrekkingstooltip (&quot;*Aanraak overal om*&quot;te beginnen) moet worden getoond of niet terwijl het kanaal loopt.

### DayParting {#dayparting}

De programma&#39;s, wanneer gecombineerd met **DayParting**, laten u een globaal programma met veelvoudige kanalen plaatsen die op specifieke tijden van de dag lopen, en hergebruiken die opstelling voor al uw vertoningen in één keer.

DayParting wordt bedoeld als het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. Met AEM Screens kunt u kanalen plannen in termen van DayPparting binnen een dag, week of maand volgens de vereiste.

In de volgende voorbeelden wordt het parseren van dagen in kanalen in drie verschillende scenario&#39;s uitgelegd:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld ziet u hoe een restaurant DayParting gebruikt om het ontbijt, de lunch en het dinermenu te tonen.

Hier, verdeelt u elke dag in drie verschillende tijdgroeven zodat de kanaalinhoud op de gespecificeerde tijd van de dag speelt:

| **Kanaal** | **Rol** | **Prioriteit** | **Programma** |
|---|---|---|---|
| Menu_A | Ontbijt |  | Na 6:00 en vóór 11:00 |
| Menu_B | Lunch |  | Na 11:00 en vóór 15:00 |
| Menu_C | Diner |  | Na 15:00 en vóór 20:00 |

#### Inhoud afspelen op een bepaalde dag van de week {#playing-content-on-a-particular-day-of-the-week}

Dit voorbeeld toont dayParting die in een casino wordt bereikt waar de levende gebeurtenis elk weekend van 8:00 p.m. tot 10:00 p.m. voorkomt en de specials zijn beschikbaar voor dinermenu na 10:00 p.m. tot 1:00 a.m.

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
   <td>21 oktober 2017 - 22 oktober 2017 <br /> na 20:00 vóór 22:00</td>
  </tr>
  <tr>
   <td>SpecialsDiner</td>
   <td>Weekend</td>
   <td> </td>
   <td>21 oktober 2017 - 22 oktober 2017 <br /> na 22:00 voor 1:00</td>
  </tr>
 </tbody>
</table>

#### Inhoud afspelen voor een bepaalde maand/maanden {#playing-content-for-a-particular-month-months}

Dit voorbeeld toont DayParting voor een opslag die hun zomerinzameling van de maanden van Juni tot Augustus en herinzameling van September tot eind Oktober toont.

Hier, creeert u DayParting zoals per maand, zodat de kanaalinhoud zoals per de gespecificeerde maanden van het jaar speelt.

| **Kanaal** | **Rol** | **Prioriteit** | **Programma** |
|---|---|---|---|
| SummerCollection | Zomer |  | 1 juni 2017 - 31 augustus 2017 |
| FallCollection | Herfst |  | 1 september 2017 - 30 oktober 2017 |

>[!NOTE]
>
>Ook, kunt u ***Prioriteit*** voor elk van de kanalen bepalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

#### Inhoud afspelen voor kanalen met dezelfde prioriteit {#playing-content-for-channels-with-same-priority}

Dit voorbeeld toont DayParting voor een opslag die hun winterinzameling met het zelfde programma in de maand van December toont. Maar aangezien kanaal B de prioriteit heeft die als 2 wordt geplaatst, tijdens die week; kanaal B speelt zijn inhoud eerder dan kanaal A.

| **Kanaal** | **Rol** | **Prioriteit** | **Programma** |
|---|---|---|---|
| A | Winter | 1 | 1 december 2017 - 31 december 2017 |
| B | Kerstmis | 2 | 24 december 2017 - 31 december 2017 |


>[!NOTE]
>
> Zie de volgende secties voor meer informatie over DayParting:
>
>* [ Behandelend Herhaling in Assets ](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling)
>* [ Behandelende Herhaling voor Assets in een Kanaal ](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation)
