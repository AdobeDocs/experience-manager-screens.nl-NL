---
title: Perpetual TakeOver Channel
description: Leer hoe u een Perpetual TakeOver-kanaal maakt.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 0%

---

# Perpetual TakeOver Channel {#perpetual-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Perpetual te creëren TakeOver kanaal dat voor een specifieke tijddag en een tijd onophoudelijk speelt.

## Omschrijving hoofdletter gebruiken {#use-case-description}

Dit gebruiksgeval verklaart hoe te om een kanaal tot stand te brengen dat ** van het normale speelkanaal voor een vertoning of een groep vertoningen overneemt. De overname duurt een bepaalde dag en een bepaalde tijd onafgebroken.
Bijvoorbeeld, is er een Perpetual TakeOver kanaal dat elke Vrijdag van 9:00 a.m. door 10:00 a.m. speelt. Tijdens deze tijd, zou geen ander kanaal moeten spelen. In het volgende voorbeeld wordt de creatie getoond van een perpetual takeover channel waarmee de inhoud elke woensdag gedurende twee uur van 2:00 tot 4:00 uur kan worden afgespeeld.

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

1. Creeer een Project van AEM Screens dat als **PerpetualTakeOver** wordt genoemd, zoals hieronder getoond.

   ![ activa ](assets/p_usecase1.png)

1. Creeer a **MainAdChannel** in de **omslag van Kanalen**.

   ![ activa ](assets/p_usecase2.png)

1. Klik **MainAdChannel** en klik **uitgeven** van de actiebar. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![ activa ](assets/p_usecase3.png)


   >[!NOTE]
   >**MainAdChannel** in dit voorbeeld toont een opeenvolgingskanaal aan dat inhoud onophoudelijk speelt.

1. Creeer a **TakeOver** kanaal dat de inhoud in **MainAdChannel** overneemt en elke Woensdag van 2:00 P.M. door 4:00 P.M. speelt.

1. Klik **TakeOver** en klik **uitgeven** van de actiebar. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![ activa ](assets/p_usecase4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld, worden de volgende plaats **MainLobby** en vertoning **MainLobbyDisplay** opstelling voor dit project.

   ![ activa ](assets/p_usecase5.png)

**Toewijzend Kanalen aan een Vertoning**

1. Klik de vertoning **MainLobbyDisplay** van de **omslag van Plaatsen**. Klik **toewijzen Kanaal** van de actiebar zodat kunt u de **Toekenning van het Kanaal** dialoogdoos openen.

   >[!NOTE]
   >Leren hoe te om een kanaal aan een vertoning toe te wijzen, zie **[Toewijzing van het Kanaal](channel-assignment.md)**.

1. Vul de gebieden (**Weg van het Kanaal**, **Prioriteit**, en **Gesteunde Gebeurtenissen**) van het **7} de dialoogvakje van de Toewijzing van het Kanaal en klik** sparen **om** MainAdChannel **aan uw vertoning toe te wijzen.**

   * **Weg van het Kanaal**: Klik de weg aan het **MainAdChannel** kanaal
   * **Prioriteit**: Plaats de prioriteit van dit kanaal als 1.
   * **Gesteunde Gebeurtenissen**: Klik de **Aanvankelijke Lading** en **het Niet-actieve Scherm**.

   ![ activa ](assets/p_usecase6.png)

1. Klik de vertoning **TakeOver** van de **omslag van Plaatsen**. Klik **toewijzen Kanaal** van de actiebar zodat kunt u het overnamekanaal toewijzen.

1. Het toewijzen van het **** kanaal TakeOver aan uw vertoning in een geplande tijd. Dan, die de volgende gebieden van de **1} de dialoogdoos van de Toewijzing van het Kanaal bevolken {en** selecteren sparen **:**

   * **Weg van het Kanaal**: Klik de weg aan het **** kanaal TakeOver
   * **Prioriteit**: Plaats de prioriteit van dit kanaal groter dan **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.
   * **Ondersteunde Gebeurtenissen**: Klik het **Onactieve Scherm** en **Tijdopnemer**.
   * **Programma**: Ga de tekst voor het programma in dat u dit kanaal op de vertoning wilt in werking stellen. De tekst in het **Programma** die in dit voorbeeld wordt vermeld is *op Woensdag na 14:00 en vóór 16:00*.

     >[!NOTE]
     >Meer over de uitdrukkingen leren u aan het **Programma** kunt toevoegen, zie de [ sectie van de Uitdrukkingen van het Voorbeeld ](#example-expressions) hieronder.
   * **actief van**: De datum en de tijd van het Begin.
   * **actief tot**: Einddatum en tijd.

     Bijvoorbeeld, staat de tekst in **Programma** en **actief van** en **tot** datum en tijd hier de inhoud toe om elke Woensdag van 2:00 P.M. tot 4:00 P.M. te spelen.


     ![ activa ](assets/p_usecase7.png)

     Navigeer aan de vertoning van **TakeOver** > **Plaats** > **MainLobby** > **MainLobbyDisplay**, dan, klik **Dashboard** van de actiebar zodat kunt u de toegewezen kanalen met hun prioriteiten bekijken, zoals hieronder getoond.

     >[!NOTE]
     >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

     ![ activa ](assets/p_usecase8.png)
Nu, neemt **** kanaal TakeOver **MainAdChannel** bij 2:00 P.M. voor twee uren tot 4:00 P.M. elke Woensdag over en speelt zijn inhoud van Januari 09, 2020 tot 31 Januari, 2020.

## Voorbeeldexpressies {#example-expressions}

De volgende tabel geeft een overzicht van een aantal voorbeeldexpressies die u aan het schema kunt toevoegen terwijl u een kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | het kanaal speelt vóór 08:00 om 00 elke dag |
| na 2:00 | het kanaal speelt na 2:00 p.m. elke dag |
| na 12:15 en vóór 12:45 | het kanaal speelt elke dag om 12:15 uur gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | Het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 |
| op de eerste dag van januari na 14.00 uur, ook op de tweede dag van januari en ook op de derde dag van januari vóór 3.00 uur &#39;s middags. | Het kanaal begint na 2:00 uur &#39;s middags op 1 januari 2011, wordt de hele dag afgespeeld op 2 januari 2002, helemaal tot 17:00 uur &#39;s middags op 3 januari 2003 |
| op de 1-2 dagen van januari na 2:00 uur, ook op de 2-3 dagen van januari vóór 3:00 uur. | Het kanaal start speler na 2:00 uur &#39;s middags op 1 januari, gaat verder met afspelen tot 17:00 uur &#39;s middags op 2 januari 2002. Het begint vervolgens opnieuw om 2:00 uur &#39;s middags en gaat verder met afspelen tot 17:00 uur &#39;s avonds op 3 januari 2003. |

>[!NOTE]
>
>U kunt _militaire tijd_ aantekening (14:00) in plaats van *ook gebruiken A.M./P.M.* (2:00 P.M.).
