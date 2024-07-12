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

Alternatief, als Inhoudsauteur kunt u **off-line Inhoud van de Update** manueel klikken.

>[!NOTE]
>
>Leren hoe te om bulk off-line update te gebruiken, zie [ Update van de Inhoud als Dienst ](/help/user-guide/content-update-as-a-service.md).

## Workflow voor directe plaatsing configureren {#configuring-workflow}

>[!IMPORTANT]
>
>Installeer de `[Demo  Package](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip)` voordat u de configuratie start. Nadat u het pakket hebt geïnstalleerd, zou u het van uw AEM instantie > Hulpmiddelen (pictogram) moeten kunnen bekijken en toegang hebben > **Werkschema** > **Modellen van het Werkschema**.

Voer de onderstaande stappen uit om de workflow voor directe plaatsing te configureren:

1. Navigeer aan AEM Screens van uw AEM instantie en creeer een project van Screens dat als **Werkschema van Activa** wordt genoemd.

1. Creeer een kanaal genoemd als **werkschema-Assets** onder de **omslag van Kanalen**.

