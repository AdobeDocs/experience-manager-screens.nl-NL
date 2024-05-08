---
title: Single-Use TakeOver Channel
description: Volg dit gebruiksgeval voor het creëren van een enig-Gebruik NeemOver Kanaal.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3317f07a-784f-4c4a-93ea-c84f4e42e9f2
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Overnamekanaal voor één gebruik {#single-use-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Enig kanaal tot stand te brengen TakeOver dat één keer voor een specifieke tijd speelt.

## Omschrijving hoofdletter gebruiken {#use-case-description}

In dit geval wordt uitgelegd hoe u een kanaal maakt dat *overname* in het normale afspeelkanaal voor een weergave of groep weergaven. De overname vindt slechts eenmaal en voor een bepaalde tijd plaats.

Er is bijvoorbeeld een Single TakeOver-kanaal dat vanaf vrijdag 9.00 uur tot 10.00 uur &#39;s ochtends wordt afgespeeld. Tijdens deze tijd, zou geen ander kanaal moeten spelen. Voor en na deze keer wordt het overnamekanaal voor eenmalig gebruik niet afgespeeld. In het volgende voorbeeld ziet u hoe u één overnamekanaal maakt waarmee de inhoud gedurende 2 minuten vóór 12:00 uur &#39;s middags op 31 december kan worden afgespeeld tot 12:01 uur &#39;s middags.

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

1. Een AEM Screens-project maken met de naam **SingleUseTakeOver**, zoals hieronder weergegeven.

   ![element](assets/single-takeover1.png)

1. Een **MainAdChannel** in de **Kanalen** map.

   ![element](assets/single-takeover2.png)

1. Klik op de knop **MainAdChannel** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/single-takeover2.png)


   >[!NOTE]
   >De **MainAdChannel** in dit voorbeeld wordt een volgnummer weergegeven waarmee inhoud continu wordt afgespeeld.

   ![element](assets/single-takeover3.png)

1. Een **Overname** kanaal dat de inhoud in **MainAdChannel** en wordt alleen gedurende een bepaalde dag en tijd afgespeeld.

1. Klik op de knop **Overname** en klik op **Bewerken** in de actiebalk. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/single-takeover4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld het volgende **Lobby** locatie en  **MainLobbyDisplay** de vertoning wordt opstelling voor dit project.

   ![element](assets/single-takeover5.png)

**Kanalen toewijzen aan een weergave**

1. Klik op de weergave **MainLobbyDisplay** van de **Locaties** map. Klikken **Kanaal toewijzen** in de actiebalk.

   ![element](assets/single-takeover6.png)

   >[!NOTE]
   >Ga voor meer informatie over het toewijzen van een kanaal aan een weergave naar **[Kanaaltoewijzing](channel-assignment.md)**.

1. Vul de velden (**Kanaalpad**, **Prioriteit**, en **Ondersteunde gebeurtenissen**) van de **Kanaaltoewijzing** en klik op **Opslaan**. U hebt nu de opdracht **MainAdChannel** op uw scherm.

   ![element](assets/single-takeover7.png)

1. Klik op de weergave **Overname** van de **Locaties** map. Klikken **Kanaal toewijzen** op de actiebalk, zodat u het kanaal voor één keer overnemen kunt toewijzen.

1. Wijs het **Overname** naar de weergave op een gepland moment en vul de volgende velden in via het menu **Kanaaltoewijzing** en klik op **Opslaan**:

   * **Kanaalpad**: Klik op het pad naar het kanaal TakeOver
   * **Prioriteit**: Stel de prioriteit van dit kanaal groter in dan de **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.

     >[!NOTE]
     >Prioriteit kan elke waarde zijn die hoger is dan de prioritaire waarde van het normale afspeelkanaal.
   * **Ondersteunde gebeurtenissen**: Klik op de knop **Niet-actief scherm** en **Timer**.
   * **Schema**: Ga de tekst voor het programma in dat u dit kanaal wilt in werking stellen de vertoning. De tekst hier staat bijvoorbeeld toe dat de inhoud 2 minuten vóór 12.00 uur &#39;s middags wordt afgespeeld op 31 dec tot 12.01 uur &#39;s middags. De tekst in de **Schema** in dit voorbeeld wordt vermeld *op de 31 dag van december na 23.58 uur en ook op de 1 dag van januari vóór 00.01*.

     ![element](assets/single-takeover8.png)

     Navigeren naar de weergave vanuit **SingleUseTakeOver** > **Locaties** > **Lobby** > **MainLobbyDisplay** en klik op **Dashboard** in de actiebalk, zodat u de toegewezen kanalen met hun prioriteiten kunt weergeven, zoals hieronder wordt weergegeven.

     >[!NOTE]
     >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

     ![element](assets/single-takeover9.png)

>[!NOTE]
>
>Het is aan te raden om het kanaal voor het meenemen van overnames voor eenmalig gebruik te verwijderen als dit eenmaal is afgespeeld.
