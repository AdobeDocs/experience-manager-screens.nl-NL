---
title: Workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren
description: Leer hoe u een workflow maakt voor het automatisch verwerken van naar Adobe Experience Manager geüploade elementen en het dynamisch toewijzen van deze middelen aan een rasterkanaal.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
source-git-commit: 3c4b37b3b9f268b500562fa4ce3782b7be1e7d74
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---


# Workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren {#automate-channel-updates-workflow}

Leer hoe u een workflow maakt voor het automatisch verwerken van naar Adobe Experience Manager geüploade elementen en het dynamisch toewijzen van deze middelen aan een rasterkanaal. Wanneer in dit voorbeeld een afbeelding aan een specifieke map wordt toegevoegd, wordt een workflow geactiveerd die een dynamische tekstbedekking (watermerkproces) toepast en de afbeelding toewijst aan een rasterkanaal. De lessen die u in dit voorbeeld hebt geleerd, kunnen op een groot aantal verschillende automatiseringsscenario&#39;s worden toegepast.

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [AEM 6,5](https://experienceleague.adobe.com/en/docs/experience-manager-65)
1. [AEM Service Pack 8 of hoger](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes)
1. [AEM 6.5 Schermen FP7 of hoger](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103)

## Snelle installatie {#quick-setup}

In de onderstaande video ziet u hoe u een pakket voorbeeldcode kunt installeren waarmee Adobe Experience Manager een nieuwe workflow krijgt. Met deze functie kan een gebruiker de eigenschappen van een map in AEM Assets bijwerken en naar een rasterkanaal verwijzen. Wanneer een afbeelding aan die map wordt toegevoegd, wordt deze aan het opgegeven AEM Screens-kanaal toegevoegd.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Download het gecompileerde codepakket: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installeer het bovenstaande pakket met AEM Package Manager.

## Workflowmodel {#workflow-model}

Er is een aangepast metagegevensschema voor de map gemaakt om het doelkanaal voor rasters vast te leggen waaraan afbeeldingen moeten worden toegevoegd. Er worden twee workflowmodellen gebruikt om de verwerking van middelen te automatiseren. De **DAM Update-element** de workflow is aangepast om een aangepaste workflow aan te roepen; **Schermen van de verwerking van demo-elementen** waarmee de bovenliggende map van het element wordt geïnspecteerd om het doelkanaal voor rasters te bepalen. De **Schermen van de verwerking van demo-elementen** is ook verantwoordelijk voor het toepassen van het watermerk op de afbeelding.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Proces voor aangepaste workflowprocessen {#workflow-process-step}

Inspect: twee stappen van het aangepaste workflowproces die worden gebruikt als onderdeel van de **Schermen van de verwerking van demo-elementen** workflow.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

De `AssetProcessingCheck.java` een aangepaste werkstroom is een proces dat een controle van de lading van de werkstroom uitvoert. Het bepaalt als de lading een middel is en als de bevattende omslag wordt gevormd om aan een kanaal van AEM Screens te richten. Als aan de vereisten wordt voldaan, houdt de processtap twee eigenschappen voort, `screen-channel` en `asset-path`, naar de metagegevens van de workflow.

De `AddAssetToChannel.java` een aangepaste workflow is een processtap die de metagegevens van de workflow controleert en het AEM Screens-kanaal bijwerkt om naar de afbeelding te verwijzen.

1. Download de broncode: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Pak de code uit en bekijk deze met uw favoriete IDE.
