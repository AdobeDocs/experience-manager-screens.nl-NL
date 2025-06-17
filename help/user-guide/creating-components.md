---
title: Componenten maken
description: Leer hoe AEM-componenten worden gebruikt om de inhoud die op uw webpagina's beschikbaar is, vast te houden, op te maken en weer te geven.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 4d673039-4963-458a-89e9-023a993dd354
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Componenten maken {#creating-components}

AEM-componenten worden gebruikt om de inhoud die op uw webpagina&#39;s beschikbaar is, op te slaan en weer te geven.

>[!NOTE]
>
>Zie AEM-componenten ontwikkelen voor meer informatie over het maken van AEM-componenten.

## Auteurskanalen {#authoring-channels}

Het kanaal is het centrale object van inhoud dat aan een set weergaven wordt geleverd. Daarom zou een Content Author normaal gesproken een kanaal openen in de editor om inhoud toe te voegen of te wijzigen. Omdat het Kanaal een *** `cq:Page`*** is, volgt het het zelfde traditionele patroon van UX om componenten op het kanaal toe te voegen en te veranderen.

Omdat componenten in een kanaal doorgaans echter op volledig scherm worden weergegeven, heeft de ontwerpervaring te lijden onder het bewerken van afzonderlijke componenten of het samenstellen van nieuwe bestellingen. Daarom is het kanaal afhankelijk van kiezers om verschillende weergaven van de componenten te renderen. De ontwerpomgeving gebruikt de kiezer `edit` om de rendering van aangepaste kanalen te activeren.

Bijvoorbeeld: `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

De gebruiker hoeft tijdens het bewerken geen kiezer aan de URL toe te voegen. Een cliënt-zijlogica luistert aan de gebeurtenis van de laagschakelaar en voegt de selecteur toe als het kanaal het specifieke middeltype *schermen/kern/componenten/kanaal* heeft.

## Componenten renderen {#rendering-components}

Componenten moeten de volgende twee renderingen opgeven om correct schrijven mogelijk te maken:

| **Component** | **Vertoningen** |
|---|---|
| *my-component/my-component.html* | productierendering |
| *my-component/edit.html* | rendering bewerken in een kleinere weergave |

De ingebouwde componenten gebruiken de volgende categorieën van de cliëntbibliotheek:

| **Component** | **de Bibliotheek van de Cliënt** |
|---|---|
| *cq.screens.components.edit* | CSS en JS die tijdens het ontwerpen moeten worden geladen |
| *cq.screens.components.production* | CSS en JS die moeten worden geladen wanneer het kanaal wordt uitgevoerd |
| *cq.screens.components* | gedeelde CSS en JS |

>[!NOTE]
>
>Om douanecomponenten te ontwikkelen, gebruik het *** [ malplaatje van de steekproefcomponent van AEM Screens ](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.
