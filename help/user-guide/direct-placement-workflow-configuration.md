---
title: 'Configuratie werkstroom voor directe plaatsing '
seo-title: Configuratie werkstroom voor directe plaatsing
description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
seo-description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
translation-type: tm+mt
source-git-commit: 19baf90409eab4c72fb38e992c272338b0098d89

---


# Configuratie werkstroom voor directe plaatsing {#direct-placement-workflow}

Volg deze pagina voor meer informatie over het configureren van een middelenworkflow waarmee u een element programmatisch kunt invoegen in een vooraf gedefinieerd AEM-rasterkanaal.

In deze sectie worden de volgende onderwerpen behandeld:

* Overzicht
* Workflow voor directe plaatsing configureren

## Overzicht {#overview}

De directe Configuratie van de Werkstroom van de Plaatsing wijst een AEM het projectkanaal van Schermen aan een specifieke omslag in activa toe en staat voor plaatsing van om het even welk middel in die omslag toe. Het wordt aangeraden een bulkofflineupdate te activeren om de publicatie te voltooien.

U kunt als auteur van inhoud ook handmatig klikken op Offlineinhoud **** bijwerken.

>[!NOTE]
> Leer hoe te om bulk off-line update te gebruiken, verwijs naar de Update van de [Inhoud als Dienst](/help/user-guide/content-update-as-a-service.md).

## Workflow voor directe plaatsing configureren {#configuring-workflow}

>[!IMPORTANT]
> Voordat u de configuratie start, moet u het [demopakket](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip)installeren. Nadat u het pakket hebt geïnstalleerd, kunt u het weergeven en openen vanuit uw AEM-instantie —> Extra (pictogram) —> **Workflow** —> **Workflowmodellen**.

Voer de onderstaande stappen uit om de workflow voor directe plaatsing te configureren:

1. Navigeer naar AEM-schermen vanuit uw AEM-instantie en maak een Screens-project met de naam **Asset Workflow**.

1. Maak een kanaal met de naam **Workflow-Assets** onder de map **Kanalen** .

1. 