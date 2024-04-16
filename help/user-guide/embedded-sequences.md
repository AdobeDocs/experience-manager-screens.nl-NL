---
title: Ingesloten reeksen
description: Leer over ingebedde opeenvolgingen voor kanalen die u componenten in het ouderkanaal toevoegen en ook de inhoud van een verschillend kanaal hergebruiken en het inbedden in het ouderkanaal.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 0%

---

# Ingesloten reeksen {#embedded-sequences}

Gebruiken ***Ingesloten reeksen*** Met de optie Kanalen kan de gebruiker componenten toevoegen aan het bovenliggende kanaal en ook de inhoud van een ander kanaal hergebruiken en in het bovenliggende kanaal insluiten.

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

1. Klik op het kanaal waar u een pagina wilt insluiten. Bijvoorbeeld: **`We.Retail`In-Store** > **Kanalen** > **Niet-actief kanaal**.

1. Klikken **Bewerken** in de actiebalk.
1. Klik in de editormodus op het pictogram Componenten op de linkerzijbalk, zodat u de ingesloten pagina kunt toevoegen. Sleep de **Ingesloten reeks** aan de redacteur.
1. Dubbelklik op de knop **Ingesloten reeks** zodat u het kanaal aan uw origineel opeenvolgingskanaal kunt toevoegen.
1. Klik op de knop **Kanaalpad** van het kanaal.
1. Klik op de knop **Duur (milliseconden)** voor uw ingesloten kanaal in het dialoogvenster **Reeks** tab. Standaard is de duur ingesteld op **-1**, wat betekent dat het ingesloten kanaal volledig wordt uitgevoerd. Als de gebruiker een duur opgeeft, wordt de volgende duur onderbroken (dat wil zeggen, wordt deze onderbroken) op het opgegeven tijdstip.

1. Stel de **Metered Playback Strategy** tot **normaal**.

Standaard is deze ingesteld op **normaal**. De waarde instellen op **normaal** (Alle items afspelen) betekent dat de volgende reeks volledig wordt uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Eén item afspelen**. Die waarde toont slechts één punt van de verdere opeenvolging op elke looppas. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.

>[!IMPORTANT]
>
>Wijs het kanaal dat in ingesloten volgorde wordt gebruikt, toe aan dezelfde weergave.
>
>Voer de onderstaande stappen uit nadat u een ingesloten reeks uit de voorgaande stappen hebt toegevoegd aan uw kanaal:
>
>1. Navigeer naar de weergave en klik op de weergave vanuit **Locaties** map.
>1. Klikken **Dashboard** in de actiebalk.
>1. Klik op het weergavedashboard op **+ Kanalen toewijzen** van de **TOEGEWEZEN KANALEN EN GEPLANDE DEELVENSTERS** zodat u de **Kanaaltoewijzing, dialoogvenster**.
>
>1. Klik op het pad van het kanaal waarin u (gebruikt in ingesloten reeks) **Kanaalpad**.
>1. Zorg ervoor dat de **Prioriteit** is lager dan het hoofdkanaal.
>
>1. Klik niet op **Ondersteunde gebeurtenissen**.
>1. Klikken **Opslaan** wanneer gereed.
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

1. Klik op het kanaal waar u een dynamische reeks wilt insluiten. Bijvoorbeeld: **`We.Retail`In-Store** > **Kanalen** > **Niet-actief kanaal**.

1. Klikken **Bewerken** in de actiebalk.
1. Klik in de editormodus op het componentpictogram op de linkerzijbalk, zodat u de dynamische ingesloten reeks kunt toevoegen. Sleep de **Dynamisch** **Ingesloten reeks** aan de redacteur.

1. Dubbelklik op de knop **Dynamisch** **Ingesloten reeks** zodat u de pagina aan uw opeenvolgingskanaal kunt toevoegen.

1. Voer de **Kanaaltoewijzingsrol**.
1. Stel de **Metered Playback Strategy** tot **normaal**. Standaard is deze ingesteld op **normaal**. De waarde instellen op **normaal** (Alle items afspelen) betekent dat de volgende reeks volledig wordt uitgevoerd op elke cyclus van de bovenliggende reeks. De andere mogelijke waarde is **Eén item afspelen**. Die waarde toont slechts één punt van de verdere opeenvolging op elke looppas. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.

1. Klik op de knop **Duur (milliseconden)** in **Reeks** voor het ingesloten kanaal in de reeks.

![nieuwste](assets/latest.gif)
