---
title: Opmerkingen bij de release van Screens Feature Pack 20250327
description: Meer informatie over het AEM Screens Feature Pack 20250327 dat op 27 maart 2025 werd uitgegeven.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: cadd83cd-fe64-436d-b3fd-6d72b9565885
source-git-commit: 6cdf350fa4e45b816d50b64252b8ed6d5e0904d0
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 20250327 {#release-notes-for-screens-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van 6.5 Adobe Experience Manager (AEM 6.5). U kunt de recentste versieinformatie van [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-65/content/release-notes/release-notes) krijgen.
>&#x200B;>Adobe raadt u aan FP11.6 te gebruiken met SP(servicepack) >= 21.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 11.6 uitgebracht.

U kunt het recentste Pak van de Eigenschap voor AEM Screens 6.5.11.6 Versie van het [&#x200B; Portaal van de Distributie van de Software &#x200B;](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer aan het **Adobe Experience Manager** lusje en onderzoek naar **Screens** om het recentste Pak van de Eigenschap te krijgen dat als **AEM 6.5 Screens FP11.6** wordt genoemd.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 20250327 is 27 maart 2025.

### Wat is er nieuw? {#what-is-new}

* Deze release verhelpt het pakketconflict waarmee gebruikers worden geconfronteerd met Service Pack 21 en hoger.

* Deze versie verhelpt het probleem met de kaartweergave met SP22 en hoger.

* **Update op de Players van AEM Screens**
   * De op Linux gebaseerde AEM Screens Player is officieel verouderd. Gebruikers wordt aangeraden te migreren naar een ander besturingssysteem dat door AEM Screens wordt ondersteund.
   * Er worden geen updates of verbeteringen aangebracht voor de AEM Screens Player die op Android is gebaseerd. Gebruikers worden aangemoedigd om te migreren naar een alternatief besturingssysteem dat door AEM Screens wordt ondersteund.

### Opgeloste problemen {#bug-fixes}

* Pakketconflict met Service Pack 21 en Screens Feature Pack. (SCRNS-4638)

* Screens-dashboard werkt niet. (SCRNS-4749)

* XSS-probleem op /libs/screens/dcc/components/dashboard/clientlibs/device-clear-cache.js (SCRNS-4761)
