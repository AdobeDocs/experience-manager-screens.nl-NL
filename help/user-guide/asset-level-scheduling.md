---
title: Activering van middelenniveau
description: Leer hoe u een specifiek middel in een kanaal activeert voor een gepland tijdkader in de lokale tijdzone van de speler.
feature: Authoring Screens, Asset Level Activation
role: Admin, Developer
level: Intermediate
exl-id: a2f5b2cc-6797-4397-b49c-72175a2d2ef7
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 0%

---

# Activering van middelenniveau {#asset-level-scheduling}

Deze pagina beschrijft activering op middelenniveau voor de middelen die in Kanalen worden gebruikt.

De volgende onderwerpen worden behandeld in deze sectie:

* Overzicht
* Activeringsvenster
* Afspelen van één gebeurtenis
* Herhaling van activa afhandelen
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

***Activering van middelenniveau*** Hiermee kunt u een specifiek middel in een kanaal activeren voor een gepland tijdkader in de lokale tijdzone van de speler. Dit is beschikbaar voor afbeeldingen, video&#39;s, overgangen, pagina&#39;s en ingesloten kanalen (dynamisch of statisch).

*Bijvoorbeeld*, wilt u dat een speciale promotie alleen tijdens het gelukkig uur (23.00 uur tot 17.00 uur) op maandag en woensdag wordt weergegeven.

Met deze functie kunt u niet alleen de begin- en einddatum en -tijd opgeven, maar ook een herhalingspatroon.

## Activeringsvenster {#single-event-playback}

Activering van middelenniveau wordt uitgevoerd door de **Activering** te gebruiken tijdens het openen van eigenschappen van een element.

Voer de onderstaande stappen uit om de middelenplanning uit te voeren:

1. Klik op een kanaal en klik vervolgens op **Bewerken** in de actiebalk.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >Meer informatie over hoe u
   >
   >* Een project maken, zie [Een nieuw project maken](creating-a-screens-project.md).
   >* Inhoud maken en toevoegen aan een kanaal, zie [Kanalen beheren](managing-channels.md).

1. Klikken **Bewerken** zodat kunt u de kanaaleditor openen en op een element klikken waarop u de planning wilt toepassen.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Klik op het element en klik vervolgens linksboven **Configureren** (moersleutelpictogram).

   Klik op de knop **Activering** tab.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level3.png)

1. U kunt de datum vanaf de datumkiezer opgeven met **Actief van** en **Actief tot** velden.

   Als u op de knop **Actief van** en **Actief tot** datum en tijd, de activa tonen en lussen slechts tussen die begindatum/tijd en einddatum/tijd, respectievelijk.

   ![afbeelding](/help/user-guide/assets/asset-activation/asset-level3.png)

## Herhaling van activa afhandelen {#handling-recurrence-in-assets}

U kunt ook bepalen dat de middelen elke dag, week of maand opnieuw worden uitgevoerd, afhankelijk van uw vereisten.

Stel dat u een afbeelding alleen op vrijdag van 13.00 uur tot 22.00 uur wilt weergeven. U kunt de **Activering** om het gewenste herhalingsinterval voor uw element in te stellen.

### Dagverdeling {#day-parting}

1. Klik op het element en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw middel wordt weergegeven voor het bepaalde interval van dag en tijd.

#### Voorbeeldexpressies voor dagparatie {#example-one}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| vóór 8:00 | Het middel in het kanaal speelt vóór 8:00 a.m. dagelijks |
| na 2:00 | Het middel in het kanaal speelt na 2:00 p.m. dagelijks af |
| na 12:15 en vóór 12:45 | Het middel in het kanaal speelt na 23:15 uur elke dag gedurende 30 minuten af |
| vóór 12:15 ook na 12:45 | Het middel in het kanaal speelt vóór 12:15 elke dag en dan ook na 12:45 uur. |

>[!NOTE]
>
>U kunt ook _militaire tijd_ notatie (14:00) in plaats van *A.M./P.M.* (14:00)

### WeekParting {#week-parting}

1. Klik op het element en klik vervolgens op **Configureren** (moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor WeekParting {#example-two}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `Mon,Wed,Fri` | het element wordt vanaf maandag, woensdag en vrijdag in het kanaal afgespeeld |
| `Mon-Thu` | de activa spelen in het kanaal van op Maandagen aan Donderdag |

>[!NOTE]
>
>U kunt ook _volledig_ notatie (`Monday,Wednesday,Friday`) in plaats van _kortzichtig_ (`Mon,Wed,Fri`).


### MonthParting {#month-parting}

1. Klik op het element en klik vervolgens op **Configureren** (moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor MonthParting {#example-three}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `on February,May,August,November` | de activa spelen in het kanaal in februari, mei, augustus en november |
| `on February-July` | de activa spelen in het kanaal van februari tot eind juli |

>[!NOTE]
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte- als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en januari.

### Combinatie van partners {#combined-parting}

1. Klik op het element en klik vervolgens op **Configureren** (moersleutelpictogram).

1. Na het ingaan van de begindatum/de tijd en eind/datumtijd, kunt u een uitdrukking of een natuurlijke tekstversie gebruiken om uw herhalingsprogramma te specificeren.

   >[!NOTE]
   >U kunt de **Actief van** en **Actief tot** en voeg de expressie toe aan het veld Planningen, naar wens.

1. Voer de expressie in de **Schema** en uw activa toont voor het bepaalde interval van dag en tijd.

#### Voorbeelden van expressies voor de combinatie van delen {#example-four}

In de volgende tabel worden enkele voorbeeldexpressies samengevat die u aan het schema kunt toevoegen terwijl u kanaal toewijst aan een weergave.

| **Uitdrukking** | **Interpretatie** |
|---|---|
| `after 6:00 and before 18:00 on Mon,Wed of Jan-Mar` | de activa spelen in het kanaal tussen 6.00 uur en 6.00 uur op maandag en woensdag van januari tot en met eind maart |
| `on the 1st day of January after 2:00 P.M. also on the 2nd day of January also on the 3rd day of January before 3:00 A.M.` | het middel in het kanaal begint na 1 januari om 2.00 uur af te spelen, blijft de hele dag afspelen op 2 januari tot 3.00 uur &#39;s middags op 3 januari |
| `on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 A.M.` | Het middel in het kanaal start speler na 1 januari om 2:00 uur, gaat verder met afspelen tot 2 januari om 3:00 uur &#39;s middags, vervolgens begint het opnieuw op 2 januari om 2:00 uur &#39;s middags en wordt verder afgespeeld tot 3:00 uur &#39;s middags op 3 januari |

>[!NOTE]
>Wanneer u dagen van de week en maanden definieert, kunt u zowel de korte- als de volledige-naamnotatie gebruiken, zoals Mon/Maandag en januari. U kunt ook _militaire tijd_ notatie (14:00) in plaats van *A.M./P.M.*(14:00)


## Activering van meerdere middelen {#multi-asset-scheduling}

<!--
>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3. -->

***Activering van meerdere middelen*** Hiermee kan de gebruiker op meerdere elementen klikken en een afspeelschema toepassen op alle geselecteerde elementen.

### Vereisten {#prerequisites}

Als u activering op meerdere niveaus voor uw middelen wilt gebruiken, maakt u een AEM Screens-project met een volgnummer. In het volgende voorbeeld wordt de implementatie van de functie getoond:

* Een AEM Screens-project maken met de naam **MultiAssetDemo**.
* Een kanaal maken met de naam **MultiAssetChannel** en voeg inhoud aan het kanaal toe, zoals aangetoond in hieronder figuur.

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Voer de onderstaande stappen uit om op meerdere elementen te klikken en de weergave ervan in een AEM Screens-project te plannen:

1. Klikken **MultiAssetChannel** en klik vervolgens op **Bewerken** in de actiebalk.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Klik op meerdere elementen in de editor en klik vervolgens op **Activering bewerken** (pictogram linksboven).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Klik op de datum en tijd in **Actief van** en **Actief tot** van de **Componentactivering** in. Klik op het pictogram van het vinkje wanneer u klaar bent met het selecteren van de schema&#39;s.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Klik op Vernieuwen om de elementen te controleren waarop het schema voor meerdere elementen is toegepast.

   >[!NOTE]
   >
   >Het planningspictogram is in de rechterbovenhoek zichtbaar voor de elementen waarvoor elementen met meerdere elementen zijn geactiveerd.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)

## Algemene Overschrijving voor universele begintijd {#global-override-scheduling}

***Algemene Overschrijving voor universele begintijd***, is een instelling waarmee de auteur van de inhoud het afspelen van een afbeelding of video-element kan definiëren op basis van een specifieke tijd. De tijd-/tijdzone-instelling van een afzonderlijke speler wordt niet gebruikt.

Doorgaans wordt het afspelen bepaald door de lokale tijd van een bepaalde speler, maar met de algemene overschrijving kan een specifieke, universele begintijd worden gebruikt om het afspelen van het element te starten.

Op deze manier kan de auteur van de inhoud het afspelen van een bepaald element aanduiden als actief op een bepaalde datum/tijd, ongeacht de lokale klok, op alle spelers met de toegewezen inhoud.

De globale Opheffing voor de Universele Tijd van het Begin wordt gedaan door te vormen **Activering** te gebruiken tijdens het openen van eigenschappen van een element. Voer de onderstaande stappen uit om een globale overschrijving uit te voeren voor het plannen van elementen:

1. Klik op een kanaal en klik vervolgens op **Bewerken** op de actiebalk, zodat u inhoud aan het kanaal kunt toevoegen of bewerken.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Klikken **Bewerken**.
1. Klik in de kanaaleditor op een element waarvan u het schema wilt toepassen.

   ![screen_shot_2018-12-21at70550am](/help/user-guide/assets/asset-activation/Asset-level4.png)

1. Voer voor een globale overschrijving de activeringstijd in het dialoogvenster **Tijdzoneoverschrijving** voor het element. Als u niets in dit gebied invoert, wordt de tijdzone van de speler toegepast.


