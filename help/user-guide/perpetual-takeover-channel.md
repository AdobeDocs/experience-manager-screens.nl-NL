---
title: Perpetual TakeOver Channel
description: Volg dit Geval van Gebruik voor het creëren van een PerpetualTakeOver Kanaal.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 0%

---

# Perpetual TakeOver Channel {#perpetual-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Perpetual te creëren TakeOver kanaal dat voor een specifieke tijddag en een tijd onophoudelijk speelt.

## Omschrijving hoofdletter gebruiken {#use-case-description}

Met deze optie wordt uitgelegd hoe u een kanaal maakt dat *overname* in het normale afspeelkanaal voor een weergave of groep weergaven. De overname duurt een bepaalde dag en een bepaalde tijd onafgebroken.
Bijvoorbeeld, is er een Perpetual TakeOver kanaal dat elke Vrijdag van 9:00 a.m. door 10:00 a.m. speelt. Tijdens deze tijd, zou geen ander kanaal moeten spelen. In het volgende voorbeeld ziet u hoe u een perpetual takeover channel maakt waarmee de inhoud elke woensdag gedurende twee uur vanaf 2.00 tot 16.00 uur kan worden afgespeeld.

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

1. Selecteer de **MainAdChannel** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/p_usecase3.png)


   >[!NOTE]
   >De **MainAdChannel** in dit voorbeeld wordt een volgnummer weergegeven waarmee inhoud continu wordt afgespeeld.

1. Een **Overname** kanaal dat de inhoud in **MainAdChannel** en speelt elke woensdag van 2:00 tot 16:00

1. Selecteer de **Overname** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/p_usecase4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld de volgende locatie **MainLobby** en weergave **MainLobbyDisplay** voor dit project zijn opgezet.

   ![element](assets/p_usecase5.png)

**Kanalen toewijzen aan een weergave**

1. De weergave selecteren **MainLobbyDisplay** van de **Locaties** map. Klikken **Kanaal toewijzen** op de actiebalk, zodat u de **Kanaaltoewijzing** in.

   >[!NOTE]
   >Raadpleeg voor meer informatie over het toewijzen van een kanaal aan een weergave **[Kanaaltoewijzing](channel-assignment.md)**.

1. Vul de velden (**Kanaalpad**, **Prioriteit**, en **Ondersteunde gebeurtenissen**) van de **Kanaaltoewijzing** en klik op **Opslaan** om de **MainAdChannel** op uw scherm.

   * **Kanaalpad**: Selecteer het pad naar de **MainAdChannel** kanaal
   * **Prioriteit**: Stel de prioriteit van dit kanaal in op 1.
   * **Ondersteunde gebeurtenissen**: Selecteer de **Oorspronkelijke belasting** en **Niet-actief scherm**.

   ![element](assets/p_usecase6.png)

1. De weergave selecteren **Overname** van de **Locaties** map. Klikken **Kanaal toewijzen** op de actiebalk, zodat u het overnamekanaal kunt toewijzen.

1. Het toewijzen van **Overname** kanaal naar uw weergave op een gepland tijdstip en de volgende velden vullen vanuit de **Kanaaltoewijzing** dialoogvenster en klikken **Opslaan**:

   * **Kanaalpad**: Selecteer het pad naar de **Overname** kanaal
   * **Prioriteit**: Stel de prioriteit van dit kanaal groter in dan de **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.
   * **Ondersteunde gebeurtenissen**: Selecteer de **Niet-actief scherm** en **Timer**.
   * **Schema**: Ga de tekst voor het programma in dat u dit kanaal wilt in werking stellen de vertoning. De tekst in de **Schema** in dit voorbeeld wordt vermeld *Woensdag na 14.00 uur en vóór 16.00 uur*.

     >[!NOTE]
     >Meer informatie over de expressies die u kunt toevoegen aan de **Schema**, verwijst u naar de [Voorbeeldexpressies](#example-expressions) hieronder.
   * **actief van**: Begindatum en -tijd.
   * **actief tot**: Einddatum en -tijd.

     De tekst in **Schema** en **actief van** en **actief tot** datum en tijd hier staat de inhoud toe om elke Woensdag van 2:00 p.m. tot 4:00 p.m. te spelen.


     ![element](assets/p_usecase7.png)

     Navigeren naar de weergave vanuit **Overname** > **Locaties** > **MainLobby** > **MainLobbyDisplay** en klik op **Dashboard** in de actiebalk, zodat u de toegewezen kanalen met hun prioriteiten kunt weergeven, zoals hieronder wordt weergegeven.

     >[!NOTE]
     >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

     ![element](assets/p_usecase8.png)
Nu, **Overname** kanaal neemt het over **MainAdChannel** om 2:00 uur voor twee uur tot 16:00 uur elke woensdag en speelt de inhoud van januari 2020 tot 31 januari 2020 af.

## Voorbeeldexpressies {#example-expressions}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | het kanaal speelt vóór 08:00 om 00 elke dag |
| na 2:00 | het kanaal speelt na 2:00 p.m. elke dag |
| na 12:15 en vóór 12:45 | het kanaal speelt elke dag om 12:15 uur gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | Het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 |
| op de eerste dag van januari na 2:00 uur, ook op de tweede dag van januari, ook op de derde dag van januari vóór 3:00 uur. | het kanaal begint na 1 januari om 14.00 uur af te spelen, gaat de hele dag door met afspelen op 2 januari tot 3.00 uur &#39;s middags op 3 januari |
| op de 1-2 dagen van januari na 2:00 uur, ook op de 2-3 dagen van januari vóór 3:00 uur. | Het kanaal start speler na 1 januari om 2:00 uur, gaat verder met spelen tot 2 januari om 3:00 uur &#39;s middags, dan begint het opnieuw op 2 januari om 2:00 uur &#39;s middags en wordt verder afgespeeld tot 3:00 uur &#39;s avonds op 3 januari |

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (14:00) in plaats van *A.M./P.M.* (14:00)
