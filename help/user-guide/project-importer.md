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
source-git-commit: c0fa0717034e5094108eb1e23d4e9f1f16aeb57e
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Nieuwe importmodule voor project uit bestand {#new-project-importer-from-file}

In deze sectie wordt een functionaliteit beschreven voor het bulksgewijs importeren van een set locaties vanuit een CSV/XLS-spreadsheet naar uw AEM Screens-project.

## Inleiding {#introduction}

Wanneer u een AEM Screens-project voor het eerst in uw organisatie instelt, moet u ook alle locaties maken. Als uw project vele plaatsen impliceert, resulteert het in een vervelende taak die veel het klikken en het wachten in UI impliceert.

Het doel van deze functie is de tijd die nodig is om het project op te zetten te verkorten en zo begrotingsproblemen op te lossen.

Door de auteur een spreadsheet als inputdossier te laten verstrekken, en het systeem te laten automatisch de locatieboom in het achterste eind creëren, deze eigenschap:

* *behaalt betere prestaties dan handmatig door de gebruikersinterface te klikken*
* *laat de klant de plaatsen uitvoeren zij van hun eigen systeem hebben en hen gemakkelijk direct in AEM invoeren*

Dit bespaart zowel tijd als geld tijdens aanvankelijke projectopstelling of wanneer het uitbreiden van bestaande AEM Screens tot nieuwe plaatsen.

## Overzicht van architectuur {#architectural-overview}

In het volgende diagram ziet u het architecturale overzicht van de functie Project Importer:

![screen_shot_2019-05-14at20618pm](assets/screen_shot_2019-05-14at20618pm.png)

### Gegevensmodel {#data-model}

Het gegevensmodel voor de projectimportmodule wordt hieronder beschreven:

>[!NOTE]
>
>De huidige versie ondersteunt alleen het importeren van locaties.

| **Eigenschap** | **Beschrijving** |
|---|---|
| ***`path {string*}`*** | Het bronnenpad voor de locatie |
| ***`[./jcr:title] {string*}`*** | De naam van de sjabloon die moet worden gebruikt (dat wil zeggen de locatie voor *schermen/kern/sjablonen/locatie*) |
| ***`template {string}`*** | Optionele titel voor de pagina |
| ***`[./jcr:description] {string}`*** | Optionele beschrijving voor de pagina |

Voor het spreadsheetbestand (CSV/XLS) zijn dus de volgende kolommen vereist:

* **pad {string}** - Het pad voor de te importeren locatie, waarbij de hoofdmap van het pad de locatiemap voor het project is (dat wil zeggen: *`/foo`* wordt geïmporteerd naar *`/content/screens/<project>/locations/foo`*)
* **template {string}** - De sjabloon die voor de nieuwe locatie moet worden gebruikt, is nu de enige toegestane waarde &quot;location&quot;, maar deze wordt in de toekomst uitgebreid tot alle screeningsjablonen (`display`, `sequencechannel`, enzovoort)
* **[./*] {string}** - Een optionele eigenschap die op de locatie moet worden ingesteld (dat wil zeggen: `./jcr:title`, `./jcr:description`, `./foo, ./bar`). De huidige versie staat geen filtreren toe.

>[!NOTE]
>
>Een kolom die niet voldoet aan de bovenstaande voorwaarden, wordt genegeerd. Als er bijvoorbeeld een andere kolom in het bestand CSV/XLS (sheet) is gedefinieerd, behalve **pad**, **template**, **titel**, en **beschrijving** in uw bestand worden deze velden genegeerd. En, **Project importeren** valideert deze aanvullende velden voor het importeren van uw project naar uw AEM Screens-project niet.

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

* Een project maken met de naam **DemoProjectImport**

* Gebruik een voorbeeld-CSV- of Excel-bestand dat u moet importeren.

Voor demo-doeleinden kunt u een Excel-bestand downloaden uit de onderstaande sectie.

[Bestand ophalen](assets/minimal-file.xls)

### Het bestand met minimaal vereiste velden importeren {#importing-the-file-with-minimum-required-fields}

Voer de onderstaande stappen uit om een bestand te importeren naar een locatiemap met minimaal vereiste velden:

>[!NOTE]
>
>In het volgende voorbeeld worden de minimaal vier velden weergegeven die vereist zijn om uw project te importeren:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Ga naar uw AEM Screens-project (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Selecteer het project,** DemoProjectImporter **>** Maken **>** Locaties** importeren vanaf de zijbalk.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. De **Importeren** wordt weergegeven. Selecteer het bestand voor uw project met locaties of selecteer het bestand (***minimum-file.xls***) die u hebt gedownload van de *Vereisten* sectie.

   Als u het bestand hebt geselecteerd, klikt u op **Volgende**.

   ![screen_shot_2019-05-15at113718am](assets/screen_shot_2019-05-15at113718am.png)

1. Controleer de inhoud van het bestand (locaties) via de wizard Importeren en klik op **Importeren**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. Hierdoor kunt u nu alle locaties weergeven die in uw project zijn geïmporteerd.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)
