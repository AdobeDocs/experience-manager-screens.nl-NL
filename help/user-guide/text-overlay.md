---
title: Tekstbedekking
seo-title: Text Overlay
description: Tekstbedekking is een functie die beschikbaar is in AEM Screens en waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven. Volg deze pagina voor meer informatie.
seo-description: Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image. Follow this page to learn more.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: bbc719df-24a7-4cfb-9786-1c3496f9f082
source-git-commit: 10a4918eeb56df5e8542bbc2e8806f766a86f781
workflow-type: tm+mt
source-wordcount: '797'
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
>De **Tekstbedekking** Deze functie is alleen beschikbaar als u AEM 6.3 Feature Pack 5 of AEM 6.4 Feature Pack 3 hebt geïnstalleerd.

## Overzicht {#overview}

Tekstbedekking is een functie die beschikbaar is in AEM Screens en waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven.

Als u wilt leren hoe u uw eigen aangepaste component kunt maken, raadpleegt u **AEM Screens-componenten uitbreiden**.

In deze sectie wordt alleen uitgelegd hoe u de postercomponent in een AEM Screens-project kunt gebruiken en toepassen en deze als tekstbedekking kunt gebruiken in een van uw reekskanalen.

## Tekstbedekking gebruiken {#using-text-overlay}

In de volgende sectie wordt het gebruik van tekstbedekking in een AEM Screens-project beschreven.

**Vereisten**

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u een project hebt ingesteld als voorwaarde voor het implementeren van tekstbedekking. Bijvoorbeeld,

* Een AEM Screens-project maken (in dit voorbeeld: **TextOverlayDemo**)

* Een volgnummer maken met de naam **TextSample** krachtens **Kanalen** map

* Inhoud toevoegen aan uw **TextSample** Kanaal

In de volgende afbeelding wordt de **TextOverlayDemo** project met **TextSample** kanaal in **Kanalen** map.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Voer de onderstaande stappen uit om tekstbedekking in een AEM Screens-kanaal te gebruiken:

1. Navigeren naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** in de actiebalk om de editor te openen.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Selecteer de afbeelding en klik op **Configureren** (moersleutelpictogram) om het dialoogvenster Eigenschappen te openen.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Selecteer **Tekstbedekking** in de navigatiebalk van het dialoogvenster, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Eigenschappen van tekstbedekking {#understanding-text-overlay-properties}

Met de eigenschappen van de Tekstbedekking kunt u tekst toevoegen aan een van de componenten in het project Schermen. In het volgende gedeelte wordt een overzicht gegeven van de eigenschappen die beschikbaar zijn in Tekstbedekking:

![text](assets/text.gif)

U kunt tekst toevoegen aan het tekstvak en typografische accenten toevoegen, zoals vet, cursief en onderstrepen.

**Kleurvariant** Met deze optie kan de tekst Donker (zwarte tekst) of Licht (witte tekst) zijn.

**Grootte en positionering** Met deze optie kan de gebruiker de tekst horizontaal of verticaal uitlijnen of ook met fijnkorrelige gereedschappen tekstuitlijning uitlijnen.

>[!NOTE]
>
>Als u verfijnde gereedschappen correct wilt gebruiken, moet u de juiste positie in pixels identificeren met (px) als achtervoegsel, bijvoorbeeld 200 px. Het resultaat van deze expressie is 200 pixels vanaf het beginpunt.

## ContextHub-waarden gebruiken in tekstbedekking {#using-text-overlay-context-hub}

In de volgende sectie wordt het gebruik beschreven van waarden uit een gegevensopslagruimte, bijvoorbeeld Google-werkbladen in tekstbedekkingscomponenten.

**Vereisten**

Opstelling configuraties ContextHub voor uw project van AEM Screens.

Raadpleeg voor meer informatie over het instellen en beheren van gegevensgestuurde elementwijzigingen in een gegevensopslag [ContextHub configureren in AEM Screens](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/configuring-context-hub.html).

Nadat u de vereiste configuraties voor uw project hebt ingesteld, volgt u de onderstaande stappen om waarden uit de Google-werkbladen te gebruiken:

1. Navigeren naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Eigenschappen** in de actiebalk.

1. Selecteer **Personalisatie** aan opstelling de configuraties ContextHub.

   1. Selecteer **ContextHub-pad** als **libben** > **instellingen** > **cloudinstellingen** > **default** > **ContextHub-configuraties** en klik op **Selecteren**.

   1. Selecteer **Segmentpad** als **conf** > **schermen** > **instellingen** > **wcm** > **segmenten** en klik op **Selecteren**.

   1. Klikken **Opslaan en sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigeren naar **TextOverlayDemo** —> **Kanalen** —> **TextSample** en klik op **Bewerken** in de actiebalk om de editor te openen.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Voeg een component voor afbeelding en tekstbedekking toe aan de afbeelding, zoals beschreven in [Tekstbedekking gebruiken](/help/user-guide/text-overlay.md#using-text-overlay) van deze pagina.

1. Klikken op **Configureren** (moersleutelpictogram) om het dialoogvenster te openen **Afbeelding** in.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Ga naar de **ContextHub** van de **Afbeelding** in. Klikken **Toevoegen**.

   >[!NOTE]
   >Als u opstelling uw configuraties ContextHub niet hebt, is deze optie gehandicapt voor uw project.

1. Enter **Waarde** in de **Plaatsaanduiding** veld. Selecteer de rij waarin u de waarde op uw Google-blad wilt ophalen **ContextHub-variabele**. In dit geval wordt de waarde opgehaald uit rij 2 en kolom 1 van de Google-bladen. Voer nu de **Standaardwaarde** als **20**, zoals weergegeven in onderstaande afbeelding. Klik op het vinkje als u klaar bent.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Ter referentie geeft de volgende afbeelding de waarde weer die wordt opgehaald uit de hoekbladen:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Ga terug naar de **Tekstbedekking** van het dialoogvenster Afbeelding en voeg de tekst toe *Huidige temperatuur {waarde}*, zoals weergegeven in onderstaande afbeelding.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klikken op **Voorvertoning** om de gewenste uitvoer weer te geven.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)
