---
title: Overnamekanaal voor één gebruik
seo-title: Overnamekanaal voor één gebruik
description: Volg dit Geval van Gebruik voor het creëren van Één enkel Gebruik neemOver Kanaal.
seo-description: Volg dit Geval van Gebruik voor het creëren van Één enkel Gebruik neemOver Kanaal.
contentOwner: jsyal
feature: Ontwerpschermen
role: Administrator, Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---


# Single Use TakeOver Channel {#single-use-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Enig kanaal tot stand te brengen TakeOver dat slechts één keer voor een specifieke tijd speelt.


## Hoofdletterbeschrijving gebruiken {#use-case-description}

Met deze optie wordt uitgelegd hoe u een kanaal kunt maken dat *de normale weergavekanaal voor een weergave of groep weergaven overneemt van*. De overname vindt slechts eenmaal en voor een bepaald tijdstip plaats.
Er is bijvoorbeeld een Single TakeOver-kanaal dat op vrijdag van 9.00 tot 10.00 uur wordt afgespeeld. Tijdens deze tijd, zou geen ander kanaal moeten spelen. Voor en na deze keer wordt het overnamekanaal voor eenmalig gebruik niet afgespeeld. In het volgende voorbeeld ziet u hoe u een enkel overnamekanaal maakt waarmee de inhoud gedurende 2 minuten vóór 12:00 uur op 31 december tot 12:01 uur kan worden afgespeeld.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire ACTOR {#primary-actors}

Inhoudsauteurs

## Het project {#setting-up-the-project} instellen

Voer de onderstaande stappen uit om een project in te stellen:

**Kanalen en weergave instellen**

1. Maak een AEM Screens-project met de naam **SingleUseTakeOver**, zoals hieronder wordt weergegeven.

   ![element](assets/single-takeover1.png)

1. Maak een **MainAdChannel** in de map **Kanalen**.

   ![element](assets/single-takeover2.png)

1. Selecteer **MainAdChannel** en klik **Edit** van de actiebar. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/single-takeover2.png)


   >[!NOTE]
   >**MainAdChannel** in dit voorbeeld toont een opeenvolgingskanaal aan dat inhoud onophoudelijk speelt.

   ![element](assets/single-takeover3.png)

1. Maak een **TakeOver**-kanaal dat de inhoud in **MainAdChannel** overneemt en alleen voor een bepaalde dag en tijd afspeelt.

1. Selecteer **TakeOver** en klik **Edit** van de actiebar. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/single-takeover4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld, wordt de volgende plaats **Lobby** en vertoning **MainLobbyDisplay** opstelling voor dit project.

   ![element](assets/single-takeover5.png)

**Kanalen toewijzen aan een weergave**

1. Selecteer de weergave **MainLobbyDisplay** in de map **Locations**. Klik **Kanaal toewijzen** van de actiebar.

   ![element](assets/single-takeover6.png)

   >[!NOTE]
   >Meer informatie over het toewijzen van een kanaal aan een weergave vindt u in **[Kanaaltoewijzing](channel-assignment.md)**.

1. Vul de velden (**Kanaalpad**, **Prioriteit** en **Ondersteunde gebeurtenissen**) in het dialoogvenster **Kanaaltoewijzing** en klik op **Opslaan**. U hebt nu **MainAdChannel** aan uw vertoning toegewezen.

   ![element](assets/single-takeover7.png)

1. Selecteer de weergave **TakeOver** in de map **Locations**. Klik **Kanaal toewijzen** van de actiebar om het enige kanaal van de gebruiksovername toe te wijzen.

1. Als u het kanaal **TakeOver** op een gepland tijdstip wilt toewijzen aan uw weergave, vult u de volgende velden in het dialoogvenster **Kanaaltoewijzing** en klikt u op **Opslaan**:

   * **Kanaalpad**: Het pad naar het kanaal TakeOver selecteren
   * **Prioriteit**: Plaats de prioriteit van dit kanaal groter dan  **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.

      >[!NOTE]
      >Prioriteit kan elke waarde zijn die hoger is dan de prioritaire waarde van het normaal afspeelkanaal.
   * **Ondersteunde gebeurtenissen**: Selecteer het  **inactieve** scherm en de  **Timer**.
   * **Schema**: Voer de tekst in voor het schema waarop u wilt dat dit kanaal de weergave uitvoert. De tekst hier staat bijvoorbeeld toe dat de inhoud 2 minuten vóór 12.00 uur op 31 december wordt afgespeeld tot 12.01 uur.
De tekst in **Schedule** in dit voorbeeld is *op de 31 dag van december na 23:58 en ook op de 1 dag van januari vóór 00.01*.

      ![element](assets/single-takeover8.png)

      Navigeer naar de weergave vanuit **SingleUseTakeOver** —> **Locaties** —> **Lobby** —> **MainLobbyDisplay** en klik **Dashboard** op de actiebalk om de toegewezen kanalen met hun prioriteiten weer te geven, als hieronder weergegeven.

      >[!NOTE]
      >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

      ![element](assets/single-takeover9.png)

>[!NOTE]
>
>Het is aan te raden om het kanaal voor het meenemen van overnames voor eenmalig gebruik te verwijderen als dit eenmaal is afgespeeld.