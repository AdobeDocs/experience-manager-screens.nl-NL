---
title: Tekstbedekking
seo-title: Tekstbedekking
description: Tekstbedekking is een functie die beschikbaar is in AEM Screens en waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven. Volg deze pagina voor meer informatie.
seo-description: Tekstbedekking is een functie die beschikbaar is in AEM Screens en waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven. Volg deze pagina voor meer informatie.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
translation-type: tm+mt
source-git-commit: 651627223e1b9bd0f650b010d2b92f004b9e2ea2
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 1%

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

Tekstbedekking is een functie die beschikbaar is in AEM Screens en waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven.

Meer informatie over het maken van uw eigen aangepaste component vindt u in **AEM Screens-componenten uitbreiden**.

In deze sectie wordt alleen uitgelegd hoe u de postercomponent in een AEM Screens-project kunt gebruiken en gebruiken als tekstbedekking in een van uw reekskanalen.

## Tekstbedekking {#using-text-overlay} gebruiken

In de volgende sectie wordt het gebruik van tekstbedekking in een AEM Screens-project beschreven.

**Vereisten**

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van tekstbedekking. Bijvoorbeeld,

* Een AEM Screens-project maken (in dit voorbeeld **TextOverlayDemo**)

* Creeer een opeenvolgingskanaal genoemd als **TextSample** onder **Kanalen** omslag

* Inhoud toevoegen aan uw **TextSample** Channel

De volgende afbeelding toont het **TextOverlayDemo**-project met **TextSample**-kanaal in **Channels**-map.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Voer de onderstaande stappen uit om tekstbedekking in een AEM Screens-kanaal te gebruiken:

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** op de actiebalk om de editor te openen.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Selecteer de afbeelding en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Selecteer de optie **Tekstbedekking** in de navigatiebalk van het dialoogvenster, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Eigenschappen van tekstbedekking {#understanding-text-overlay-properties}

Met de eigenschappen van de Tekstbedekking kunt u tekst toevoegen aan een van de componenten in uw project Schermen. In het volgende gedeelte wordt een overzicht gegeven van de eigenschappen die beschikbaar zijn in Tekstbedekking:

![text](assets/text.gif)

U kunt tekst toevoegen aan het tekstvak en typografische accenten toevoegen, zoals vet, cursief, onderstrepen enzovoort.

**KleurvariantMet** deze optie kan de tekst donker (zwart gekleurde tekst) of Licht (wit gekleurde tekst) zijn.

**Grootte wijzigen en** plaatsenMet deze optie kan de gebruiker de tekst horizontaal of verticaal uitlijnen of bovendien verfijnde gereedschappen gebruiken voor tekstuitlijning.

>[!NOTE]
>
>Als u verfijnde gereedschappen correct wilt gebruiken, moet u de juiste positie in pixels identificeren met (px) als achtervoegsel, bijvoorbeeld 200 px. Het resultaat van deze expressie is 200 pixels vanaf het beginpunt.

## ContextHub-waarden gebruiken in tekstbedekking {#using-text-overlay-context-hub}

In de volgende sectie wordt het gebruik beschreven van waarden uit een gegevensopslagruimte, bijvoorbeeld Google-werkbladen in tekstbedekkingscomponenten.

**Vereisten**

U moet opstelling configuraties ContextHub voor uw project van AEM Screens.

Leren hoe te om gegevens gedreven activaveranderingen te plaatsen en te beheren gebruikend een gegevensopslag, verwijs naar [Het Vormen ContextHub in AEM Screens](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/developing/configuring-context-hub.html).

Nadat u de vereiste configuraties voor uw project hebt ingesteld, volgt u de onderstaande stappen om waarden uit de Google-werkbladen te gebruiken:

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik **Eigenschappen** op de actiebalk.

1. Selecteer **Personalization** lusje om de configuraties te plaatsen ContextHub.

   1. Selecteer **ContextHub Path** als **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Configurations** en klik ****.

   1. Selecteer **Segmentpad** als **conf** > **screens** > **settings** > **wcm** > **segments** en klik **Selecteer a1 3/>.**

   1. Klik **Opslaan en sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigeer naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** op de actiebalk om de editor te openen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Voeg een component voor afbeelding en tekstbedekking toe aan de afbeelding zoals wordt beschreven in de sectie [Tekstbedekking](/help/user-guide/text-overlay.md#using-text-overlay) van deze pagina gebruiken.

1. Klik op **Configureer** (moersleutelpictogram) om het dialoogvenster **Afbeelding** te openen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigeer aan **ContextHub** lusje van **Beeld** dialoogvakje. Klik **Add**.

   >[!NOTE]
   >Als u geen opstelling uw configuraties ContextHub hebt, zal deze optie voor uw project worden onbruikbaar gemaakt.

1. Voer **Waarde** in het veld **Placeholder** in, selecteer de rij die u wilt ophalen uit uw hoekblad in **ContextHub Variable** (in dit geval wordt de waarde opgehaald uit rij 2 en kolom 1 uit de hoekbladen) en voer **Default Value** in als &lt;a6 a8/>20 **, zoals weergegeven in de onderstaande afbeelding.** Als u klaar bent, klikt u op het vinkje.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Ter referentie geeft de volgende afbeelding de waarde weer die wordt opgehaald uit de hoekbladen:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Navigeer terug naar het tabblad **Tekstbedekking** in het dialoogvenster Afbeelding en voeg de tekst *Huidige temperatuur {Waarde}* toe, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klik op **Voorvertoning** om de gewenste uitvoer weer te geven.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)















