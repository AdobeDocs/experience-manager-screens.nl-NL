---
title: Overzicht en configuraties van adaptieve uitvoeringen van architectuur
description: Leer meer over het architectuuroverzicht en de configuraties in CRXDE Lite voor Adaptieve Uitvoeringen in AEM Screens.
exl-id: 0419b9c6-3c27-4a61-84ff-a6fe697e773f
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 1%

---

# Adaptieve uitvoeringen: Overzicht van architectuur en configuraties {#adaptive-renditions}

## Inleiding {#introduction}

Met Adaptieve uitvoeringen kunnen apparaten automatisch op de beste uitvoering klikken voor een apparaat dat is gebaseerd op door de klant gedefinieerde regels. De apparaten downloaden automatisch en spelen de meest aangewezen vertoning van activa die op deze regels worden gebaseerd, die klanten toestaan om zich bij het ontwerpen van de *belangrijkste* slechts ervaring te concentreren.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Configureer de Adaptieve uitvoeringen voordat een Content Author deze functie in een AEM Screens-kanaal kan gebruiken.

## Overzicht van architectuur {#architectural-overview}

De adaptieve Vertoningen zijn gebaseerd op het idee van het hebben van veelvoudige vertoningen van een activa genoemd volgens een specifieke noemende overeenkomst. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost.

De mogelijkheid om een naampatroon voor de uitvoering te hebben, definieert een regel voor de renditie-toewijzing, zoals Staand of Liggend, zoals in de onderstaande afbeelding wordt getoond. Na het berekenen van alle beschikbare expressies verzamelt de Screens-speler de naampatronen die overeenkomen met de overeenkomende regels. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.

![afbeelding](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Eigenschap voor renderingstoewijzing toevoegen aan het Screens-project {#rendition-mapping-new}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de volgende toewijzingsregels aanwezig moeten zijn en de Context-Aware (CA) Configuratie zou voor kanalen en vertoningen moeten oplosbaar zijn.

>[!NOTE]
>Meer over inhoud-Aware Configuraties leren, zie [ hier ](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Voer de onderstaande stappen uit om de installatie te configureren:

1. Navigeer aan **CRXDE Lite**. Controle, als de **vertoning-afbeelding** configuratie in `/conf/screens/sling:configs/rendition-mapping` bestaat, zoals aangetoond in het hieronder cijfer.

   >![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Als u het recentste Pak 202109 van de Eigenschap installeerde, ziet u de **vertoning-afbeelding** knoopstructuur vooraf bevolkt in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite. Zie {de Nota&#39;s van de Versie voor het Pak 202109 van de Eigenschap ](/help/user-guide/release-notes-fp-202109.md) om details op het recentste Pak van de Eigenschap te krijgen.[
   >Voor bestaande projecten, zorg ervoor dat het project van Screens de **vertoning-afbeelding** verbonden configuratie heeft. Zie [ Toevoegend Afbeelding van de Vertoning aan een Bestaand project ](#rendition-mapping-existing) sectie voor meer informatie.

### Eigenschap voor renderingstoewijzing toevoegen aan een bestaand project {#rendition-mapping-existing}

1. Navigeer aan **CRXDE Lite**.

1. Definieer expliciet de koppeling tussen de uitvoering en toewijzing door de eigenschap `sling:configRef` toe te voegen die `/conf/screens` aanwijst aan het knooppunt met de projectinhoud, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

Voer de onderstaande stappen uit om een knooppunt toe te voegen onder Uitvoeringstoewijzing:

1. Navigeer aan deze weg `/conf/screens/sling:configs/rendition-mapping` van **CRXDE Lite**.
1. Creeer een knoop onder **vertoning-afbeelding**. Klik **vertoning-afbeelding** met de rechtermuisknop aan en klik **creeer** > **creeer Knoop**, zoals aangetoond in hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Ga de **Naam** voor uw toewijzingsregel zoals **rule1** en het knoop **Type** als **`nt:unstructured`** in **creëren de dialoogdoos van de Knoop** in. Klik **OK**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Voeg de expressie-eigenschap toe met de waarde die de query-expressie bevat.

   >[!NOTE]
   >Zie [ Gebruikend de Syntaxis van de Vraag van Media ](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) om meer te leren.

   Klik **rule1** die u creeerde, en ga de **uitdrukking** in **Naam** in en **(richtlijn:landschap)** in **Waarde**, zoals hieronder getoond. Klik **toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat.

   >[!NOTE]
   >De waarde die in de patrooneigenschap wordt gedefinieerd, komt overeen met de nieuwe elementuitvoering en wordt geselecteerd als de expressie wordt geëvalueerd op true.

   Om het patroonbezit toe te voegen, klik **rule1** dat u creeerde, en ga het **patroon** in **Naam** en **landschap** in **Waarde**, zoals hieronder getoond. Klik **toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klik **sparen allen** en merk de eigenschappen onder de knoop op u onder **vertoning-afbeelding** creeerde.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node5.png)

## De volgende stappen {#next-steps}

Nadat u eigenschappen en regels voor renderingstoewijzing hebt toegevoegd als inhoudsauteur, kunt u uw elementen configureren. U kunt de Aangepaste Vertoningen gebruiken en ook uw apparaten migreren voor grote netwerken om deze eigenschap in uw kanalen van AEM Screens te gebruiken. Zie [ Gebruikend Aangepaste Vertoningen in AEM Screens ](/help/user-guide/using-adaptive-renditions.md) voor meer informatie.
