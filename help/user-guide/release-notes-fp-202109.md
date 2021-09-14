---
title: Opmerkingen bij de release voor Feature Pack 202109
description: '"Volg deze pagina voor meer informatie over het AEM Screens Feature Pack 202105, uitgebracht op 22 september 2021."'
feature: Feature Pack
role: Developer
level: Intermediate
index: false
source-git-commit: e96c314ea7487932d2ab994ffc41ca8d2af61c5c
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>We raden u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). Schermen bieden onderhoudsondersteuning voor AEM 6.3 Schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 9 uitgebracht.

U kunt het recentste eigenschappak voor AEM Screens 6.5.9 Versie van [het Portaal van de Distributie van de Software](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer naar **Adobe Experience Manager** tab en zoek **Screens** om het nieuwste functiepakket met de naam **AEM 6.5 Screens FP9** te krijgen.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202109 is 9 september 2021.

### Wat is er nieuw? {#what-is-new}

* **Pagina vergrendelen in een AEM Screens-kanaal**

   AEM Screens biedt nu ondersteuning voor *Een pagina vergrendelen*, zoals al is geïmplementeerd in AEM Sites. Met Adobe Experience Manager (AEM) kunt u een pagina vergrendelen, zodat niemand anders de inhoud kan wijzigen. Dit is handig wanneer u veel bewerkingen uitvoert op een bepaalde pagina of wanneer u een pagina even wilt stilzetten.

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

Raadpleeg **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)** voor meer informatie over de opgeloste problemen.
