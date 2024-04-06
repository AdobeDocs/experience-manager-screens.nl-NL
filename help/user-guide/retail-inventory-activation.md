---
title: Gerichte activering in de detailhandel
seo-title: Retail Inventory Targeted Activation
description: In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.
seo-description: This Use Case showcases the retail inventory stock for three different colored sweatshirts. Depending on the number of sweatshirts available in stock that is recorded in Google Sheets, the image (red, green, or blue sweatshirt) with highest number is displayed on the screen.
uuid: 8e7faa65-b004-42b3-8865-4f71eb5dc1b1
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 70147920-5bdb-401c-884e-51d268d40585
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 926f529b-f3cf-471d-83b4-6ccb628cf160
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Gerichte activering in de detailhandel {#retail-inventory-targeted-activation}

In het volgende gebruiksgeval worden drie verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-werkblad.

## Beschrijving {#description}

In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.

Voor dit geval van Gebruik, zal de Rood, Groen, of Blauwe trui op uw scherm tonen die op de hoogste waarde van aantal sweaters wordt gebaseerd die beschikbaar is.

## Voorwaarden {#preconditions}

Voordat u begint met het implementeren van de activering van de inventarisatie voor handelsdoeleinden, moet u leren hoe u de ***Gegevensopslag***, ***Auditiesegmentatie*** en ***Doelstelling voor kanalen inschakelen*** in een AEM Screens-project.

Zie [ContextHub configureren in AEM Screens](configuring-context-hub.md) voor nadere informatie.

## Basisstroom {#basic-flow}

Volg de onderstaande stappen om de Gebruiksscenario voor de activering van de Retail Inventory te implementeren:

1. **De Google-bladen vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg drie kolommen (Rood, Groen en Blauw) toe met de bijbehorende waarden voor drie verschillende sweatshirts.

   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Het publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (raadpleeg ***Stap 2: De Segmentatie van het publiek instellen*** in **[ContextHub configureren in AEM Screens](configuring-context-hub.md)** voor meer informatie).

   1. Drie nieuwe segmenten toevoegen **Voor_rood**, **For_Green**, en **Voor_blauw**.

   1. Selecteren **Voor_rood** en klik op **Bewerken** in de actiebalk.

   1. Sleep de **Compare : property - property** aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Voornaam van eigenschap**

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu

   1. Selecteren **Gegevenstype** als **getal**

   1. Selecteren **goochelesheets/value/1/1** in de vervolgkeuzelijst **Tweede eigenschapsnaam**.

   1. Slepen en slepen **another Comparation : Property - Property** aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Voornaam van eigenschap**.

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu

   1. Selecteren **Gegevenstype** als **getal**

   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Tweede eigenschapsnaam**

   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Op dezelfde manier bewerkt en voegt u vergelijkingseigenschapsregels toe aan **Voor_blauw** segment zoals weergegeven in onderstaande afbeelding:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Op dezelfde manier geef en voeg vergelijkingsbezitsregels aan* voor_Groene **segment toe zoals aangetoond in het hieronder cijfer:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >U zult merken dat voor segmenten **For_Green** en **For_Green** gegevens kunnen niet worden opgelost in de editor, omdat alleen de eerste vergelijking op dit moment geldig is volgens de waarden in het Google-blad.

1. Navigeer en selecteer uw **DataDrivenRetail** kanaal (een volgend kanaal) en klik op **Bewerken** in de actiebalk.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >U moet uw **ContextHub** **Configuraties** het kanaal gebruiken **Eigenschappen** > **Personalisatie** tab.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   >
   >U moet beide **Merk** en de **Gebied** voor de activiteiten die correct moeten worden vermeld wanneer u het Targeting proces begint.

1. **Een standaardafbeelding toevoegen**

   1. Voeg een standaardafbeelding toe aan uw kanaal en klik op **Targeting**.
   1. Selecteren **Merk** en de **Activiteit** in het keuzemenu en klik op **Doelstelling starten**.

   1. Klikken **Doelstelling starten**.

   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   >
   >Voordat u de doelframes gaat opgeven, moet u de segmenten toevoegen (**For_Green**, **Voor_rood**, en **Voor_blauw**) door op **+ Toevoeging Ervaring richten** van de zijspoorstaaf, zoals aangegeven in onderstaande figuur.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Voeg de afbeeldingen toe aan alle drie de verschillende scenario&#39;s, zoals hieronder wordt weergegeven.

   ![retail_targeting](assets/retail_targeting.gif)

1. **De voorvertoning controleren**

   1. Klikken **Voorvertoning.** Open ook het Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde voor alle drie de kolommen en u ziet hoe de afbeelding van de weergave wordt bijgewerkt volgens de hoogste waarde in de voorraad.

   ![retail_result](assets/retail_result.gif)
