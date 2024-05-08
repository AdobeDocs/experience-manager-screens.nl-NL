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

Met Adaptieve uitvoeringen kunnen apparaten automatisch op de beste uitvoering klikken voor een apparaat dat is gebaseerd op door de klant gedefinieerde regels. De apparaten downloaden en spelen automatisch de meest aangewezen vertoning van activa die op deze regels wordt gebaseerd, die klanten toestaan om zich op het ontwerpen van te concentreren *hoofd* alleen ervaring.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. Configureer de Adaptieve uitvoeringen voordat een Content Author deze functie in een AEM Screens-kanaal kan gebruiken.

## Overzicht van architectuur {#architectural-overview}

De adaptieve Vertoningen zijn gebaseerd op het idee van het hebben van veelvoudige vertoningen van een activa genoemd volgens een specifieke noemende overeenkomst. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost.

De mogelijkheid om een naampatroon voor de uitvoering te hebben, definieert een regel voor de renditie-toewijzing, zoals Staand of Liggend, zoals in de onderstaande afbeelding wordt getoond. Na het berekenen van alle beschikbare uitdrukkingen, verzamelt de speler van het Scherm de noemende patronen die aan de passende regels beantwoorden. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.

![afbeelding](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Eigenschap voor renderingstoewijzing toevoegen aan het schermproject {#rendition-mapping-new}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de volgende toewijzingsregels aanwezig moeten zijn en de Context-Aware (CA) Configuratie zou voor kanalen en vertoningen moeten oplosbaar zijn.

>[!NOTE]
>Ga voor meer informatie over configuraties met behoud van inhoud naar [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Voer de onderstaande stappen uit om de installatie te configureren:

1. Navigeren naar **CRXDE Lite**. Controleer of de **rendition-mapping** configuratie bestaat in `/conf/screens/sling:configs/rendition-mapping`, zoals weergegeven in onderstaande afbeelding.

   >![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Als u de nieuwste versie van Feature Pack 202109 hebt geïnstalleerd, ziet u de **rendition-mapping** knooppuntstructuur vooraf ingevuld in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite. Zie [Opmerkingen bij de release voor Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) voor meer informatie over het nieuwste elementenpakket.
   >Voor bestaande projecten moet u ervoor zorgen dat het project Screens de **rendition-mapping** gekoppelde configuratie. Zie [Uitvoeringstoewijzing toevoegen aan een bestaand project](#rendition-mapping-existing) voor meer informatie.

### Eigenschap voor renderingstoewijzing toevoegen aan een bestaand project {#rendition-mapping-existing}

1. Navigeren naar **CRXDE Lite**.

1. De koppeling voor de renditie-toewijzing expliciet definiëren door deze toe te voegen `sling:configRef` eigenschap die wijst op `/conf/screens` aan de knoop van de projectinhoud, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

Voer de onderstaande stappen uit om een knooppunt toe te voegen onder Uitvoeringstoewijzing:

1. Naar dit pad navigeren `/conf/screens/sling:configs/rendition-mapping` van **CRXDE Lite**.
1. Een knooppunt maken onder **rendition-mapping**. Klikken met rechtermuisknop **rendition-mapping** en klik op **Maken** > **Knooppunt maken**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Voer de **Naam** voor uw toewijzingsregel, zoals **rule1** en het knooppunt **Type** als **`nt:unstructured`** in **Knooppunt maken** in. Klikken **OK**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. Voeg de expressie-eigenschap toe met de waarde die de query-expressie bevat.

   >[!NOTE]
   >Zie [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries) voor meer informatie.

   Klikken **rule1** die u hebt gemaakt, en voert u de **expression** in **Naam** en **(oriëntatie:liggend)** in **Waarde**, zoals hieronder weergegeven. Klikken **Toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat.

   >[!NOTE]
   >De waarde die in de patrooneigenschap wordt gedefinieerd, komt overeen met de nieuwe elementuitvoering en wordt geselecteerd als de expressie wordt geëvalueerd op true.

   Klik op **rule1** die u hebt gemaakt, en voert u de **patroon** in **Naam** en **landschap** in **Waarde**, zoals hieronder weergegeven. Klikken **Toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klikken **Alles opslaan** en bekijk de eigenschappen onder de knoop u onder creeerde **rendition-mapping**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node5.png)

## De volgende stappen {#next-steps}

Nadat u eigenschappen en regels voor renderingstoewijzing hebt toegevoegd als inhoudsauteur, kunt u uw elementen configureren. U kunt de Aangepaste Vertoningen gebruiken en ook uw apparaten migreren voor grote netwerken om deze eigenschap in uw kanalen van AEM Screens te gebruiken. Zie [Adaptieve uitvoeringen gebruiken in AEM Screens](/help/user-guide/using-adaptive-renditions.md) voor meer informatie .
