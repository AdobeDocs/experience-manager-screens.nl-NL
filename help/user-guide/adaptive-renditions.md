---
title: Overzicht en configuraties van adaptieve uitvoeringen van architectuur
description: Deze pagina beschrijft Overzicht van architectuur en Configuraties in CRXDE Lite voor Aangepaste Uitvoeringen in AEM Screens.
exl-id: 0419b9c6-3c27-4a61-84ff-a6fe697e773f
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 1%

---

# Adaptieve uitvoeringen: Overzicht van architectuur en configuraties {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *hoofd* ervaring.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. U moet de Adaptieve uitvoeringen configureren voordat de auteur van de inhoud deze functie in een AEM Screens-kanaal kan gebruiken.

## Overzicht van architectuur {#architectural-overview}

Aangepaste uitvoeringen zijn gebaseerd op het idee dat meerdere elementuitvoeringen worden genoemd volgens een specifieke naamgevingsconventie. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost.

De mogelijkheid om een gekoppeld naampatroon voor de uitvoering te hebben, definieert een regel voor de uitvoering, zoals Staand of Liggend, zoals in de onderstaande afbeelding wordt getoond. Na het berekenen van alle beschikbare uitdrukkingen zal de speler van het Scherm de noemende patronen verzamelen die aan de passende regels beantwoorden. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.

![afbeelding](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Eigenschap voor renderingstoewijzing toevoegen aan het schermproject {#rendition-mapping-new}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de volgende toewijzingsregels aanwezig moeten zijn en de Context-Aware (CA) Configuratie zou voor kanalen en vertoningen moeten oplosbaar zijn.

>[!NOTE]
>Ga voor meer informatie over configuraties met behoud van inhoud naar [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Voer de onderstaande stappen uit om de installatie te configureren:

1. Navigeren naar **CRXDE Lite**. Controleer of de **rendition-mapping** configuratie bestaat in `/conf/screens/sling:configs/rendition-mapping`, zoals weergegeven in onderstaande afbeelding.

   >![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Als u de nieuwste versie van Feature Pack 202109 hebt geïnstalleerd, kunt u **rendition-mapping** knooppuntstructuur vooraf ingevuld in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite. Zie [Opmerkingen bij de release voor Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) voor meer informatie over het nieuwste functiepakket.
   >Voor bestaande projecten moet u ervoor zorgen dat het project Screens de **rendition-mapping** gekoppelde configuratie. Zie [Uitvoeringstoewijzing toevoegen aan een bestaand project](#rendition-mapping-existing) voor meer informatie.

### Eigenschap voor renderingstoewijzing toevoegen aan een bestaand project {#rendition-mapping-existing}

1. Navigeren naar **CRXDE Lite**.

1. De koppeling voor de rendiingtoewijzing expliciet definiëren door deze toe te voegen `sling:configRef` eigenschap die wijst op `/conf/screens` aan de knoop van de projectinhoud, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

Voer de onderstaande stappen uit om een knooppunt toe te voegen onder Uitvoeringstoewijzing:

1. Naar dit pad navigeren `/conf/screens/sling:configs/rendition-mapping` van **CRXDE Lite**.

1. Een knooppunt maken onder **rendition-mapping**. Rechtsklik ingeschakeld **rendition-mapping** en klik op **Maken** > **Knooppunt maken**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Voer de **Naam** voor uw toewijzingsregel, zoals **rule1** en het knooppunt **Type** als **nt:ongestructureerd** in **Knooppunt maken** in. Klikken op **OK**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. U moet het uitdrukkingsbezit met de waarde toevoegen die de vraaguitdrukking bevat.

   >[!NOTE]
   >Zie [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) voor meer informatie.

   Klikken op **rule1** die u hebt gemaakt, en voert u in **expression** in **Naam** en **(oriëntatie:liggend)** in **Waarde**, zoals hieronder weergegeven. Klikken op **Toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat.

   >[!NOTE]
   >De waarde die in de patrooneigenschap is gedefinieerd, wordt aangepast aan de nieuwe elementuitvoering en wordt geselecteerd als de expressie wordt geëvalueerd op true.

   Klik op **rule1** die u hebt gemaakt, en voert u in **patroon** in **Naam** en **landschap** in **Waarde**, zoals hieronder weergegeven. Klikken op **Toevoegen**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klikken op **Alles opslaan** en u zult de eigenschappen onder de knoop zien u onder creeerde **rendition-mapping**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node5.png)


## De volgende stappen {#next-steps}

Zodra u eigenschappen en regels van de vertoningsafbeelding van de vertoning hebt toegevoegd, nu als Inhoudsauteur, kunt u uw activa vormen om Aangepaste Vertoningen te gebruiken en ook uw apparaten voor grote netwerken migreren om deze eigenschap, in uw kanalen van AEM Screens te gebruiken. Zie [Adaptieve uitvoeringen gebruiken in AEM Screens](/help/user-guide/using-adaptive-renditions.md) voor meer informatie .
