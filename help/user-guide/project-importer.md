---
title: Nieuwe importmodule voor project uit bestand
description: Met deze functie kunt u een set locaties vanuit een CSV/XLS-spreadsheet bulksgewijs importeren naar uw AEM Screens-project.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3bff9ef3-0d6f-41d8-a8ef-bcc5a795990e
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Nieuwe importmodule voor project uit bestand {#new-project-importer-from-file}

In deze sectie wordt een functionaliteit beschreven voor het bulksgewijs importeren van een set locaties vanuit een CSV/XLS-spreadsheet naar uw AEM Screens-project.

## Inleiding {#introduction}

Wanneer u een AEM Screens-project voor het eerst in uw organisatie instelt, maakt u ook alle locaties. Als uw project vele plaatsen impliceert, resulteert het in een vervelende taak die veel het selecteren en het wachten in UI impliceert.

Het doel van deze functie is de tijd die nodig is om het project op te zetten te verkorten en zo begrotingsproblemen op te lossen.

Door de auteur een spreadsheet als inputdossier te laten verstrekken, en het systeem te laten automatisch de locatieboom in het achterste eind creëren, deze eigenschap:

* *bereikt betere prestaties dan manueel het selecteren door UI*
* *laat de klant de plaatsen uitvoeren zij van hun eigen systeem hebben en hen gemakkelijk direct in AEM* invoeren

Dit proces bespaart zowel tijd als geld tijdens aanvankelijke projectopstelling of wanneer het uitbreiden van bestaande AEM Screens tot nieuwe plaatsen.

## Overzicht van architectuur {#architectural-overview}

In het volgende diagram ziet u het architecturale overzicht van de functie Project Importer:

![ screen_shot_2019-05-14at20618pm ](assets/screen_shot_2019-05-14at20618pm.png)

### Gegevensmodel {#data-model}

Het gegevensmodel voor de projectimportmodule wordt hieronder beschreven:

>[!NOTE]
>
>De huidige versie ondersteunt alleen het importeren van locaties.

| **Bezit** | **Beschrijving** |
|---|---|
| ***`path {string*}`*** | Het bronnenpad voor de locatie |
| ***`[./jcr:title] {string*}`*** | De naam van het malplaatje aan gebruik (namelijk de plaats voor *schermen/kern/templates/plaats*) |
| ***`template {string}`*** | Optionele titel voor de pagina |
| ***`[./jcr:description] {string}`*** | Optionele beschrijving voor de pagina |

Voor het spreadsheetbestand (CSV/XLS) zijn dus de volgende kolommen vereist:

* **weg {string}** - de weg voor de plaats die moet worden ingevoerd, waar de wortel van de weg de plaatsomslag voor het project (namelijk *`/foo`* wordt ingevoerd in *`/content/screens/<project>/locations/foo`*) is
* **malplaatje {string}** - het malplaatje voor de nieuwe plaats te gebruiken, nu is de enige toegestane waarde &quot;plaats&quot;, maar deze waarde wordt uitgebreid tot alle malplaatjes van Screens in de toekomst (`display`, `sequencechannel`, etc.)
* **[./* ] {string}** - Om het even welke facultatieve bezit dat op de plaats (namelijk `./jcr:title`, `./jcr:description`, `./foo, ./bar`) moet worden geplaatst. De huidige versie staat geen filtreren toe.

>[!NOTE]
>
>Een kolom die niet voldoet aan de bovenstaande voorwaarden, wordt genegeerd. Bijvoorbeeld, als u een andere kolom hebt die in uw blad (CSV/XLS) dossier buiten **wordt bepaald weg**, **malplaatje**, **titel**, en **beschrijving** in uw dossier, worden die gebieden genegeerd. En, **bevestigt de Importeur van het Project** niet die extra gebieden voor het invoeren van uw project aan uw project van AEM Screens.

## Project importeren gebruiken {#using-project-importer}

In de volgende sectie wordt beschreven hoe de projectimportmodule wordt gebruikt in een AEM Screens-project.

>[!CAUTION]
>
>Beperkingen:
>
>* Andere bestanden dan CSV/XLS/XLSX-extensies worden niet ondersteund in de huidige versie.
>* Er bestaat geen filter voor de eigenschappen van geïmporteerde bestanden en alles wat begint met &quot;./&quot; wordt geïmporteerd.
>

### Vereisten {#prerequisites}

* Creeer een project dat als **wordt genoemd DemoProjectImport**

* Gebruik een voorbeeld-CSV- of Excel-bestand dat u moet importeren.

Voor demo-doeleinden kunt u een Excel-bestand downloaden uit de onderstaande sectie.

[Bestand ophalen](assets/minimal-file.xls)

### Het bestand met minimaal vereiste velden importeren {#importing-the-file-with-minimum-required-fields}

Voer de onderstaande stappen uit om een bestand te importeren naar een locatiemap met de minimaal vereiste velden:

>[!NOTE]
>
>In het volgende voorbeeld worden de minimaal vier velden weergegeven die vereist zijn om uw project te importeren:

![ screen_shot_2019-05-14at21523pm ](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigeer aan uw project van AEM Screens (**DemoProjectImport**).

   ![ screen_shot_2019-05-12at52651am ](assets/screen_shot_2019-05-12at52651am.png)

1. Klik het project,** DemoProjectImporter **>** creeer **>** de Plaatsen van de Invoer** van de zijbar.

   ![ screen_shot_2019-05-12at52433am ](assets/screen_shot_2019-05-12at52433am.png)

1. De **tovenaar van de Invoer** wordt getoond. Klik het dossier voor uw project met plaatsen of klik het dossier (***minimum-file.xls***) u van de *sectie van Eerste vereisten* downloadde.

   Nadat u het dossier hebt geselecteerd, klik **daarna**.

   ![ screen_shot_2019-05-15at113718am ](assets/screen_shot_2019-05-15at113718am.png)

1. Verifieer de inhoud van het dossier (plaatsen) van de tovenaar van de Invoer en klik **Invoer**.

   ![ screen_shot_2019-05-12at53131am ](assets/screen_shot_2019-05-12at53131am.png)

1. Hierdoor kunt u nu alle locaties weergeven die in uw project zijn geïmporteerd.

   ![ screen_shot_2019-05-12at53450am ](assets/screen_shot_2019-05-12at53450am.png)
