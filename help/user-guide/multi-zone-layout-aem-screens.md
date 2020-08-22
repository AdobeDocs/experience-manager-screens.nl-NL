---
title: Layout meerdere zones
seo-title: Layout meerdere zones
description: Met Layout meerdere zones kunt u inhoud voor meerdere zones maken en een groot aantal verschillende elementen gebruiken, zoals video's, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. Volg deze pagina voor meer informatie.
seo-description: Met Layout meerdere zones kunt u inhoud voor meerdere zones maken en een groot aantal verschillende elementen gebruiken, zoals video's, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. Volg deze pagina voor meer informatie.
uuid: 2ad689ef-700a-4eed-b5e2-fc57f2288388
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 4c073172-d93c-4b73-87ab-0b08789193a3
noindex: true
translation-type: tm+mt
source-git-commit: 081db31efda17ac12cdc88f79ed2f4e1fbfc7edf
workflow-type: tm+mt
source-wordcount: '1197'
ht-degree: 0%

---


# Layout meerdere zones {#multi-zone-layout}

De volgende pagina beschrijft het gebruik van lay-out met meerdere zones en behandelt de volgende onderwerpen:

* Overzicht
* Layout meerdere zones maken
* Vereisten
* Single Assets in een of meer zones gebruiken
* Gesegrafeerde inhoud gebruiken in een of meer zones

## Overzicht {#overview}

***Met Layout*** voor meerdere zones kunt u inhoud voor meerdere zones maken en verschillende elementen gebruiken, zoals video&#39;s, afbeeldingen en tekst die in één scherm kunnen worden gecombineerd. U kunt afbeeldingen, video&#39;s en tekst aan elkaar trekken, zodat deze allemaal kunnen overvloeien en een intuïtieve digitale ervaring ontstaat.

Zoals bij de projectvereisten, soms hebt u veelvoudige streken in een kanaal nodig en geeft hen uit als één uitvoerige eenheid. Bijvoorbeeld, een productopeenvolging met een verwante sociale media voer die in drie afzonderlijke streken op één enkel kanaal loopt.


### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u de conceptuele kennis over:

* [Een AEM Screens-project maken](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project.html)
* [Weergave maken](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays.html)
* [Een kanaal toewijzen aan een weergave](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/setting-up-projects/channel-assignment.html)

## Layout meerdere zones maken {#creating-multi-zone-layout}

Tijdens het maken van een kanaal kunt u verschillende sjablonen gebruiken om zones in uw kanaal te maken. U kunt één afbeelding, video of ingesloten kanaal toevoegen waarmee meerdere elementen in een reeks kunnen worden weergegeven.

**Het kanaal maken**

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en **klik vervolgens op Schermen**. U kunt ook rechtstreeks naar: `http://localhost:4502/screens.html/content/screens`.
1. Navigeer naar de map **Kanalen** en klik op **Maken** op de actiebalk.

1. Selecteer **1x2 Gesplitst het Kanaal** van het Scherm van de **Create** tovenaar.

1. Klik op **Volgende** en voer de **titel** in als **MultiZone**.

1. Klik op **Maken** om het maken van het kanaal te voltooien.

### Single Assets in een of meer zones gebruiken {#using-single-assets-in-one-or-more-zones}

U kunt afzonderlijke elementen, zoals een afbeelding of een video, in alle afzonderlijke zones gebruiken. Volg de onderstaande stappen voor implementatie:

1. **Inhoud toevoegen aan het kanaal**

   1. Navigeer naar **zones** —> **Kanalen**—> **MultiZone**.
   1. Selecteer het kanaal **MultiZone** en klik op **Bewerken** op de actiebalk om de editor te openen.

1. **Afbeeldingen toevoegen aan het kanaal**

   Als u één afbeelding of video in twee zones wilt afspelen, sleept u een afbeelding naar elke zone in de Kanaaleditor, zoals in de onderstaande afbeelding wordt getoond:

   ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Gesegrafeerde inhoud gebruiken in een of meer zones {#using-sequenced-content-in-one-or-more-zones}

Als u wilt dat in de zones een reeks afbeeldingen en een video in de verschillende zones wordt weergegeven, volgt u onderstaande stappen voor meer informatie.

1. **Een kanaalmap maken**

   1. Navigeer naar **zones** —> **MultiZone** —> **Kanalen** en klik op **Maken** op de actiebalk.
   1. Selecteer **de Omslag** van Kanalen van de **Create** tovenaar en klik **daarna**.
   1. Voer de titel in als **EmbeddedChannels** en klik op **Maken**.

   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Twee kanalen toevoegen aan de kanaalmap**

   1. Navigeer naar **zones** —> **Kanalen** —> **Ingesloten kanalen** en klik op **Maken** op de actiebalk.
   1. Selecteer **Volgkanaal** in de wizard **Maken** om een kanaal met de naam **Zone1** te maken.
   1. Selecteer **Zone1** en klik op **Bewerken** op de actiebalk om de editor te openen.
   1. Sleep enkele afbeeldingen naar dit kanaal.
   1. Maak op dezelfde manier een ander volgnummer met de naam **Zone2** in de map **EmbeddedChannel** .
   1. Sleep een video naar dit kanaal.

   In de volgende afbeelding ziet u de kanalen **Zone1** en **Zone2**:

   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   De afbeeldingen die zijn toegevoegd aan de editor van het kanaal van de **Zone1** -reeks worden hieronder weergegeven:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   De video die aan redacteur van het **Zone2** opeenvolgingskanaal wordt toegevoegd wordt hieronder getoond:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Ingesloten reeksen (component) toevoegen aan hoofdkanaal (MultiZone)**

   1. Navigeer naar **zones** —> **Kanalen** —> **MultiZone**.
   1. Klik op **Bewerken** op de actiebalk om de editor te openen.
   1. Sleep de component **Ingesloten reeks** naar beide zones.
   1. Selecteer de ingesloten reeks in een van de zones.
   1. Klik het **Configure** (moersleutel) pictogram aan één van de ingebedde opeenvolgingen in de redacteur.
   1. Selecteer het kanaalpad als **zones** —> **Kanalen** —> **Ingesloten kanalen** —> **Zone1**, zoals in de onderstaande afbeelding wordt getoond.
   1. Op dezelfde manier voeg **Zone2** aan een andere ingebedde opeenvolgingscomponent in de redacteur toe.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-3.png)

### Een locatie en een weergave maken {#creating-location}

U moet een locatie en een weergave maken om de inhoud in de Schermspeler weer te geven. Voer de onderstaande stappen uit om een locatie en een weergave te maken.

1. **Een locatie maken**

   1. Navigeer naar de map **Zones** —> **Locations** .
   1. Selecteer de map **Locations** en klik op **Maken** op de actiebalk.
   1. Selecteer **Locatie** in de wizard **Maken** en klik op **Volgende**.
   1. Voer de **titel** in als **SanJose** en klik op **Maken**.

1. **Weergave maken**

   1. Navigeer naar de map **Zones** —> **Locations** .
   1. Selecteer de locatie **SanJose** en klik op **Maken** op de actiebalk.
   1. Selecteer **Weergave** in de wizard **Maken** en klik op **Volgende**.
   1. Voer de **titel** in als **lobby** en klik op **Maken**.

### Kanalen toewijzen aan de weergave {#channel-channel}

U moet de kanalen aan de vertoning toewijzen om de inhoud te bekijken. Voer de onderstaande stappen uit om het kanaal aan de weergave toe te wijzen.

1. **Kanaal toewijzen aan de weergave**

   1. Navigeer naar **zones** —> **Locaties** —> **SanJose**—> **Lobby**.
   1. Selecteer de weergave **Lobby** en klik op Kanaal **** toewijzen op de actiebalk.
   1. Voer het pad naar het **multikanaalskanaal** in **Kanaalpad**.
   1. Stel de **ondersteunde gebeurtenissen** in op **Eerste Laden**, **Niet-actief scherm** en **Timer**.
   1. Click **Save**.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Op dezelfde manier moet u de andere twee ingebedde kanalen (**Zone1** en **Zone2**) aan deze vertoning toewijzen.
   1. Nadat u alle drie kanalen aan de **Lobby** -weergave hebt toegewezen, kunt u de toegewezen kanalen vanaf het weergavedashboard bekijken.

      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img8.png)


      >[!IMPORTANT]
      >
      > Wanneer u het hoofdkanaal (in dit geval **MultiZone**) aan het scherm hebt toegewezen, is het verplicht om de andere twee ingesloten kanalen **Zone1** en **Zone2** ook aan hetzelfde scherm toe te wijzen.

### Het apparaat registreren {#registering-device}

Nadat u een locatie en een weergave hebt ingesteld, voert u de onderstaande stappen uit om het apparaat te registreren en de weergave aan het apparaat toe te wijzen.

1. **Het apparaat registreren**

   1. Navigeer naar de map **Zones** —> **Devices** .
   1. Selecteer de map **Apparaten** en klik op **Apparaatbeheer** op de actiebalk.
   1. Klik op **Apparaatregistratie** en selecteer het apparaat in behandeling in de lijst.

      >[!NOTE]
      > De titel van het apparaat moet overeenkomen met het apparaattoken (**token** ) dat wordt weergegeven op het tabblad **Apparaatregistratie** .
   1. Als de titel overeenkomt met het apparaattoken, selecteert u het apparaat en klikt u op Apparaat **** registreren op de actiebalk.
   1. Als de registratiecode overeenkomt met de code op het tabblad Apparaatregistratie **van de schermspeler, klikt u op** Valideren **** op de actiebalk.
      ![afbeelding](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Voer de **titel** in als **Chrome-Device1** en klik op **Registreren**.
   1. Selecteer Weergave **** toewijzen en selecteer het pad naar de apparaatconfiguratie.

   >[!NOTE]
   >Als u de inhoud in de Schermspeler probeert te bekijken, zorg ervoor u **Update Offline Inhoud** van het kanaaldashboard voor elk van de kanalen klikt die aan de vertoning worden toegewezen.

### Het resultaat weergeven {#viewing-the-result}

Als u lay-outs met meerdere zones hebt geïmplementeerd met behulp van de voorgaande stappen, wordt de volgende uitvoer weergegeven.

Controleer de schermspeler om de uitvoer weer te geven die de inhoud in twee verschillende zones weergeeft. De linker- en rechterzones (beide gebruiken een ingesloten reeks als een component).

De linkerzone is een reekskanaal en de rechterzone bevat een video.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)


