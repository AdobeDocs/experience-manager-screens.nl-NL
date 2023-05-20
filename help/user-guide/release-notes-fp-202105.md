---
title: Opmerkingen bij de release voor Feature Pack 202105
description: "Volg deze pagina voor meer informatie over het AEM Screens Feature Pack 202105, uitgebracht op 4 juni 2021."
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: fc210d9d-5fac-4147-849d-182ffbaf0a5e
source-git-commit: 02bc399d61f5666918caad9fce3d69d63f0782d7
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202105 {#release-notes-for-feature-pack}

>[!CAUTION]
>We raden u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). Schermen bieden onderhoudsondersteuning voor AEM 6.3 Schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 8 uitgebracht.

U kunt het nieuwste functiepakket voor de AEM Screens 6.5.8-versie downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID. Navigeren naar **Adobe Experience Manager** tabblad en zoeken naar **Schermen** om het nieuwste functiepakket met de naam **AEM 6.5 Schermen FP8**.

>[!IMPORTANT]
>Als u de pakketten hebt geïnstalleerd, moet u een minimale versie van AEM 6.5 Feature Pack 8 voor de AMS-aansluiting installeren `screens-cloud-ams-pkg-0.0.20`, `screens-cloud-ams-pkg-0.0.16` en de `screens core bundles`.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202105 is 4 juni 2021.

### Wat is er nieuw? {#what-is-new}

* **Pagina vergrendelen in een AEM Screens-kanaal**

   AEM Screens ondersteunt nu *Een pagina vergrendelen*, zoals reeds geïmplementeerd in AEM Sites. Met Adobe Experience Manager (AEM) kunt u een pagina vergrendelen, zodat niemand anders de inhoud kan wijzigen. Dit is handig wanneer u veel bewerkingen uitvoert op een bepaalde pagina of wanneer u een pagina even wilt stilzetten.

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

* De speler toonde een zwart scherm wanneer het schakelen aan kanaal dat dynamische ingebedde opeenvolging bevat.
* De schermspelers blokkeren nu de overstap naar een verbroken kanaal waarmee nog meer 404 fouten of een pagina met een foutbericht worden voorkomen.

### Uitgebrachte AEM Screens-spelers {#released-aem-screens-players}

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak van de Eigenschap 8:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### Downloads voor AEM Screens Player  {#aem-screens-player-downloads}

Als u de nieuwste AEM Screens-speler wilt downloaden en meer wilt weten over de opgeloste problemen, raadpleegt u **[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/index.html)**.
