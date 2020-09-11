---
title: Ondersteuningscontrole
seo-title: Ondersteuningscontrole voor AEM Screens
description: De pagina beschrijft Support Monitoring for AEM Screens Best Practices Guide
seo-description: De pagina beschrijft Support Monitoring for AEM Screens Best Practices Guide
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---


# Ondersteuningscontrole {#support-monitoring}

Deze sectie verstrekt beste praktijken met betrekking tot het beheren van apparaat en inhoudanomalieën in een digitaal ondertekeningsproject.

De controle van de steun omvat:

* **Apparaatcontrole**
* **Inhoud controleren**

## Inhoud controleren {#content-monitoring}

Met contentcontrole kunt u problemen oplossen met betrekking tot inhoud die niet correct op het scherm wordt weergegeven:

1. Als een probleem met een leeg scherm wordt aangetroffen:

   * Controleer de *voorvertoning* om te zien of het kanaal een zwart scherm weergeeft
   * Registreer een *lokale chroomspeler* (als extensie) op uw laptop voor dat beeldscherm en controleer of dat een zwart scherm weergeeft.
   * Klik met de rechtermuisknop en controleer de *toepasselijke logboeken*.

   Als dit niet gebeurt op de lokale speler, maar alleen op het apparaat:

   * Controleer het *mediatype* (dat wordt gebruikt) dat mogelijk problemen heeft op dat apparaat en bevestig ook of de inhoud lokaal is gedownload (de cache van het kanaal voor de beheerdersinterface is leeg).
   * Neem alle *apparaatlogboeken* op in het ticket voor snelle probleemoplossing.
   * *Verzamel logboeken* van het apparaat van AEM.


## Apparaatcontrole {#device-monitoring}

Apparaatbewaking met betrekking tot de bewaking van het fysieke apparaat als er een probleem optreedt met een leeg scherm:

1. Als een probleem met een leeg scherm wordt aangetroffen:

   * Controleer of de *weergave* is ingeschakeld.
   * Controleer of de *computer* is ingeschakeld en het signaal verzendt.
   * Klik met de rechtermuisknop, inspecteer en controleer de *toepasselijke logboeken*.

