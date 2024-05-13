---
title: Configuratie werkstroom voor directe plaatsing
description: Deze pagina markeert de Configuratie van de Werkstroom van de Directe Plaatsing.
source-git-commit: f7653d8b386c02f510eb7a770cf3cdc22c41a5fb
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Configuratie werkstroom voor directe plaatsing {#direct-placement-workflow}

Volg deze pagina zodat u over het vormen van een middelwerkschema kunt leren dat u programmatically activa aan een vooraf bepaald kanaal van AEM Screens kunt opnemen.

In deze sectie worden de volgende onderwerpen behandeld:

* Overzicht
* Workflow voor directe plaatsing configureren

## Overzicht {#overview}

Met Direct Placement Workflow Configuration wordt een AEM Screens-projectkanaal toegewezen aan een specifieke map in middelen en kan elk middel in die map worden geplaatst. Adobe raadt u aan een bulksgewijze offline update te activeren om de publicatie te voltooien.

U kunt ook als Content Author handmatig klikken **Offline inhoud bijwerken**.

>[!NOTE]
>
>Zie voor meer informatie over het gebruik van bulkofflineupdate [Inhoud bijwerken als service](/help/user-guide/content-update-as-a-service.md).

## Workflow voor directe plaatsing configureren {#configuring-workflow}

>[!IMPORTANT]
>
>Installeer voordat u de configuratie start de `[Demo  Package](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip)`. Nadat u het pakket hebt geïnstalleerd, kunt u het weergeven en openen via de AEM > Gereedschappen (pictogram) > **Workflow** > **Workflowmodellen**.

Voer de onderstaande stappen uit om de workflow voor directe plaatsing te configureren:

1. Navigeer naar AEM Screens vanaf uw AEM en maak een Screens-project met de naam **Workflow voor middelen**.

1. Een kanaal maken met de naam **Workflow-middelen** onder de **Kanalen** map.

