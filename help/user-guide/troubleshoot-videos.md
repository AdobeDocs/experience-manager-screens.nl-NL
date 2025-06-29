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
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# Configuratie en probleemoplossing voor videoweergave {#video-playback-configuration-and-troubleshooting}

Wanneer u een video uploadt naar de DAM en deze toevoegt aan uw kanaal, kunnen er problemen optreden waarbij de video mogelijk niet wordt afgespeeld in de AEM Screens Player.

In de volgende secties wordt beschreven hoe u fouten kunt opsporen in het afspelen van video in uw kanaal en hoe u deze kunt oplossen.

## DAM-uitvoeringen {#dam-renditions}

Nadat u de video naar het kanaal hebt geüpload, moet AEM beginnen met het maken van enkele uitvoeringen voor de video. U kunt uw video&#39;s bekijken onder Assets.

De video weergeven:

1. Navigeer naar uw video, bijvoorbeeld `http://localhost:4502/assets.html/content/dam/we-retail/en/videos` .
1. Klik de video en breid het top-linker menu uit en klik **Vertoningen**.

Er moeten verschillende uitvoeringen zijn (een MP4 of M4V).

Als er geen uitvoering is, controleert u of FFMPEG is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.

>[!CAUTION]
>
>Als er geen uitvoering is, controleert u of FFMPEG is geïnstalleerd op het besturingssysteem waarop AEM wordt uitgevoerd.
>
>Klik [ hier ](https://www.ffmpeg.org/download.html) om FFMPEG te installeren.

## Video Assets {#video-assets}

Als u geen bronkenmerk onder video ziet, kan het zijn dat de video niet is gecodeerd. Als de video op de juiste wijze is getranscodeerd, wordt deze weergegeven in het dashboard, zoals hieronder wordt getoond:

Controleer of FFMPEG is geïnstalleerd en of de videoprofielen zijn geïnstalleerd.

![ chlimage_1-2 ](assets/chlimage_1-2.png)

### Videoprofiel controleren {#checking-video-profile}

1. Navigeer aan het **VideoProfiel**, namelijk `http://localhost:4502/etc/dam/video.html` en klik **upload Video van de Test**.

   ![ chlimage_1-3 ](assets/chlimage_1-3.png)

1. Upload een testvideo en klik **O.K.** zodat kunt u met transcoding beginnen.

   Als de getranscodeerde video mislukt, vouwt u de uitvoer van FFMPEG uit om fouten in de uitvoer van de console van FFMPEG te begrijpen.

   ![ chlimage_1-4 ](assets/chlimage_1-4.png)

   Ook als de videotranscodes het getranscodeerde bestand kunnen downloaden.

   ![ chlimage_1-5 ](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Zorg ervoor dat u voldoende tijd hebt om de video te transcoderen (de nieuwe tag wordt weergegeven in plaats van verwerkt) voordat u de video aan een kanaal toevoegt.

### Profiel controleren met een videocomponent {#checking-profile-with-a-video-component}

Controleer de lijst met profielen in het paginaontwerp als de videocomponent niet correct is geconfigureerd.

1. Navigeer aan uw kanaal en klik de **wijze van het Ontwerp**.

   ![ chlimage_1-6 ](assets/chlimage_1-6.png)

1. Klik de video en open **uitgeven** dialoog. Open het **Profielen** lusje.

   >[!NOTE]
   >Klik op verschillende profielen (er moet ten minste het profiel &quot;Hoge kwaliteit H.264&quot; zijn).

### De video controleren in de webspeler {#checking-the-video-in-the-web-player}

Gebruik de **Speler van het Web** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` om playback in browsers (Chrome en Safari) te bevestigen. Chrome wordt gebruikt op Android™-apparaten terwijl Safari de browser OS X en iOS is.

Als de video niet wordt uitgevoerd op Safari, wordt deze ook niet uitgevoerd in de OS X- en iOS-spelers. Dit probleem is waarschijnlijk een coderingsprobleem en de video moet opnieuw worden gecodeerd.

Ga als volgt te werk als u een DAM-workflow wilt gebruiken om FullHD-uitvoeringen te maken:

1. Navigeer aan de *beheerder van het werkschemamodel* die `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models` is.
1. Klik het **model van de Activa van de Update van 0&rbrace; Screens.**
1. Klik **Werkschema van het Begin** van de actiebar.
1. Van het **de dialoogvakje van het Werkschema van de Looppas**, klik uw videoactiva in de **nuttige lading**.
1. Klik **Looppas**.

>[!NOTE]
>
>Zorg ervoor dat u enige tijd hebt om de uitvoeringen te maken, maar laad de webspeler na een paar seconden/minuten (afhankelijk van de videogrootte) opnieuw in Safari.

#### Problemen met AutoPlay-beleidsmarkering oplossen {#troubleshooting-autoplay-policy-flag}

Als de AEM Screens Player de video oppikt maar niet weergeeft, los dan de markering Beleid automatisch afspelen problemen op.

Voer de onderstaande stappen uit om een probleem met de Google-markering voor automatisch afspelen op te lossen:

1. Navigeer aan ***chrome://flags/#autoplay-policy***
1. Het beleid van Autoplay van de verandering **van** Gebrek **aan** geen gebruikersbeweging wordt vereist **&#x200B;**

1. Start de webbrowser opnieuw en werk de speler bij

>[!NOTE]
>
>Meer informatie over beste praktijken voor goede gebruikerservaring met het nieuwe autoplay beleid in Chrome. Zie *Veranderingen van het Beleid Autoplay* bij `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

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

1. Navigeer naar de auteur van het kanaal en klik op de component sequence zoals in de onderstaande afbeelding wordt weergegeven.
1. Open het configuratievenster.
1. Bewerk de **Strategie** en voeg absolute toe.

   ![ chlimage_1-8 ](assets/chlimage_1-8.png)

   >[!NOTE]
   >Het besturingssysteem van de spelers moet dezelfde klok hebben.

**het Uitlijnen van Klokken op OS X** volg de hieronder stappen om de klokken op OS X te richten:

1. Open **voorkeur van 0&rbrace; Datum &amp; van de Tijd &lbrace;op elk OS X vakje**
1. Controle **vastgestelde datum en tijd automatisch**
1. Waarde plakken 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in de vervolgkeuzelijst of gewoon uitvoeren *`sudo ntpdate -u -v 0.pool.ntp.org`*
1. De 2+ spelers starten

Het kan enige tijd duren voordat de spelers een nieuwe uitgelijnde reeks beginnen.
