---
title: Overnamekanaal voor één gebruik
seo-title: Overnamekanaal voor één gebruik
description: Volg dit Geval van Gebruik voor het creëren van Één enkel Gebruik neemOver Kanaal.
seo-description: Volg dit Geval van Gebruik voor het creëren van Één enkel Gebruik neemOver Kanaal.
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: d64eb2ca3efc4d15be119c9b8efd9ff2b8f8daf4

---


# Overnamekanaal voor één gebruik {#single-use-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Enig kanaal tot stand te brengen TakeOver dat slechts één keer voor een specifieke tijd speelt.


## Omschrijving hoofdletter gebruiken {#use-case-description}

Met deze optie wordt uitgelegd hoe u een kanaal kunt maken dat het normale afspeelkanaal *overneemt* voor een weergave of groep weergaven. De overname vindt slechts eenmaal en voor een bepaald tijdstip plaats.
Er is bijvoorbeeld een Single TakeOver-kanaal dat op vrijdag van 9.00 tot 10.00 uur wordt afgespeeld. Tijdens deze tijd, zou geen ander kanaal moeten spelen. Voor en na deze keer wordt het overnamekanaal voor eenmalig gebruik niet afgespeeld. In het volgende voorbeeld ziet u hoe u een enkel overnamekanaal maakt waarmee de inhoud gedurende 2 minuten vóór 12:00 uur op 31 december tot 12:01 uur kan worden afgespeeld.

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

1. Maak een AEM-schermproject met de naam **SingleUseTakeOver**, zoals hieronder wordt weergegeven.

   ![element](assets/single-takeover1.png)

1. Maak een **MainAdChannel** in de map **Kanalen** .

   ![element](assets/single-takeover2.png)

1. Selecteer **MainAdChannel** en klik op **Bewerken** op de actiebalk. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/single-takeover2.png)


   >[!NOTE]
   >Het **MainAdChannel** in dit voorbeeld toont een opeenvolgingskanaal aan dat inhoud onophoudelijk speelt.

   ![element](assets/single-takeover3.png)

1. Creeer een **TakeOver** kanaal dat de inhoud in **MainAdChannel** overneemt en slechts voor een specifieke dag en een tijd zal spelen.

1. Selecteer **TakeOver** en klik **uitgeven** van de actiebar. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/single-takeover4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld, wordt de volgende plaats **Lobby** en vertoning **MainLobbyDisplay** opstelling voor dit project.

   ![element](assets/single-takeover5.png)

**Kanalen toewijzen aan een weergave**

1. Selecteer de display **MainLobbyDisplay** in de map **Locations** . Klik op Kanaal **** toewijzen in de actiebalk.

   ![element](assets/single-takeover6.png)

   >[!NOTE]
   >Zie **[Kanaaltoewijzing](channel-assignment.md)**voor meer informatie over het toewijzen van een kanaal aan een weergave.

1. Vul de velden (**Kanaalpad**, **Prioriteit** en **Ondersteunde gebeurtenissen**) in het dialoogvenster **Kanaaltoewijzing** en klik op **Opslaan**. U hebt nu **MainAdChannel** aan uw vertoning toegewezen.

   ![element](assets/single-takeover7.png)

1. Selecteer de weergave **TakeOver** in de map **Locations** . Klik op Kanaal **** toewijzen op de actiebalk om het eenmalige kanaal voor het overnemen van taken toe te wijzen.

1. Als u het kanaal **TakeOver** op een gepland tijdstip aan uw weergave wilt toewijzen, vult u de volgende velden in vanuit het dialoogvenster **Kanaaltoewijzing** en klikt u op **Opslaan**:

   * **Kanaalpad**: Het pad naar het kanaal TakeOver selecteren
   * **Prioriteit**: Plaats de prioriteit van dit kanaal groter dan **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.
      >[!NOTE]
      >Prioriteit kan elke waarde zijn die hoger is dan de prioritaire waarde van het normaal afspeelkanaal.
   * **Ondersteunde gebeurtenissen**: Selecteer het **Stationele Scherm** en de **Tijdopnemer**.
   * **Schema**: Voer de tekst in voor het schema waarop u wilt dat dit kanaal de weergave uitvoert. De tekst hier staat bijvoorbeeld toe dat de inhoud 2 minuten vóór 12.00 uur op 31 december wordt afgespeeld tot 12.01 uur.
De tekst in het in dit voorbeeld vermelde **schema** staat *op 31 december na 23:58 en ook op 1 januari vóór 00.01*.

      ![element](assets/single-takeover8.png)

      Navigeer naar de weergave vanuit **SingleUseTakeOver** —> **Locaties** —> **Lobby** —> **MainLobbyDisplay** en klik op **Dashboard** op de actiebalk om de toegewezen kanalen met hun prioriteiten weer te geven, zoals hieronder wordt weergegeven.

      >[!NOTE]
      >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

      ![element](assets/single-takeover9.png)

>[!NOTE]
>Het is aan te raden om het kanaal voor het meenemen van overnames voor eenmalig gebruik te verwijderen als dit eenmaal is afgespeeld.