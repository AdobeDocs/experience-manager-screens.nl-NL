---
title: Single-Use TakeOver Channel
description: Volg deze handige optie voor het maken van een eenmalig overnamekanaal.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3317f07a-784f-4c4a-93ea-c84f4e42e9f2
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Overnamekanaal voor één gebruik {#single-use-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Enig kanaal tot stand te brengen TakeOver dat één keer voor een specifieke tijd speelt.

## Omschrijving hoofdletter gebruiken {#use-case-description}

Dit gebruiksgeval verklaart hoe te om een kanaal tot stand te brengen dat ** van het normale speelkanaal voor een vertoning of een groep vertoningen overneemt. De overname vindt slechts eenmaal en voor een bepaalde tijd plaats.

Er is bijvoorbeeld een Single TakeOver-kanaal dat vanaf vrijdag 9.00 uur tot 10.00 uur &#39;s ochtends wordt afgespeeld. Tijdens deze tijd, zou geen ander kanaal moeten spelen. Voor en na deze keer wordt het overnamekanaal voor eenmalig gebruik niet afgespeeld. In het volgende voorbeeld ziet u hoe u één overnamekanaal maakt waarmee de inhoud gedurende 2 minuten vóór 12:00 uur &#39;s middags op 31 december kan worden afgespeeld tot 12:01 uur &#39;s middags.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[creeer en beheer Kanalen](managing-channels.md)**
* **[creeer en beheer Plaatsen](managing-locations.md)**
* **[creeer en beheer Programma&#39;s](managing-schedules.md)**
* **[Registratie van het Apparaat](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Het project instellen {#setting-up-the-project}

Voer de onderstaande stappen uit om een project in te stellen:

**Vestiging de Kanalen en Vertoning**

1. Creeer een Project van AEM Screens dat als **wordt genoemd SingleUseTakeOver**, zoals hieronder getoond.

   ![&#x200B; activa &#x200B;](assets/single-takeover1.png)

1. Creeer a **MainAdChannel** in de **omslag van Kanalen**.

   ![&#x200B; activa &#x200B;](assets/single-takeover2.png)

1. Klik **MainAdChannel** en klik **uitgeven** van de actiebar. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![&#x200B; activa &#x200B;](assets/single-takeover2.png)


   >[!NOTE]
   >**MainAdChannel** in dit voorbeeld toont een opeenvolgingskanaal aan dat inhoud onophoudelijk speelt.

   ![&#x200B; activa &#x200B;](assets/single-takeover3.png)

1. Creeer a **TakeOver** kanaal dat de inhoud in **MainAdChannel** overneemt en slechts voor een specifieke dag en een tijd speelt.

1. Klik **TakeOver** en klik **uitgeven** van de actiebar. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![&#x200B; activa &#x200B;](assets/single-takeover4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld, worden de volgende **plaats 0&rbrace; Lobby {en** 3} vertoning MainLobbyDisplay opstelling voor dit project.**&#x200B;**

   ![&#x200B; activa &#x200B;](assets/single-takeover5.png)

**Toewijzend Kanalen aan een Vertoning**

1. Klik de vertoning **MainLobbyDisplay** van de **omslag van Plaatsen**. Klik **toewijzen Kanaal** van de actiebar.

   ![&#x200B; activa &#x200B;](assets/single-takeover6.png)

   >[!NOTE]
   >Leren hoe te om een kanaal aan een vertoning toe te wijzen, zie **[Toewijzing van het Kanaal](channel-assignment.md)**.

1. Vul de gebieden (**Weg van het Kanaal**, **Prioriteit**, en **Ondersteunde Gebeurtenissen**) van het **7&rbrace; de dialoogvakje van de Toewijzing van het Kanaal en klik** sparen **.** U hebt nu **MainAdChannel** aan uw vertoning toegewezen.

   ![&#x200B; activa &#x200B;](assets/single-takeover7.png)

1. Klik de vertoning **TakeOver** van de **omslag van Plaatsen**. Klik **toewijzen Kanaal** van de actiebar zodat kunt u het enig-gebruiks overnamekanaal toewijzen.

1. Wijs het **kanaal 0&rbrace; TakeOver &lbrace;aan uw vertoning in een geplande tijd toe en bevolk de volgende gebieden van het** de dialoogvakje van de Toewijzing van het Kanaal **en klik** sparen **:**

   * **Weg van het Kanaal**: Klik de weg aan het kanaal TakeOver
   * **Prioriteit**: Plaats de prioriteit van dit kanaal groter dan **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.

     >[!NOTE]
     >Prioriteit kan elke waarde zijn die hoger is dan de prioritaire waarde van het normale afspeelkanaal.
   * **Ondersteunde Gebeurtenissen**: Klik het **Onactieve Scherm** en **Tijdopnemer**.
   * **Programma**: Ga de tekst voor het programma in dat u dit kanaal op de vertoning wilt in werking stellen. De tekst hier staat bijvoorbeeld toe dat de inhoud 2 minuten vóór 12.00 uur &#39;s middags wordt afgespeeld op 31 dec tot 12.01 uur &#39;s middags.
De tekst in het **Programma** die in dit voorbeeld wordt vermeld is *op de 31 dag van December na 23:58 en ook op de 1 dag van Januari vóór 00.01*.

     ![&#x200B; activa &#x200B;](assets/single-takeover8.png)

     Navigeer aan de vertoning van **SingleUseTakeOver** > **Plaatsen** > **Lobby** > **MainLobbyDisplay**. Klik **Dashboard** van de actiebar zodat kunt u de toegewezen kanalen met hun prioriteiten bekijken, zoals hieronder getoond.

     >[!NOTE]
     >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

     ![&#x200B; activa &#x200B;](assets/single-takeover9.png)

>[!NOTE]
>
>Het is aan te raden om het kanaal voor het meenemen van overnames voor eenmalig gebruik te verwijderen als dit eenmaal is afgespeeld.
