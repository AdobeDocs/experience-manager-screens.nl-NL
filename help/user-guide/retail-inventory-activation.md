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
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Gerichte activering in de detailhandel {#retail-inventory-targeted-activation}

In het volgende gebruiksgeval worden drie verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-werkblad.

## Beschrijving {#description}

In deze gebruikszaak wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad die wordt opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven.

De trui Rood, Groen of Blauw wordt weergegeven op basis van de hoogste waarde van het aantal beschikbare sweaters.

## Voorwaarden {#preconditions}

Alvorens u begint de kleinhandelsinventaris richtend activering uit te voeren, leer hoe te opstelling ***Opslag van Gegevens***, ***Segmentatie van het publiek*** en ***het richten voor Kanalen*** in een Project van AEM Screens toelaten.

Zie [ het Vormen ContextHub in AEM Screens ](configuring-context-hub.md) voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Volg de onderstaande stappen om de Gebruiksscenario voor de activering van de Retail Inventory te implementeren:

1. **die de Bladen van Google bevolkt**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg drie kolommen (Rood, Groen en Blauw) toe met de bijbehorende waarden voor drie verschillende sweatshirts.

   ![ screen_shot_2019-05-06at101755am ](assets/screen_shot_2019-05-06at101755am.png)

1. **Vormend het publiek zoals per de vereisten**

   1. Navigeer aan de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het Publiek van de vestiging*** in **[het Vormen ContextHub in AEM Screens](configuring-context-hub.md)** pagina voor meer details).

   1. Voeg drie nieuwe segmenten **For_Red**, **For_Green**, en **For_Blue** toe.

   1. Klik **For_Red** en klik **uitgeven** van de actiebar.

   1. Sleep-en-daling de **Vergelijking: Bezit - Bezit** aan de redacteur.
   1. Klik het **pictogram van de Configuratie**.
   1. Klik **googesheets/value/1/2** van drop-down in **Eerste naam van het Bezit**.
   1. Klik de **Exploitant**, en als **groter-dan** van het drop-down menu.
   1. Klik **Type van Gegevens**, en als **aantal**.
   1. Klik **googesheets/value/1/1** van drop-down in **Tweede Naam van het Bezit**.
   1. Sleep-en-daling **een andere Vergelijking: Bezit - Bezit** aan de redacteur en klik het **pictogram van de Configuratie**.
   1. Klik **googesheets/value/1/2** van drop-down in **Eerste naam van het Bezit**.
   1. Klik de **Exploitant**, en als **groter-dan** van het drop-down menu.
   1. Klik **Type van Gegevens**, en als **aantal**.
   1. Klik **googesheets/value/1/0** van drop-down in **Tweede Naam van het Bezit**.

   ![ screen_shot_2019-05-06at102600am ](assets/screen_shot_2019-05-06at102600am.png)

   Op dezelfde manier geef uit en voeg vergelijkingsbezitsregels aan het **For_Blue** segment zoals aangetoond in het hieronder cijfer toe:

   ![ screen_shot_2019-05-06at103728am ](assets/screen_shot_2019-05-06at103728am.png)

   Op dezelfde manier geef uit en voeg vergelijkingsbezitsregels aan het **For_Green** segment zoals aangetoond in het hieronder cijfer toe:

   ![ screen_shot_2019-05-06at103418am ](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   >
   >Bericht dat voor segmenten **For_Green** en **For_Green**, gegevens niet in de redacteur kunnen worden opgelost aangezien slechts de eerste vergelijking vanaf nu geldig is zoals op de waarden in het Blad van Google.

1. Navigeer en klik uw **kanaal 0} DataDrivenRetail {(een opeenvolgingskanaal).**
1. Klik **uitgeven** van de actiebar.

   ![ screen_shot_2019-05-06at104257am ](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   >
   >U zou reeds opstelling moeten hebben uw **ContextHub** **Configuraties** gebruikend het kanaal **Eigenschappen** > **Personalization** tabel.

   ![ screen_shot_2019-05-06at105214am ](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   >
   >Klik zowel het **Merk** als het **Gebied** voor de activiteiten om behoorlijk worden vermeld wanneer u het het richten proces begint.

1. **Toevoegend een standaardbeeld**

   1. Voeg een standaardbeeld aan uw kanaal toe en klik **het richten**.
   1. Klik **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.
   1. Klik **Begin richtend**.

   ![ screen_shot_2019-05-06at121253pm ](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   >
   >Alvorens u begint te richten, voeg de segmenten (**For_Green**, **For_Red**, en **For_Blue**) toe door **te selecteren + voeg Ervaring toe richtend** van de zijspoorstaaf zoals aangetoond in het hieronder cijfer.

   ![ screen_shot_2019-05-06at123554pm ](assets/screen_shot_2019-05-06at123554pm.png)

1. Voeg de afbeeldingen toe aan alle drie de verschillende scenario&#39;s, zoals hieronder wordt weergegeven.

   ![ retail_targeting ](assets/retail_targeting.gif)

1. **die de Voorproef** controleert

   1. Klik **Voorproef.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde voor alle drie de kolommen. U ziet dat de beeldweergave wordt bijgewerkt volgens de hoogste waarde in het overzicht.

   ![ retail_result ](assets/retail_result.gif)
