---
title: Een workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren
description: Leer hoe u een workflow maakt om elementen die naar Adobe Experience Manager zijn geüpload automatisch te verwerken en ze dynamisch aan een Screens-kanaal toe te wijzen.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Een workflow gebruiken om middelenupdates voor een AEM Screens-kanaal te automatiseren {#automate-channel-updates-workflow}

Leer hoe u een workflow maakt om elementen die naar Adobe Experience Manager zijn geüpload automatisch te verwerken en ze dynamisch aan een Screens-kanaal toe te wijzen. In dit voorbeeld wordt een workflow gestart wanneer een afbeelding wordt toegevoegd aan een specifieke map. De workflow past een dynamische tekstbedekking (watermerkproces) toe en wijst de afbeelding toe aan een Screens-kanaal. De lessen die u in dit voorbeeld hebt geleerd, kunnen op een groot aantal verschillende automatiseringsscenario&#39;s worden toegepast.

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [ AEM 6.5 ](https://experienceleague.adobe.com/en/docs/experience-manager-65)
1. [ AEM Service Pack 8 of hoger ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes)
1. [ AEM 6.5 Screens FP7 of hoger ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103)

## Snelle installatie {#quick-setup}

In de onderstaande video ziet u hoe u een pakket voorbeeldcode kunt installeren waarmee Adobe Experience Manager een nieuwe workflow krijgt. Met deze functie kan een gebruiker de eigenschappen van een map in AEM Assets bijwerken en naar een Screens-kanaal wijzen. Wanneer een afbeelding aan die map wordt toegevoegd, wordt deze aan het opgegeven AEM Screens-kanaal toegevoegd.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Download het gecompileerde codepakket: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Installeer het bovenstaande pakket met AEM Package Manager.

## Workflowmodel {#workflow-model}

Er is een aangepast metagegevensschema voor mappen gemaakt om het doel-Screens-kanaal vast te leggen waaraan afbeeldingen moeten worden toegevoegd. Er worden twee workflowmodellen gebruikt om de verwerking van middelen te automatiseren. Het **DAM werkschema van de Activa van de Update** wordt uitgegeven om een douanewerkschema, **Screens de Verwerking van Activa van de Demo te roepen die de activa bevattende omslag inspecteert om het doelScreens kanaal te bepalen. Het **werkschema van de Verwerking van de Activa van de Demo van Screens** is ook verantwoordelijk voor het toepassen van het watermerk op het beeld.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Proces voor aangepaste workflowprocessen {#workflow-process-step}

Inspect twee stappen van het douanewerkschemaproces die als deel van het **werkschema van de Verwerking van de Activa van de Demo van Screens** worden gebruikt.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

De aangepaste workflow van `AssetProcessingCheck.java` is een proces dat een controle uitvoert op de lading van de workflow. Het bepaalt als de lading een middel is en als de bevattende omslag wordt gevormd om aan een kanaal van AEM Screens te richten. Als aan de vereisten wordt voldaan, zal de processtap twee eigenschappen `screen-channel` en `asset-path` aan de meta-gegevens van het werkschema voortzetten.

De aangepaste workflow van `AddAssetToChannel.java` is een processtap die de metagegevens van de workflow controleert en het AEM Screens-kanaal bijwerkt om naar de afbeelding te verwijzen.

1. Download de broncode: **[schermen-demo-main.zip](./assets/screens-demo-main.zip)**
1. Pak de code uit en bekijk deze met uw favoriete IDE.
