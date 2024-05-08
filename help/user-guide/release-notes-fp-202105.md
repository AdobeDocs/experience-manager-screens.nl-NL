---
title: Opmerkingen bij de release voor Feature Pack 202105
description: Meer informatie over AEM Screens Feature Pack 202105, uitgebracht op 4 juni 2021.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: fc210d9d-5fac-4147-849d-182ffbaf0a5e
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202105 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). AEM Screens biedt ondersteuning voor onderhoud voor het AEM 6.3-schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 8 uitgebracht.

U kunt de nieuwste versie van het Feature Pack voor de AEM Screens 6.5.8 downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID. Ga naar de **Adobe Experience Manager** tabblad en zoeken naar **Schermen** om het nieuwste elementenpakket met de titel **AEM 6.5 Schermen FP8**.

>[!IMPORTANT]
>Installeer de minimale versie van AEM 6.5-functiepakket 8 voor de AMS-aansluiting die werkt nadat u de pakketten hebt geïnstalleerd `screens-cloud-ams-pkg-0.0.20`, `screens-cloud-ams-pkg-0.0.16`en de `screens core bundles`.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202105 is 4 juni 2021.

### Wat is er nieuw? {#what-is-new}

* **Pagina vergrendelen in een AEM Screens-kanaal**

  AEM Screens ondersteunt nu *Een pagina vergrendelen*, zoals reeds geïmplementeerd in AEM Sites. Met Adobe Experience Manager (AEM) kunt u een pagina vergrendelen, zodat niemand anders de inhoud kan bewerken. Deze functie is handig wanneer u meerdere bewerkingen uitvoert op een bepaalde pagina of wanneer u een pagina een korte tijd moet stilzetten.

* **Naam van AEM Screens Player-apparaat**

  De AEM Screens-spelers beschikken nu over de mogelijkheid om een apparaatnaam naar Adobe Experience Manager (AEM) te verzenden.
Wanneer bulkregistratie wordt gebruikt om een apparaat te registreren, wordt standaard een door het systeem gegenereerde gebruikersnaam ingevoerd in het titelveld. Als alternatief kan een klant een asset-tag of een andere vriendelijke naam gebruiken, zodat deze in AEM zichtbaar is en gemakkelijker geschikte inhoud kan toewijzen.

  Raadpleeg de volgende documentatie voor informatie over het configureren van de naam in elk ondersteund besturingssysteem:

   * [Android](/help/user-guide/implementing-android-player.md#name-android)
   * [Windows](/help/user-guide/implementing-windows-player.md#name-windows)
   * [Tizen](/help/user-guide/tizen-player.md#name-tizen)
   * [Chrome-besturingssysteem](/help/user-guide/implementing-chrome-os-player.md#name-chrome)

* **Manifest Generation**

  Snellere kanaalmanifestgeneratie met betere prestaties zoals het toewijzen van minder middelen op de server.

### Opgeloste problemen {#bug-fixes}

* De speler gaf een zwart scherm weer wanneer naar een kanaal met een dynamische ingesloten reeks werd geschakeld.
* De schermspelers blokkeren nu de overstap naar een verbroken kanaal waarmee een fout van 404 of een pagina met een foutbericht verder wordt voorkomen.

### Uitgebrachte AEM Screens-spelers

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak van de Eigenschap 8:

* ChromeOS
* Windows
* Tizen
* Android™
* Linux®

#### Downloads voor AEM Screens Player

Als u de nieuwste AEM Screens Player wilt downloaden en meer wilt weten over de opgeloste problemen, raadpleegt u **[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/index.html)**.
