---
title: Workflow voor het opvullen van video's maken
seo-title: Workflow voor het opvullen van video's maken
description: Volg deze pagina voor meer informatie over het maken van een video-opvulling in de workflow voor uw elementen.
seo-description: Volg deze pagina voor meer informatie over het maken van een video-opvulling in de workflow voor uw elementen.
uuid: c0f004ca-c934-47f8-bcdc-da58ea62118e
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
discoiquuid: a90e3950-c95a-4aff-8cb3-9229c660a815
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Vereisten**
* **Workflow voor het opvullen van video&#39;s maken**
   * **Een workflow maken**
   * **De workflow gebruiken in AEM Screens Project**

* **De uitvoer voor de workflow valideren**

## Overzicht {#overview}

Het volgende gebruiksgeval betreft het plaatsen van een video (voorbeeld: 1280 x 720) in een kanaal met een beeldscherm van 1920 x 1080 en een video van 0 x 0 (linksboven). De video mag op geen enkele manier worden uitgerekt of gewijzigd en gebruikt **Omslag** niet in de video-component.

De video wordt weergegeven als een object van pixel 1 tot pixel 1280, van pixel 1 tot pixel 720, en de rest van het kanaal als standaardkleur.

## Vereisten {#prerequisites}

Vul de volgende voorwaarden in voordat u een workflow voor video maakt:

1. Een video uploaden naar de map **Middelen** in uw AEM-instantie
1. Maak een AEM-schermproject (bijvoorbeeld **TestVideoRendition**) en een kanaal met de naam (**VideoRendering**), zoals in de onderstaande afbeelding wordt getoond:

![screen_shot_2018-10-17at85307pm](assets/screen_shot_2018-10-17at85307pm.png)

## Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow-1}

Als u een werkstroom voor het opvullen van video wilt maken, moet u een werkstroom voor uw video maken en vervolgens hetzelfde gebruiken in het projectkanaal voor AEM-schermen.

Voer de onderstaande stappen uit om de workflow te maken en te gebruiken:

1. Een workflow maken
1. De workflow gebruiken in een AEM-schermproject

### Een workflow maken {#creating-a-workflow}

Voer de onderstaande stappen uit om een workflow voor uw video te maken:

1. Navigeer naar uw AEM-exemplaar en klik op gereedschappen vanaf de zijspoor. Selecteer **Workflow** —> **Modellen** om een nieuw model te maken.

   ![screen_shot_2018-10-17at90025pm](assets/screen_shot_2018-10-17at90025pm.png)

1. Klik op **Modellen** —> **Maken** —> **Model** maken. Voer de **titel** (als **VideoRendition**) en de **naam** in het **workflowmodel** toevoegen in. Klik op **Gereed** om het workflowmodel toe te voegen.

   ![screen_shot_2018-10-17at90747pm](assets/screen_shot_2018-10-17at90747pm.png)

1. Nadat u het workflowmodel hebt gemaakt, selecteert u het model (**VideoRendition**) en klikt u op **Bewerken** op de actiebalk.

   ![screen_shot_2018-10-17at91256pm](assets/screen_shot_2018-10-17at91256pm.png)

1. Sleep de component **Command Line **naar uw werkstroom.

   ![screen_shot_2018-10-22at14846pm](assets/screen_shot_2018-10-22at14846pm.png)

1. Selecteer de component **Opdrachtregel** en open het dialoogvenster Eigenschappen.

   ![screen_shot_2018-10-17at95752pm](assets/screen_shot_2018-10-17at95752pm.png)

1. Selecteer het tabblad **Argumenten** om de velden in te voeren in het dialoogvenster **Opdrachtregel - Step Properties** .

   Voer de indeling in de **MIME-typen** (als ***video/mp4***) en de opdracht in als (**/usr/local/Cellar/ffmpeg -i ${filename} -vf &quot;pad=1920:height=1080:x=0:y=0:color=black&quot; cq5dam.video.fullhp .mp4***) om de workflow te starten in het veld **Opdrachten** .

   Raadpleeg de details over **MIME-typen** en - **opdrachten** in de onderstaande opmerking.

   ![screen_shot_2018-10-18at105300am](assets/screen_shot_2018-10-18at105300am.png)

1. Selecteer de workflow (**VideoRenditions**) en klik op Workflow **** starten op de actiebalk om het dialoogvenster Workflow **** uitvoeren te openen.

   ![screen_shot_2018-10-18at105335am](assets/screen_shot_2018-10-18at105335am.png)

1. Selecteer het pad van uw element in de **Payload** (als ***/content/dam/huseinpeyda-crossroad01_512kb 2.mp4***) en voer de **Title **(as ***RunVideo***) in en klik op **Uitvoeren**.

   ![screen_shot_2018-10-18at112043am](assets/screen_shot_2018-10-18at112043am.png)

### De workflow gebruiken in een AEM-schermproject {#using-the-workflow-in-an-aem-screens-project}

Voer de onderstaande stappen uit om de workflow in uw AEM Screens-project te gebruiken:

1. Navigeer naar een AEM Screens-project (**TestVideoRendition** —> **Kanalen** —>**VideoRendition**).

   ![screen_shot_2018-10-17at100715pm](assets/screen_shot_2018-10-17at100715pm.png)

1. Klik op **Bewerken** op de actiebalk. Sleep de video die u aanvankelijk naar **Elementen** hebt geüpload.

   ![screen_shot_2018-10-17at102806pm](assets/screen_shot_2018-10-17at102806pm.png)

1. Nadat u de video hebt geüpload, klikt u op **Voorvertoning** om de uitvoer weer te geven.

   ![screen_shot_2018-10-22at15151pm](assets/screen_shot_2018-10-22at15151pm.png)

## De uitvoer voor de workflow valideren {#validating-the-output-for-the-workflow}

U kunt de uitvoer valideren door:

* De voorvertoning van de video in het kanaal controleren
* Ga naar ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, zoals getoond in de hieronder figuur:

![screen_shot_2018-10-22at14326pm](assets/screen_shot_2018-10-22at14326pm.png)
