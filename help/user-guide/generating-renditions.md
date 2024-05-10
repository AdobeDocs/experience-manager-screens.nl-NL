---
title: Video-uitvoeringen
description: Leer hoe u full HD-uitvoeringen genereert voor uw AEM Screens-project.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 752c74d7-5d6d-4363-97ef-b96e97d2f6b1
source-git-commit: a89aec16bb36ecbde8e417069e9ed852363acd82
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Video-uitvoeringen {#video-renditions}

U kunt handmatige en automatische full-HD uitvoeringen genereren. In de volgende sectie wordt de workflow beschreven voor het toevoegen van uitvoeringen aan uw elementen.

## Automatisch Full HD-uitvoeringen genereren {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>Als de AEM Screens-video-uitvoeringen niet optimaal worden afgespeeld op uw apparaat, neemt u contact op met de hardwareleverancier voor de specificaties van de video. Zo krijgt u de beste prestaties op het apparaat. Hiermee kunt u uw eigen aangepaste videoprofiel maken waarin u de juiste parameters voor FFMPEG opgeeft om uw vertoning te genereren. Vervolgens kunt u met de onderstaande stappen uw aangepaste videoprofiel toevoegen aan de lijst met profielen.
>
>Zie ook [Video&#39;s oplossen](troubleshoot-videos.md) om fouten op te sporen in het afspelen van video in uw kanaal en deze problemen op te lossen.

Voer de onderstaande stappen uit om automatisch full-HD-uitvoeringen te genereren:

1. Klik op de Adobe Experience Manager-koppeling (linksboven) en klik op het hamerpictogram zodat u op **Workflow**.

   Klikken **Modellen**.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. Klik in het workflowmodelbeheer op de knop **DAM Update-element** model en klik **Bewerken** in de actiebalk.

   ![step5_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. In de **DAM Update-element** venster, dubbelklikt u op de knop **MPEG-transcodering** stap.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Klik op de knop **Proces** tab.
1. Geef de volledige HD-profielen op in de lijst in **Argumenten** als volgt:
   ***`,profile:fullhd-bp,profile:fullhd-hp`***
1. Klikken **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Klikken **Opslaan** linksboven in het dialoogvenster **DAM Update-element** scherm.

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigeren naar **Activa** en uploadt u een nieuwe video. Klik op de video en open de rails aan de zijkant van de rendities. Let op de twee full HD video&#39;s.

   ![step10_-_open_videoAsset](assets/step10_-_open_thevideoasset.png)

1. Openen **Uitvoeringen** van de zijspoor.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Let op twee nieuwe full HD-uitvoeringen.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Handmatig Full HD-uitvoeringen genereren {#manually-generating-full-hd-renditions}

Voer de onderstaande stappen uit om volledige HD-uitvoeringen handmatig te genereren:

1. Klik op de Adobe Experience Manager-koppeling (linksboven) en klik op het hamerpictogram zodat u op gereedschappen kunt klikken en op **Workflow**.

   Klikken **Modellen**.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. Klik in workflowmodelbeheer op de knop **Element voor schermupdate** en klik op de knop **Workflow starten** om de **Workflow uitvoeren** in.

   ![step5_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Klik op de gewenste video in het deelvenster **Payload** en klik op **Uitvoeren**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigeren naar **Activa**, gaat u naar uw element en klikt u erop.

   ![stap7_open_theVideoAsset](assets/step7_-_open_thevideoasset.png)

1. Open de **Uitvoeringen** zijspoor. Let op de nieuwe full HD-uitvoeringen.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)
