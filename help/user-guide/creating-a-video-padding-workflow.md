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
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Eerste vereisten**
* **Creërend een Video het Opvullen Werkschema**
   * **Creërend een Werkschema**
   * **Gebruikend het Werkschema in het Project van AEM Screens**

* **Validerend de Output voor het Werkschema**

## Overzicht {#overview}

Het volgende gebruiksgeval bestaat uit het plaatsen van een video (bijvoorbeeld 1280 x 720) in een kanaal met een beeldscherm van 1920 x 1080 en het plaatsen van de video op 0 x 0 (linksboven). De video zou niet op om het even welke manier moeten worden uitgerekt of worden gewijzigd en gebruikt niet **Omslag** in de videocomponent.

De video wordt weergegeven als een object van pixel 1 tot pixel 1280, van pixel 1 tot pixel 720. De rest van het kanaal is de standaardkleur.

## Vereisten {#prerequisites}

Voordat u een workflow voor video maakt, moet u aan de volgende voorwaarden voldoen:

1. Upload een video in de **Assets** omslag in uw instantie van AEM
1. Creeer een project van AEM Screens (bijvoorbeeld, **TestVideoRendition**) en een genoemd kanaal (**VideoRendering**), zoals aangetoond in het hieronder cijfer:

![ screen_shot_2018-10-17at85307pm ](assets/screen_shot_2018-10-17at85307pm.png)

## Workflow voor het opvullen van video&#39;s maken {#creating-a-video-padding-workflow-1}

Als u een workflow voor het opvullen van video&#39;s wilt maken, maakt u een workflow voor uw video en gebruikt u dezelfde workflow in het AEM Screens-projectkanaal.

Voer de onderstaande stappen uit om de workflow te maken en te gebruiken:

1. Een workflow maken
1. De workflow gebruiken in een AEM Screens-project

### Een workflow maken {#creating-a-workflow}

Voer de onderstaande stappen uit om een workflow voor uw video te maken:

1. Navigeer naar uw AEM-exemplaar.
1. Klik op de gereedschappen van de zijspoor.
1. Klik **Werkschema** > **Modellen** zodat kunt u een model creëren.

   ![ screen_shot_2018-10-17at90025pm ](assets/screen_shot_2018-10-17at90025pm.png)

1. Klik **Modellen** > **creeer** > **creeer Model**. Ga de **Titel** (zoals **VideoRendition**) in en **Naam** in **voegt het Model van het Werkschema** toe. Klik **Gedaan** om het werkschemamodel toe te voegen.

   ![ screen_shot_2018-10-17at90747pm ](assets/screen_shot_2018-10-17at90747pm.png)

1. Nadat u het werkschemamodel creeert, klik het model (**VideoRendition**), en klik **uitgeven** van de actiebar.

   ![ screen_shot_2018-10-17at91256pm ](assets/screen_shot_2018-10-17at91256pm.png)

1. Sleep de component **`Command Line`** naar de workflow.

   ![ screen_shot_2018-10-22at14846pm ](assets/screen_shot_2018-10-22at14846pm.png)

1. Klik op de component **`Command Line`** en open het dialoogvenster met eigenschappen.

   ![ screen_shot_2018-10-17at95752pm ](assets/screen_shot_2018-10-17at95752pm.png)

1. Klik de **Argumenten** tabel.
1. In de **Lijn van het Bevel - de dialoogdoos van de Eigenschappen van de Stap**, ga het formaat in de **Types van MIME** (als ***video/mp4***) en het bevel als (*** `/usr/local/Cellar/ffmpeg -i ${filename} -vf "pad=1920:height=1080:x=0:y=0:color=black" cq5dam.video.fullhd-hp.mp4` ***) in. Dit bevel begint het werkschema op het **gebied van Bevelen**.

   Zie de details op **Types van MIME** en **Bevelen** in de nota hieronder.

   ![ screen_shot_2018-10-18at105300am ](assets/screen_shot_2018-10-18at105300am.png)

1. Klik het werkschema (**VideoRenditions**).
1. Klik **Werkschema van het Begin** van de actiebar.

   ![ screen_shot_2018-10-18at105335am ](assets/screen_shot_2018-10-18at105335am.png)

1. In het **dialoogvakje van het Werkschema van de Looppas**, klik de weg van uw activa in **Payload** (als ***/content/dam/huseinpeyda-crossways01_512kb 2.mp4***) en ga **Titel** als ***RunVideo*** in en klik **Looppas**.

   ![ screen_shot_2018-10-18at112043am ](assets/screen_shot_2018-10-18at112043am.png)

### De workflow gebruiken in een AEM Screens-project {#using-the-workflow-in-an-aem-screens-project}

Voer de onderstaande stappen uit om de workflow in uw AEM Screens-project te gebruiken:

1. Navigeer aan een project van AEM Screens (**TestVideoRendition** > **Kanalen** > **VideoRendition**).

   ![ screen_shot_2018-10-17at100715pm ](assets/screen_shot_2018-10-17at100715pm.png)

1. Klik **uitgeven** van de actiebar. Sleep en laat vallen de video die u aanvankelijk aan **Assets** uploadde.

   ![ screen_shot_2018-10-17at102806pm ](assets/screen_shot_2018-10-17at102806pm.png)

1. Wanneer u de video hebt geupload, klik **Voorproef** om de output te bekijken.

   ![ screen_shot_2018-10-22at15151pm ](assets/screen_shot_2018-10-22at15151pm.png)

## De uitvoer voor de workflow valideren {#validating-the-output-for-the-workflow}

U kunt de uitvoer valideren door:

* Een voorvertoning van de video in het kanaal controleren
* Navigeer aan ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, zoals aangetoond in het hieronder cijfer:

![ screen_shot_2018-10-22at14326pm ](assets/screen_shot_2018-10-22at14326pm.png)
