---
title: Video-uitvoeringen
seo-title: Video-uitvoeringen
description: Volg deze pagina voor meer informatie over het genereren van volledige HD-uitvoeringen voor uw project Screens.
seo-description: Volg deze pagina voor meer informatie over het genereren van volledige HD-uitvoeringen voor uw project Screens.
uuid: 0a3b009e-8a97-4396-ad47-97077fe26cde
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 40a182fd-7772-4ef7-b4fd-29ef99390b4a
translation-type: tm+mt
source-git-commit: 209a9a833957d9a8bb7c7ec70ff421514f5b974c

---


# Video-uitvoeringen {#video-renditions}

U kunt handmatige en automatische Full HD-uitvoeringen genereren. In de volgende sectie wordt de workflow beschreven voor het toevoegen van uitvoeringen aan uw elementen.

## Automatisch Full HD-uitvoeringen genereren {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>Als de video-uitvoeringen in AEM-schermen niet optimaal worden afgespeeld op uw apparaat, neemt u contact op met de leverancier van de hardware voor de specificaties van de video. Dit zal helpen om de beste prestaties op het apparaat te krijgen en vandaar uw eigen douanevideoprofiel tot stand te brengen waar u de aangewezen parameters voor FFMPEG verstrekt om uw vertoning te produceren. Gebruik vervolgens de onderstaande stappen om uw aangepaste videoprofiel toe te voegen aan de lijst met profielen.
>
>Zie ook [Problemen oplossen met video](troubleshoot-videos.md) &#39;s om fouten op te sporen en problemen op te lossen bij het afspelen van video in uw kanaal.

Voer de onderstaande stappen uit om automatisch volledige HD-uitvoeringen te genereren:

1. Selecteer de koppeling Adobe Experience Manager (linksboven) en klik op het hamerpictogram om gereedschappen te selecteren om **Workflow** te selecteren.

   Klik op **Modellen** om het workflowmodellenbeheer in te voeren.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. Selecteer het model **DAM Update Asset** en klik op Bewerken op de actiebalk om het venster **DAM Update Asset** te openen.

   ![step5_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. Dubbelklik op de **transcoderingsstap** FFmpeg.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Selecteer het tabblad **Proces** om de procesargumenten te bewerken. Voer de volledige HD-profielen als volgt in op de lijst in **Argumenten** : ***,profile:fullhd-bp,profile:fullhd-hp*** en klik op **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Klik op **Opslaan** linksboven in het scherm **DAM Update Asset** .

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigeer naar **Middelen** en upload een nieuwe video. Klik op de video, open de Renditions side rail en u zult de twee full HD video&#39;s zien.

   ![step10_-_open_videoAsset](assets/step10_-_open_thevideoasset.png)

1. Open **Vertoningen** van de zijspoorstaaf.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Er zullen twee nieuwe full-HD vertoningen verschijnen.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Handmatig Full HD-uitvoeringen genereren {#manually-generating-full-hd-renditions}

Voer de onderstaande stappen uit om handmatig volledige HD-uitvoeringen te genereren:

1. Selecteer de koppeling Adobe Experience Manager (linksboven) en klik op het hamerpictogram om gereedschappen te selecteren om **Workflow** te selecteren.

   Klik op **Modellen** om het workflowmodellenbeheer in te voeren.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. Selecteer het model **Screens Update Asset** en klik op de **Start Workflow** om het dialoogvenster **Workflow** uitvoeren te openen.

   ![step5_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Selecteer de gewenste video in de **Payload** en klik op **Uitvoeren**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigeer naar **Middelen**, boor omlaag naar uw element en klik erop.

   ![stap7_open_theVideoAsset](assets/step7_-_open_thevideoasset.png)

1. Open de **Renditions** side rail en u zult de nieuwe full HD vertoningen merken.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)

