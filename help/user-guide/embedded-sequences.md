---
title: Ingesloten reeksen
seo-title: Ingesloten reeksen
description: Volg deze pagina voor meer informatie over ingesloten reeksen voor kanalen waarmee de gebruiker componenten in het bovenliggende kanaal kan toevoegen en ook de inhoud van een ander kanaal kan hergebruiken en in het bovenliggende kanaal kan insluiten.
seo-description: Volg deze pagina voor meer informatie over ingesloten reeksen voor kanalen waarmee de gebruiker componenten in het bovenliggende kanaal kan toevoegen en ook de inhoud van een ander kanaal kan hergebruiken en in het bovenliggende kanaal kan insluiten.
uuid: 72a8d4e6-e5ce-4069-bf3b-864d03f61585
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: fc13d713-af30-4a54-8408-920f78fd2b2f
docset: aem65
translation-type: tm+mt
source-git-commit: 23ecaf3533c2298d98c37f2bbcb6cbe50aed17fc

---


# Ingesloten reeksen {#embedded-sequences}

Met ***Ingesloten reeksen*** kan de gebruiker voor kanalen componenten toevoegen aan het bovenliggende kanaal en ook de inhoud van een ander kanaal hergebruiken en in het bovenliggende kanaal insluiten.

## Ingesloten reeksen toevoegen {#adding-embedded-sequences}

U kunt de volgende componenten toevoegen aan uw volgnummer:

* Ingesloten reeks
* Dynamische ingesloten reeks

>[!NOTE]
>
>Meer over het gebruiken van andere componenten in uw project van het Scherm, zie het [Toevoegen van Componenten aan een Kanaal](adding-components-to-a-channel.md).

### Een ingesloten reeks toevoegen {#adding-an-embedded-sequence}

U kunt een ingesloten reeks toevoegen aan uw kanaal. Een ingesloten reeks is een ander kanaal dat elementen zoals afbeeldingen of video&#39;s bevat. Door een ingesloten reeks toe te voegen, kan de gebruiker de reeks via ***Kanaalpad*** aan een kanaal toevoegen.

>[!NOTE]
>
>***Kanaalpad*** definieert een expliciete verwijzing naar het kanaal.
>
>Voor meer informatie over de Weg *van het* Kanaal, zie de Toewijzing [van het](channel-assignment.md) Kanaal in de Authoring Schermen.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een pagina wilt insluiten. Bijvoorbeeld **We.Retail In-Store** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klik op **Bewerken** op de actiebalk om het kanaal te openen in de bewerkingsmodus.
1. Klik op het pictogram Componenten op de linkerzijbalk om de ingesloten pagina toe te voegen. Sleep de **ingesloten reeks** naar de editor.
1. Dubbelklik op de component **Ingesloten reeks** om het kanaal aan het oorspronkelijke volgnummer toe te voegen.
1. Selecteer het **Kanaalpad** van het kanaal.
1. Selecteer de **Duur (ms)** voor het ingesloten kanaal op het tabblad **Reeks** . Standaard is de duur ingesteld op **-1**, wat betekent dat het ingesloten kanaal volledig wordt uitgevoerd. Als de gebruiker een duur opgeeft, wordt de volgende duur onderbroken (dat wil zeggen cut-off) op het opgegeven tijdstip.

1. Stel de **Metered Playback Strategy** in op **normal**.

Standaard is deze ingesteld op **normaal**. Als u de waarde instelt op **normaal** (Alle items afspelen), wordt de volgende waarde volledig uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is één enkel punt **** Spelen (Spel één enkel punt) en die slechts één punt van de opeenvolging op elke looppas zouden tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

>[!Ibelangrijk]
>U moet het kanaal (gebruikt in ingesloten volgorde) aan dezelfde weergave toewijzen.
>
>Voer de onderstaande stappen uit nadat u een ingesloten reeks uit de voorgaande stappen hebt toegevoegd aan uw kanaal:
>
>1. Navigeer naar de weergave en selecteer de weergave in de map **Locations** .
>1. Klik op het **dashboard** op de actiebalk om naar het weergavedashboard te navigeren.
>1. Selecteer **+ Kanalen** toewijzen in de **TOEGEWEZEN KANALEN EN GEPLANDE DEELVENSTERS** om het dialoogvenster **** Kanaaltoewijzing te openen.
   >
   >
1. Selecteer het pad van het kanaal dat u (in ingesloten volgorde) in **Kanaalpad** gebruikt.
>1. Controleer of de **prioriteit** lager is dan het hoofdkanaal.
   >
   >
1. U mag geen **ondersteunde gebeurtenissen** selecteren.
>1. Klik eenmaal op **Opslaan** .
>



In het volgende voorbeeld ziet u hoe u een ingesloten reeks (**Niet-actief kanaal - Nacht**) toevoegt aan een bestaand kanaal (**Niet-actief kanaal**).

![new2](assets/new2.gif)

### Een dynamische ingesloten reeks toevoegen {#adding-a-dynamic-embedded-sequence}

U kunt een dynamische ingesloten reeks toevoegen aan uw kanaal. Een dynamische ingesloten reeks lijkt op een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in één kanaal zijn aangebracht, worden doorgegeven aan een ander kanaal in relatie tot dat kanaal. De klasse volgt de bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s. Door een dynamische reeks toe te voegen, kan de gebruiker een kanaal-voor-kanaalrol toevoegen.

>[!NOTE]
>
>***De rol*** van het Kanaal bepaalt de rol van het Kanaal bepaalt de context van de vertoning.
>
>Meer over de Rol *van het* Kanaal, zie de Toewijzing [van het](channel-assignment.md) Kanaal in de Authoring Schermen.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een dynamische reeks wilt insluiten. Bijvoorbeeld **We.Retail In-Store** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klik op **Bewerken** op de actiebalk om het kanaal te openen in de bewerkingsmodus.
1. Klik op het pictogram Componenten op de linkerzijbalk om de dynamische ingesloten reeks toe te voegen. Sleep en **zet deDynamische** **Ingesloten Reeks **naar de redacteur neer.

1. Dubbelklik op de component **Dynamische** **ingesloten reeks** om de pagina aan het kanaal van de reeks toe te voegen.

1. Voer de **rol** Kanaaltoewijzing in.
1. Stel de **Metered Playback Strategy** in op **normal**. Standaard is deze ingesteld op **normaal**. Als u de waarde instelt op **normaal** (Alle items afspelen), wordt de volgende waarde volledig uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is één enkel punt **** Spelen (Spel één enkel punt) en die slechts één punt van de opeenvolging op elke looppas zouden tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

1. Selecteer de **Duur (ms)** op het tabblad **Reeks** voor het ingesloten kanaal in de reeks.

![nieuwste](assets/latest.gif)
