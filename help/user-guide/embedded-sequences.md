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
feature: Ontwerpschermen
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 0%

---

# Ingesloten reeksen {#embedded-sequences}

Met ***Ingesloten reeksen*** kan de gebruiker voor kanalen componenten toevoegen aan het bovenliggende kanaal en ook de inhoud van een ander kanaal hergebruiken en deze insluiten in het bovenliggende kanaal.

## Ingesloten reeksen toevoegen {#adding-embedded-sequences}

U kunt de volgende componenten toevoegen aan uw volgnummer:

* Ingesloten reeks
* Dynamische ingesloten reeks

>[!NOTE]
>
>Om over het gebruiken van andere componenten in uw project van Schermen te leren, zie [Toevoegend Componenten aan een Kanaal](adding-components-to-a-channel.md).

### Een ingesloten reeks toevoegen {#adding-an-embedded-sequence}

U kunt een ingesloten reeks toevoegen aan uw kanaal. Een ingesloten reeks is een ander kanaal dat elementen zoals afbeeldingen of video&#39;s bevat. Door een ingesloten reeks toe te voegen, kan de gebruiker de reeks aan een kanaal toevoegen met ***Kanaalpad***.

>[!NOTE]
>***Kanaalpad*** definieert een expliciete verwijzing naar het kanaal.
>Zie [Kanaaltoewijzing](channel-assignment.md) in Ontwerpschermen voor meer informatie over *Kanaalpad*.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een pagina wilt insluiten. Bijvoorbeeld **We.Retail In-Store** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klik **Bewerken** van de actiebar om het kanaal op de redacteurswijze te openen.
1. Klik op het pictogram Componenten op de linkerzijbalk om de ingesloten pagina toe te voegen. Sleep de **Ingesloten reeks** naar de editor.
1. Dubbelklik op de component **Ingesloten reeks** om het kanaal toe te voegen aan het oorspronkelijke volgnummer.
1. Selecteer **Kanaalpad** van het kanaal.
1. Selecteer **Duur (ms)** voor uw ingesloten kanaal in **Reeks** tabel. Standaard is de duur ingesteld op **-1**, wat betekent dat het ingesloten kanaal volledig wordt uitgevoerd. Als de gebruiker een duur opgeeft, wordt de volgende duur onderbroken (dat wil zeggen cut-off) op het opgegeven tijdstip.

1. Stel de **Metered Playback Strategy** in op **normal**.

Standaard is dit **normal**. Als u de waarde instelt op **normal** (Play all items), betekent dit dat de volgende waarde volledig wordt uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Spel één enkel punt** (Spel één enkel punt) en dat slechts één punt van de opeenvolging op elke looppas zou tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

>[!IMPORTANT]
>
>U moet het kanaal (gebruikt in ingesloten volgorde) aan dezelfde weergave toewijzen.
>
>Voer de onderstaande stappen uit nadat u een ingesloten reeks uit de voorgaande stappen hebt toegevoegd aan uw kanaal:
>
>1. Navigeer naar de weergave en selecteer de weergave in de map **Locations**.
>1. Klik op **Dashboard** van de actiebar om aan het vertoningsdashboard te navigeren.
>1. Selecteer **+ Kanalen toewijzen** van **TOEGEWEZEN KANALEN &amp; GEPLANDE PANELS** om **de dialoogdoos van de Toewijzing van het Kanaal te openen**.

   >
   >
1. Selecteer het pad van het kanaal dat u (in ingesloten volgorde) in **Kanaalpad** gebruikt.
>1. Zorg ervoor dat **Priority** lager is dan het hoofdkanaal.

   >
   >
1. U mag geen **Ondersteunde gebeurtenissen** selecteren.
>1. Klik **Opslaan** eenmaal gereed.

>



Het volgende voorbeeld toont de toevoeging van een ingebedde opeenvolging (**Niet-actief Kanaal - Nacht**) aan een reeds bestaand kanaal (**Niet-actief Kanaal**).

![new2](assets/new2.gif)

### Een dynamische ingesloten reeks toevoegen {#adding-a-dynamic-embedded-sequence}

U kunt een dynamische ingesloten reeks toevoegen aan uw kanaal. Een dynamische ingesloten reeks lijkt op een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in één kanaal zijn aangebracht, worden doorgegeven aan een ander kanaal in relatie tot dat kanaal. De klasse volgt de bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s. Door een dynamische reeks toe te voegen, kan de gebruiker een kanaal-op-kanaalrol toevoegen.

>[!NOTE]
>
>***Channel*** Roledefine bepaalt de rol van het Kanaal de context van de vertoning.
>
>Zie [Kanaaltoewijzing](channel-assignment.md) in Ontwerpschermen voor meer informatie over *Kanaalrol*.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Selecteer het kanaal waar u een dynamische reeks wilt insluiten. Bijvoorbeeld **We.Retail In-Store** —> **Kanalen** —> **Niet-actief kanaal**.

1. Klik **Bewerken** van de actiebar om het kanaal op de redacteurswijze te openen.
1. Klik op het pictogram Componenten op de linkerzijbalk om de dynamische ingesloten reeks toe te voegen. Sleep **Dynamisch** **Ingesloten reeks** naar de editor.

1. Dubbelklik op de component **Dynamisch** **Ingesloten reeks** om de pagina aan het kanaal van de reeks toe te voegen.

1. Voer de **Kanaaltoewijzingsrol** in.
1. Stel de **Metered Playback Strategy** in op **normal**. Standaard is dit **normal**. Als u de waarde instelt op **normal** (Play all items), betekent dit dat de volgende waarde volledig wordt uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Spel één enkel punt** (Spel één enkel punt) en dat slechts één punt van de opeenvolging op elke looppas zou tonen (bijvoorbeeld, het eerste punt op de eerste lijn, het tweede punt op de tweede lijn, etc.)

1. Selecteer **Duur (ms)** in **Reeks** lusje voor uw ingebed kanaal in de opeenvolging.

![nieuwste](assets/latest.gif)
