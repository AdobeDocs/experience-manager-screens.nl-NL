---
title: Ingesloten reeksen
description: Leer over ingebedde opeenvolgingen voor kanalen die u componenten in het ouderkanaal laten toevoegen. U kunt de inhoud ook vanuit een ander kanaal hergebruiken en in het bovenliggende kanaal insluiten.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Ingesloten reeksen {#embedded-sequences}

Gebruikend ***Ingebedde Reeksen***, voor kanalen, laat een gebruiker componenten in het ouderkanaal toevoegen en ook de inhoud van een verschillend kanaal hergebruiken en het inbedden in het ouderkanaal.

## Ingesloten reeksen toevoegen {#adding-embedded-sequences}

U kunt de volgende componenten toevoegen aan uw volgnummer:

* Ingesloten reeks
* Dynamische ingesloten reeks

>[!NOTE]
>
>Om over het gebruiken van andere componenten in uw project van Screens te leren, zie [&#x200B; Toevoegend Componenten aan een Kanaal &#x200B;](adding-components-to-a-channel.md).

### Een ingesloten reeks toevoegen {#adding-an-embedded-sequence}

U kunt een ingesloten reeks toevoegen aan uw kanaal. Een ingesloten reeks is een ander kanaal dat elementen zoals afbeeldingen of video&#39;s bevat. Toevoegend een ingebedde opeenvolging staat de gebruiker toe om de opeenvolging aan een kanaal toe te voegen door ***Weg van het Kanaal***.

>[!NOTE]
>***Weg van het Kanaal*** bepaalt een expliciete verwijzing naar het kanaal.
>Meer over *Weg van het Kanaal* leren, zie [&#x200B; Toewijzing van het Kanaal &#x200B;](channel-assignment.md) in het Authoring van Screens.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Klik op het kanaal waar u een pagina wilt insluiten. Bijvoorbeeld, **`We.Retail`in-opslag** > **Kanalen** > **Onactief Kanaal**.

1. Klik **uitgeven** van de actiebar.
1. Klik in de editormodus op het componentpictogram op de linkerzijbalk, zodat u de ingesloten pagina kunt toevoegen. Sleep en laat vallen de **Ingebedde Opeenvolging** aan de redacteur.
1. Dubbelklik de **Ingebedde component van de Opeenvolging** zodat kunt u het kanaal aan uw origineel opeenvolgingskanaal toevoegen.
1. Klik de **Weg van het Kanaal** van het kanaal.
1. Klik de **Duur (milliseconden)** voor uw ingebedde kanaal in de **Opeenvolging** tabel. Door gebrek, wordt de duur geplaatst aan **- 1**, dat betekent het ingebedde kanaal volledig in werking wordt gesteld. Als de gebruiker een duur opgeeft, wordt de volgende duur onderbroken (dat wil zeggen, wordt deze onderbroken) op het opgegeven tijdstip.

1. Plaats de **Gememateerde Strategie van de Playback** aan **normaal**.

Door gebrek, wordt het geplaatst aan **normaal**. Het plaatsen van de waarde aan **normaal** (Spel alle punten) betekent dat de verdere looppas volledig op elke cyclus van de ouderopeenvolging. De andere mogelijke waarde is **Spel één enkel punt**. Die waarde toont slechts één punt van de verdere opeenvolging op elke looppas. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.

>[!IMPORTANT]
>
>Wijs het kanaal dat in de ingesloten reeks wordt gebruikt aan de zelfde vertoning toe.
>
>Voer de onderstaande stappen uit nadat u een ingesloten reeks uit de voorgaande stappen hebt toegevoegd aan uw kanaal:
>
>1. Navigeer aan de vertoning en klik de vertoning van de **omslag van Plaatsen**.
>1. Klik **Dashboard** van de actiebar.
>1. Op het vertoningsdashboard, klik **+ Wijs Kanalen** van **TOEGEWEZEN KANALEN &amp; GEPLANDE PANELS** toe zodat kunt u het **de dialoogvakje van de Toewijzing van het Kanaal openen**.
>
>1. Klik de weg van het kanaal dat u in de ingebedde opeenvolging, in **Weg van het Kanaal** gebruikte.
>1. Zorg ervoor dat de **Prioriteit** lager is dan het belangrijkste kanaal.
>
>1. Klik geen **Gesteunde Gebeurtenissen**.
>1. Klik **sparen** wanneer gedaan.
>

Het volgende voorbeeld toont de toevoeging van een ingebedde opeenvolging (**Niet-actief Kanaal - Nacht**) aan een bestaand kanaal (**Onactief Kanaal**).

![&#x200B; new2 &#x200B;](assets/new2.gif)

### Een dynamische ingesloten reeks toevoegen {#adding-a-dynamic-embedded-sequence}

U kunt een dynamische ingesloten reeks toevoegen aan uw kanaal. Een dynamische ingesloten reeks lijkt op een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in één kanaal zijn aangebracht, worden doorgegeven aan een ander kanaal in relatie tot dat kanaal. De klasse volgt een bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s. Door een dynamische reeks toe te voegen, kan de gebruiker een kanaal toevoegen via Kanaalrol.

>[!NOTE]
>
>{de Rol van het 0} Kanaal ***bepaalt de context van de vertoning.***
>
>Meer over *Rol van het Kanaal* leren, zie [&#x200B; Toewijzing van het Kanaal &#x200B;](channel-assignment.md) in het Authoring van Screens.

Voer de onderstaande stappen uit om een ingesloten reeks aan uw kanaal toe te voegen:

1. Klik op het kanaal waar u een dynamische reeks wilt insluiten. Bijvoorbeeld, **`We.Retail`in-opslag** > **Kanalen** > **Onactief Kanaal**.

1. Klik **uitgeven** van de actiebar.
1. Klik in de editormodus op het componentpictogram op de linkerzijbalk, zodat u de dynamische ingesloten reeks kunt toevoegen. De belemmering en laat vallen **Dynamische** **Ingebedde Opeenvolging** aan de redacteur.

1. Dubbelklik de **Dynamische** **Ingebedde component van de Opeenvolging** zodat kunt u de pagina aan uw opeenvolgingskanaal toevoegen.

1. Ga de **Rol van de Taak van het Kanaal** in.
1. Plaats de **Gememateerde Strategie van de Playback** aan **normaal**. Door gebrek, wordt het geplaatst aan **normaal**. Het plaatsen van de waarde aan **normaal** (Spel alle punten) betekent dat de verdere looppas volledig op elke cyclus van de ouderopeenvolging. De andere mogelijke waarde is **Spel één enkel punt**. Die waarde toont slechts één punt van de verdere opeenvolging op elke looppas. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.

1. Klik de **Duur (milliseconden)** in het **3&rbrace; lusje van de Opeenvolging &lbrace;voor uw ingebed kanaal in de opeenvolging.**

![&#x200B; recentste &#x200B;](assets/latest.gif)
