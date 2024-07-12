---
title: Activering van middelenniveau
description: Leer hoe u een specifiek middel in een kanaal activeert voor een gepland tijdkader, allemaal binnen de lokale tijdzone van de speler.
feature: Authoring Screens, Asset Level Activation
role: Admin, Developer
level: Intermediate
exl-id: a2f5b2cc-6797-4397-b49c-72175a2d2ef7
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 0%

---

# Activering van middelenniveau {#asset-level-scheduling}

Deze pagina beschrijft activering op middelenniveau voor de middelen die in Kanalen worden gebruikt.

De volgende onderwerpen worden behandeld in deze sectie:

* Overzicht
* Activeringsvenster
* Afspelen van één gebeurtenis
* Herhaling in Assets afhandelen
   * DayParting
   * WeekParting
   * MonthParting
   * Combinatie van partners
* Activering van meerdere middelen
* Algemene Overschrijving voor universele begintijd

<!-- REFERS TO ARCHIVED VERSIONS THAT ADOBE NO LONGER SUPPORTS>
>[!CAUTION]
>
>This AEM Screens functionality is only available if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permission, you can download it from Package Share. -->

## Overzicht {#overview}

***Activering van het Niveau van Activa*** laat u een specifiek middel in een kanaal voor een gepland tijdkader, allen binnen lokale timezone van de speler activeren. Deze mogelijkheid is beschikbaar voor afbeeldingen, video&#39;s, overgangen, pagina&#39;s en ingesloten kanalen (dynamisch of statisch).

*bijvoorbeeld*, wilt u een speciale bevordering om slechts tijdens gelukkig uur (2PM aan 5PM) op Maandagen en Woensdag worden getoond.

Met deze functie kunt u niet alleen een begin- en einddatum en -tijd opgeven, maar ook een herhalingspatroon.

## Activeringsvenster {#single-event-playback}

De Activering van het Niveau van activa wordt gedaan door het **lusje van de Activering** te vormen terwijl de toegang tot van de eigenschappen van een activa.

Voer de onderstaande stappen uit om de middelenplanning uit te voeren:

1. Klik om het even welk kanaal, dan klik **uitgeven** van de actiebar.

   ![ screen_shot_2018-04-23at111422am ](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >Meer informatie over hoe u
   >
   >* Maak een project. Zie [ Creërend een nieuw Project ](creating-a-screens-project.md).
   >* Maak inhoud en voeg inhoud toe aan een kanaal. Zie [ het Leiden Kanalen ](managing-channels.md).

1. Klik **uitgeven** zodat kunt u de kanaalredacteur openen en activa klikken u het plannen op wilt toepassen.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Klik de activa, dan klik linksboven **vormen** (het moersleutelpictogram).

   Klik de **Activering** tabel.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level3.png)

1. U kunt de datum van de datumkiezer specificeren gebruikend **Actieve van** en **Actieve tot** gebieden.

   Als u **Actief van** en **Actief tot** datum en tijd klikt, toont de activa en lijnen slechts tussen die begindatum/tijd en einddatum/tijd, respectievelijk.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level3.png)

## Herhaling in Assets afhandelen {#handling-recurrence-in-assets}

U kunt activa plannen om met bepaalde intervallen op een dagelijkse, wekelijkse, of maandelijkse basis volgens uw vereiste terug te komen.

Stel dat u een afbeelding alleen op vrijdag van 13.00 uur tot 22.00 uur wilt weergeven. U kunt het **lusje van de Activering** gebruiken om het gewenste terugkomende interval voor uw activa te plaatsen.

### Dagverdeling {#day-parting}

1. Klik de activa en klik op **vormen** (het moersleutelpictogram) om de doos van de eigenschappendialoog te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt overslaan of **Actief van** omvatten en **Actief tot** gebieden en de uitdrukking toevoegen aan het gebied van Programma&#39;s, zoals per uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa wordt getoond voor het bepaalde interval van dag en tijd.

#### Voorbeeldexpressies voor dagparatie {#example-one}

De volgende tabel geeft een overzicht van een aantal voorbeeldexpressies die u aan het schema kunt toevoegen terwijl u een kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | Het middel in het kanaal speelt vóór 8:00 a.m. dagelijks |
| na 2:00 | Het middel in het kanaal speelt na 2:00 p.m. dagelijks af |
| na 12:15 en vóór 12:45 | Het middel in het kanaal speelt na 23:15 uur elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | Het middel in het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 uur. |

>[!NOTE]
>
>U kunt _militaire tijd_ aantekening (14:00) in plaats van *ook gebruiken A.M./P.M.* (2:00 P.M.).

### WeekParting {#week-parting}

1. Klik de activa, dan klik **vormen** (het moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt overslaan of **Actief van** omvatten en **Actief tot** gebieden en de uitdrukking toevoegen aan het gebied van Programma&#39;s, zoals per uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor WeekParting {#example-two}

De volgende tabel geeft een overzicht van een aantal voorbeeldexpressies die u aan het schema kunt toevoegen terwijl u een kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `Mon,Wed,Fri` | het element wordt vanaf maandag, woensdag en vrijdag in het kanaal afgespeeld |
| `Mon-Thu` | de activa spelen in het kanaal van op Maandagen aan Donderdag |

>[!NOTE]
>
>U kunt _volledige_ aantekening (`Monday,Wednesday,Friday`) in plaats van _gebruiken korthand_ (`Mon,Wed,Fri`).


### MonthParting {#month-parting}

1. Klik de activa, dan klik **vormen** (het moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt overslaan of **Actief van** omvatten en **Actief tot** gebieden en de uitdrukking toevoegen aan het gebied van Programma&#39;s, zoals per uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor MonthParting {#example-three}

De volgende tabel geeft een overzicht van een aantal voorbeeldexpressies die u aan het schema kunt toevoegen terwijl u een kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `on February,May,August,November` | de activa spelen in het kanaal in februari, mei, augustus en november |
| `on February-July` | de activa spelen in het kanaal van februari tot eind juli |

>[!NOTE]
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte- als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en januari.

### Combinatie van partners {#combined-parting}

1. Klik de activa, dan klik **vormen** (het moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt overslaan of **Actief van** omvatten en **Actief tot** gebieden en de uitdrukking toevoegen aan het gebied van Programma&#39;s, zoals per uw vereiste.

1. Ga de uitdrukking in het **Programma** in en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor de combinatie van delen {#example-four}

De volgende tabel geeft een overzicht van een aantal voorbeeldexpressies die u aan het schema kunt toevoegen terwijl u een kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `after 6:00 and before 18:00 on Mon,Wed of Jan-Mar` | de activa spelen in het kanaal tussen 6.00 uur en 6.00 uur op maandag en woensdag van januari tot eind maart |
| `on the 1st day of January after 2:00 P.M. also on the 2nd day of January also on the 3rd day of January before 3:00 A.M.` | het middel in het kanaal begint na 1 januari om 2.00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3.00 uur &#39;s middags op 3 januari |
| `on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 A.M.` | Het middel in het kanaal start speler na 1 januari om 2:00 uur, gaat verder met afspelen tot 2 januari om 3:00 uur &#39;s middags, vervolgens begint het opnieuw op 2 januari om 2:00 uur &#39;s middags en wordt verder afgespeeld tot 3:00 uur &#39;s middags op 3 januari |

>[!NOTE]
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte- als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en januari. Ook, kunt u _militaire tijd_ aantekening (14:00) in plaats van *ook gebruiken A.M./P.M.* (2:00 P.M.).


## Activering van meerdere middelen {#multi-asset-scheduling}

<!--
>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3. -->

***Multi-asset Activation*** laat de gebruiker veelvoudige activa klikken en een playbackprogramma op alle geselecteerde activa toepassen.

### Vereisten {#prerequisites}

Als u activering op meerdere niveaus voor uw middelen wilt gebruiken, maakt u een AEM Screens-project met een volgnummer. In het volgende voorbeeld wordt de implementatie van de functie getoond:

* Creeer een project van AEM Screens dat als **wordt genoemd MultiAssetDemo**.
* Creeer een kanaal genoemd als **MultiAssetChannel** en voeg inhoud aan het kanaal toe, zoals aangetoond in het hieronder cijfer.

![ screen_shot_2018-12-21at70128am ](assets/screen_shot_2018-12-21at70128am.png)

Voer de onderstaande stappen uit om op meerdere elementen te klikken en de weergave ervan in een AEM Screens-project te plannen:

1. Klik **MultiAssetChannel**, dan klik **uitgeven** van de actiebar.

   ![ screen_shot_2018-12-21at70313am ](assets/screen_shot_2018-12-21at70313am.png)

1. Klik veelvoudige activa van de redacteur, dan klik **Activatie** (top-left pictogram) uitgeven.

   ![ screen_shot_2018-12-21at70550am ](assets/screen_shot_2018-12-21at70550am.png)

1. Klik de datum en de tijd in **Actief van** en **Actief tot** van het **de dialoogvakje van de Activering van de Component**. Klik op het pictogram van het vinkje wanneer u klaar bent met het selecteren van de schema&#39;s.

   ![ screen_shot_2018-12-17at20337pm ](assets/screen_shot_2018-12-17at20337pm.png)

1. Klik verfrissen om de activa te controleren waarop het multi-activa programma wordt toegepast.

   >[!NOTE]
   >
   >Het planningspictogram is in de rechterbovenhoek zichtbaar voor de elementen waarvoor elementen met meerdere elementen zijn geactiveerd.

   ![ screen_shot_2018-12-21at70722am ](assets/screen_shot_2018-12-21at70722am.png)

## Algemene Overschrijving voor universele begintijd {#global-override-scheduling}

***Globale Opheffing voor de Universele Tijd van het Begin***, is het plaatsen die de Inhoudsauteur toestaat om de playback van een beeld of videoactiva te bepalen die op een specifieke tijd wordt gebaseerd. De tijd-/tijdzone-instelling van een afzonderlijke speler wordt niet gebruikt.

Doorgaans wordt het afspelen bepaald door de lokale tijd van een bepaalde speler. Maar met de globale overschrijving kan een specifieke, universele begintijd worden gebruikt om het afspelen van het element te starten.

Als zodanig kan de Content Author het afspelen van een bepaald element aanwijzen. Ze kunnen de inhoud op een bepaalde datum/tijd weergeven, ongeacht de lokale klok op spelers die de toegewezen inhoud hebben.

***Globale Opheffing voor de Universele Tijd van het Begin*** wordt gedaan door het **lusje van de Activering** te vormen terwijl de toegang tot van eigenschappen van een activa. Voer de onderstaande stappen uit om een globale overschrijving uit te voeren voor het plannen van elementen:

1. Klik om het even welk kanaal, dan klik **uitgeven** van de actiebar zodat kunt u inhoud in uw kanaal toevoegen of uitgeven.

   ![ screen_shot_2018-04-23at111422am ](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Klik **uitgeven**.
1. Klik in de kanaaleditor op een element waarvan u het schema wilt toepassen.

   ![ screen_shot_2018-12-21at70550am ](/help/user-guide/assets/asset-activation/Asset-level4.png)

1. Voor een globale opheffing, ga de activeringstijd in de **sectie van de tijdzoneoverschrijving** voor de activa in. Als u niets in dit gebied invoert, wordt de tijdzone van de speler toegepast.


