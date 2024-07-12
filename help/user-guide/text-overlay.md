---
title: Tekstbedekking
description: In deze video leert u over tekstbedekking in AEM Screens waarmee u een aantrekkelijke ervaring kunt creëren in een Volgkanaal door een titel of een beschrijving boven op een afbeelding op te geven.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: bbc719df-24a7-4cfb-9786-1c3496f9f082
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 0%

---

# Tekstbedekking {#text-overlay}

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Gebruikend de Bedekking van de Tekst**
* **Begrijpend de Eigenschappen van de Bedekking van de Tekst**
* **Gebruikend Waarden ContextHub in de Bedekking van de Tekst**

>[!CAUTION]
>
>De **eigenschap van de Bedekking van de Tekst** is slechts beschikbaar als u AEM 6.3 Pak van de Eigenschap 5 of AEM 6.4 Pak 3 van de Eigenschap hebt geïnstalleerd.

## Overzicht {#overview}

De functie Tekstbedekking is beschikbaar in AEM Screens. Met deze functie kunt u een aantrekkelijke ervaring creëren in een volgreekkanaal door een titel of beschrijving boven op een afbeelding te plaatsen.

Leren hoe te om uw eigen douanecomponent tot stand te brengen, zie **Uitbreidend een Component van AEM Screens**.

In deze sectie wordt alleen weergegeven hoe u de postercomponent in een AEM Screens-project kunt gebruiken en toepassen. Het toont ook gevallen waarin het als een tekstbedekking in één van uw opeenvolgingskanalen wordt gebruikt.

## Tekstbedekking gebruiken {#using-text-overlay}

In de volgende sectie wordt het gebruik van tekstbedekking in een AEM Screens-project beschreven.

**Eerste vereisten**

Voordat u deze functionaliteit implementeert, moet u een project instellen als een voorwaarde voor het implementeren van tekstbedekking. Bijvoorbeeld:

* Creeer een project van AEM Screens (in dit voorbeeld, **TextOverlayDemo**)

* Creeer een opeenvolgingskanaal als **TextSample** onder de **omslag van Kanalen** wordt genoemd

* Voeg inhoud aan uw **** Kanaal TextSample toe

Het volgende beeld toont het **TextOverlayDemo** project met het **** kanaal TextSample in de **omslag van Kanalen**.

![ screen_shot_2018-12-16at75908pm ](assets/screen_shot_2018-12-16at75908pm.png)

Voer de onderstaande stappen uit om tekstbedekking in een AEM Screens-kanaal te gebruiken:

1. Navigeer aan **TextOverlayDemo** > **Kanalen** > **TextSample** en klik **uitgeven** van de actiebar.

   ![ screen_shot_2018-12-16at80017pm ](assets/screen_shot_2018-12-16at80017pm.png)

1. Klik het beeld en klik **vormen** (het moersleutelpictogram) om de doos van de eigenschappendialoog te openen.

   ![ screen_shot_2018-12-16at80221pm ](assets/screen_shot_2018-12-16at80221pm.png)

1. Klik de **optie van de Bedekking van de Tekst** van de navigatiebar van de dialoogdoos, zoals aangetoond in het hieronder cijfer.

   ![ screen_shot_2018-12-16at80424pm ](assets/screen_shot_2018-12-16at80424pm.png)

### Eigenschappen van tekstbedekking {#understanding-text-overlay-properties}

Met de eigenschappen van de Tekstbedekking kunt u tekst toevoegen aan een van de componenten in uw Screens-project. In het volgende gedeelte wordt een overzicht gegeven van de eigenschappen die beschikbaar zijn in Tekstbedekking:

![ tekst ](assets/text.gif)

U kunt tekst toevoegen aan het tekstvak en typografische accenten toevoegen, zoals vet, cursief en onderstrepen.

**Variant van de Kleur** Deze optie staat de tekst toe om of Donker (tekst in zwarte kleur) of Licht (tekst in witte kleur) te zijn.

**het Rangschikken &amp; het plaatsen** Deze optie laat de gebruiker de tekst horizontaal of verticaal richten of ook verfijnen hulpmiddelen voor tekstgroepering gebruiken.

>[!NOTE]
>
>Wanneer u verfijnde gereedschappen gebruikt, moet u de juiste positie in pixels identificeren met (px) als achtervoegsel, bijvoorbeeld 200 px. Het resultaat van deze expressie is 200 pixels van het beginpunt.

## ContextHub-waarden gebruiken in tekstbedekking {#using-text-overlay-context-hub}

In de volgende sectie wordt het gebruik beschreven van waarden uit een gegevensopslagruimte, bijvoorbeeld Google-werkbladen in de component Text Overlay.

**Eerste vereisten**

Opstelling configuraties ContextHub voor uw project van AEM Screens.

Leren hoe te opstelling en gegevens gedreven activaveranderingen te beheren gebruikend een gegevensopslag, zie [ Vormend ContextHub in AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/configuring-context-hub).

Nadat u de vereiste configuraties voor uw project hebt ingesteld, volgt u de onderstaande stappen om waarden uit de Google-werkbladen te gebruiken:

1. Navigeer aan **TextOverlayDemo** > **Kanalen** > **TextSample** en klik **Eigenschappen** van de actiebar.

1. Klik het **Personalization** lusje zodat kunt u opstelling de configuraties ContextHub.

   1. Klik de **Weg ContextHub** als **bibliotheken** > **montages** > **wolkenmontages** > **gebrek** > **Configuratie ContextHub** en klik **Uitgezocht**.

   1. Klik de **Weg van Segmenten** als **conf** > **schermen** > **montages** > **wcm** > **segmenten** en klik **Uitgezocht**.

   1. Klik **sparen &amp; Sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigeer aan **TextOverlayDemo** > **Kanalen** > **TextSample** en klik **uitgeven** van de actiebar.

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Voeg een beeld en een component van de tekstbedekking aan uw beeld toe zoals die in [ wordt beschreven Gebruikend de sectie van de Bedekking van de Tekst ](/help/user-guide/text-overlay.md#using-text-overlay) van deze pagina.

1. Klik op **vormen** (het moersleutelpictogram) om het **de dialoogvakje van het Beeld** te openen.

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigeer aan het **ContextHub** lusje van het **de dialoogvakje van het Beeld**. Klik **toevoegen**.

   >[!NOTE]
   >Als u opstelling uw configuratie ContextHub niet hebt, is deze optie gehandicapt voor uw project.

1. Ga **Waarde** op het **Placeholder** gebied in. Klik de rij die u de waarde van uw blad van Google in **Variabele ContextHub** wilt krijgen. In dit geval wordt de waarde opgehaald uit rij 2 en kolom 1 van de Google-bladen. Nu, ga de **StandaardWaarde** als **20** in, getoond in hieronder cijfer. Klik op het vinkje als u klaar bent.

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >Ter referentie ziet u in de volgende afbeelding de waarde die is opgehaald uit de Google-bladen:

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Navigeer terug naar het **lusje van de Bedekking van de Tekst** van de de dialoogdoos van het Beeld en voeg de tekst *Huidige Temperatuur {Value}* toe, zoals aangetoond in het hieronder cijfer.

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Klik **Voorproef**.

   ![ image1 ](/help/user-guide/assets/text-overlay/text-overlay10.png)
