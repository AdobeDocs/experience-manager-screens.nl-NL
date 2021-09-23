---
title: Overzicht en configuraties van adaptieve uitvoeringen van architectuur
description: Deze pagina beschrijft Overzicht van architectuur en Configuraties in CRXDE Lite voor Aangepaste Uitvoeringen in AEM Screens.
source-git-commit: d30426f871d319bcfacb7a832479b87400e18fc2
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---


# Adaptieve uitvoeringen: Overzicht en configuraties van architectuur {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *main* slechts te concentreren ervaring.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. U moet de Adaptieve uitvoeringen configureren voordat de auteur van de inhoud deze functie in een AEM Screens-kanaal kan gebruiken.

## Overzicht van architectuur {#architectural-overview}

Aangepaste uitvoeringen zijn gebaseerd op het idee dat meerdere elementuitvoeringen worden genoemd volgens een specifieke naamgevingsconventie. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost.

De mogelijkheid om een gekoppeld naampatroon voor de uitvoering te hebben, definieert een regel voor de uitvoering, zoals Staand of Liggend, zoals in de onderstaande afbeelding wordt getoond. Na het berekenen van alle beschikbare uitdrukkingen zal de speler van het Scherm de noemende patronen verzamelen die aan de passende regels beantwoorden. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.

![afbeelding](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Eigenschap voor renderingstoewijzing toevoegen aan het schermproject {#rendition-mapping-new}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de volgende toewijzingsregels aanwezig moeten zijn en de Context-Aware (CA) Configuratie zou voor kanalen en vertoningen moeten oplosbaar zijn.

>[!NOTE]
>Voor meer informatie over Inhoud-Aware Configuraties, zie [hier](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Voer de onderstaande stappen uit om de installatie te configureren:

1. Navigeer naar **CRXDE Lite**. Controleer of de **rendition-mapping**-configuratie bestaat in `/conf/screens/sling:configs/rendition-mapping`, zoals in de onderstaande afbeelding wordt getoond.

   >![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >Als u het recentste Pak 202109 van de Eigenschap installeerde, zult u **rendition-mapping** knoopstructuur vooraf bevolkt in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite zien. Zie [Opmerkingen bij de release voor Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) voor meer informatie over het nieuwste functiepakket.
   >Voor bestaande projecten, zorg ervoor dat het project van Schermen **rendition-mapping** bijbehorende configuratie heeft. Zie [Toewijzing van de Vertoning aan een Bestaand project](#rendition-mapping-existing) sectie toevoegen om meer te leren.

### Eigenschap voor renderingstoewijzing toevoegen aan een bestaand project {#rendition-mapping-existing}

1. Navigeer naar **CRXDE Lite**.

1. Definieer expliciet de koppeling naar de uitvoeringstoewijzing door `sling:configRef`-eigenschap toe te voegen die `/conf/screens` aanwijst naar het knooppunt met de projectinhoud, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

Voer de onderstaande stappen uit om een knooppunt toe te voegen onder Uitvoeringstoewijzing:

1. Navigeer naar dit pad `/conf/screens/sling:configs/rendition-mapping` van **CRXDE Lite**.

1. Maak een knooppunt onder **rendition-mapping**. Klik met de rechtermuisknop op **rendition-mapping** en klik op **Create** —> **Create Node**, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Voer de **Naam** voor uw toewijzingsregel in, zoals **rule1** en het knooppunt **Type** als **nt:unStructured** in het dialoogvenster **Node maken**. Klik op **OK**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. U moet het uitdrukkingsbezit met de waarde toevoegen die de vraaguitdrukking bevat.

   >[!NOTE]
   >Raadpleeg [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) voor meer informatie.

   Klik op **rule1** die u hebt gemaakt en voer **expression** in **Name** en **(orientation:landscape)** in **Value** in, zoals hieronder wordt getoond. Klik op **Add**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node3.png)

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat.

   >[!NOTE]
   >De waarde die in de patrooneigenschap is gedefinieerd, wordt aangepast aan de nieuwe elementuitvoering en wordt geselecteerd als de expressie wordt geëvalueerd op true.

   Als u de patrooneigenschap wilt toevoegen, klikt u op **rule1** die u hebt gemaakt en voert u **pattern** in **Name** en **landscape** in **Value** in, zoals hieronder wordt weergegeven. Klik op **Add**.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Klik op **Alles opslaan** en u ziet de eigenschappen onder het knooppunt dat u onder **rendition-mapping** hebt gemaakt.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-node5.png)


## De volgende stappen {#next-steps}

Zodra u eigenschappen en regels van de vertoningsafbeelding van de vertoning hebt toegevoegd, nu als Inhoudsauteur, kunt u uw activa vormen om Aangepaste Vertoningen te gebruiken en ook uw apparaten voor grote netwerken migreren om deze eigenschap, in uw kanalen van AEM Screens te gebruiken.
