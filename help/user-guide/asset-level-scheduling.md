---
title: Activering van middelenniveau
seo-title: Activering van middelenniveau
description: Volg deze pagina om te leren hoe u een specifiek middel in een kanaal activeert voor een gepland tijdkader in de lokale tijdzone van de speler.
seo-description: Volg deze pagina om te leren hoe u een specifiek middel in een kanaal activeert voor een gepland tijdkader in de lokale tijdzone van de speler.
translation-type: tm+mt
source-git-commit: af244dc18aa4eb526978ab9ced60e8b818f6201e

---


# Activering van middelenniveau {#asset-level-scheduling}

Deze pagina beschrijft activering op middelenniveau voor de middelen die in Kanalen worden gebruikt.

De volgende onderwerpen worden behandeld in deze sectie:

* Overzicht
* Activeringsvenster
* Afspelen van één gebeurtenis
* Herhaling van activa afhandelen
   * Dagverdeling
   * Wekelijkse scheiding
   * Maandverdeling
   * Combinatie van partners
* Activering van meerdere middelen

>[!CAUTION]
>
>Deze AEM-schermfunctionaliteit is alleen beschikbaar als u AEM 6.3 Feature Pack 3 of AEM 6.4 Screens Feature Pack 1 hebt geïnstalleerd.
>
>Neem contact op met de ondersteuning van Adobe om toegang te krijgen tot dit onderdeel. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

## Overzicht {#overview}

***Activering*** op middelenniveau, waarmee u een specifiek middel in een kanaal kunt activeren voor een gepland tijdframe in de lokale tijdzone van de speler. Dit is beschikbaar voor afbeeldingen, video&#39;s, overgangen, pagina&#39;s en ingesloten kanalen (dynamisch of statisch).

*U wilt bijvoorbeeld* dat een speciale promotie alleen gedurende een gelukkig uur (2.00 tot 17.00 uur) op maandag en woensdag wordt weergegeven.

Met deze functie kunt u niet alleen de begin- en einddatum en -tijd opgeven, maar ook een herhalingspatroon.

## Activeringsvenster {#single-event-playback}

Activering op middelenniveau wordt uitgevoerd door het tabblad **Activering** te configureren terwijl eigenschappen van een element worden benaderd.

Voer de onderstaande stappen uit om de middelenplanning uit te voeren:

1. Selecteer een kanaal en klik op **Bewerken** op de actiebalk om inhoud aan uw kanaal toe te voegen of te bewerken.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >Meer informatie over hoe u
   >
   >* Creeer een project, zie het [Creëren van een nieuw Project](creating-a-screens-project.md).
   >* Zie Kanalen [beheren voor informatie over het maken en toevoegen van inhoud aan een kanaal](managing-channels.md).


1. Klik op **Bewerken** om de kanaaleditor te openen en selecteer een element waarop u de planning wilt toepassen.

   ![image](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Selecteer het element en klik linksboven op **Configureren** (moersleutelpictogram) om de eigenschappen van de afbeelding te openen.

   Klik op het tabblad **Activering** .

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

1. U kunt de datum vanaf de datumkiezer opgeven met **Actief van** en **Actief tot** velden.

   Als u **Actief van** en **Actief tot** datum en tijd selecteert, zal de activa en lijn slechts tussen die begindatum/tijd en einddatum/tijd respectievelijk tonen.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

## Herhaling van activa afhandelen {#handling-recurrence-in-assets}

U kunt ook bepalen dat de middelen elke dag, week of maand opnieuw worden uitgevoerd, afhankelijk van uw vereisten.

Stel dat u een afbeelding alleen op vrijdag van 13.00 tot 19.00 uur wilt weergeven. U kunt het tabblad **Activering** gebruiken om het gewenste herhalingsinterval voor uw element in te stellen.

### Dagverdeling {#day-parting}

1. Selecteer het element en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   > [!NOTE]
   > U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeeldexpressies voor dagparatie {#example-one}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| vóór 8:00 | het middel in het kanaal speelt vóór 20:00 uur dagelijks |
| 14:00 | het middel in het kanaal speelt na 2:00 pm dagelijks af |
| na 12:15 en vóór 12:45 | het middel in het kanaal speelt na 12:15 elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | het middel in het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 uur af |


>[!NOTE]
>U kunt ook _militaire tijd_ notatie (dat wil zeggen 14:00) gebruiken in plaats van *am/pm* notatie (dat wil zeggen, 2:00 pm).

### Wekelijkse scheiding {#week-parting}

1. Selecteer het element en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   > [!NOTE]
   > U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeeldexpressies voor het parseren van weken {#example-two}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| Ma,Wed,Fri | de activa spelen in het kanaal vanaf maandag, woensdag en vrijdag |
| Mon-Thu | de activa spelen in het kanaal van op Maandagen aan Donderdag |

>[!NOTE]
>U kunt ook _volledige_ notatie gebruiken (maandag, woensdag, vrijdag) in plaats van _korte notatie_ (dat wil zeggen: Mon,Wed,Fri).


### Maandverdeling {#month-parting}

1. Selecteer het element en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   > [!NOTE]
   > U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor maandspatiëring {#example-three}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| van februari,mei,augustus,november | de activa spelen in februari, mei, augustus en november op het kanaal |
| van februari-juli | het actief vanaf februari tot eind juli op het kanaal wordt afgespeeld |

> [!NOTE]
> Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.

### Combinatie van partners {#combined-parting}

1. Selecteer het element en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   > [!NOTE]
   > U kunt **Actief van** en **Actief tot** gebieden overslaan of omvatten en de uitdrukking toevoegen aan het gebied van Programma&#39;s, volgens uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa zullen voor het bepaalde interval van dag en tijd tonen.

#### Voorbeelden van expressies voor de combinatie van delen {#example-four}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Expressie** | **Interpretatie** |
|---|---|
| na 6.00 uur en vóór 18.00 uur op de maan,Wed van Jan-Mar | de activa spelen in het kanaal tussen 6.00 uur en 6.00 uur op maandag en woensdag van januari tot en met eind maart |
| op de eerste dag van januari na 23.00 uur ook op de tweede dag van januari, ook op de derde dag van januari vóór 15.00 uur | het middel in het kanaal begint na 1 januari om 2:00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3:00 uur op 3 januari |
| op de 1-2 dag van januari na 2:00 uur, ook op de 2-3 dag van januari vóór 15.00 uur | Het middel in het kanaal begint speler na 1 januari om 2:00 uur, blijft spelen tot 2 januari om 3:00 uur, dan begint het opnieuw op 2 januari om 2:00 uur en blijft spelen tot 3:00 uur op 3 januari |

> [!NOTE]
> Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en Jan/januari.  Bovendien kunt u ook _militaire tijdnotatie_ gebruiken (dat wil zeggen 14:00) in plaats van *am/pm* -notatie (dat wil zeggen 2:00 pm).


## Activering van meerdere middelen {#multi-asset-scheduling}

>[!CAUTION]
>
>De functie **Multi-Asset Activation** is alleen beschikbaar als u AEM 6.3 Feature Pack 5 of AEM 6.4 Feature Pack 3 hebt geïnstalleerd.

***Door activering*** van meerdere elementen kan de gebruiker meerdere elementen selecteren en een afspeelschema toepassen op alle geselecteerde elementen.

### Vereisten {#prerequisites}

Als u activering op meerdere niveaus voor uw elementen wilt gebruiken, maakt u een AEM-schermproject met een volgnummer. In het volgende voorbeeld wordt de implementatie van de functie getoond:

* Een AEM-schermproject maken met de naam **MultiAssetDemo**
* Maak een kanaal met de naam **MultiAssetChannel** en voeg inhoud toe aan het kanaal, zoals in de onderstaande afbeelding wordt getoond

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Voer de onderstaande stappen uit om meerdere elementen te selecteren en de weergave ervan in een AEM-rasterproject te plannen:

1. Selecteer **MultiAssetChannel** en klik op **Bewerken** op de actiebalk om de editor te openen.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Selecteer meerdere elementen in de editor en klik op Activering **** bewerken (pictogram linksboven).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Selecteer de datum en tijd in **Actief van** en **Actief tot** van de de dialoogdoos van de Activering **van de** Component. Klik op het pictogram van het vinkje wanneer u klaar bent met het selecteren van de schema&#39;s.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Klik verfrissen om de activa te controleren waarop multi-activa programma wordt toegepast.

   >[!NOTE]
   >
   >Het planningspictogram is in de rechterbovenhoek zichtbaar voor de elementen die worden geactiveerd met meerdere elementen.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)
