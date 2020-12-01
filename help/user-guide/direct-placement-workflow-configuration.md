---
title: 'Configuratie werkstroom voor directe plaatsing '
seo-title: Configuratie werkstroom voor directe plaatsing
description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
seo-description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# Configuratie werkstroom voor directe plaatsing {#direct-placement-workflow}

Volg deze pagina voor meer informatie over het configureren van een middelenworkflow waarmee u via programmacode middelen kunt invoegen in een vooraf gedefinieerd AEM Screens-kanaal.

In deze sectie worden de volgende onderwerpen behandeld:

* Overzicht
* Workflow voor directe plaatsing configureren

## Overzicht {#overview}

Met Direct Placement Workflow Configuration wordt een AEM Screens-projectkanaal toegewezen aan een specifieke map in middelen en kan elk middel in die map worden geplaatst. Het wordt aangeraden een bulkofflineupdate te activeren om de publicatie te voltooien.

U kunt ook als auteur van inhoud handmatig op **Offlineinhoud bijwerken** klikken.

>[!NOTE]
>
>Als u wilt leren hoe u bulksgewijs offline updates kunt gebruiken, raadpleegt u [Inhoud bijwerken als service](/help/user-guide/content-update-as-a-service.md).

## Workflow voor directe plaatsing configureren {#configuring-workflow}

>[!IMPORTANT]
>
>Voordat u de configuratie start, moet u [Demopakket](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip) installeren. Nadat u het pakket hebt geïnstalleerd, kunt u het vanuit uw AEM-instantie weergeven en openen —> Gereedschappen (pictogram) —> **Workflow** —> **Workflowmodellen**.

Voer de onderstaande stappen uit om de workflow voor directe plaatsing te configureren:

1. Navigeer vanuit uw AEM naar AEM Screens en maak een Screens-project met de naam **Asset Workflow**.

1. Creeer een kanaal genoemd als **Workflow-Assets** onder **Kanalen** omslag.

