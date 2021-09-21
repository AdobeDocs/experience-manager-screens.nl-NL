---
title: Adaptieve uitvoeringen in AEM Screens
description: Op deze pagina vindt u het overzicht van de architectuur en de configuraties voor adaptieve uitvoeringen in AEM Screens.
index: false
source-git-commit: 773632de04b10b2e9040fede8e85e8d9092be5a6
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---


# Adaptieve uitvoeringen: Overzicht en configuraties van architectuur {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *main* slechts te concentreren ervaring.

## Doelstelling {#objective}

Als AEM Screens Developer kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudvariaties hoeft te maken. U moet de adaptieve uitvoeringen configureren voordat een inhoudsauteur deze functie in een AEM Screens-kanaal kan gebruiken.

Als u dus een aantal verschillende apparaten hebt geïmplementeerd, kan het apparaat met deze functie automatisch de meest geschikte uitvoering van een element downloaden en afspelen op basis van de regels.

## Overzicht van architectuur {#architectural-overview}

Aangepaste uitvoeringen zijn gebaseerd op het idee dat meerdere elementuitvoeringen worden genoemd volgens een specifieke naamgevingsconventie. Het besluit om een specifieke vertoning af te spelen wordt genomen door media vraaguitdrukkingen te evalueren die slechts op apparaten met verwachte mogelijkheden kunnen worden opgelost. De mogelijkheid om een gekoppeld naamgevingspatroon voor vertoningen te hebben, definieert een regel voor vertoningstoewijzing. Na het berekenen van alle beschikbare uitdrukkingen zal de speler van het Scherm de noemende patronen verzamelen die aan de passende regels beantwoorden. De patronen worden gebruikt om de juiste vertoningen tijdens het opeenvolgingsplayback te vinden door de patronen in de vertoningsnamen te zoeken.


## De instelling configureren voor het gebruik van adaptieve uitvoeringen {#setup-adaptive-renditions}

Om de Aangepaste eigenschap van Uitvoeringen toe te laten, zouden de toewijzingsregels aanwezig moeten zijn en de configuratie van CA oplosbaar voor kanalen en vertoningen:

1. Controleer of de configuratie van de vertoningstoewijzing bestaat in `JCR`. Alle recentste eigenschapspakketten hebben deze knoopstructuur vooraf bevolkt.

   >[!NOTE]
   >Alle recentste eigenschapspakketten hebben deze knoopstructuur vooraf bevolkt.


1. Zorg ervoor dat aan het project Screens de configuratie van de vertoningstoewijzing is gekoppeld.

   * Elk nieuw project dat met de het projecttovenaar van de Schermen wordt gecreeerd zal een verwijzing bevatten die aan de configuratie van de vertoningstoewijzing richt.

   * In een oudere versie van de projecten van het Scherm, moet de vereniging uitdrukkelijk worden bepaald door `sling:configRef` bezit toe te voegen die bij `/conf/screens` aan de knoop van de projectinhoud richten.

## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken, adviseert men dat de migratie geleidelijk wordt gedaan om de risico&#39;s te verlichten aangezien de eigenschap veranderingen in manifest en dossieropslagformaat zal introduceren.

Om de eigenschap toe te laten, voeg minstens één toewijzingsregel toe en zorg ervoor de configuratie van de vertoningstoewijzing in de context van vertoningen en kanalen oplosbaar is:

1. Regels voor renderingstoewijzing toevoegen.
1. Maak een map voor nieuwe kanalen en voeg een verwijzing toe die naar de configuratie van de vertoningstoewijzing wijst.
1. Maak nieuwe kanalen die de oude vervangen en upload uitvoeringen.
1. Wijs vertoningen aan de nieuwe kanalen opnieuw toe.
1. Voeg een verwijzing naar de gemigreerde vertoningen/plaatsen toe die bij de configuratie van de vertoningstoewijzing richten.
1. Herhaal stap 3, 4 en 5 voor alle resterende kanalen en beeldschermen.
1. Na het beëindigen met migratie, verwijder alle config verwijzingen uit kanalen/vertoningen/plaatsen en voeg één aan de knoop van de projectinhoud toe.

## Auteur instellen en publiceren {#setup-author-publish}

Overweeg de volgende aanbevelingen in Auteur en Publiceer voorafgaand aan het gebruiken van Aangepaste Vertoningen:

* Uitvoeringstoewijzing moet handmatig worden herhaald.

* Elementuitvoeringen worden niet standaard gerepliceerd. Alle relevante activa moeten handmatig worden gerepliceerd.

## Regels voor renderingstoewijzing toevoegen {#adding-rendition-mapping-rules}

1. Als u een toewijzingsregel wilt toevoegen, moet u een knooppunt van het type `nt:unstructured` onder het knooppunt voor de renditie-toewijzing maken.

1. Voeg de expressie-eigenschap toe met de waarde die de query-expressie bevat.

   >[!NOTE]
   >Raadpleeg [Mediaquerysyntaxis gebruiken](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) voor meer informatie.

1. Voeg de patrooneigenschap toe met de waarde die het weergavematroon bevat dat wordt geselecteerd als de expressie wordt geëvalueerd op true.

## Uitvoeringen uploaden {#upload-renditions}

1. Maak een versie van het element die beter geschikt is voor de signaalweergave, bijvoorbeeld `portrait orientation`.

1. Kies het naamgevingspatroon van de vertoning, bijvoorbeeld `portrait`.

1. Wijzig de naam van het elementbestand zodat het het patroon bevat, bijvoorbeeld `my_asset_portrait.png`.

1. Upload de vertoning door op de knop Vertoning toevoegen op de werkbalk te klikken.


## De volgende stappen {#next-steps}

Nadat u de uitvoeringen hebt geüpload, kunt u nu Adaptieve uitvoeringen gebruiken in uw AEM Screens-kanalen. Zie Adaptieve uitvoeringen gebruiken voor meer informatie.
