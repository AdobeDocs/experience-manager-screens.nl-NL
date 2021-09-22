---
title: Adaptieve uitvoeringen in AEM Screens
description: Op deze pagina vindt u het overzicht van de architectuur en de configuraties voor adaptieve uitvoeringen in AEM Screens.
index: false
source-git-commit: 951fd38d5f69cdab1bf9b23f07b4e92075e87baf
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

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


## Auteur instellen en publiceren {#setup-author-publish}

Overweeg de volgende aanbevelingen in Auteur en Publiceer voorafgaand aan het gebruiken van Aangepaste Vertoningen:

* Uitvoeringstoewijzing moet handmatig worden herhaald.

* Elementuitvoeringen worden niet standaard gerepliceerd. Alle relevante activa moeten handmatig worden gerepliceerd.

## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

1. Als u een toewijzingsregel wilt toevoegen, moet u een knooppunt van het type `nt:unstructured` onder het knooppunt **rendition-mapping** maken.

1. Voeg de expressie-eigenschap toe met de waarde die de query-expressie bevat.

   >[!NOTE]
   >Raadpleeg [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) voor meer informatie.

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat dat wordt geselecteerd als de expressie wordt geëvalueerd op true.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules4.png)


## De volgende stappen {#next-steps}

Nadat u de uitvoeringen hebt geconfigureerd en geüpload, kunt u als inhoudsauteur nu Adaptieve uitvoeringen gebruiken en ook uw apparaten migreren voor grote netwerken om deze functie te gebruiken, in uw AEM Screens-kanalen. Zie [Aangepaste uitvoeringen gebruiken](/help/user-guide/using-adaptive-renditions.md) voor meer informatie.
