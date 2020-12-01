---
title: Componenten maken
seo-title: Componenten maken
description: AEM componenten worden gebruikt om de inhoud die op uw webpagina's beschikbaar is, vast te houden, op te maken en weer te geven. Volg deze pagina voor meer informatie over ontwerpkanalen en renderingcomponenten.
seo-description: AEM componenten worden gebruikt om de inhoud die op uw webpagina's beschikbaar is, vast te houden, op te maken en weer te geven. Volg deze pagina voor meer informatie over ontwerpkanalen en renderingcomponenten.
uuid: 66c76dd5-495a-4dcb-ad18-7f8a92669752
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: cdc530d8-ef0e-4b61-b1f0-5f4d831f1392
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---


# Componenten {#creating-components} maken

AEM componenten worden gebruikt om de inhoud die op uw webpagina&#39;s beschikbaar is, vast te houden, op te maken en weer te geven.

>[!NOTE]
>
>Zie AEM Componenten ontwikkelen voor meer informatie over het maken van AEM Componenten.

## Kanalen ontwerpen {#authoring-channels}

Het kanaal is het centrale object van inhoud dat aan een set weergaven wordt geleverd. Daarom zou een inhoudauteur typisch een kanaal in de redacteur openen om inhoud toe te voegen of te wijzigen. Aangezien het Kanaal een ***cq:Pagina*** is zal het het zelfde traditionele patroon volgen UX om componenten op het kanaal toe te voegen en te veranderen.

Aangezien componenten in een kanaal doorgaans echter op volledig scherm worden weergegeven, heeft het schrijven van deze functie echter nadelige gevolgen wanneer wordt geprobeerd afzonderlijke componenten te bewerken of nieuwe bestellingen samen te stellen. Daarom zal het kanaal op selecteurs baseren om verschillende meningen van de componenten terug te geven. De ontwerpomgeving gebruikt de bewerkingskiezer om de rendering van aangepaste kanalen te activeren.

Bijvoorbeeld, `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

De gebruiker hoeft tijdens het bewerken geen kiezer aan de URL toe te voegen. Een logica aan de clientzijde luistert naar de gebeurtenis Layer Switch en voegt de kiezer toe als een kanaal het toegewezen middeltype *screens/core/components/channel heeft.*

## Rendercomponenten {#rendering-components}

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
>Als u aangepaste componenten wilt ontwikkelen, gebruikt u de sjabloon ***[AEM Screens-voorbeeldcomponent](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.

