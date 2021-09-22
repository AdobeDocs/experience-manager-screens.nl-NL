---
title: Adaptieve uitvoeringen in AEM Screens
description: Op deze pagina vindt u het overzicht van de architectuur en de configuraties voor adaptieve uitvoeringen in AEM Screens.
index: false
source-git-commit: d3a2c7695afb296e9344aa55f6630798db5b1941
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 1%

---


# Adaptieve uitvoeringen: Overzicht en configuraties van architectuur {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *main* slechts te concentreren ervaring.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. U moet de adaptieve uitvoeringen configureren voordat een inhoudsauteur deze functie in een AEM Screens-kanaal kan gebruiken.

Als u dus een aantal verschillende apparaten hebt geïmplementeerd, kan het apparaat met deze functie automatisch de meest geschikte uitvoering van een element downloaden en afspelen op basis van de regels.

## Overzicht van architectuur {#architectural-overview}

Aangepaste uitvoeringen zijn gebaseerd op het idee dat meerdere elementuitvoeringen worden genoemd volgens een specifieke naamgevingsconventie. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost. De mogelijkheid om een gekoppeld naamgevingspatroon voor vertoningen te hebben, definieert een regel voor vertoningstoewijzing. Na het berekenen van alle beschikbare uitdrukkingen zal de speler van het Scherm de noemende patronen verzamelen die aan de passende regels beantwoorden. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.

![afbeelding](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## De instelling configureren voor het gebruik van adaptieve uitvoeringen {#setup-adaptive-renditions}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de toewijzingsregels aanwezig moeten zijn en de Context-Aware Configuratie oplosbaar voor kanalen en vertoningen:

1. Controleer of de configuratie van de vertoningstoewijzing bestaat in `JCR`. Alle recentste eigenschapspakketten hebben deze knoopstructuur vooraf bevolkt.

   >[!NOTE]
   >Alle recentste eigenschapspakketten hebben deze knoopstructuur vooraf bevolkt.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

1. Zorg ervoor dat aan het project Screens de configuratie van de vertoningstoewijzing is gekoppeld.

   * Elk nieuw project dat met de het projecttovenaar van de Schermen wordt gecreeerd zal een verwijzing bevatten die aan de configuratie van de vertoningstoewijzing richt.

      ![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules2.png)

   * In een oudere versie van de projecten van het Scherm, moet de vereniging uitdrukkelijk worden bepaald door `sling:configRef` bezit toe te voegen die bij `/conf/screens` aan de knoop van de projectinhoud richten.

      ![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules3.png)

## Auteur instellen en publiceren {#setup-author-publish}

Overweeg de volgende aanbevelingen in Auteur en Publiceer voorafgaand aan het gebruiken van Aangepaste Vertoningen:

* Uitvoeringstoewijzing moet handmatig worden herhaald.

* Elementuitvoeringen worden niet standaard gerepliceerd. Alle relevante activa moeten handmatig worden gerepliceerd.

## Regels voor renderingstoewijzing toevoegen {#add-rendition-mapping-rules}

1. Als u een toewijzingsregel wilt toevoegen, moet u een knooppunt van het type `nt:unstructured` onder het knooppunt voor de renditie-toewijzing maken.

1. Voeg de expressie-eigenschap toe met de waarde die de query-expressie bevat.

   >[!NOTE]
   >Raadpleeg [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) voor meer informatie.

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat dat wordt geselecteerd als de expressie wordt geëvalueerd op true.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/mapping-rules4.png)



## De volgende stappen {#next-steps}

Nadat u de uitvoeringen hebt geconfigureerd en geüpload, kunt u als inhoudsauteur nu Adaptieve uitvoeringen gebruiken en ook uw apparaten migreren om deze functie toe te passen, op uw AEM Screens-kanalen. Zie [Aangepaste uitvoeringen gebruiken](/help/user-guide/using-adaptive-renditions.md) voor meer informatie.
