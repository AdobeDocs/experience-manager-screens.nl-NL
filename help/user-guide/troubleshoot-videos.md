---
title: Configuratie en probleemoplossing voor het afspelen van video
seo-title: Troubleshooting Videos
description: Volg deze pagina om te leren hoe u fouten kunt opsporen in video die wordt afgespeeld in uw kanaal en hoe u problemen kunt oplossen.
seo-description: Follow this page to learn how to troubleshoot videos. When you upload a video to the DAM and add it your channel, you might encounter issues that video might not play in Screens player and this section describes how to debug and troubleshoot video playing in your channel.
uuid: 825b2440-5626-40d5-8c93-7689c24474d4
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
discoiquuid: 65ecc6f1-ba0e-443f-85a1-ac19f9a52c2c
feature: Channels, Interactive
role: Developer
level: Intermediate
exl-id: dfdd58b6-689b-47ca-9459-9c205f1841eb
source-git-commit: 707833ddd8ab2573abcac4e9a77ec88778624435
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# Configuratie en probleemoplossing voor het afspelen van video {#video-playback-configuration-and-troubleshooting}

Wanneer u een video uploadt naar de DAM en deze aan uw kanaal toevoegt, kunnen er problemen optreden die video mogelijk niet afspeelt in de schermspeler.

In de volgende secties wordt beschreven hoe u fouten kunt opsporen in het afspelen van video in uw kanaal en hoe u deze kunt oplossen.

## DAM-uitvoeringen {#dam-renditions}

Nadat u de video naar het kanaal hebt geüpload, moet AEM beginnen met het maken van enkele uitvoeringen voor de video. U kunt uw video&#39;s weergeven onder Middelen.

De video weergeven:

1. Naar uw video navigeren, bijvoorbeeld `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Klik op de video en vouw het menu linksboven uit en klik op **Uitvoeringen**.

Er moeten verschillende uitvoeringen zijn (een MP4 of M4V).

Als er geen uitvoering is, controleert u of mpeg is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.

>[!CAUTION]
>
>Als er geen uitvoering is, controleert u of mpeg is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.
>
>Klikken [hier](https://www.ffmpeg.org/download.html) om fmpeg te installeren.

## Video-elementen {#video-assets}

Als u geen bronkenmerk onder video ziet, kan het zijn dat de video niet is gecodeerd. Als de video op de juiste wijze is getranscodeerd, wordt deze weergegeven in het dashboard, zoals in de onderstaande afbeelding wordt getoond.

Controleer of mpeg is geïnstalleerd en of de videoprofielen zijn geïnstalleerd.

![chlimage_1-2](assets/chlimage_1-2.png)

### Videoprofiel controleren {#checking-video-profile}

1. Ga naar de **Videoprofiel**, dat wil zeggen: `http://localhost:4502/etc/dam/video.html` en klik op **Testvideo uploaden**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Upload een testvideo en klik op **OK** om de transcodering te starten.

   Als de transcode ontbreekt, breid de output van ffmpeg uit om het even welke fouten in de consoleverrichting van ffmpeg te begrijpen.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Ook als de videotranscodes het getranscodeerde bestand kunnen downloaden.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Zorg ervoor dat u voldoende tijd geeft om de video te transcoderen (de tag moet nieuw zijn in plaats van te worden verwerkt) voordat u de video aan een kanaal toevoegt.

### Profiel controleren met een videocomponent {#checking-profile-with-a-video-component}

Controleer de lijst met profielen in het paginaontwerp als de videocomponent niet correct is geconfigureerd.

1. Navigeer naar het kanaal en selecteer het **Ontwerp** in.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Selecteer de video en open de **Bewerken** . Open de **Profielen** tab.

   >[!NOTE]
   >Selecteer verschillende profielen (er moet ten minste het profiel &quot;Hoge kwaliteit H.264&quot; zijn).

### De video controleren in de webspeler {#checking-the-video-in-the-web-player}

Gebruik de **Webspeler** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` om het afspelen in browsers (Chrome en Safari) te valideren. Chrome wordt gebruikt op Android-apparaten terwijl Safari de OSX- en iOS-browser is.

Als de video niet wordt uitgevoerd op Safari, wordt deze niet uitgevoerd in de OSX- en iOS-spelers. Dit is waarschijnlijk een coderingsprobleem en de video moet opnieuw worden gecodeerd.

Ga als volgt te werk om een DAM-workflow te gebruiken om FullHD-uitvoeringen te maken:

1. Ga naar de *workflowmodel-beheerder*, dat wil zeggen `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Selecteer **Element voor schermupdate** model.
1. klikken **Workflow starten** van de actiebalk om het dialoogvenster **Workflow uitvoeren** in.

1. Selecteer uw video-element in het dialoogvenster **Payload**.
1. Klikken **Uitvoeren**.

>[!NOTE]
>
>Zorg ervoor dat u enige tijd hebt om de uitvoeringen te maken, maar laad de webspeler na een paar seconden/minuten (afhankelijk van de videogrootte) opnieuw in Safari.

#### Problemen met AutoPlay-beleidsmarkering oplossen {#troubleshooting-autoplay-policy-flag}

Als de AEM Screens-speler de video oppikt maar niet wordt weergegeven, moet u de markering Beleid automatisch afspelen oplossen.

Voer de onderstaande stappen uit om het probleem met de automatisch afspeelbeleidsmarkering van google op te lossen:

1. Navigeren naar ***chrome://flags/#autoplay-policy***
1. Wijzigen **Beleid voor automatisch afspelen** van **Standaard** tot **geen beweging van de gebruiker vereist**

1. Start de webbrowser opnieuw en werk de speler bij

>[!NOTE]
>
>Voor meer informatie over de beste praktijken voor goede gebruikerservaring met het nieuwe autoplay beleid in Chrome, gelieve documentatie voor te zien *Beleidswijzigingen automatisch afspelen*, dat wil zeggen: `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Video synchroniseren over meerdere spelers {#syncing-video-across-multiple-players}

Als u video&#39;s synchroon wilt afspelen op meerdere apparaten, moet u de absolute strategie gebruiken voor de reeks waarvan de video deel uitmaakt.

#### Vereisten {#requirements}

* identieke 2+ spelers
* ideaal vergelijkbare hardware
* identieke netwerktopologie (de spelers worden verbonden met een server NTP die hun interne systeemklokken richt)

#### Vaststelling van de absolute strategie {#setting-up-the-absolute-strategy}

De absolute strategie:

* berekent een ankertijd (middernacht van de huidige dag)
* berekent de duur van de reeks (som van de duur van alle items in de reeks)
* op om het even welk ogenblik, berekent het welk punt momenteel en het volgende punt door opeenvolging _remaining_time = (current_time - anchor_time) % sequence_duration zou moeten worden gespeeld.

Volg de onderstaande stappen om een absolute strategie op te zetten:

1. Navigeer naar de auteur van het kanaal en selecteer de sequentiecomponent zoals in de onderstaande afbeelding wordt getoond.
1. Open het configuratievenster.
1. Bewerk de **Strategie** en absolute waarden toevoegen.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   >[!NOTE]
   >Het besturingssysteem van de spelers moet dezelfde klok hebben.

**Klokken uitlijnen op OS X** Voer de onderstaande stappen uit om de klokken uit te lijnen op OSX:

1. Openen **Datum en tijd** voorkeuren voor elk OSX-vak
1. Controleren **Datum en tijd automatisch instellen**
1. Plak waarde 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in de dropdown of eenvoudig in werking stellen *sudo ntpdate -u -v 0.pool.ntp.org*
1. De 2+ spelers starten

Het kan enige tijd duren voordat de spelers een nieuwe uitgelijnde reeks beginnen.
