---
title: Activering op kanaalniveau - Afspelen van één gebeurtenis
seo-title: Channel Level Activation - Single Event Playback
description: Volg deze handleiding om de activering van het kanaalniveau te begrijpen met het afspelen van één gebeurtenis.
topic-tags: authoring
feature: Authoring Screens, Channels
role: Admin, Developer
level: Intermediate
exl-id: 51a63429-2488-45be-b8f5-cb755ca69c7f
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1792'
ht-degree: 0%

---

# Activering op kanaalniveau {#channel-level-activation-single-event-playback}

Op deze pagina vindt u een beschrijving van de activering op kanaalniveau voor de middelen die in Kanalen worden gebruikt.

De volgende onderwerpen worden behandeld in deze sectie:

* Overzicht
* Activeringsvenster
* Activering op kanaalniveau gebruiken als één gebeurtenis afspelen
* Herhaling van middelen in een kanaal afhandelen
   * DayParting
   * WeekParting
   * MonthParting
   * Combinatie van partners
* Activering op kanaalniveau gebruiken als één gebeurtenis afspelen

## Overzicht {#overview}

***Activering op kanaalniveau*** staat de kanalen toe om na een bepaald vastgestelde programma te schakelen. Het enige gebeurteniskanaal vervangt het hoofdkanaal na een ingesteld programma en speelt gedurende een bepaalde tijd af, totdat de inhoud van het hoofdkanaal opnieuw wordt afgespeeld.

In het volgende voorbeeld wordt een oplossing geboden waarbij de nadruk ligt op de volgende sleuteltermen:

* a ***hoofdsequentiekanaal*** voor de algemene reeks
* a ***één gebeurteniskanaal*** dat slechts eenmaal bij een ingestelde tijd wordt uitgevoerd
* a ***tijdschema en prioriteit*** voor de enige afspeelgebeurtenis die plaatsvindt binnen het hoofdkanaal van de reeks

## Activeringsvenster {#using-channel-level-activation}

In de volgende sectie wordt uitgelegd hoe u één gebeurtenis kunt afspelen in een kanaal voor een AEM Screens-project.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u aan de volgende voorwaarden kunt voldoen om activering op kanaalniveau te kunnen starten:

* Een AEM Screens-project maken, in dit voorbeeld **Activering op kanaalniveau**

* Een kanaal maken als **MainAdChannel** krachtens **Kanalen** map

* Een ander kanaal maken als **TargetedSinglePlay** krachtens **Kanalen** map

* Relevante elementen aan beide kanalen toevoegen

In de volgende afbeelding wordt de **Activering op kanaalniveau** project met **MainAdChannel** en **TargetedSinglePlay** kanalen in **Kanalen** map.

![screen_shot_2018-11-27at104500am](assets/screen_shot_2018-11-27at104500am.png)

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over het maken van een project en het maken van een volgnummer:
>
>* [Projecten maken en beheren](creating-a-screens-project.md)
>
>* [Een kanaal beheren](managing-channels.md)
>

### Implementatie {#implementation}

Het uitvoeren van de Activering van het Niveau van het Kanaal in een project van AEM Screens omvat drie belangrijke taken:

1. **Projecttaxonomie instellen, waaronder Kanalen, Locaties en Weergaven**
1. **Kanalen toewijzen aan weergave**
1. **Een planning en prioriteit instellen**

Voer de volgende stappen uit om de functionaliteit te implementeren:

1. **Een locatie maken**

   Ga naar uw **Locaties** in uw AEM Screens-project en maak een locatie als **Regio**.

   ![screen_shot_2018-11-27at112112am](assets/screen_shot_2018-11-27at112112am.png)

   >[!NOTE]
   >
   >Raadpleeg voor meer informatie over het maken van een locatie **[Locaties maken en beheren](managing-locations.md)**.

1. **Weergave onder locatie maken**

   1. Navigeren naar **Activering op kanaalniveau** > **Locaties** > **Regio**.
   1. Selecteren **Regio** en klik op **+ Maken** in de actiebalk.
   1. Selecteren **Weergave** van de wizard en maakt u een weergave met de naam **RegionDisplay.**

   ![screen_shot_2018-11-27at112216am](assets/screen_shot_2018-11-27at112216am.png)

1. **Kanalen toewijzen aan weergave**

   Voor **MainAdChannel:**

   1. Navigeren naar **Activering op kanaalniveau** > **Locaties** > **Regio** > **RegionDisplay** en klik op **Kanaal toewijzen** in de actiebalk.
   1. **Kanaaltoewijzing** wordt geopend.
   1. Selecteren **Referentiekanaal**.. per pad.
   1. Selecteer de **Kanaalpad** als **Activering op kanaalniveau** > ***Kanalen*** > ***MainAdChannel***.
   1. De **Kanaalrol** is gevuld als **hoofdkanaal**.
   1. Selecteer de **Prioriteit** als **1**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Oorspronkelijke belasting** en **Niet-actief scherm**.
   1. Klikken **Opslaan**.

   ![screen_shot_2018-11-27at124626pm](assets/screen_shot_2018-11-27at124626pm.png)

   >[!NOTE]
   >
   >U kunt ook kanaal toewijzen vanaf het weergavedashboard door te navigeren naar **Activering op kanaalniveau** > **Locaties** > **Regio** > **RegionDisplay** en klikken **Dashboard** in de actiebalk. Klikken **+ Kanaal toewijzen** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster.

   Kanaal toewijzen **TargetedSinglePlay** voor display**:

   1. Navigeren naar **Activering op kanaalniveau** > **Locaties** > **Regio** > **RegionDisplay** en klik op **Kanaal toewijzen** in de actiebalk.
   1. **Kanaaltoewijzing** wordt geopend.
   1. Selecteren **Referentiekanaal**.. per pad.
   1. Selecteer de **Kanaalpad** als **Activering op kanaalniveau*** > ***Kanalen*** > ***TargetedSinglePlay***.
   1. De **Kanaalrol** is gevuld als **doelgericht**.
   1. Stel de **Prioriteit** als **2**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Oorspronkelijke belasting**, **Niet-actief scherm** en **Timer**, *zoals weergegeven in de onderstaande afbeelding.
   1. Kies in **actief van** 27 november 2018, 11:59 en in **actief tot** 28 november 2018 12:05
   1. Klikken **Opslaan**.

   >[!CAUTION]
   >
   >U moet de prioriteit instellen voor **TargetedSinglePlay** kanaal hoger dan **MainAdSegment** kanaal.

   ![screen_shot_2018-11-27at31206pm](assets/screen_shot_2018-11-27at31206pm.png)

   >[!NOTE]
   >
   >Als u dezelfde dag wilt kiezen, moet u de volgende dag selecteren en de datum handmatig op dezelfde dag maar voor een later tijdstip bewerken. Hierdoor kan de gebruiker geen datum uit het verleden selecteren. Raadpleeg het onderstaande voorbeeld:

   ![new1](assets/new1.gif)

## De resultaten bekijken {#viewing-the-results}

Wanneer u de instellingen voor kanalen hebt ingesteld en de weergave voltooid is, start u de AEM Screens-speler om de inhoud weer te geven.

De speler geeft de inhoud van **MainAdChannel** en precies om 11:59 uur (zoals bepaald in het schema), **TargetedSinglePlay** het kanaal zal zijn inhoud tot 12:05 en dan tonen **MainAdChannel** wordt het afspelen van de inhoud hervat.

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over AEM Screen Player:
>[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/)
>[Werken met AEM Screens Player](working-with-screens-player.md)


## Herhaling van middelen in een kanaal afhandelen {#handling-recurrence-in-assets}

U kunt middelen in een kanaal plannen om ook met bepaalde tussenpozen op dag, week of maandbasis opnieuw te komen naar wens.

Stel dat u de inhoud van een kanaal alleen op vrijdag van 13.00 uur tot 10.00 uur wilt weergeven. U kunt de **Activering** om het gewenste herhalingsinterval voor uw element in te stellen.

### Dagverdeling {#day-parting}

1. Selecteer het kanaal en klik op **Dashboard** van de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van **Kanaaltoewijzing** kunt u een expressie of een natuurlijke tekstversie gebruiken om uw schema voor herhalingen op te geven.

   >[!NOTE]
   >
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw middel zal voor het bepaalde interval van dag en tijd tonen.

#### Voorbeeldexpressies voor dagparatie {#example-one}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | het middel in het kanaal speelt vóór 20:00 uur dagelijks |
| 14:00 | het middel in het kanaal speelt na 2:00 pm dagelijks af |
| na 12:15 en vóór 12:45 | het middel in het kanaal speelt na 12:15 elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | het middel in het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 uur af |
| Mon,Tue,Wed of MonWed | het actief vanaf maandag tot en met woensdag in het kanaal wordt afgespeeld |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het middel in het kanaal begint na 1 januari om 2:00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het middel in het kanaal begint speler na 1 januari om 2:00 uur, blijft spelen tot 2 januari om 3:00 uur, dan begint het opnieuw op 2 januari om 2:00 uur en blijft spelen tot 3:00 uur op 3 januari |

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (14:00) in plaats van *am/pm* notatie (dat wil zeggen, 14:00 uur).

### WeekParting {#week-parting}

1. Selecteer het kanaal en klik op **Dashboard** van de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van **Kanaaltoewijzing** kunt u een expressie of een natuurlijke tekstversie gebruiken om uw schema voor herhalingen op te geven.

   >[!NOTE]
   >
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw middel zal voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor WeekParting {#example-two}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| Mon,Tue,Wed of MonWed | het actief vanaf maandag tot en met woensdag in het kanaal wordt afgespeeld |
| vóór 8:00 | het middel in het kanaal speelt vóór 20:00 uur dagelijks |
| 14:00 | het middel in het kanaal speelt na 2:00 pm dagelijks af |
| na 12:15 en vóór 12:45 | het middel in het kanaal speelt na 12:15 elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | het kanaal wordt dagelijks vóór 12:15 uur afgespeeld en vervolgens ook na 12:45 uur |

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (14:00) in plaats van *am/pm* notatie (dat wil zeggen, 14:00 uur).


### MonthParting {#month-parting}

1. Selecteer het kanaal en klik op **Dashboard** van de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van **Kanaaltoewijzing** kunt u een expressie of een natuurlijke tekstversie gebruiken om uw schema voor herhalingen op te geven.

   >[!NOTE]
   >
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw middel zal voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor MonthParting {#example-three}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| van februari,mei,augustus,november | de activa spelen in februari, mei, augustus, november |

>[!NOTE]
>
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (14:00) in plaats van *am/pm* notatie (dat wil zeggen, 14:00 uur).

### Combinatie van partners {#combined-parting}

1. Selecteer het kanaal en klik op **Dashboard** van de actiebalk om het kanaaldashboard te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd van **Kanaaltoewijzing** kunt u een expressie of een natuurlijke tekstversie gebruiken om uw schema voor herhalingen op te geven.

   >[!NOTE]
   >
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw middel zal voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor de combinatie van delen {#example-four}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| na 6.00 uur en vóór 18.00 uur op de maan,Wed van Jan-Mar | de activa spelen in het kanaal tussen 6.00 uur en 6.00 uur op maandag en woensdag van januari tot en met eind maart |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het middel in het kanaal begint na 1 januari om 2:00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het middel in het kanaal begint speler na 1 januari om 2:00 uur, blijft spelen tot 2 januari om 3:00 uur, dan begint het opnieuw op 2 januari om 2:00 uur en blijft spelen tot 3:00 uur op 3 januari |

>[!NOTE]
>
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.  Bovendien kunt u ook _militaire tijd_ notatie (14:00) in plaats van *am/pm* notatie (dat wil zeggen, 14:00 uur).
