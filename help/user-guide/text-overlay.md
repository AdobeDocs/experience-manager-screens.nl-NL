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
source-git-commit: 651627223e1b9bd0f650b010d2b92f004b9e2ea2

---


# Tekstbedekking {#text-overlay}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Tekstbedekking gebruiken**
* **Eigenschappen van tekstbedekking**
* **ContextHub-waarden gebruiken in tekstbedekking**

>[!CAUTION]
>
>De functie **Tekstbedekking** is alleen beschikbaar als u AEM 6.3 Feature Pack 5 of AEM 6.4 Feature Pack 3 hebt geïnstalleerd.

## Overzicht {#overview}

Tekstbedekking is een functie die beschikbaar is in AEM-rasters en waarmee u een aantrekkelijke ervaring kunt creëren in een volgreekskanaal door een titel of een beschrijving boven op een afbeelding op te geven.

Als u wilt leren hoe u uw eigen aangepaste component maakt, raadpleegt u **Een AEM-schermaponent** uitbreiden.

In deze sectie wordt alleen uitgelegd hoe u de postercomponent in een AEM-rasterproject kunt gebruiken en gebruiken als tekstbedekking in een van uw reekskanalen.

## Tekstbedekking gebruiken {#using-text-overlay}

In de volgende sectie wordt het gebruik van tekstbedekking in een AEM-schermproject beschreven.

**Vereisten**

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van tekstbedekking. Bijvoorbeeld:

* Een AEM-schermproject maken (in dit voorbeeld **TextOverlayDemo**)

* Een volgnummer maken met de naam **TextSample** onder de map **Kanalen**

* Inhoud toevoegen aan uw **TextSample** -kanaal

De volgende afbeelding toont het **TextOverlayDemo** -project met **TextSample** -kanaal in de map **Kanalen** .

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Voer de onderstaande stappen uit om tekstbedekking in een AEM-rasterkanaal te gebruiken:

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

## ContextHub-waarden gebruiken in tekstbedekking {#using-text-overlay-context-hub}

In de volgende sectie wordt het gebruik beschreven van waarden uit een gegevensopslagruimte, bijvoorbeeld Google-werkbladen in tekstbedekkingscomponenten.

**Vereisten**

U moet opstelling configuraties ContextHub voor uw project van de Schermen AEM.

Leren hoe te om gegevens gedreven activaveranderingen te plaatsen en te beheren gebruikend een gegevensopslag, verwijs naar het [Vormen ContextHub in de Schermen](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/developing/configuring-context-hub.html)van AEM.

Nadat u de vereiste configuraties voor uw project hebt ingesteld, volgt u de onderstaande stappen om waarden uit de Google-werkbladen te gebruiken:

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Eigenschappen** op de actiebalk.

1. Selecteer het lusje van de **Personalisatie** aan opstelling de configuraties ContextHub.

   1. Selecteer het **ContextHub-pad** als **bibliotheken** > **instellingen** > **cloudinstellingen** > **standaard** **** ****> ContextHub Configurations en klik opSelect.

   1. Selecteer het pad **** Segmenten als **conf** > **schermen** > **instellingen** > **wcm** **** ****> segments en klik op Select.

   1. Klik op **Opslaan en sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** op de actiebalk om de editor te openen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Voeg een component voor afbeelding en tekstbedekking toe aan de afbeelding zoals wordt beschreven in de sectie [Tekstbedekking](/help/user-guide/text-overlay.md#using-text-overlay) gebruiken van deze pagina.

1. Klik op **Configureren** (moersleutelpictogram) om het dialoogvenster **Afbeelding** te openen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigeer aan het **lusje ContextHub** van het de dialoogvakje van het **Beeld** . Click **Add**.

   >[!NOTE]
   >Als u geen opstelling uw configuraties ContextHub hebt, zal deze optie voor uw project worden onbruikbaar gemaakt.

1. Ga **Waarde** op het **Plaatsaanduiding** gebied in, selecteer de rij die u de waarde van uw google blad in de Variabele **ContextHub wilt krijgen (in dit geval, wordt de waarde teruggewonnen van rij 2 en kolom 1 van de google bladen), en ga de** Standaardwaarde **als** 20 **** in, zoals aangetoond in het hieronder cijfer. Als u klaar bent, klikt u op het vinkje.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Ter referentie geeft de volgende afbeelding de waarde weer die wordt opgehaald uit de hoekbladen:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Navigeer terug naar het tabblad **Tekstbedekking** in het dialoogvenster Afbeelding en voeg de tekst *Huidige temperatuur {waarde}* toe, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klik op **Voorvertoning** om de gewenste uitvoer weer te geven.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)















