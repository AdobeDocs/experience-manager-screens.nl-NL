---
title: Video-uitvoeringen
seo-title: Video Renditions
description: Volg deze pagina voor meer informatie over het genereren van volledige HD-uitvoeringen voor uw project Screens.
seo-description: Follow this page to learn about generating full HD renditions for your Screens project.
uuid: 0a3b009e-8a97-4396-ad47-97077fe26cde
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 40a182fd-7772-4ef7-b4fd-29ef99390b4a
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 752c74d7-5d6d-4363-97ef-b96e97d2f6b1
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Video-uitvoeringen {#video-renditions}

U kunt handmatige en automatische Full HD-uitvoeringen genereren. In de volgende sectie wordt de workflow beschreven voor het toevoegen van uitvoeringen aan uw elementen.

## Automatisch Full HD-uitvoeringen genereren  {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>Als de AEM Screens-video-uitvoeringen niet optimaal worden afgespeeld op uw apparaat, neemt u contact op met de hardwareleverancier voor de specificaties van de video. Dit zal helpen om de beste prestaties op het apparaat te krijgen en vandaar uw eigen douanevideoprofiel tot stand te brengen waar u de aangewezen parameters voor FFMPEG verstrekt om uw vertoning te produceren. Gebruik vervolgens de onderstaande stappen om uw aangepaste videoprofiel toe te voegen aan de lijst met profielen.
>
>Zie ook [Problemen met video&#39;s oplossen](troubleshoot-videos.md) om fouten op te sporen in het afspelen van video in uw kanaal en deze problemen op te lossen.

Voer de onderstaande stappen uit om automatisch volledige HD-uitvoeringen te genereren:

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en klik op het hamerpictogram om de gereedschappen te selecteren **Workflow**.

   Klikken **Modellen** om het workflowmodellenbeheer in te voeren.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. Selecteer **DAM Update-element** model en klik op Bewerken op de actiebalk om het dialoogvenster **DAM Update-element** venster.

   ![step5_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. Dubbelklik op de knop **MPEG-transcodering** stap.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Selecteer **Proces** om de procesargumenten te bewerken. Geef de volledige HD-profielen op in de lijst in **Argumenten** als: ***,profile:fullhd-bp,profile:fullhd-hp*** en klik op **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Klikken **Opslaan** linksboven in het dialoogvenster **DAM Update-element** scherm.

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigeren naar **Activa** en uploadt u een nieuwe video. Klik op de video, open de Renditions side rail en u zult de twee full HD video&#39;s zien.

   ![step10_-_open_videoAsset](assets/step10_-_open_thevideoasset.png)

1. Openen **Uitvoeringen** van de zijspoor.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Er zullen twee nieuwe full-HD vertoningen verschijnen.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Handmatig Full HD-uitvoeringen genereren {#manually-generating-full-hd-renditions}

Voer de onderstaande stappen uit om handmatig volledige HD-uitvoeringen te genereren:

1. Selecteer de Adobe Experience Manager-koppeling (linksboven) en klik op het hamerpictogram om de gereedschappen te selecteren **Workflow**.

   Klikken **Modellen** om het workflowmodellenbeheer in te voeren.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. Selecteer **Element voor schermupdate** en klik op de knop **Workflow starten** om de **Workflow uitvoeren** in.

   ![step5_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Selecteer de gewenste video in het dialoogvenster **Payload** en klik op **Uitvoeren**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigeren naar **Activa**, gaat u naar uw element en klikt u erop.

   ![stap7_open_theVideoAsset](assets/step7_-_open_thevideoasset.png)

1. Open de **Uitvoeringen** en u zult de nieuwe full-HD vertoningen merken.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)
