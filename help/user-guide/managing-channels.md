---
title: Kanalen maken en beheren
description: Meer informatie over het maken en beheren van kanalen. Ook wordt het kanaaldashboard en het bewerken van inhoud voor een kanaal uitgelegd.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 7bbd211a-f54f-42b9-a1b3-516efe6fb579
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 0%

---

# Kanalen maken en beheren {#creating-and-managing-channels}

Een kanaal geeft een reeks inhoud (afbeeldingen en video&#39;s) weer en geeft ook een website of een toepassing van één pagina weer.

Op deze pagina worden kanalen voor AEM Screens gemaakt en beheerd.

**Voorwaarden**:

* [Screens configureren en implementeren](configuring-screens-introduction.md)
* [Screens-project maken en beheren](creating-a-screens-project.md)

## Een nieuw kanaal maken {#creating-a-new-channel}

Nadat u uw project voor AEM Screens hebt gemaakt, volgt u de onderstaande stappen om een kanaal voor uw project te maken:

1. Klik op de Adobe Experience Manager-koppeling (linksboven) en vervolgens op Screens. U kunt ook rechtstreeks naar `https://localhost:4502/screens.html/content/screens` navigeren.

1. Navigeer aan uw project van Screens en klik de **omslag van Kanalen**.

1. Klik **creëren** van de actiebar.

   ![ demochannel ](assets/create-channel1.png)

1. Klik het **malplaatje van het Kanaal van de Opeenvolging 1} van** creëren **tovenaar en klik** daarna **.**

   ![ demochannel ](assets/create-channel2.png)

1. Ga Titel als **ScreensChannel** in en klik **creeer**.

   ![ demochannel ](assets/create-project4.png)

1. Een kanaal van de Opeenvolging wordt nu toegevoegd aan uw **omslag van Kanalen**.

### Kanaaltypen {#channel-types}

De volgende sjabloonopties zijn beschikbaar wanneer u de wizard gebruikt, zoals:

| **optie van het Malplaatje** | **Beschrijving** |
|---|---|
| Map Kanalen | Maak een map waarin u een verzameling kanalen wilt opslaan. |
| Volgekanaal | Maak een kanaal waarmee de componenten opeenvolgend worden afgespeeld (een voor een in een presentatie). |
| Toepassingskanaal | Toon uw aangepaste webtoepassing in de Screens-speler. |
| 1 x 1 gesplitst schermkanaal | Een component weergeven in één zone. |
| 1 x 2 gesplitst schermkanaal | De elementen weergeven in twee zones (horizontaal gesplitst). |
| 2 x 1 gesplitst rasterkanaal | De elementen weergeven in twee zones (verticaal gesplitst). |
| 2 x 2 gesplitst schermkanaal | Geef de elementen weer in vier zones (horizontaal en verticaal opgesplitst in een matrix). |
| 2 tot 3 gesplitste schermkanaal | Geef de elementen weer in twee zones (horizontaal gesplitst) waarbij een van de zones groter is dan de andere. |
| Linker- of rechterL-balkgesplitste schermkanaal | Inhoudsauteurs kunnen verschillende typen elementen weergeven in zones met het juiste formaat. |

>[!NOTE]
>
>De gesplitste kanalen van het Scherm verdelen de vertoning in veelvoudige streken zodat kunt u verscheidene ervaringen tezelfdertijd, zij aan zij spelen. De ervaringen kunnen statische elementen/tekst of ingesloten reeksen zijn.

>[!IMPORTANT]
>
>Nadat u inhoud aan uw kanaal hebt gemaakt en toegevoegd, bestaat de volgende stap uit het maken van een locatie, gevolgd door het maken van een weergave. Bovendien wijst u dat kanaal toe aan een scherm. Zie de bronnen hieronder aan het einde van de sectie.

## Werken met kanalen {#working-with-channels}

U kunt een kanaal bewerken, weergeven, eigenschappen en dashboard, kopiëren, voorvertonen en verwijderen.


![ screen_shot_2019-07-24at103723am ](assets/screen_shot_2019-07-24at103723am.png)

### Inhoud toevoegen aan of bewerken in een kanaal {#adding-editing-content-to-a-channel}

Ga als volgt te werk om inhoud aan een kanaal toe te voegen of te bewerken:

1. Klik op het kanaal dat u wilt bewerken (zoals in de bovenstaande afbeelding wordt getoond).
1. Klik **uitgeven** van de hoogste-linkerhoek van de actiebar zodat kunt u de kanaaleigenschappen uitgeven. De redacteur opent die u activa/componenten aan uw kanaal kunt toevoegen die u wilt publiceren.

>[!NOTE]
>U kunt componenten aan uw kanaal toevoegen. Zie **[Toevoegend Componenten aan een Kanaal](adding-components-to-a-channel.md)** voor meer details.

![ demochannel1 ](assets/demochannel1.gif)

**Uploading Video&#39;s aan het Kanaal**

Voer de onderstaande stappen uit om video&#39;s naar uw kanaal te uploaden:

1. Klik op het kanaal waar u de video wilt uploaden.
1. Klik **uitgeven** van de actiebar.
1. In de redacteur, klik **Video&#39;s** onder Assets en sleep en laat vallen de vereiste video&#39;s.

>[!NOTE]
>Als u kwesties ontmoet die video&#39;s in uw kanaal uploaden, zie [ het Oplossen van problemen Video&#39;s ](troubleshoot-videos.md).

### Eigenschappen van een kanaal weergeven of bewerken {#viewing-properties}

1. Klik op het kanaal dat u wilt bewerken.
1. Klik **Eigenschappen** van de actiebar zodat kunt u de kanaaleigenschappen bekijken/uitgeven. Op het volgende tabblad kunt u de opties wijzigen.

![ eigenschappen ](assets/properties.gif)

### Het dashboard weergeven {#viewing-dashboard}

1. Klik op het kanaal dat u wilt bewerken.
1. Klik **Dashboard** van de actiebar.

![ dashboard ](assets/dashboard.gif)

### Kanaalgegevens {#channel-information}

In het deelvenster Kanaalgegevens worden de kanaaleigenschappen beschreven, samen met de voorvertoning naar het kanaal. Ook, verstrekt het u informatie over of het kanaal off-line of online is.

Klik (**...**) van de **INFORMATIE VAN HET KANAAL** actiebar zodat kunt u eigenschappen bekijken, de inhoud uitgeven, of het geheime voorgeheugen (off-line inhoud) voor het kanaal bijwerken.

![ screen_shot_2017-12-20at82048am ](assets/screen_shot_2017-12-20at82048am.png)

#### De manifest weergeven {#view-manifest}

U kunt manifest van het kanaaldashboard bekijken.

>[!IMPORTANT]
>Deze optie is alleen beschikbaar bij AEM 6.4 Feature Pack 8 of AEM 6.5 Feature Pack 4.

Voer de volgende stappen uit, zodat u deze optie kunt inschakelen via het kanaaldashboard:

1. **plaats het Kanaal aan Off-line**
   1. Klik het kanaal en klik **Eigenschappen** van de actiebar
   1. Navigeer aan het **Kanaal** lusje en zorg ervoor dat u **de Wijze van de Ontwikkelaar uncheck (forceer kanaal om online te zijn)** optie
   1. Klik **sparen &amp; Sluiten**
1. **Update Offline Inhoud**
   1. Klik het kanaal en klik **Dashboard** van de actiebar
   1. Navigeer aan het **paneel van de INFORMATIE VAN HET KANAAL** en klik *..*
   1. Klik **Update Offline Inhoud**

U zou de **Manifest van de Mening** optie van het **paneel van de INFORMATIE VAN HET KANAAL** in het dashboard van het Kanaal moeten zien.

![ image1 ](assets/channel-one.png)


### Online- en offlinekanalen {#online-and-offline-channels}

>[!NOTE]
>Wanneer u een kanaal maakt, is dit standaard offline.

Wanneer u een kanaal maakt, kan dit worden gedefinieerd als een online- of een offlinekanaal.

Een ***Online Kanaal*** toont de bijgewerkte inhoud in het milieu in real time terwijl een ***Off-line Kanaal*** de caching inhoud toont.

Volg de onderstaande stappen om het kanaal online te maken:

1. Navigeer aan het kanaal als **TestProject** > **Kanalen** > **TestChannel**.

   Klik op het kanaal.

   ![ screen_shot_2019-08-01at31406pm ](assets/screen_shot_2019-08-01at31406pm.png)

   Klik **Dashboard** van de actiebar zodat kunt u het statuut van de speler bekijken. Het **paneel van de INFORMATIE VAN HET KANAAL** verstrekt informatie over of het kanaal online of off-line is.

   ![ screen_shot_2019-08-01at31458pm ](assets/screen_shot_2019-08-01at31458pm.png)

1. Klik **Eigenschappen** van de actiebar en navigeer aan het **3} lusje van het Kanaal {zoals hieronder getoond:**

   ![ screen_shot_2019-08-01at31542pm ](assets/screen_shot_2019-08-01at31542pm.png)

1. Controleer de **** wijze van de 1} Ontwikkelaar **(dwang het kanaal om online te zijn)** om het kanaal als online te maken.

   Klik **sparen &amp; Sluiten** om uw optie te bewaren.

   ![ screen_shot_2019-08-01at31658pm ](assets/screen_shot_2019-08-01at31658pm.png)

   Navigeer terug naar het kanaaldashboard en nu toont het **paneel van de INFORMATIE VAN HET KANAAL** de online status van de speler.

   ![ screen_shot_2019-08-01at31821pm ](assets/screen_shot_2019-08-01at31821pm.png)

>[!NOTE]
>Om uw kanaal opnieuw als off-line te vormen, uncheck de de wijzeoptie van de Ontwikkelaar van het **Eigenschappen** lusje (zoals aangetoond in stap (3)). Dan, van het **paneel van de INFORMATIE VAN HET KANAAL** klik **de Offline Inhoud van de Update**, zoals aangetoond in het hieronder cijfer.

![ dashboard2 ](assets/dashboard2.gif)

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
   <td>Inhoud wordt automatisch bijgewerkt</td>
   <td><p>Inhoud bijgewerkt op "Device: Push Config"</p> <p>Of,</p> <p>Inhoud bijgewerkt op <strong><i> Apparaat: Begin </i></strong> opnieuw</p> </td>
  </tr>
  <tr>
   <td>Wijziging in offlinekanaal, maar Channel "Push Content" wordt NIET geactiveerd (geen offlinepakket wordt opnieuw gemaakt)</td>
   <td>Geen inhoud bijwerken</td>
   <td>Geen inhoud bijwerken</td>
  </tr>
  <tr>
   <td>Wijziging in offlinekanaal en Kanaal wordt "pushinhoud" geactiveerd (nieuw offlinepakket)</td>
   <td>Inhoud wordt automatisch bijgewerkt</td>
   <td><p>Inhoud bijgewerkt op <strong><i> Apparaat: Duw Config </i></strong></p> <p>Of,</p> <p>Inhoud bijgewerkt op <strong><i> Apparaat: Begin </i></strong> opnieuw</p> </td>
  </tr>
  <tr>
   <td><p>Wijzigen in configuratie</p>
    <ul>
     <li>Weergave (geforceerd kanaal)</li>
     <li>Apparaat</li>
     <li>Kanaaltoewijzingen (nieuw kanaal, verwijderd kanaal)</li>
     <li>Kanaaltoewijzing (rol, gebeurtenis, planning)</li>
    </ul> </td>
   <td>Configuratie wordt automatisch bijgewerkt</td>
   <td><p>De configuratie wordt bijgewerkt op <strong><i> Apparaat: Duw Config </i></strong></p> <p>Of,</p> <p>Config bijgewerkt op <strong><i> Apparaat: Begin </i></strong></p> </td>
  </tr>
 </tbody>
</table>

### Toegewezen beeldschermen {#assigned-displays}

Het **Toegewezen paneel van Vertoningen** toont de vertoning verbonden aan het kanaal. Het verstrekt een momentopname van de toegewezen vertoning samen met de resolutie.

De bijbehorende vertoningen worden vermeld in het **Toegewezen paneel van Vertoningen**, zoals hieronder getoond:

![ chlimage_1-27 ](assets/chlimage_1-27.png)

>[!NOTE]
>Zie voor meer informatie over het maken van een weergave op een locatie:
>
>* [ creeer en beheer Plaatsen ](managing-locations.md)
>* [ creeer en beheer Vertoningen ](managing-displays.md)
>

Ook, klik de vertoning in **TOEGEWEZEN WEERGAVEN** paneel, om de vertoningsinformatie, zoals hieronder getoond te bekijken:

![ chlimage_1-28 ](assets/chlimage_1-28.png)

### De volgende stappen {#the-next-steps}

De volgende stap na het maken van een kanaal en het toevoegen/bewerken van inhoud in uw kanaal is te leren hoe u een locatie en weergave kunt maken. Vervolgens wijst u een kanaal toe aan dat beeldscherm.

Zie de volgende bronnen voor de volgende stappen:

* [Kanalen maken en beheren](managing-channels.md)
* [Locaties maken en beheren](managing-locations.md)
* [Weergaven maken en beheren](managing-displays.md)
