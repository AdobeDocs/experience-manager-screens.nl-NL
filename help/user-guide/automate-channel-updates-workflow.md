---
title: Workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren
seo-title: Workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren
description: Leer hoe u een workflow maakt voor het automatisch verwerken van naar Adobe Experience Manager geüploade elementen en het dynamisch toewijzen van deze middelen aan een rasterkanaal. In dit voorbeeld wordt een workflow geactiveerd die een dynamisch watermerk toepast en de afbeelding toewijst aan een rasterkanaal wanneer een afbeelding aan een specifieke map wordt toegevoegd. De lessen die u in dit voorbeeld hebt geleerd, kunnen op een groot aantal verschillende automatiseringsscenario's worden toegepast.
seo-description: Leer hoe u een workflow maakt voor het automatisch verwerken van naar Adobe Experience Manager geüploade elementen en het dynamisch toewijzen van deze middelen aan een rasterkanaal. In dit voorbeeld wordt een workflow geactiveerd die een dynamisch watermerk toepast en de afbeelding toewijst aan een rasterkanaal wanneer een afbeelding aan een specifieke map wordt toegevoegd. De lessen die u in dit voorbeeld hebt geleerd, kunnen op een groot aantal verschillende automatiseringsscenario's worden toegepast.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Schermen ontwikkelen
role: Developer
level: Intermediate
source-git-commit: 8d1633dab9e70ea988516cf9ee4d1b0a780bc7e9
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---


# Workflow gebruiken om middelenupdates te automatiseren voor een AEM Screens-kanaal {#automate-channel-updates-workflow}

Leer hoe u een workflow maakt voor het automatisch verwerken van naar Adobe Experience Manager geüploade elementen en het dynamisch toewijzen van deze middelen aan een rasterkanaal. Wanneer in dit voorbeeld een afbeelding aan een specifieke map wordt toegevoegd, wordt een workflow geactiveerd die een dynamische tekstbedekking (watermerkproces) toepast en de afbeelding toewijst aan een rasterkanaal. De lessen die u in dit voorbeeld hebt geleerd, kunnen op een groot aantal verschillende automatiseringsscenario&#39;s worden toegepast.

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [AEM 6,5](https://experienceleague.adobe.com/docs/experience-manager-65.html)
1. [AEM Service Pack 8 of hoger](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html)
1. [AEM 6.5 Schermen FP7 of hoger](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103.html)

## Snelle installatie {#quick-setup}

In de onderstaande video ziet u hoe u een pakket voorbeeldcode kunt installeren waarmee een nieuwe workflow in Adobe Experience Manager wordt geïntroduceerd. Met deze functie kan een gebruiker de eigenschappen van een map in AEM Assets bijwerken en naar een rasterkanaal verwijzen. Wanneer een afbeelding aan die map wordt toegevoegd, wordt deze aan het opgegeven rasterkanaal toegevoegd.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Download het gecompileerde codepakket: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installeer het bovenstaande pakket met AEM Package Manager.

## Workflowmodel {#workflow-model}

Er is een aangepast metagegevensschema voor de map gemaakt om het doelkanaal voor rasters vast te leggen waaraan afbeeldingen moeten worden toegevoegd. Er worden twee workflowmodellen gebruikt om de verwerking van bedrijfsmiddelen te automatiseren. De **DAM Update Asset**-workflow is gewijzigd om een aangepaste workflow aan te roepen, **Schermen Demo Asset Processing**, die de map met elementen inspecteert om het doelrasterkanaal te bepalen. De **Schermdemo Asset Processing**-workflow is ook verantwoordelijk voor het toepassen van het watermerk op de afbeelding.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Aangepaste stappen voor workflowproces {#workflow-process-step}

Inspect voert twee aangepaste stappen uit voor workflowverwerking die worden gebruikt als onderdeel van de **Workflow voor demo-asset-verwerking**.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

`AssetProcessingCheck.java` is een aangepast workflowproces dat een controle van de lading van de workflow uitvoert om te bepalen of de lading een middel is en of de bevattende map is geconfigureerd om naar een kanaal van het Scherm te wijzen. Als aan de vereisten wordt voldaan, blijft de processtap twee eigenschappen, `screen-channel` en `asset-path`, aan de meta-gegevens van het werkschema voortzetten.

`AddAssetToChannel.java` is een stap van het douanewerkschemaproces dat de meta-gegevens van het werkschema inspecteert en het kanaal van Screens bijwerkt om op het beeld te verwijzen.

1. Download de broncode: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Pak de code uit en bekijk deze met uw favoriete IDE.
