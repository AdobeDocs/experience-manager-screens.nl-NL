---
title: Componenten maken
description: Leer hoe AEM componenten worden gebruikt om de inhoud die op uw webpagina's beschikbaar is, vast te houden, op te maken en weer te geven.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 4d673039-4963-458a-89e9-023a993dd354
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# Componenten maken {#creating-components}

AEM componenten worden gebruikt om de inhoud die op uw webpagina&#39;s beschikbaar is, vast te houden, op te maken en weer te geven.

>[!NOTE]
>
>Zie AEM componenten ontwikkelen voor meer informatie over het maken van AEM componenten.

## Kanalen ontwerpen {#authoring-channels}

Het kanaal is het centrale object van inhoud dat aan een set weergaven wordt geleverd. Daarom zou een Content Author normaal gesproken een kanaal openen in de editor om inhoud toe te voegen of te wijzigen. Omdat het Kanaal een *** is`cq:Page`***, volgt het zelfde traditionele patroon van UX om componenten op het kanaal toe te voegen en te veranderen.

Omdat componenten in een kanaal doorgaans echter op volledig scherm worden weergegeven, heeft de ontwerpervaring te lijden onder het bewerken van afzonderlijke componenten of het samenstellen van nieuwe bestellingen. Daarom is het kanaal afhankelijk van kiezers om verschillende weergaven van de componenten te renderen. De ontwerpomgeving gebruikt de bewerkingskiezer om de rendering van aangepaste kanalen te activeren.

Bijvoorbeeld: `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

De gebruiker hoeft tijdens het bewerken geen kiezer aan de URL toe te voegen. Een cliënt-zijlogica luistert aan de gebeurtenis van de laagschakelaar en voegt selecteur toe als het kanaal het specifieke middeltype heeft *schermen/kern/componenten/kanaal*.

## Componenten renderen {#rendering-components}

Componenten moeten de volgende twee renderingen opgeven om correct schrijven mogelijk te maken:

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
>Als u aangepaste componenten wilt ontwikkelen, gebruikt u ***[AEM Screens-voorbeeldcomponentsjabloon](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.
