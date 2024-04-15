---
title: Gerichte activering in de detailhandel
description: Meer informatie over deze AEM Screens-gebruikszaak die de voorraad in de detailhandel toont voor drie verschillende gekleurde sweatshirts.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 926f529b-f3cf-471d-83b4-6ccb628cf160
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---

# Gerichte activering in de detailhandel {#retail-inventory-targeted-activation}

In het volgende gebruiksgeval worden drie verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-werkblad.

## Beschrijving {#description}

In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.

Voor deze optie gebruikt u de optie Rode, groene of blauwe trui op uw scherm op basis van de hoogste waarde van het aantal beschikbare sweaters.

## Voorwaarden {#preconditions}

Leer hoe u de activering van de detailhandelsvoorraad voor activering start ***Gegevensopslag***, ***Auditiesegmentatie*** en ***Doelstelling voor kanalen inschakelen*** in een AEM Screens-project.

Zie [ContextHub configureren in AEM Screens](configuring-context-hub.md) voor nadere informatie.

## Basisstroom {#basic-flow}

Volg de onderstaande stappen om de Gebruiksscenario voor de activering van de Retail Inventory te implementeren:

1. **De Google-bladen vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg drie kolommen (Rood, Groen en Blauw) toe met de bijbehorende waarden voor drie verschillende sweatshirts.

   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Het publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het publiek instellen*** in **[ContextHub configureren in AEM Screens](configuring-context-hub.md)** voor meer informatie).

   1. Drie nieuwe segmenten toevoegen **Voor_rood**, **For_Green**, en **Voor_blauw**.

   1. Selecteren **Voor_rood** en selecteert u **Bewerken** in de actiebalk.

   1. Sleep de **Compare : property - property** aan de redacteur.
   1. Selecteer de **Configuratie** pictogram.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Voornaam van eigenschap**.
   1. Selecteer de **Operator** als **groter dan** in het keuzemenu.
   1. Selecteren **Gegevenstype** als **getal**.
   1. Selecteren **goochelesheets/value/1/1** in de vervolgkeuzelijst **Tweede eigenschapsnaam**.
   1. Slepen en neerzetten **another Comparation : Property - Property** aan de redacteur en selecteer **Configuratie** pictogram.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Voornaam van eigenschap**.
   1. Selecteer de **Operator** als **groter dan** in het keuzemenu.
   1. Selecteren **Gegevenstype** als **getal**.
   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Tweede eigenschapsnaam**.

   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Op dezelfde manier bewerkt en voegt u vergelijkingseigenschapsregels toe aan **Voor_blauw** segment zoals weergegeven in onderstaande afbeelding:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Op dezelfde manier bewerkt en voegt u vergelijkingseigenschapsregels toe aan **For_Green** segment zoals weergegeven in onderstaande afbeelding:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >Merk op dat voor segmenten **For_Green** en **For_Green** gegevens kunnen niet worden opgelost in de editor, omdat alleen de eerste vergelijking op dit moment geldig is volgens de waarden in het Google-blad.

1. Navigeer en selecteer uw **DataDrivenRetail** kanaal (een volgnummer).
1. Selecteren **Bewerken** in de actiebalk.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >U moet uw **ContextHub** **Configuraties** het kanaal gebruiken **Eigenschappen** > **Personalisatie** tab.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   >
   >Selecteer beide opties **Merk** en de **Gebied** voor de activiteiten die correct moeten worden vermeld wanneer u het Targeting proces begint.

1. **Een standaardafbeelding toevoegen**

   1. Voeg een standaardafbeelding toe aan uw kanaal en selecteer **Targeting**.
   1. Selecteren **Merk** en de **Activiteit** in het keuzemenu en selecteert u **Doelstelling starten**.
   1. Selecteren **Doelstelling starten**.

   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   >
   >Voeg eerst de segmenten toe voordat u de doelframes maakt (**For_Green**, **Voor_rood**, en **Voor_blauw**) door **+ Toevoeging Ervaring richten** van de zijspoorstaaf, zoals aangegeven in onderstaande figuur.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Voeg de afbeeldingen toe aan alle drie de verschillende scenario&#39;s, zoals hieronder wordt weergegeven.

   ![retail_targeting](assets/retail_targeting.gif)

1. **De voorvertoning controleren**

   1. Selecteren **Voorvertoning.** Open ook het Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde voor alle drie de kolommen. U ziet dat de beeldweergave wordt bijgewerkt volgens de hoogste inventariswaarde.

   ![retail_result](assets/retail_result.gif)
