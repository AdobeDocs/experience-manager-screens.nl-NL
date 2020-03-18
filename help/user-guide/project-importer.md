---
title: Nieuwe importmodule voor project uit bestand
seo-title: Nieuwe importmodule voor project uit bestand
description: Met deze functionaliteit kunt u een set locaties vanuit een CSV/XLS-spreadsheet bulksgewijs importeren naar uw AEM-schermproject.
seo-description: Met deze functionaliteit kunt u een set locaties vanuit een CSV/XLS-spreadsheet bulksgewijs importeren naar uw AEM-schermproject.
uuid: e1ad76ae-6925-4d72-80ce-8343a76125ce
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
discoiquuid: f1df8d05-bb61-4bc9-aea1-c6af9e3519b4
docset: aem65
translation-type: tm+mt
source-git-commit: 121aee4c8bf08e30898cc25d274ef4fc6bded5aa

---


# Nieuwe importmodule voor project uit bestand {#new-project-importer-from-file}

In deze sectie wordt een functionaliteit beschreven voor het bulksgewijs importeren van een set locaties vanuit een CSV/XLS-spreadsheet naar uw AEM Screens-project.

## Inleiding {#introduction}

Wanneer u een project van de Schermen van AEM, voor het eerst in uw organisatie opstelt, moet u alle plaatsen ook tot stand brengen. Als uw project een groot aantal plaatsen impliceert, resulteert het in een vervelende taak die veel het klikken en het wachten in UI impliceert.

Het doel van deze functie is de tijd die nodig is om het project op te zetten te verkorten en zo begrotingsproblemen op te lossen.

Door de auteur een spreadsheet als inputdossier te laten verstrekken, en het systeem te laten automatisch de locatieboom in het achterste eind creëren, deze eigenschap:

* *behaalt betere prestaties dan handmatig door de gebruikersinterface te klikken*
* *laat de klant de plaatsen uitvoeren zij van hun eigen systeem hebben en hen gemakkelijk direct invoeren in AEM*

Dit bespaart zowel tijd als geld tijdens aanvankelijke projectopstelling of wanneer het uitbreiden van de bestaande schermen AEM tot nieuwe plaatsen.

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
| ***path {string *}** | Het bronnenpad voor de locatie |
| ***[./jcr:title]{string *}** | De naam van de sjabloon die moet worden gebruikt (dat wil zeggen de locatie voor *schermen/kern/sjablonen/locatie*) |
| ***template {string}*** | Optionele titel voor de pagina |
| ***[./jcr:description]{string}*** | Optionele beschrijving voor de pagina |

Voor het spreadsheetbestand (CSV/XLS) zijn dus de volgende kolommen vereist:

* **path {string}** The path for the location to be imported, where the root of the path is the location folder for the project (that is, */foo* will be imported to */content/screens/&lt;project>/locations/foo*)

* **template {string}** De sjabloon die voor de nieuwe locatie moet worden gebruikt, is nu de enige toegestane waarde &#39;location&#39;, maar deze wordt in de toekomst uitgebreid naar alle schermsjablonen (&#39;display&#39;, &#39;sequencechannel&#39; enzovoort).
* **[./*]{string}**Elke optionele eigenschap die op de locatie moet worden ingesteld (dat wil zeggen: ./jcr:title, ./jcr:description, ./foo, ./bar). De huidige versie staat momenteel geen filtreren toe

>[!NOTE]
>
>Elke kolom die niet aan de bovenstaande voorwaarden voldoet, wordt gewoon genegeerd. Bijvoorbeeld, als u een andere kolom die in uw dossier van het blad (CSV/XLS) behalve **weg**,**malplaatje**,**titel**, en **beschrijving** in uw dossier wordt bepaald, zullen die gebieden worden genegeerd en zal de Importeur **van het** Project die extra gebieden voor het invoeren van uw project aan uw project van de Schermen AEM niet bevestigen.

## Project importeren gebruiken {#using-project-importer}

In de volgende sectie wordt beschreven hoe de projectimportmodule wordt gebruikt in een AEM-schermproject.

>[!CAUTION]
>
>Beperkingen:
>
>* Andere bestanden dan CSV/XLS/XLSX-extensies worden niet ondersteund in de huidige versie.
>* Er bestaat geen filter voor de eigenschappen van geïmporteerde bestanden en alles wat begint met &quot;./&quot; wordt geïmporteerd.
>



### Vereisten {#prerequisites}

* Een nieuw project maken met de naam **DemoProjectImport**

* Gebruik een voorbeeld-CSV- of Excel-bestand dat u wilt importeren.

Voor demo-doeleinden kunt u een Excel-bestand downloaden uit de onderstaande sectie.

[Bestand ophalen](assets/minimal-file.xls)

### Het bestand met minimaal vereiste velden importeren {#importing-the-file-with-minimum-required-fields}

Voer de onderstaande stappen uit om een bestand te importeren naar de map locations met minimaal vereiste velden:

>[!NOTE]
>
>In het volgende voorbeeld worden de minimaal vier velden weergegeven die vereist zijn om uw project te importeren:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigeer naar uw AEM-rasterproject (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Selecteer het project,** DemoProjectImporter **—>** Maken **—>** Locaties importeren** op de zijbalk.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. De wizard **Importeren** wordt geopend. Selecteer het bestand dat u voor uw project hebt met locaties of selecteer het bestand (***minimum-file.xls***) dat u hebt gedownload in de sectie *Voorwaarden* .

   Als u het bestand hebt geselecteerd, klikt u op **Volgende**.

   ![screen_shot_2019-05-15at113718am](assets/screen_shot_2019-05-15at113718am.png)

1. Controleer de inhoud van het bestand (locaties) via de wizard Importeren en klik op **Importeren**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. Hierdoor kunt u nu alle locaties weergeven die in uw project zijn geïmporteerd.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)

