---
title: Tekstbedekking
seo-title: Tekstbedekking
description: Tekstbedekking is een functie die beschikbaar is in AEM-rasters en waarmee u een aantrekkelijke ervaring kunt creëren in een volgreekskanaal door een titel of een beschrijving boven op een afbeelding op te geven. Volg deze pagina voor meer informatie.
seo-description: Tekstbedekking is een functie die beschikbaar is in AEM-rasters en waarmee u een aantrekkelijke ervaring kunt creëren in een volgreekskanaal door een titel of een beschrijving boven op een afbeelding op te geven. Volg deze pagina voor meer informatie.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Tekstbedekking {#text-overlay}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Tekstbedekking gebruiken**
* **Vereisten**
* **Eigenschappen van tekstbedekking**

>[!CAUTION]
>
>De functie **Tekstbedekking** is alleen beschikbaar als u AEM 6.3 Feature Pack 5 of AEM 6.4 Feature Pack 3 hebt geïnstalleerd.

## Overzicht {#overview}

Tekstbedekking is een functie die beschikbaar is in AEM-rasters en waarmee u een aantrekkelijke ervaring kunt creëren in een volgreekskanaal door een titel of een beschrijving boven op een afbeelding op te geven.

Als u wilt leren hoe u uw eigen aangepaste component maakt, raadpleegt u **Een AEM-schermaponent** uitbreiden.

In deze sectie wordt alleen uitgelegd hoe u de postercomponent in een AEM-rasterproject kunt gebruiken en gebruiken als tekstbedekking in een van uw reekskanalen.

## Tekstbedekking gebruiken {#using-text-overlay}

In de volgende sectie wordt het gebruik van tekstbedekking in een AEM-schermproject beschreven.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van tekstbedekking. Bijvoorbeeld:

* Een AEM-schermproject maken (in dit voorbeeld **TextOverlayDemo**)

* Een kanaal maken als **TextSample** in de map **Kanalen**

* Inhoud toevoegen aan uw **TextSample** -kanaal

De volgende afbeelding toont het **TextOverlayDemo** -project met **TextSample** -kanaal in de map **Kanalen** .

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** op de actiebalk om de editor te openen.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Selecteer de afbeelding en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Selecteer de optie **Tekstbedekking** op de navigatiebalk van het dialoogvenster, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Eigenschappen van tekstbedekking {#understanding-text-overlay-properties}

Met de eigenschappen van de Tekstbedekking kunt u tekst toevoegen aan een van de componenten in uw project Schermen. In het volgende gedeelte wordt een overzicht gegeven van de eigenschappen die beschikbaar zijn in Tekstbedekking:

![text](assets/text.gif)

U kunt tekst toevoegen aan het tekstvak en typografische accenten toevoegen, zoals vet, cursief, onderstrepen enzovoort.

**Kleurvariant** Met deze optie kan de tekst donker (zwart gekleurde tekst) of Licht (wit gekleurde tekst) zijn.

**Grootte wijzigen en plaatsen** Met deze optie kan de gebruiker de tekst horizontaal of verticaal uitlijnen of bovendien verfijnde gereedschappen gebruiken voor tekstuitlijning.

>[!NOTE]
>
>Als u verfijnde gereedschappen correct wilt gebruiken, moet u de juiste positie in pixels identificeren met (px) als achtervoegsel, bijvoorbeeld 200 px. Het resultaat van deze expressie is 200 pixels vanaf het beginpunt.

