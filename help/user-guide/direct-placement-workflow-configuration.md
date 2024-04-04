---
title: Configuratie werkstroom voor directe plaatsing
seo-title: Direct Placement Workflow Configuration
description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
seo-description: This page highlights Direct Placement Workflow Configuration.
source-git-commit: d1adadbab2cb13626dd8ce70deacced9f55aa4c9
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---


# Configuratie werkstroom voor directe plaatsing {#direct-placement-workflow}

Volg deze pagina voor meer informatie over het configureren van een middelenworkflow waarmee u een element programmatisch kunt invoegen in een vooraf gedefinieerd AEM Screens-kanaal.

In deze sectie worden de volgende onderwerpen behandeld:

* Overzicht
* Workflow voor directe plaatsing configureren

## Overzicht {#overview}

Met Direct Placement Workflow Configuration wordt een AEM Screens-projectkanaal toegewezen aan een specifieke map in middelen en kan elk middel in die map worden geplaatst. Het wordt aangeraden een bulkofflineupdate te activeren om de publicatie te voltooien.

U kunt ook als auteur van inhoud handmatig klikken **Offline inhoud bijwerken**.

>[!NOTE]
>
>Raadpleeg voor meer informatie over het gebruik van bulksgewijze offline updates de [Inhoud bijwerken als service](/help/user-guide/content-update-as-a-service.md).

## Workflow voor directe plaatsing configureren {#configuring-workflow}

>[!IMPORTANT]
>
>Voordat u de configuratie start, moet u de [Demopakket](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip). Nadat u het pakket hebt geïnstalleerd, kunt u het weergeven en openen via de AEM > Gereedschappen (pictogram) > **Workflow** > **Workflowmodellen**.

Voer de onderstaande stappen uit om de workflow voor directe plaatsing te configureren:

1. Navigeer naar AEM Screens vanaf uw AEM en maak een screens-project met de naam: **Workflow voor middelen**.

1. Een kanaal maken met de naam **Workflow-middelen** krachtens **Kanalen** map.

