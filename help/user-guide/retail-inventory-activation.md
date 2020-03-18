---
title: Gerichte activering in de detailhandel
seo-title: Gerichte activering in de detailhandel
description: In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.
seo-description: In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.
uuid: 8e7faa65-b004-42b3-8865-4f71eb5dc1b1
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 70147920-5bdb-401c-884e-51d268d40585
docset: aem65
translation-type: tm+mt
source-git-commit: a7d3ec582dde83ed6efb08a6c3c6a75cc0820970

---


# Gerichte activering in de detailhandel {#retail-inventory-targeted-activation}

In het volgende gebruiksgeval worden drie verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-werkblad.

## Beschrijving {#description}

In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.

Voor dit geval van Gebruik, zal de Rood, Groen, of Blauwe trui op uw scherm tonen die op de hoogste waarde van aantal sweaters wordt gebaseerd die beschikbaar is.

## Voorwaarden {#preconditions}

Voordat u begint met het implementeren van de in de detailhandel verkrijgbare activering, moet u leren hoe u ***Gegevensopslag***, Segmentatie ***van het*** publiek en Doelstelling voor kanalen ****** inschakelen in een AEM-schermproject instelt.

Verwijs naar het [Vormen ContextHub in Schermen](configuring-context-hub.md) AEM voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Volg de onderstaande stappen om de Gebruiksscenario voor de activering van de Retail Inventory te implementeren:

1. **De Google Sheets vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg drie kolommen (Rood, Groen en Blauw) toe met de bijbehorende waarden voor drie verschillende sweatshirts.
   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Het publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie*** van het publiek van de vestiging in het **[Vormen ContextHub in AEM de pagina van Schermen](configuring-context-hub.md)**voor meer details).

   1. Voeg drie nieuwe segmenten **voor_rood**, **voor_groen**, en **voor_blauw** toe.

   1. Selecteer **For_Red** en klik op **Bewerken** op de actiebalk.

   1. Sleep en zet de **vergelijking neer: Bezit - Bezit** aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst in de naam van de **vooreigenschap**

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu

   1. Selecteer **Gegevenstype** als **nummer**

   1. Selecteer **gumesheets/value/1/1** in de vervolgkeuzelijst in de naam **van de** tweede eigenschap.

   1. Sleep en zet **een andere vergelijking neer: Bezit - Bezit** aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst in de naam **van de** eerste eigenschap.

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu

   1. Selecteer **Gegevenstype** als **nummer**

   1. Selecteer **gumesheets/value/1/0** in het keuzemenu met de naam van de **tweede eigenschap**
   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Op dezelfde manier geef en voeg vergelijkingsbezitsregels aan segment **For_Blue** toe zoals aangetoond in het hieronder cijfer:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Op dezelfde manier geef en voeg vergelijkingsbezitsregels aan* voor_Groen **segment toe zoals aangetoond in het hieronder cijfer:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >U zult merken dat voor segmenten **For_Green** en **For_Green**, gegevens niet kunnen worden opgelost in de editor omdat alleen de eerste vergelijking nu geldig is volgens de waarden in het Google-blad.

1. Navigeer en selecteer uw **DataDrivenRetail** -kanaal (een opeenvolgend kanaal) en klik op **Bewerken** op de actiebalk.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   U moet zowel het **Merk** als het **Gebied** selecteren om de activiteiten behoorlijk te worden vermeld wanneer u het Targeting proces begint.

1. **Een standaardafbeelding toevoegen**

   1. Voeg een standaardafbeelding toe aan uw kanaal en klik op **Doel**.
   1. Selecteer **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.

   1. Klik op **Doelstelling** starten.
   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   Voordat u de focus begint te plaatsen, moet u de segmenten (**For_Green**, **For_Red** en **For_Blue**) toevoegen door op **+ te klikken. Voeg ervaringen toe die gericht** zijn vanaf de zijspoor, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Voeg de afbeeldingen toe aan alle drie de verschillende scenario&#39;s, zoals hieronder wordt weergegeven.

   ![retail_targeting](assets/retail_targeting.gif)

1. **De voorvertoning controleren**

   1. Klik op **Voorvertoning.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde voor alle drie de kolommen en u ziet hoe de afbeelding van de weergave wordt bijgewerkt volgens de hoogste inventariswaarde.
   ![retail_result](assets/retail_result.gif)

