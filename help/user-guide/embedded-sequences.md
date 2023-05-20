---
title: Ingesloten reeksen
seo-title: Embedded Sequences
description: Volg deze pagina voor meer informatie over ingesloten reeksen voor kanalen waarmee de gebruiker componenten in het bovenliggende kanaal kan toevoegen en ook de inhoud van een ander kanaal kan hergebruiken en in het bovenliggende kanaal kan insluiten.
seo-description: Follow this page to learn about embedded sequences for channels that allows the user to add components in the parent channel and also to re-use the content from a different channel and embed it into the parent channel.
uuid: 72a8d4e6-e5ce-4069-bf3b-864d03f61585
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: fc13d713-af30-4a54-8408-920f78fd2b2f
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# Ingesloten reeksen {#embedded-sequences}

Gebruiken ***Ingesloten reeksen*** Met de optie voor kanalen kan de gebruiker componenten toevoegen aan het bovenliggende kanaal en ook de inhoud van een ander kanaal hergebruiken en in het bovenliggende kanaal insluiten.

## Ingesloten reeksen toevoegen {#adding-embedded-sequences}

U kunt de volgende componenten toevoegen aan uw volgnummer:

* Ingesloten reeks
* Dynamische ingesloten reeks

>[!NOTE]
>
>Om over het gebruiken van andere componenten in uw project van het Scherm te leren, zie [Componenten toevoegen aan een kanaal](adding-components-to-a-channel.md).

### Een ingesloten reeks toevoegen {#adding-an-embedded-sequence}

U kunt een ingesloten reeks toevoegen aan uw kanaal. Een ingesloten reeks is een ander kanaal dat elementen zoals afbeeldingen of video&#39;s bevat. Door een ingesloten reeks toe te voegen, kan de gebruiker de reeks aan een kanaal toevoegen door ***Kanaalpad***.

>[!NOTE]
>***Kanaalpad*** definieert een expliciete verwijzing naar het kanaal.
>Meer informatie over *Kanaalpad*, zie [Kanaaltoewijzing](channel-assignment.md) in ontwerprasters.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een pagina wilt insluiten. Bijvoorbeeld: **We.Winkel voor winkels** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klikken **Bewerken** in de actiebalk om het kanaal te openen in de editormodus.
1. Klik op het pictogram Componenten op de linkerzijbalk om de ingesloten pagina toe te voegen. Sleep de **Ingesloten reeks** aan de redacteur.
1. Dubbelklik op de knop **Ingesloten reeks** om het kanaal toe te voegen aan het oorspronkelijke volgnummer.
1. Selecteer **Kanaalpad** van het kanaal.
1. Selecteer **Duur (ms)** voor uw ingesloten kanaal in het dialoogvenster **Reeks** tab. Standaard is de duur ingesteld op **-1**, wat betekent dat het ingesloten kanaal volledig wordt uitgevoerd. Als de gebruiker een duur opgeeft, wordt de volgende duur onderbroken (dat wil zeggen cut-off) op het opgegeven tijdstip.

1. Stel de **Metered Playback Strategy** tot **normaal**.

Standaard is deze ingesteld op **normaal**. De waarde instellen op **normaal** (Alle items afspelen) betekent dat de volgende reeks volledig wordt uitgevoerd in elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Eén item afspelen** (Spel één enkel punt) en dat slechts één punt van de opeenvolging op elke looppas zou tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

>[!IMPORTANT]
>
>U moet het kanaal (gebruikt in ingesloten volgorde) aan dezelfde weergave toewijzen.
>
>Voer de onderstaande stappen uit nadat u een ingesloten reeks uit de voorgaande stappen hebt toegevoegd aan uw kanaal:
>
>1. Navigeer naar de weergave en selecteer de weergave vanuit **Locaties** map.
>1. Klikken op **Dashboard** van de actiebalk om naar het weergavedashboard te navigeren.
>1. Selecteren **+ Kanalen toewijzen** van de **TOEGEWEZEN KANALEN EN GEPLANDE DEELVENSTERS** om de **Kanaaltoewijzing, dialoogvenster**.
>
>1. Selecteer het pad van het kanaal waarin u (gebruikt in ingesloten reeks) **Kanaalpad**.
>1. Zorg ervoor dat de **Prioriteit** is lager dan het hoofdkanaal.
>
>1. U mag geen **Ondersteunde gebeurtenissen**.
>1. Klikken **Opslaan** eenmaal gedaan.

>


In het volgende voorbeeld wordt de toevoeging van een ingesloten reeks getoond (**Niet-actief kanaal, nacht**) naar een bestaand kanaal (**Niet-actief kanaal**).

![new2](assets/new2.gif)

### Een dynamische ingesloten reeks toevoegen {#adding-a-dynamic-embedded-sequence}

U kunt een dynamische ingesloten reeks toevoegen aan uw kanaal. Een dynamische ingesloten reeks lijkt op een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in één kanaal zijn aangebracht, worden doorgegeven aan een ander kanaal in relatie tot dat kanaal. De klasse volgt de bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s. Door een dynamische reeks toe te voegen, kan de gebruiker een kanaal-op-kanaalrol toevoegen.

>[!NOTE]
>
>***Kanaalrol*** Hiermee definieert u de rol Kanaal als de context van de weergave.
>
>Meer informatie over *Kanaalrol*, zie [Kanaaltoewijzing](channel-assignment.md) in ontwerprasters.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een dynamische reeks wilt insluiten. Bijvoorbeeld: **We.Winkel voor winkels** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klikken **Bewerken** in de actiebalk om het kanaal te openen in de editormodus.
1. Klik op het pictogram Componenten op de linkerzijbalk om de dynamische ingesloten reeks toe te voegen. Sleep de **Dynamisch** **Ingesloten reeks**  aan de redacteur.

1. Dubbelklik op de knop **Dynamisch** **Ingesloten reeks** om de pagina aan uw volgnummer toe te voegen.

1. Voer de **Kanaaltoewijzingsrol**.
1. Stel de **Metered Playback Strategy** tot **normaal**. Standaard is deze ingesteld op **normaal**. De waarde instellen op **normaal** (Alle items afspelen) betekent dat de volgende reeks volledig wordt uitgevoerd in elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Eén item afspelen** (Spel één enkel punt) en dat slechts één punt van de opeenvolging op elke looppas zou tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

1. Selecteer **Duur (ms)** in **Reeks** voor het ingesloten kanaal in de reeks.

![nieuwste](assets/latest.gif)
