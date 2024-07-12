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
>Ook, zie [ het Oplossen van problemen Video&#39;s ](troubleshoot-videos.md) om video te zuiveren en problemen op te lossen die in uw kanaal speelt.

Voer de onderstaande stappen uit om automatisch full-HD-uitvoeringen te genereren:

1. Klik de verbinding van Adobe Experience Manager (top-left) en klik het hamerpictogram zodat kunt u **Werkschema** klikken.

   Klik **Modellen**.

   ![ screen_shot_2018-02-01at123407pm ](assets/screen_shot_2018-02-01at123407pm.png)

1. In het beheer van het werkschemamodel, klik het **model van de Activa van de Update van 0} DAM {en klik** uitgeven **van de actiebar.**

   ![ stap5_edit_thedamupdateassetmodel ](assets/step5_-_edit_thedamupdateassetmodel.png)

1. In het **DAM venster van de Activa van de Update**, klik de **Fmpeg transcoding** stap tweemaal.

   ![ screen_shot_2018-02-01at124454pm ](assets/screen_shot_2018-02-01at124454pm.png)

1. Klik het **Proces** lusje.
1. Ga de volledige profielen HD aan de lijst in **Argumenten** als volgt in:
   ***`,profile:fullhd-bp,profile:fullhd-hp`***
1. Klik **OK**.

   ![ screen_shot_2018-02-02at103340am ](assets/screen_shot_2018-02-02at103340am.png)

1. Klik **sparen** op top-left van het **DAM scherm van de Activa van de Update van de Update**.

   ![ screen_shot_2018-02-02at101830am ](assets/screen_shot_2018-02-02at101830am.png)

1. Navigeer aan **Assets** en upload een nieuwe video. Klik op de video en open de rails aan de zijkant van de rendities. Let op de twee full HD video&#39;s.

   ![ step10_-_open_videoasset ](assets/step10_-_open_thevideoasset.png)

1. Open **Vertoningen** van de zijspoor.

   ![ step11_-_open_therenditionssiderail ](assets/step11_-_open_therenditionssiderail.png)

1. Let op twee nieuwe full HD-uitvoeringen.

   ![ step12_-_2_new_renditionsareaddedtothevideo ](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Handmatig Full HD-uitvoeringen genereren {#manually-generating-full-hd-renditions}

Voer de onderstaande stappen uit om volledige HD-uitvoeringen handmatig te genereren:

1. Klik de verbinding van Adobe Experience Manager (verlaten bovenkant) en klik het hamerpictogram zodat kunt u hulpmiddelen klikken en **Werkschema** klikken.

   Klik **Modellen**.

   ![ screen_shot_2018-02-01at123407pm-1 ](assets/screen_shot_2018-02-01at123407pm-1.png)

1. In werkschemamodel beheer, klik het **model van de Activa van de Update van Screens 0} {en klik het** Werkschema van het Begin **om het** de dialoogvakje van het Werkschema van de Looppas **te openen.**

   ![ stap5_start_a_newscreensupdateassetworkflow ](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Klik de gewenste video in de **nuttige lading** en klik **Looppas**.

   ![ stap6_-_select_thedesiredvideo ](assets/step6_-_select_thedesiredvideo.png)

1. Navigeer aan **Assets**, boor neer aan uw activa, en klik het.

   ![ stap7_open_videoasset ](assets/step7_-_open_thevideoasset.png)

1. Open de **zijspoor 0} van Vertoningen {.** Let op de nieuwe full HD-uitvoeringen.

   ![ step8_-_open_therenditionssiderail ](assets/step8_-_open_therenditionssiderail.png)
