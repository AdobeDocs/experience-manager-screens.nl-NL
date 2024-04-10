---
title: Kanaaltoewijzing
description: Meer informatie over Kanaaltoewijzing en Dagverdeling.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 0%

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

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoProject** > **Locaties** > **SanJose** > **StoreDisplay**.

   ![afbeelding](assets/screen_shot_2018-08-23at25359pm.png)

1. Selecteren **Kanaal toewijzen** in de actiebalk.

   of

   Selecteren **Dashboard** en selecteert u **+Kanaal toewijzen** van de **TOEGEWEZEN KANALEN** zodat u het deelvenster **Kanaaltoewijzing** in.

   ![afbeelding](/help/user-guide/assets/channel-assign1.png)

   U kunt de eigenschappen configureren via de **Kanaaltoewijzing** in de onderstaande sectie. Zie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.

## Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

### Referentiekanaal {#ref-channel}

Met referentiekanaal kunt u een verwijzing naar het gewenste kanaal opgeven, op naam van kanaal of op pad naar kanaal.

* **op pad** - U geeft een expliciete verwijzing op met het absolute pad van het kanaal.

* **op naam** - Voer de naam in van het kanaal dat per context wordt omgezet in een werkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met bijvoorbeeld een naam *dagblad*, waarbij de inhoud in feite in twee steden anders zou zijn, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Prioriteit {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor het minimum) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Ook, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting** - Laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Niet-actief scherm** - Wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen met een programma worden toegewezen.
* **Timer** - Moet worden vastgesteld wanneer een schema wordt verstrekt.
* **Gebruikersinteractie** - De speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie (aanraking) op het scherm plaatsvindt bij inactiviteit van het kanaal en wordt geladen wanneer het scherm wordt aangeraakt.

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Deze optie is alleen beschikbaar bij <!--AEM 6.4 Feature Pack 8 or -->AEM 6.5 Functiepakket 4.

Als auteur van inhoud, specificeer wanneer een kanaal wordt onderbroken zodat kunt u verkiezen om niet-kritieke inhoud uit te snijden, maar desgewenst belangrijke inhoud laten spelen alvorens zijn playback wegens het plannen weg te snijden.

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het menu **Kanaaltoewijzing** dialoogvenster:

* **Meteen** - Wanneer het programma wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen.
* **Aan einde van huidig item** - Wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, kunt u optioneel wachten tot het huidige item in de reeks is afgespeeld. Alleen daarna kunt u de nieuwe inhoud vernieuwen of afspelen.

  >[!NOTE]
  >Deze optie is standaard ingeschakeld.
* **Aan het einde van de reeks** - Wanneer een nieuw programma activeert of een update wordt ontvangen, kunt u naar keuze op de volledige opeenvolging wachten om zijn eind te bereiken. Vervolgens kunt u vlak voor de gewenste volgorde de nieuwe inhoud herhalen, vernieuwen of afspelen.

  >[!NOTE]
  >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden iets worden uitgesteld. De reden hiervoor is dat de speler wacht tot het einde van het item of de reeks (na de opgegeven tijd) is vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.

### Schema {#schedule-channel}

Met Planning kunt u een beschrijving in tekst opgeven wanneer het kanaal moet worden weergegeven. Hiermee kunt u ook een begindatum definiëren (**actief van**) en een einddatum (**actief tot**) voor het kanaal dat wordt weergegeven.

**Knopinfo voor activering weergeven**

Knopinfo voor aantrekken weergeven die aangeeft of de knopinfo voor aantrekken (&quot;*Tik ergens om te beginnen*&quot;) moet worden getoond of niet terwijl het kanaal loopt.

### DayParting {#dayparting}

Planningen indien gecombineerd met **DayParting**, kunt u een algemeen schema instellen met meerdere kanalen die op specifieke tijdstippen van de dag worden uitgevoerd, en die instelling opnieuw gebruiken voor al uw beeldschermen tegelijk.

DayParting verwijst naar als het opsplitsen van een dag in tijdgroeven en het specificeren van welke inhoud op de gewenste tijd speelt. Met AEM Screens kunt u kanalen plannen in termen van DayPparting binnen een dag, week of maand volgens de vereiste.

In de volgende voorbeelden wordt het parseren van dagen in kanalen in drie verschillende scenario&#39;s uitgelegd:

#### Inhoud afspelen op één dag, verdeeld in meerdere tijdsleuven {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

In dit voorbeeld ziet u hoe een restaurant DayParting gebruikt om het ontbijt, de lunch en het dinermenu te tonen.

Hier, verdeelt u elke dag in drie verschillende tijdgroeven zodat de kanaalinhoud op de gespecificeerde tijd van de dag speelt:

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
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

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| SummerCollection | Zomer |  | 1 juni 2017 - 31 augustus 2017 |
| FallCollection | Herfst |  | 1 september 2017 - 30 oktober 2017 |

>[!NOTE]
>
>U kunt ook ***Prioriteit*** voor elk van de kanalen. Bijvoorbeeld, als twee kanalen voor de zelfde dag en de tijd of voor de zelfde maand worden geplaatst, dan eerst wordt het kanaal met hogere prioriteit gespeeld. De minimumwaarde voor prioriteit kan worden ingesteld op 0.

#### Inhoud afspelen voor kanalen met dezelfde prioriteit {#playing-content-for-channels-with-same-priority}

Dit voorbeeld toont DayParting voor een opslag die hun winterinzameling met het zelfde programma in de maand van December toont. Maar aangezien Kanaal B prioriteit heeft die als 2 wordt geplaatst, tijdens die week; kanaal B speelt zijn inhoud eerder dan Kanaal A.

| **Kanaal** | **Rol** | **Prioriteit** | **Schema** |
|---|---|---|---|
| A | Winter | 1 | 1 december 2017 - 31 december 2017 |
| B | Kerstmis | 2 | 24 december 2017 - 31 december 2017 |


>[!NOTE]
>
> Raadpleeg de volgende secties voor meer informatie over DayParting:
>
>* [Herhaling van activa afhandelen](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling)
>* [Herhaling van middelen in een kanaal afhandelen](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation)
