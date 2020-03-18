---
title: Activering op kanaalniveau - Afspelen van één gebeurtenis
seo-title: Activering op kanaalniveau - Afspelen van één gebeurtenis
description: Volg deze handleiding om de activering op kanaalniveau te begrijpen met behulp van het afspelen van één gebeurtenis.
seo-description: Volg deze handleiding om de activering op kanaalniveau te begrijpen met behulp van het afspelen van één gebeurtenis.
uuid: 87230344-5f9a-42a4-a7a8-ae4203303612
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: c28fd669-f23e-4d53-bec1-a2911274567d
noindex: true
translation-type: tm+mt
source-git-commit: d6006c553b53dc7dfb52a03cfeb1a50e8e8de792

---


# Activering op kanaalniveau {#channel-level-activation-single-event-playback}

Op deze pagina vindt u een beschrijving van de activering op kanaalniveau voor de middelen die in Kanalen worden gebruikt.

De volgende onderwerpen worden behandeld in deze sectie:

* Overzicht
* Activeringsvenster
* Activering op kanaalniveau gebruiken als één gebeurtenis afspelen
* Herhaling van middelen in een kanaal afhandelen
   * Dagverdeling
   * Wekelijkse scheiding
   * Maandverdeling
   * Combinatie van partners
* Activering op kanaalniveau gebruiken als één gebeurtenis afspelen

## Overzicht {#overview}

***De Activering*** van het Niveau van het kanaal staat de kanalen toe om na een bepaald vastgestelde programma te schakelen. Het enige gebeurteniskanaal vervangt het hoofdkanaal na een ingesteld programma en speelt gedurende een bepaalde tijd af, totdat de inhoud van het hoofdkanaal opnieuw wordt afgespeeld.

In het volgende voorbeeld wordt een oplossing geboden waarbij de nadruk ligt op de volgende sleuteltermen:

* een ***hoofdvolgordekanaal*** voor de algemene reeks
* één ***gebeurteniskanaal*** dat slechts één keer bij een ingestelde tijd wordt uitgevoerd
* een ***ingesteld schema en een ingestelde prioriteit*** voor de enige afspeelgebeurtenis die plaatsvindt binnen het hoofdkanaal van de reeks

## Activeringsvenster {#using-channel-level-activation}

In de volgende sectie wordt uitgelegd hoe u één gebeurtenis afspeelt in een kanaal voor een AEM-rasterproject.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u aan de volgende voorwaarden kunt voldoen om activering op kanaalniveau te kunnen starten:

* Een AEM-schermproject maken, in dit voorbeeld activering **kanaalniveau**

* Een kanaal maken als **MainAdChannel** onder de map **Kanalen**

* Een ander kanaal maken als **gerichtSinglePlay** onder de map **Kanalen**

* Relevante elementen aan beide kanalen toevoegen

In de volgende afbeelding ziet u het **Kanaalniveauactiveringsproject** met **MainAdChannel** en de **doelkanalen SinglePlay** in de map **Kanalen** .

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over het maken van een project en het maken van een volgnummer:
>
>* [Projecten maken en beheren](creating-a-screens-project.md)
   >
   >
* [Een kanaal beheren](managing-channels.md)
>



### Implementatie {#implementation}

Het uitvoeren van de Activering van het Niveau van het Kanaal in een project van het Scherm AEM omvat drie belangrijke taken:

1. **Projecttaxonomie instellen, waaronder Kanalen, Locaties en Weergaven**
1. **Kanalen toewijzen aan weergave**
1. **Een planning en prioriteit instellen**

Voer de volgende stappen uit om de functionaliteit te implementeren:

1. **Een locatie maken**

   Navigeer naar de map **Locations** in uw AEM Screens-project en maak een locatie als **Regio**.

   ![screen_shot_2018-11-27at112112am](assets/screen_shot_2018-11-27at112112am.png)

   >[!NOTE]
   >
   >Zie Locaties **[maken en beheren voor meer informatie over het maken van een locatie](managing-locations.md)**.

1. **Weergave onder locatie maken**

   1. Navigeer naar Activering **op** Kanaalniveau > **Locaties** > **Regio**.
   1. Selecteer **Gebied** en klik op **+ Maken** in de actiebalk.
   1. Selecteer **Weergeven** in de wizard en maak een weergave met de naam **RegioDisplay.**
   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Kanalen toewijzen aan weergave**

   Voor **MainAdChannel:**

   1. Navigeer naar Activering **op** Kanaalniveau > **Locaties** > **Regio** > **Weergave** Gebied en klik op Kanaal **** toewijzen op de actiebalk.
   1. **Het dialoogvenster Kanaaltoewijzing** wordt geopend.
   1. Referentiekanaal **** selecteren.. per pad.
   1. Selecteer het **Kanaalpad** als **Kanaalniveauactivering** —> ***Kanalen*** —> ***MainAdChannel***.
   1. De **Kanaalrol** wordt gevuld als **hoofdkanaal**.
   1. Selecteer **Prioriteit** als **1**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Eerste Laden** en **Niet actief scherm**.
   1. Click **Save**.
   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >U kunt ook kanaal toewijzen vanaf het weergavedashboard door naar Activering **** kanaalniveau te navigeren —> **Locaties** —> **Regio** —> **Weergave** Gebied te klikken en op **Dashboard** op de actiebalk te klikken. Klik op **+ Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

   Wijs op dezelfde manier kanaal **TargetedSinglePlay** toe voor display**:

   1. Navigeer naar Activering **** Kanaalniveau —> **Locaties** —> **Regio** —> **Weergave** Gebied en klik op Kanaal **** toewijzen op de actiebalk.
   1. **Het dialoogvenster Kanaaltoewijzing** wordt geopend.
   1. Referentiekanaal **** selecteren.. per pad.
   1. Selecteer het **Kanaalpad** als **Kanaalniveauactivering*** —> ***Kanalen*** —> ***Gericht SinglePlay***.
   1. De rol **van het** Kanaal wordt bevolkt als **gericht singleplay**.
   1. Stel de **prioriteit** in op **2**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Eerste belasting**, **Niet-actief scherm** en **Timer**, *zoals in de onderstaande afbeelding wordt getoond.
   1. Kies de datum in **actief van** 27 november 2018 11:59 en in **actief tot** 28 november 2018 12:05.
   1. Click **Save**.
   >[!CAUTION]
   U moet de prioriteit voor **gerichtSinglePlay** kanaal hoger dan het **MainAdSegment** kanaal plaatsen.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   Als u dezelfde dag wilt kiezen, moet u de volgende dag selecteren en de datum handmatig op dezelfde dag maar voor een later tijdstip bewerken. Hierdoor kan de gebruiker geen datum uit het verleden selecteren. Raadpleeg het onderstaande voorbeeld:

   ![new1](assets/new1.gif)

## De resultaten bekijken {#viewing-the-results}

Nadat u de instellingen voor kanalen hebt ingesteld en de weergave is voltooid, start u de AEM Screens-speler om de inhoud weer te geven.

De speler geeft de inhoud van **MainAdChannel** weer en precies om 23:59 uur (zoals ingesteld in het schema), geeft het **GerichtSinglePlay** -kanaal de inhoud weer tot 12:05 uur &#39;s avonds en dan wordt het afspelen van de inhoud van het **MainAdChannel** hervat.

>[!NOTE]
Raadpleeg de volgende bronnen voor meer informatie over AEM Screen Player:
* [AEM-schermPlayer downloadt](https://download.macromedia.com/screens/)
* [Werken met AEM Screens Player](working-with-screens-player.md)



## Herhaling van middelen in een kanaal afhandelen{#handling-recurrence-in-assets}

U kunt middelen in een kanaal plannen om ook met bepaalde tussenpozen op dag, week of maandbasis opnieuw te komen naar wens.

Stel dat u de inhoud van een kanaal alleen op vrijdag van 13.00 uur tot 10.00 uur wilt weergeven. U kunt het tabblad **Activering** gebruiken om het gewenste herhalingsinterval voor uw element in te stellen.

### Dagverdeling {#day-parting}

1. Selecteer het kanaal en klik op het **dashboard** op de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van de de dialoogdoos van de Toewijzing van het **Kanaal** , kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeeldexpressies voor dagparatie {#example-one}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| vóór 8:00 | het middel in het kanaal speelt vóór 20:00 uur dagelijks |
| 14:00 | het middel in het kanaal speelt na 2:00 pm dagelijks af |
| na 12:15 en vóór 12:45 | het middel in het kanaal speelt na 12:15 elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | het middel in het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 uur af |
| Mon,Tue,Wed of MonWed | het actief vanaf maandag tot en met woensdag in het kanaal wordt afgespeeld |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het middel in het kanaal begint na 1 januari om 2:00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het middel in het kanaal begint speler na 1 januari om 2:00 uur, blijft spelen tot 2 januari om 3:00 uur, dan begint het opnieuw op 2 januari om 2:00 uur en blijft spelen tot 3:00 uur op 3 januari |

>[!NOTE]
U kunt ook _militaire tijd_ notatie (dat wil zeggen 14:00) gebruiken in plaats van *am/pm* notatie (dat wil zeggen, 2:00 pm).

### Wekelijkse scheiding {#week-parting}

1. Selecteer het kanaal en klik op het **dashboard** op de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van de de dialoogdoos van de Toewijzing van het **Kanaal** , kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeeldexpressies voor het parseren van weken {#example-two}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| Mon,Tue,Wed of MonWed | het actief vanaf maandag tot en met woensdag in het kanaal wordt afgespeeld |
| vóór 8:00 | het middel in het kanaal speelt vóór 20:00 uur dagelijks |
| 14:00 | het middel in het kanaal speelt na 2:00 pm dagelijks af |
| na 12:15 en vóór 12:45 | het middel in het kanaal speelt na 12:15 elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | het kanaal wordt dagelijks vóór 12:15 uur afgespeeld en vervolgens ook na 12:45 uur |

>[!NOTE]
U kunt ook _militaire tijd_ notatie (dat wil zeggen 14:00) gebruiken in plaats van *am/pm* notatie (dat wil zeggen, 2:00 pm).


### Maandverdeling {#month-parting}

1. Selecteer het kanaal en klik op het **dashboard** op de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van de de dialoogdoos van de Toewijzing van het **Kanaal** , kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor maandspatiëring {#example-three}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| van februari,mei,augustus,november | de activa spelen in februari, mei, augustus, november |

>[!NOTE]
Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.

>[!NOTE]
U kunt ook _militaire tijd_ notatie (dat wil zeggen 14:00) gebruiken in plaats van *am/pm* notatie (dat wil zeggen, 2:00 pm).

### Combinatie van partners {#combined-parting}

1. Selecteer het kanaal en klik op het **dashboard** op de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van de de dialoogdoos van de Toewijzing van het **Kanaal** , kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor de combinatie van delen {#example-four}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| na 6.00 uur en vóór 18.00 uur op de maan,Wed van Jan-Mar | de activa spelen in het kanaal tussen 6.00 uur en 6.00 uur op maandag en woensdag van januari tot en met eind maart |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het middel in het kanaal begint na 1 januari om 2:00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het middel in het kanaal begint speler na 1 januari om 2:00 uur, blijft spelen tot 2 januari om 3:00 uur, dan begint het opnieuw op 2 januari om 2:00 uur en blijft spelen tot 3:00 uur op 3 januari |

>[!NOTE]
Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.  Bovendien kunt u ook _militaire tijdnotatie_ gebruiken (dat wil zeggen 14:00) in plaats van *am/pm* -notatie (dat wil zeggen 2:00 pm).

