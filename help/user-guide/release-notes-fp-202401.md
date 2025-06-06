---
title: Opmerkingen bij de release van Screens Feature Pack 202401
description: Meer informatie over AEM Screens Feature Pack 202401 uitgebracht op 2 januari 2024.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: 9879f339-e70f-446d-acd3-380016269f27
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202401 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van 6.5 Adobe Experience Manager (AEM 6.5). Krijg de recentste versieinformatie van [ hier ](https://experienceleague.adobe.com/nl/docs/experience-manager-65/content/release-notes/release-notes).

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 11.1 uitgebracht.

U kunt het recentste Pak van de Eigenschap voor AEM Screens 6.5.11.1 Versie van het [ Portaal van de Distributie van de Software ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer aan het **Adobe Experience Manager** lusje en onderzoek naar **Screens** om het recentste Pak van de Eigenschap te krijgen dat als **wordt genoemd AEM 6.5 Screens FP11.1**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202204 is 20 januari 2024.

### Wat is er nieuw? {#what-is-new}

Deze release bevat alleen beveiligingsoplossingen.

### Opgeloste problemen {#bug-fixes}

* XSS-uitgave in het veld Niet-actieve tekst van AEM Screens-apparaat. (SCRNS-2614)

* XSS-probleem op `screens/dashboard/device.html` via het dialoogvenster `Clear cache` Handeling. (SCRNS-2632)

* XSS-probleem in configuratie van schermspeler op `libs/screens/player/browser/firmware.html` . (SCRNS-2652)

* Opgeslagen XSS in de titeltrekkers van apparaten teweegbrengt wanneer een apparaat wordt geschrapt. (SCRNS-2653)

* XSS-probleem op `/libs/screens/core/components/device/info.json.html` . (SCRNS-2659)

* XSS weerspiegeld met de parameter `item` at `/screens/register-device-wizard.html` . (SCRNS-2670)

* XSS weerspiegeld in `screens/dashboard/device.html` via de parameter `returnPage` . (SCRNS-3056)

* Open Omleiding op assign-device-wizard.html. (SCRNS-3444)

* Open Omleiding op het dashboard van het apparaat. (SCRNS-3443)

* XSS-probleem op `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js` . (SCRNS-3459)

* Correctie, Ontbrekend programma voor herhaling en voeg planningknoppen toe: een probleem ontdekt in Kanaalplanning. (SCRNS-2739)
