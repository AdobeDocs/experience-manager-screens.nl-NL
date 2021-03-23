---
title: Perpetual TakeOver Channel
seo-title: Perpetual TakeOver Channel
description: Volg dit Geval van Gebruik voor het creëren van een PerpetualTakeOver Kanaal.
seo-description: Volg dit Geval van Gebruik bij vestiging een project dat tot een PerpetualTakeOver kanaal leidt dat onophoudelijk voor een specifieke tijddag en een tijd speelt.
contentOwner: jsyal
feature: Ontwerpschermen
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 0%

---


# Perpetual Take Over Channel {#perpetual-takeover-channel}

De volgende pagina toont een gebruiksgeval dat op vestiging een project op benadrukt hoe te om een Perpetual te creëren TakeOver kanaal dat voor een specifieke tijddag en een tijd onophoudelijk speelt.

## Hoofdletterbeschrijving gebruiken {#use-case-description}

Met deze optie wordt uitgelegd hoe u een kanaal kunt maken dat *de normale weergavekanaal voor een weergave of groep weergaven overneemt van*. De overname zal een bepaalde dag en tijd onafgebroken plaatsvinden.
Bijvoorbeeld, is er een Perpetual TakeOver kanaal dat elke Vrijdag van 9AM aan 10AM speelt. Tijdens deze tijd, zou geen ander kanaal moeten spelen. In het volgende voorbeeld ziet u hoe u een perpetual takeover channel maakt waarmee de inhoud elke woensdag 2 uur vanaf 14.00 tot 16.00 uur kan worden afgespeeld.

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

1. Maak een AEM Screens-project met de naam **PerpetualTakeOver**, zoals hieronder wordt weergegeven.

   ![element](assets/p_usecase1.png)

1. Maak een **MainAdChannel** in de map **Kanalen**.

   ![element](assets/p_usecase2.png)

1. Selecteer **MainAdChannel** en klik **Edit** van de actiebar. Sleep enkele elementen (afbeeldingen, video&#39;s, ingesloten reeksen) naar het kanaal.

   ![element](assets/p_usecase3.png)


   >[!NOTE]
   >**MainAdChannel** in dit voorbeeld toont een opeenvolgingskanaal aan dat inhoud onophoudelijk speelt.

1. Maak een **TakeOver**-kanaal dat de inhoud in **MainAdChannel** overneemt en elke woensdag van 2:00 tot 16:00 uur afspeelt.

1. Selecteer **TakeOver** en klik **Edit** van de actiebar. Sleep enkele elementen naar uw kanaal. In het volgende voorbeeld ziet u hoe een afbeelding met één zone wordt toegevoegd aan dit kanaal.

   ![element](assets/p_usecase4.png)

1. Stel een locatie en weergave voor uw kanalen in. Bijvoorbeeld, wordt de volgende plaats **MainLobby** en vertoning **MainLobbyDisplay** opstelling voor dit project.

   ![element](assets/p_usecase5.png)

**Kanalen toewijzen aan een weergave**

1. Selecteer de weergave **MainLobbyDisplay** in de map **Locations**. Klik **Kanaal toewijzen** van de actiebalk om **Kanaaltoewijzing** dialoogvenster te openen.

   >[!NOTE]
   >Meer informatie over het toewijzen van een kanaal aan een weergave vindt u in **[Kanaaltoewijzing](channel-assignment.md)**.

1. Vul de velden (**Kanaalpad**, **Prioriteit** en **Ondersteunde gebeurtenissen**) in het dialoogvenster **Kanaaltoewijzing** en klik op **Opslaan** om het **MainAdChannel** toe te wijzen> op uw scherm.

   * **Kanaalpad**: Selecteer het pad naar het  **** MainAdChannel-kanaal
   * **Prioriteit**: Stel de prioriteit van dit kanaal in op 1.
   * **Ondersteunde gebeurtenissen**: Selecteer de  **Eerste** lading en  **Niet-actief scherm**.

   ![element](assets/p_usecase6.png)

1. Selecteer de weergave **TakeOver** in de map **Locations**. Klik **Kanaal toewijzen** van de actiebar om het overnamekanaal toe te wijzen.

1. Als u het kanaal **TakeOver** op een gepland tijdstip wilt toewijzen aan uw weergave, vult u de volgende velden in het dialoogvenster **Kanaaltoewijzing** en klikt u op **Opslaan**:

   * **Kanaalpad**: Het pad naar het  **** TakeOverchannel selecteren
   * **Prioriteit**: Plaats de prioriteit van dit kanaal groter dan  **MainAdChannel**. De prioriteit die in dit voorbeeld wordt ingesteld, is bijvoorbeeld 8.
   * **Ondersteunde gebeurtenissen**: Selecteer het  **inactieve** scherm en de  **Timer**.
   * **Schema**: Voer de tekst in voor het schema waarop u wilt dat dit kanaal de weergave uitvoert. De tekst in **Schedule** in dit voorbeeld is *op woensdag na 14:00 en vóór 16:00*.

      >[!NOTE]
      >Als u meer wilt weten over de expressies die u kunt toevoegen aan de sectie **Schedule**, raadpleegt u de sectie [Voorbeeldexpressies](#example-expressions) hieronder.
   * **actief van**: Begindatum en -tijd.
   * **actief tot**: Einddatum en -tijd.

      De tekst in **Schedule** en **actief van** en **actief tot** datum en tijd hier staat de inhoud toe om elke woensdag van 2:00 pm tot 16:00 pm te spelen.


      ![element](assets/p_usecase7.png)

      Navigeer naar de weergave vanuit **TakeOver** —> **Locaties** —> **MainLobby** —> **MainLobbyDisplay** en klik **Dashboard** op de actiebalk om de toegewezen kanalen met hun prioriteiten weer te geven, zoals hieronder wordt getoond.

      >[!NOTE]
      >Het is verplicht de prioriteit van het overnamekanaal als hoogste vast te stellen.

      ![](assets/p_usecase8.png)
assetNow, zal  **** TakeOverchannel  **** MainAdChannelat 2:00 pm voor twee uur tot 16:00 elke woensdag overnemen en zal zijn inhoud van Jan 09&#39; 2020 tot Jan 31&#39; 2020 spelen.

## Voorbeeldexpressies {#example-expressions}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| vóór 8:00 | het kanaal speelt vóór 8:00 uur dagelijks |
| 14:00 | het kanaal wordt dagelijks om 14.00 uur afgespeeld |
| na 12:15 en vóór 12:45 | het kanaal wordt 30 minuten lang elke dag om 12:15 uur afgespeeld |
| vóór 12:15 ook na 12:45 | het kanaal wordt dagelijks vóór 12:15 uur afgespeeld en vervolgens ook na 12:45 uur |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het kanaal begint na 1 januari om 2:00 uur af te spelen, gaat de hele dag door met afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het kanaal start speler na 1 januari om 2:00 uur, gaat verder met spelen tot 2 januari om 3:00 uur, dan start het opnieuw op 2 januari om 2:00 uur en gaat verder met spelen tot 3:00 uur op 3 januari |

>[!NOTE]
>
>U kunt _militaire tijd_ notatie (namelijk 14:00) in plaats van *am/pm* notatie (namelijk 2:00 pm) ook gebruiken.
