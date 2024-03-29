---
title: Componenten maken
seo-title: Creating Components
description: AEM componenten worden gebruikt om de inhoud die op uw webpagina's beschikbaar is, vast te houden, op te maken en weer te geven. Volg deze pagina voor meer informatie over ontwerpkanalen en renderingcomponenten.
seo-description: AEM components are used to hold, format, and render the content made available on your webpages. Follow this page to learn about authoring channels and rendering components.
uuid: 66c76dd5-495a-4dcb-ad18-7f8a92669752
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: cdc530d8-ef0e-4b61-b1f0-5f4d831f1392
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 4d673039-4963-458a-89e9-023a993dd354
source-git-commit: 707833ddd8ab2573abcac4e9a77ec88778624435
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Componenten maken {#creating-components}

AEM componenten worden gebruikt om de inhoud die op uw webpagina&#39;s beschikbaar is, vast te houden, op te maken en weer te geven.

>[!NOTE]
>
>Zie AEM Componenten ontwikkelen voor meer informatie over het maken van AEM Componenten.

## Kanalen ontwerpen {#authoring-channels}

Het kanaal is het centrale object van inhoud dat aan een set weergaven wordt geleverd. Daarom zou een inhoudauteur typisch een kanaal in de redacteur openen om inhoud toe te voegen of te wijzigen. Aangezien het kanaal een ***cq:pagina*** het zal het zelfde traditionele patroon van UX volgen om componenten op het kanaal toe te voegen en te veranderen.

Aangezien componenten in een kanaal doorgaans echter op volledig scherm worden weergegeven, heeft het schrijven van deze functie echter nadelige gevolgen wanneer wordt geprobeerd afzonderlijke componenten te bewerken of nieuwe bestellingen samen te stellen. Daarom zal het kanaal op selecteurs baseren om verschillende meningen van de componenten terug te geven. De ontwerpomgeving gebruikt de bewerkingskiezer om de rendering van aangepaste kanalen te activeren.

Bijvoorbeeld, `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

De gebruiker hoeft tijdens het bewerken geen kiezer aan de URL toe te voegen. Een logica aan de clientzijde luistert naar de gebeurtenis van de laagschakelaar en voegt de kiezer toe als een kanaal het specifieke middeltype heeft *schermen/kern/componenten/kanaal.*

## Componenten renderen {#rendering-components}

Om behoorlijk creatie toe te laten, moeten de componenten de volgende twee teruggaven verstrekken:

| **Component** | **Uitvoeringen** |
|---|---|
| *my-component/my-component.html* | productierendering |
| *my-component/edit.html* | rendering bewerken in een kleinere weergave |

De ingebouwde componenten gebruiken de volgende categorieën van de cliëntbibliotheek:

| **Component** | **Clientbibliotheek** |
|---|---|
| *cq.screens.components.edit* | CSS en JS die tijdens het ontwerpen moeten worden geladen |
| *cq.screens.components.production* | CSS en JS die moeten worden geladen wanneer het kanaal wordt uitgevoerd |
| *cq.screens.components* | gedeelde CSS en JS |

>[!NOTE]
>
>Als u aangepaste componenten wilt ontwikkelen, gebruikt u de ***[AEM Screens-voorbeeldcomponentsjabloon](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.
