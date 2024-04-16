---
title: Workflow voor het opvullen van video's maken
description: Meer informatie over het maken van een video-opvulling in de workflow voor uw elementen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 16180f96-2855-4250-9d55-24ed77a908b7
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Vereisten**
* **Workflow voor het opvullen van video&#39;s maken**
   * **Een workflow maken**
   * **De workflow in AEM Screens Project gebruiken**

* **De uitvoer voor de workflow valideren**

## Overzicht {#overview}

Het volgende gebruiksgeval bestaat uit het plaatsen van een video (bijvoorbeeld 1280 x 720) in een kanaal met een beeldscherm van 1920 x 1080 en het plaatsen van de video op 0 x 0 (linksboven). De video mag op geen enkele manier worden uitgerekt of gewijzigd en gebruikt deze **Omslag** in de videocomponent.

De video wordt weergegeven als een object van pixel 1 tot pixel 1280, van pixel 1 tot pixel 720, en de rest van het kanaal is de standaardkleur.

## Vereisten {#prerequisites}

Voordat u een workflow voor video maakt, moet u aan de volgende voorwaarden voldoen:

1. Een video uploaden in **Activa** map in uw AEM-instantie
1. Een AEM Screens-project maken (bijvoorbeeld **TestVideoRendition**) en een kanaal genoemd (**VideoRendering**), zoals weergegeven in onderstaande afbeelding:

![screen_shot_2018-10-17at85307pm](assets/screen_shot_2018-10-17at85307pm.png)

## Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow-1}

Als u een workflow voor het opvullen van video&#39;s wilt maken, maakt u een workflow voor uw video en gebruikt u dezelfde workflow in het AEM Screens-projectkanaal.

Voer de onderstaande stappen uit om de workflow te maken en te gebruiken:

1. Een workflow maken
1. De workflow gebruiken in een AEM Screens-project

### Een workflow maken {#creating-a-workflow}

Voer de onderstaande stappen uit om een workflow voor uw video te maken:

1. Navigeer naar de AEM.
1. Klik op gereedschappen van de zijbalk.
1. Klikken **Workflow** > **Modellen** zodat u een model kunt maken.

   ![screen_shot_2018-10-17at90025pm](assets/screen_shot_2018-10-17at90025pm.png)

1. Klikken **Modellen** > **Maken** > **Model maken**. Voer de **Titel** (as **VideoRendition**) en **Naam** in de **Workflowmodel toevoegen**. Klikken **Gereed** om het workflowmodel toe te voegen.

   ![screen_shot_2018-10-17at90747pm](assets/screen_shot_2018-10-17at90747pm.png)

1. Nadat u het workflowmodel hebt gemaakt, klikt u op het model (**VideoRendition**) en klik op **Bewerken** in de actiebalk.

   ![screen_shot_2018-10-17at91256pm](assets/screen_shot_2018-10-17at91256pm.png)

1. Sleep de **`Command Line`** aan uw werkstroom.

   ![screen_shot_2018-10-22at14846pm](assets/screen_shot_2018-10-22at14846pm.png)

1. Klik op de knop **`Command Line`** en opent u het dialoogvenster met eigenschappen.

   ![screen_shot_2018-10-17at95752pm](assets/screen_shot_2018-10-17at95752pm.png)

1. Klik op de knop **Argumenten** tab.
1. In de **Opdrachtregel - stapeigenschappen** de notatie in het dialoogvenster **MIME-typen** (as ***video/mp4***) en de opdracht als (***/usr/local/Cellar/ffmpeg -i ${filename} -vf &quot;pad=1920:height=1080:x=0:y=0:color=black&quot; cq5dam.video.fullhp.mp4**). Met deze opdracht wordt de workflow in het dialoogvenster **Opdrachten** veld.

   Zie de details op **MIME-typen** en **Opdrachten** in de onderstaande opmerking.

   ![screen_shot_2018-10-18at105300am](assets/screen_shot_2018-10-18at105300am.png)

1. Klik op de workflow (**VideoRenditions**).
1. Klikken **Workflow starten** in de actiebalk.

   ![screen_shot_2018-10-18at105335am](assets/screen_shot_2018-10-18at105335am.png)

1. In de **Workflow uitvoeren** klikt u op het pad van uw element in het dialoogvenster **Payload** (as ***/content/dam/huseinpeyda-crossroad01_512kb 2.mp4***) en voert u de **Titel** als ***RunVideo*** en klik op **Uitvoeren**.

   ![screen_shot_2018-10-18at112043am](assets/screen_shot_2018-10-18at112043am.png)

### De workflow gebruiken in een AEM Screens-project {#using-the-workflow-in-an-aem-screens-project}

Voer de onderstaande stappen uit om de workflow in uw AEM Screens-project te gebruiken:

1. Navigeren naar een AEM Screens-project (**TestVideoRendition** > **Kanalen** >**VideoRendition**).

   ![screen_shot_2018-10-17at100715pm](assets/screen_shot_2018-10-17at100715pm.png)

1. Klikken **Bewerken** in de actiebalk. Sleep de video die u aanvankelijk hebt geüpload naar **Activa**.

   ![screen_shot_2018-10-17at102806pm](assets/screen_shot_2018-10-17at102806pm.png)

1. Wanneer u de video hebt geüpload, klikt u op **Voorvertoning** om de uitvoer weer te geven.

   ![screen_shot_2018-10-22at15151pm](assets/screen_shot_2018-10-22at15151pm.png)

## De uitvoer voor de workflow valideren {#validating-the-output-for-the-workflow}

U kunt de uitvoer valideren door:

* De voorvertoning van de video in het kanaal controleren
* Ga naar de ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, zoals weergegeven in onderstaande afbeelding:

![screen_shot_2018-10-22at14326pm](assets/screen_shot_2018-10-22at14326pm.png)
