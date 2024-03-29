---
title: Kanalen maken en beheren
seo-title: Managing Channels
description: Volg deze pagina voor meer informatie over het maken en beheren van kanalen. Ook wordt het kanaaldashboard en het bewerken van inhoud voor een kanaal uitgelegd.
seo-description: Follow this page to learn about creating and managing channels. It also explains channel dashboard and editing content for a channel.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 7bbd211a-f54f-42b9-a1b3-516efe6fb579
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 0%

---

# Kanalen maken en beheren {#creating-and-managing-channels}

Een kanaal geeft een reeks inhoud (afbeeldingen en video&#39;s) weer en geeft ook een website of een toepassing van één pagina weer.

Op deze pagina worden kanalen voor AEM Screens gemaakt en beheerd.

**Voorwaarden**:

* [Schermen configureren en implementeren](configuring-screens-introduction.md)
* [Schermproject maken en beheren](creating-a-screens-project.md)

## Een nieuw kanaal maken {#creating-a-new-channel}

Nadat u uw project voor AEM Screens hebt gemaakt, volgt u de onderstaande stappen om een nieuw kanaal voor uw project te maken:

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en klik vervolgens op Rasteren. U kunt ook rechtstreeks navigeren naar `https://localhost:4502/screens.html/content/screens`.

1. Navigeer naar uw project Screens en selecteer **Kanalen** map.

1. Klikken **Maken** in de actiebalk.

   ![demochannel](assets/create-channel1.png)

1. Selecteer **Volgekanaal** sjabloon uit de **Maken** wizard en klik op **Volgende**.

   ![demochannel](assets/create-channel2.png)

1. Voer de titel in als **ScreensChannel** en klik op **Maken**.

   ![demochannel](assets/create-project4.png)

1. Er wordt nu een volgnummer toegevoegd aan uw **Kanalen** map.

### Kanaaltypen {#channel-types}

De volgende sjabloonopties zijn beschikbaar wanneer u de wizard gebruikt, zoals:

| **Sjabloon, optie** | **Beschrijving** |
|---|---|
| Map Kanalen | Hiermee kunt u een map maken waarin de verzameling kanalen wordt opgeslagen. |
| Volgekanaal | Hiermee kunt u een kanaal maken waarmee de componenten opeenvolgend worden afgespeeld (een voor een in een presentatie). |
| Toepassingskanaal | Hiermee kunt u uw aangepaste webtoepassing weergeven in de schermspeler. |
| 1 x 1 gesplitst schermkanaal | Hiermee kunt u de component in één zone weergeven. |
| 1 x 2 gesplitst schermkanaal | Hiermee kunt u de elementen weergeven in twee zones (horizontaal gesplitst). |
| 2 x 1 gesplitst rasterkanaal | Hiermee kunt u de elementen weergeven in twee zones (verticaal gesplitst). |
| 2 x 2 gesplitst schermkanaal | Hiermee kunt u de elementen weergeven in vier zones (horizontaal en verticaal in een matrix). |
| 2 tot 3 gesplitste schermkanaal | Hiermee kunt u de elementen weergeven in twee zones (horizontaal gesplitst) waarbij een van de zones groter is dan de andere. |
| Linker- of rechterL-balkgesplitste schermkanaal | Hiermee kunnen auteurs van inhoud verschillende typen elementen weergeven in zones met de juiste grootte. |

>[!NOTE]
>
>De gesplitste kanalen van het Scherm verdelen de vertoning in veelvoudige streken zodat kunt u verscheidene ervaringen tezelfdertijd, zij aan zij spelen. De ervaringen kunnen statische elementen/tekst of ingesloten reeksen zijn.

>[!IMPORTANT]
>
> Als u eenmaal inhoud aan uw kanaal hebt gemaakt en toegevoegd, bestaat de volgende stap uit het maken van een locatie, gevolgd door het maken van een weergave. Bovendien moet u dat kanaal aan een vertoning toewijzen. Zie de bronnen hieronder aan het einde van de sectie voor meer informatie.

## Werken met kanalen {#working-with-channels}

U kunt een kanaal bewerken, weergeven, eigenschappen en dashboard, kopiëren, voorvertonen en verwijderen.


![screen_shot_2019-07-24at103723am](assets/screen_shot_2019-07-24at103723am.png)

### Inhoud toevoegen aan of bewerken in een kanaal {#adding-editing-content-to-a-channel}

Ga als volgt te werk om inhoud aan een kanaal toe te voegen of te bewerken:

1. Selecteer het kanaal dat u wilt bewerken (zoals in de bovenstaande afbeelding wordt getoond).
1. Klikken **Bewerken** in de linkerbovenhoek van de actiebalk om de kanaaleigenschappen te bewerken. De redacteur opent die u toestaat om activa/componenten aan uw kanaal toe te voegen die u wilt publiceren.

>[!NOTE]
>U kunt componenten aan uw kanaal toevoegen. Zie **[Componenten toevoegen aan een kanaal](adding-components-to-a-channel.md)** voor meer informatie .

![demochannel1](assets/demochannel1.gif)

**Video&#39;s uploaden naar het kanaal**

Voer de onderstaande stappen uit om video&#39;s naar uw kanaal te uploaden:

1. Selecteer het kanaal waar u de video wilt uploaden.
1. Klikken **Bewerken** in de actiebalk om de editor te openen.
1. Selecteren **Video&#39;s** onder Elementen en sleep de gewenste video&#39;s.

>[!NOTE]
>Als u problemen ondervindt bij het uploaden van video&#39;s naar uw kanaal, raadpleegt u [Problemen met video&#39;s oplossen](troubleshoot-videos.md).

### Eigenschappen weergeven {#viewing-properties}

Volg onderstaande stappen om de eigenschappen van een kanaal weer te geven of te bewerken:

1. Klik op het kanaal u wilt uitgeven.
1. Klikken **Eigenschappen** in de actiebalk om de kanaaleigenschappen weer te geven of te bewerken. Met de volgende tabbladen kunt u de opties wijzigen.

![eigenschappen](assets/properties.gif)

### Het dashboard weergeven {#viewing-dashboard}

Voer de volgende stappen uit om het dashboard van een kanaal weer te geven:

1. Selecteer het kanaal dat u wilt bewerken.
1. Klikken **Dashboard** op de actiebalk om het dashboard weer te geven. De **KANAALINFORMATIE**,**TOEGEWEZEN WEERGAVEN**, en **AFGELOPEN LAUNCHES** wordt geopend, zoals in de onderstaande afbeelding wordt getoond:

![dashboard](assets/dashboard.gif)

### Kanaalgegevens {#channel-information}

In het deelvenster Kanaalgegevens worden de kanaaleigenschappen beschreven, samen met de voorvertoning naar het kanaal. Ook, verstrekt het u de informatie over of het kanaal off-line of online is.

Klik op de knop (**...**) van de **KANAALINFORMATIE** actiebalk om eigenschappen weer te geven, de inhoud te bewerken of de cache (offline inhoud) voor het kanaal bij te werken.

![screen_shot_2017-12-20at82048am](assets/screen_shot_2017-12-20at82048am.png)

#### De manifest weergeven {#view-manifest}

U kunt manifest van het kanaaldashboard bekijken.

>[!IMPORTANT]
>Deze optie is alleen beschikbaar bij AEM 6.4 Feature Pack 8 of AEM 6.5 Feature Pack 4.

Ga als volgt te werk om deze optie in te schakelen vanaf het kanaaldashboard:

1. **Kanaal op offline instellen**
   1. Selecteer het kanaal en selecteer **Eigenschappen** op de actiebalk
   1. Navigeren naar **Kanaal** en zorg ervoor dat u de controle ongedaan maakt **Modus voor ontwikkelaar (kanaal forceren om online te zijn)** option
   1. Klikken **Opslaan en sluiten**
1. **Offline inhoud bijwerken**
   1. Selecteer het kanaal en selecteer **Dashboard** op de actiebalk
   1. Navigeren naar **KANAALINFORMATIE** deelvenster en klik op *...*
   1. Klikken **Offline inhoud bijwerken**

U moet de **Manifest weergeven** van de **KANAALINFORMATIE** in het dashboard Kanaal.

![image1](assets/channel-one.png)


### Online en offline kanalen {#online-and-offline-channels}

>[!NOTE]
>Wanneer u een kanaal maakt, is dit standaard offline.

Wanneer u een kanaal maakt, kan dit worden gedefinieerd als een online- of een offlinekanaal.

An ***Onlinekanaal*** wordt de bijgewerkte inhoud in de real-time omgeving weergegeven, terwijl een ***Offline kanaal*** wordt de inhoud in de cache weergegeven.

Volg de onderstaande stappen om het kanaal online te maken:

1. Navigeren naar het kanaal als **TestProject** —> **Kanalen** —> **TestChannel**.

   Selecteer het kanaal.

   ![screen_shot_2019-08-01at31406pm](assets/screen_shot_2019-08-01at31406pm.png)

   Klikken **Dashboard** in de actiebalk om de status van de speler weer te geven. De **KANAALINFORMATIE** geeft informatie over of het kanaal online of offline is.

   ![screen_shot_2019-08-01at31458pm](assets/screen_shot_2019-08-01at31458pm.png)

1. Klikken **Eigenschappen** van de actiebalk en navigeer naar de **Kanaal** tabblad zoals hieronder weergegeven:

   ![screen_shot_2019-08-01at31542pm](assets/screen_shot_2019-08-01at31542pm.png)

1. Controleer de **Ontwikkelaar** **modus (kanaal forceren om online te zijn)** om het kanaal online te maken.

   Klikken **Opslaan en sluiten** om uw optie op te slaan.

   ![screen_shot_2019-08-01at31658pm](assets/screen_shot_2019-08-01at31658pm.png)

   Ga terug naar het kanaaldashboard en nu het **KANAALINFORMATIE** geeft de onlinestatus van de speler weer.

   ![screen_shot_2019-08-01at31821pm](assets/screen_shot_2019-08-01at31821pm.png)

>[!NOTE]
>Als u uw kanaal opnieuw offline wilt configureren, schakelt u de optie voor de modus Ontwikkelaar uit via de optie **Eigenschappen** tab (zoals weergegeven in stap (3)) en vervolgens vanaf het tabblad **KANAALINFORMATIE** paneelklik **Offline inhoud bijwerken**, zoals weergegeven in onderstaande afbeelding.

![dashboard2](assets/dashboard2.gif)

#### Automatische versus handmatige updates van het apparaatdashboard {#automatic-versus-manual-updates-from-the-device-dashboard}

De volgende tabel geeft een overzicht van de gebeurtenissen die zijn gekoppeld aan de automatische en handmatige updates van het apparaatdashboard.

<table>
 <tbody>
  <tr>
   <td><strong>Gebeurtenis</strong></td>
   <td><strong>Automatisch bijwerken van apparaat</strong></td>
   <td><strong>Handmatige update van apparaat</strong></td>
  </tr>
  <tr>
   <td>Wijzigen in onlinekanaal</td>
   <td>Inhoud automatisch bijgewerkt</td>
   <td><p>Inhoud bijgewerkt op "Apparaat: Push Config"</p> <p>Of</p> <p>Inhoud bijgewerkt op <strong><i>Apparaat: Opnieuw starten</i></strong></p> </td>
  </tr>
  <tr>
   <td>Wijziging in offlinekanaal, maar Channel "Push Content" wordt NIET geactiveerd (geen offlinepakket wordt opnieuw gemaakt)</td>
   <td>Geen inhoud bijwerken</td>
   <td>Geen inhoud bijwerken</td>
  </tr>
  <tr>
   <td>Wijziging in offlinekanaal en Kanaal wordt "pushinhoud" geactiveerd (nieuw offlinepakket)</td>
   <td>Inhoud automatisch bijgewerkt</td>
   <td><p>Inhoud bijgewerkt op <strong><i>Apparaat: Push Config</i></strong></p> <p>Of</p> <p>Inhoud bijgewerkt op <strong><i>Apparaat: Opnieuw starten</i></strong></p> </td>
  </tr>
  <tr>
   <td><p>Wijzigen in configuratie</p>
    <ul>
     <li>Weergave (geforceerd kanaal)</li>
     <li>Apparaat</li>
     <li>Kanaaltoewijzingen (nieuw kanaal, verwijderd kanaal)</li>
     <li>Kanaaltoewijzing (rol, gebeurtenis, planning)</li>
    </ul> </td>
   <td>Configuratie automatisch bijgewerkt</td>
   <td><p>Configuratie bijgewerkt op <strong><i>Apparaat: Push Config</i></strong></p> <p>Of</p> <p>Configuratie bijgewerkt op <strong><i>Apparaat: Opnieuw starten</i></strong></p> </td>
  </tr>
 </tbody>
</table>

### Toegewezen beeldschermen {#assigned-displays}

In het toegewezen deelvenster wordt de weergave weergegeven die aan het kanaal is gekoppeld. Het verstrekt een momentopname van de toegewezen vertoning samen met de resolutie.

De bijbehorende weergaven worden weergegeven in het dialoogvenster **Toegewezen beeldschermen** deelvenster, zoals hieronder weergegeven:

![chlimage_1-27](assets/chlimage_1-27.png)

>[!NOTE]
>Raadpleeg de volgende bronnen voor meer informatie over het maken van een weergave op een locatie:
>
>* [Locaties maken en beheren](managing-locations.md)
>* [Weergaven maken en beheren](managing-displays.md)
>


Klik bovendien op de weergave in het dialoogvenster **TOEGEWEZEN WEERGAVEN** om de weergaveinformatie weer te geven, zoals hieronder wordt getoond:

![chlimage_1-28](assets/chlimage_1-28.png)

### De volgende stappen {#the-next-steps}

De volgende stap na het maken van een kanaal en het toevoegen/bewerken van inhoud in uw kanaal is te leren hoe u een locatie en weergave kunt maken. Vervolgens wijst u een kanaal toe aan dat beeldscherm.

Zie de volgende bronnen voor de volgende stappen:

* [Kanalen maken en beheren](managing-channels.md)
* [Locaties maken en beheren](managing-locations.md)
* [Weergaven maken en beheren](managing-displays.md)
