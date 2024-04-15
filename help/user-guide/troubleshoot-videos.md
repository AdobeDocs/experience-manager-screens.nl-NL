---
title: Configuratie en probleemoplossing voor videoweergave
description: Leer hoe u fouten kunt opsporen in het afspelen van video in uw kanaal voor AEM Screens en hoe u problemen kunt oplossen.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
feature: Channels, Interactive
role: Developer
level: Intermediate
exl-id: dfdd58b6-689b-47ca-9459-9c205f1841eb
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 0%

---

# Configuratie en probleemoplossing voor videoweergave {#video-playback-configuration-and-troubleshooting}

Wanneer u een video uploadt naar de DAM en het kanaal toevoegt, kunnen er problemen optreden waarbij de video mogelijk niet wordt afgespeeld in de AEM Screens-speler.

In de volgende secties wordt beschreven hoe u fouten kunt opsporen in het afspelen van video in uw kanaal en hoe u deze kunt oplossen.

## DAM-uitvoeringen {#dam-renditions}

Nadat u de video naar het kanaal hebt geüpload, moet AEM beginnen met het maken van enkele uitvoeringen voor de video. U kunt uw video&#39;s weergeven onder Middelen.

De video weergeven:

1. Naar uw video navigeren, bijvoorbeeld `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Klik op de video en vouw het menu linksboven uit en klik op **Uitvoeringen**.

Er moeten verschillende uitvoeringen zijn (een MP4 of M4V).

Als er geen uitvoering is, moet u ervoor zorgen dat mpeg is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.

>[!CAUTION]
>
>Als er geen uitvoering is, moet u ervoor zorgen dat mpeg is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.
>
>Klikken [hier](https://www.ffmpeg.org/download.html) om fmpeg te installeren.

## Video-elementen {#video-assets}

Als u geen bronkenmerk onder video ziet, kan het zijn dat de video niet is gecodeerd. Als de video op de juiste wijze is getranscodeerd, wordt deze weergegeven in het dashboard, zoals hieronder wordt getoond:

Controleer of mpeg is geïnstalleerd en de videoprofielen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Videoprofiel controleren {#checking-video-profile}

1. Ga naar de **Videoprofiel**, dat wil zeggen: `http://localhost:4502/etc/dam/video.html` en klik op **Testvideo uploaden**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Upload een testvideo en klik op **OK** zodat u met het transcoderen kunt beginnen.

   Als de getranscodeerde video ontbreekt, breid de output van ffmpeg uit om het even welke fouten in de consoloutput van ffmpeg te begrijpen.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Ook als de videotranscodes het getranscodeerde bestand kunnen downloaden.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Zorg ervoor dat u voldoende tijd hebt om de video te transcoderen (de nieuwe tag wordt weergegeven in plaats van verwerkt) voordat u de video aan een kanaal toevoegt.

### Profiel controleren met een videocomponent {#checking-profile-with-a-video-component}

Controleer de lijst met profielen in het paginaontwerp als de videocomponent niet correct is geconfigureerd.

1. Navigeer naar het kanaal en selecteer het **Ontwerp** -modus.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Selecteer de video en open de **Bewerken** in. Open de **Profielen** tab.

   >[!NOTE]
   >Selecteer verschillende profielen (er moet ten minste het profiel &quot;Hoge kwaliteit H.264&quot; zijn).

### De video controleren in de webspeler {#checking-the-video-in-the-web-player}

Gebruik de **Webspeler** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` om het afspelen in browsers (Chrome en Safari) te valideren. Chrome wordt gebruikt op Android™-apparaten terwijl Safari de OS X- en iOS-browser is.

Als de video niet wordt uitgevoerd op Safari, wordt deze ook niet uitgevoerd in de OS X- en iOS-spelers. Dit is waarschijnlijk een coderingsprobleem en de video moet opnieuw worden gecodeerd.

Ga als volgt te werk als u een DAM-workflow wilt gebruiken om FullHD-uitvoeringen te maken:

1. Ga naar de *workflowmodel-beheerder* dat `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Selecteer de **Element voor schermupdate** model.
1. Selecteren **Workflow starten** in de actiebalk.
1. Van de **Workflow uitvoeren** selecteert u uw video-element in het dialoogvenster **Payload**.
1. Selecteren **Uitvoeren**.

>[!NOTE]
>
>Zorg ervoor dat u enige tijd hebt om de uitvoeringen te maken, maar laad de webspeler na een paar seconden/minuten (afhankelijk van de videogrootte) opnieuw in Safari.

#### Problemen met AutoPlay-beleidsmarkering oplossen {#troubleshooting-autoplay-policy-flag}

Als de AEM Screens-speler de video oppikt maar niet wordt weergegeven, moet u de markering Beleid automatisch afspelen oplossen.

Voer de onderstaande stappen uit om een probleem met de Google-markering voor automatisch afspelen op te lossen:

1. Navigeren naar ***chrome://flags/#autoplay-policy***
1. Wijzigen **Beleid voor automatisch afspelen** van **Standaard** tot **geen beweging van de gebruiker is vereist**

1. Start de webbrowser opnieuw en werk de speler bij

>[!NOTE]
>
>Meer over de beste praktijken voor goede gebruikerservaring met het nieuwe autoplay beleid in Chrome leren, zie documentatie voor *Beleidswijzigingen automatisch uitvoeren* om `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Video synchroniseren over meerdere spelers {#syncing-video-across-multiple-players}

Als u video&#39;s synchroon wilt afspelen op meerdere apparaten, moet u de absolute strategie gebruiken voor de reeks waarvan de video deel uitmaakt.

#### Vereisten {#requirements}

* identieke 2+ spelers
* ideaal vergelijkbare hardware
* identieke netwerktopologie (de spelers worden verbonden met een server NTP die hun interne systeemklokken richt)

#### Vaststelling van de absolute strategie {#setting-up-the-absolute-strategy}

De absolute strategie:

* Berekent een ankertijd (middernacht van de huidige dag).
* Berekent de duur van de reeks (som van de duur van alle items).
* Op om het even welk ogenblik, berekent het welk punt momenteel en het volgende punt door opeenvolging _remaining_time = (current_time - anchor_time) % sequence_duration zou moeten worden gespeeld.

Volg de onderstaande stappen om een absolute strategie op te zetten:

1. Navigeer naar de auteur van het kanaal en selecteer de sequentiecomponent zoals in de onderstaande afbeelding wordt getoond.
1. Open het configuratievenster.
1. Bewerk de **Strategie** en voeg absolute waarden toe.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   >[!NOTE]
   >Het besturingssysteem van de spelers moet dezelfde klok hebben.

**Klokken uitlijnen op OS X** Voer de onderstaande stappen uit om de klokken uit te lijnen op OS X:

1. Openen **Datum en tijd** voorkeuren voor elk OS X-vak
1. Controleren **Datum en tijd automatisch instellen**
1. De waarde 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com plakken in de vervolgkeuzelijst of gewoon uitvoeren *sudo ntpdate -u-v 0.pool.ntp.org*
1. De 2+ spelers starten

Het kan enige tijd duren voordat de spelers een nieuwe uitgelijnde reeks beginnen.
