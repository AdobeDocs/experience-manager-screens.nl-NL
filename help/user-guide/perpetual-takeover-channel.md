---
title: Perpetual TakeOver Channel
seo-title: Perpetual TakeOver Channel
description: Volg dit Geval van Gebruik voor het creëren van een Perpetual TakeOver Kanaal.
seo-description: Follow this Use Case on setting up a project that creates a Perpetual TakeOver channel that plays for a specific time day and time continuously.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 0%

---

# Perpetual TakeOver Channel {#perpetual-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Perpetual te creëren TakeOver kanaal dat voor een specifieke tijddag en een tijd onophoudelijk speelt.

## Omschrijving hoofdletter gebruiken {#use-case-description}

Met deze optie wordt uitgelegd hoe u een kanaal maakt dat *overname* van het normaal afspeelkanaal voor een weergave of groep weergaven. De overname zal een bepaalde dag en tijd onafgebroken plaatsvinden.
Bijvoorbeeld, is er een Perpetual TakeOver kanaal dat elke Vrijdag van 9AM aan 10AM speelt. Tijdens deze tijd, zou geen ander kanaal moeten spelen. In het volgende voorbeeld ziet u hoe u een perpetual takeover channel maakt waarmee de inhoud elke woensdag 2 uur vanaf 14.00 tot 16.00 uur kan worden afgespeeld.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Het project instellen {#setting-up-the-project}

Voer de onderstaande stappen uit om een project in te stellen:

**Kanalen en weergave instellen**

1. Een AEM Screens-project maken met de naam **PerpetualTakeOver**, zoals hieronder weergegeven.

   ![element](assets/p_usecase1.png)

1. Een **MainAdChannel** in de **Kanalen** map.

   ![element](assets/p_usecase2.png)

1. Selecteer **MainAdChannel** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/p_usecase3.png)


   >[!NOTE]
   >De **MainAdChannel** in dit voorbeeld wordt een volgnummer weergegeven waarmee inhoud continu wordt afgespeeld.

1. Een **Overname** kanaal dat de inhoud in **MainAdChannel** en speelt elke woensdag van 2.00 tot 16.00 uur.

1. Selecteer de **Overname** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/p_usecase4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld de volgende locatie **MainLobby** en weergave **MainLobbyDisplay** is ingesteld voor dit project.

   ![element](assets/p_usecase5.png)

**Kanalen toewijzen aan een weergave**

1. De weergave selecteren **MainLobbyDisplay** van de **Locaties** map. Klikken **Kanaal toewijzen** van de actiebalk om te openen **Kanaaltoewijzing** in.

   >[!NOTE]
   >Raadpleeg voor meer informatie over het toewijzen van een kanaal aan een weergave **[Kanaaltoewijzing](channel-assignment.md)**.

1. Vul de velden (**Kanaalpad**, **Prioriteit**, en **Ondersteunde gebeurtenissen**) van de **Kanaaltoewijzing** en klik op **Opslaan** om **MainAdChannel** op uw scherm.

   * **Kanaalpad**: Selecteer het pad naar de **MainAdChannel** kanaal
   * **Prioriteit**: Stel de prioriteit van dit kanaal in op 1.
   * **Ondersteunde gebeurtenissen**: Selecteer **Oorspronkelijke belasting** en **Niet-actief scherm**.

   ![element](assets/p_usecase6.png)

1. De weergave selecteren **Overname** van de **Locaties** map. Klikken **Kanaal toewijzen** in de actiebalk om het overnamekanaal toe te wijzen.

1. Om het **Overname** naar de weergave op een gepland moment en vul de volgende velden in via het menu **Kanaaltoewijzing** en klik op **Opslaan**:

   * **Kanaalpad**: Selecteer het pad naar de **Overname** kanaal
   * **Prioriteit**: De prioriteit van dit kanaal instellen op groter dan de **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.
   * **Ondersteunde gebeurtenissen**: Selecteer **Niet-actief scherm** en **Timer**.
   * **Schema**: Voer de tekst in voor het schema waarop u wilt dat dit kanaal de weergave uitvoert. De tekst in de **Schema** in dit voorbeeld wordt vermeld *Woensdag na 14.00 uur en vóór 16.00 uur*.

      >[!NOTE]
      >Meer informatie over de expressies die u kunt toevoegen aan de **Schema**, verwijst u naar de [Voorbeeldexpressies](#example-expressions) hieronder.
   * **actief van**: Begindatum en -tijd.
   * **actief tot**: Einddatum en -tijd.

      De tekst in **Schema** en **actief van** en **actief tot** datum en tijd hier zodat de inhoud elke woensdag om 14.00 tot 16.00 uur kan worden afgespeeld.


      ![element](assets/p_usecase7.png)

      Navigeren naar de weergave vanuit **Overname** —> **Locaties** —> **MainLobby** —> **MainLobbyDisplay** en klik op **Dashboard** op de actiebalk om de toegewezen kanalen met hun prioriteiten weer te geven, zoals hieronder wordt weergegeven.

      >[!NOTE]
      >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

      ![element](assets/p_usecase8.png)
De **Overname** kanaal neemt de **MainAdChannel** om 2:00 uur gedurende twee uur tot 16:00 uur elke woensdag en speel de inhoud van 09 januari 2020 tot 31 januari 2020.

## Voorbeeldexpressies {#example-expressions}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | het kanaal speelt vóór 8:00 uur dagelijks |
| 14:00 | het kanaal wordt dagelijks om 14.00 uur afgespeeld |
| na 12:15 en vóór 12:45 | het kanaal wordt 30 minuten lang elke dag om 12:15 uur afgespeeld |
| vóór 12:15 ook na 12:45 | het kanaal wordt dagelijks vóór 12:15 uur afgespeeld en vervolgens ook na 12:45 uur |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het kanaal begint na 1 januari om 2:00 uur af te spelen, gaat de hele dag door met afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het kanaal start speler na 1 januari om 2:00 uur, gaat verder met spelen tot 2 januari om 3:00 uur, dan start het opnieuw op 2 januari om 2:00 uur en gaat verder met spelen tot 3:00 uur op 3 januari |

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (dat wil zeggen 14:00) in plaats van *am/pm* notatie (dat wil zeggen, 14:00 uur).
