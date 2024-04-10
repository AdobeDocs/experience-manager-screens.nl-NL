---
title: Temperatuuractivering in het midden van de reis
seo-title: Travel Center Temperature Activation
description: Het volgende gebruiksgeval toont het gebruik van de lokale temperatuuractivering van het reiscentrum op basis van de waarden die in Google Sheets worden bevolkt.
seo-description: The following use case demonstrates the usage of travel center local temperature activation based on the values populated in Google Sheets.
uuid: b35286d2-79be-4c36-b72e-c40ffc1a0ca0
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 9d58b971-4540-4007-968d-2a1d94d1fd38
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---

# Temperatuuractivering in het midden van de reis {#travel-center-temperature-activation}

Het volgende gebruiksgeval toont het gebruik van de lokale temperatuuractivering van het reiscentrum op basis van de waarden die in Google Sheets worden bevolkt.

## Beschrijving {#description}

Voor dit geval van Gebruik, als uw Google Bladen Waarde minder dan 50 heeft, dan zal een beeld met hete dranken tonen en als de waarde groter dan of gelijk aan 50 is, dan zal het beeld met koude dranken tonen. In het geval van een andere of geen waarde geeft de speler een standaardafbeelding weer.

## Voorwaarden {#preconditions}

Voordat u begint met het implementeren van de lokale temperatuuractivering van het reiscentrum, moet u leren hoe u het systeem instelt ***Gegevensopslag***, ***Auditiesegmentatie*** en ***Doelstelling voor kanalen inschakelen*** in een AEM Screens-project.

Zie [ContextHub configureren in AEM Screens](configuring-context-hub.md) voor nadere informatie.

## Basisstroom {#basic-flow}

Voer de onderstaande stappen uit om het gebruik-hoofdlettergebruik voor lokale temperatuuractivering van Travel Center te implementeren:

1. **De Google-bladen vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Een kolom toevoegen met **Kop1** met de bijbehorende temperatuurwaarde.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het publiek instellen*** in **[ContextHub configureren in AEM Screens](configuring-context-hub.md)** voor meer informatie).

   1. Selecteer de **Bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**

   1. Selecteer de **Operator** als **groter dan of gelijk aan** in het keuzemenu

   1. Voer de **Waarde** als **50**

   1. Selecteer op dezelfde manier de **Bladen A1 2** en klik op **Bewerken**.

   1. Selecteer de **Vergelijkingseigenschap - waarde** en klik op het configuratiepictogram om de eigenschappen te bewerken.
   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**

   1. Selecteer de **Operator** als **kleiner dan** in het keuzemenu

   1. Voer de **Waarde** als **50**

1. Navigeer en selecteer het kanaal () en klik **Bewerken** in de actiebalk. In het volgende voorbeeld: **DataDrivenWeather**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Het kanaal moet al een standaardafbeelding hebben en het publiek moet vooraf zijn geconfigureerd zoals beschreven in [ContextHub configureren in AEM Screens](configuring-context-hub.md).

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >U moet uw **ContextHub** **Configuraties** het kanaal gebruiken **Eigenschappen** > **Personalisatie** tab.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Selecteren **Targeting** in de editor en selecteer **Merk** en de **Activiteit** in het keuzemenu en klik op **Doelstelling starten**.

   ![new_activity3](assets/new_activity3.gif)

1. **De voorvertoning controleren**

   1. Klikken **Voorvertoning.** Open ook het Google-werkblad en werk de waarde ervan bij.
   1. Als u de waarde wijzigt in minder dan 50, kunt u de afbeelding van zomerdranken bekijken. Als de waarde in het Google-blad 50 of hoger is dan de waarde die u zou moeten kunnen zien voor een afbeelding van warme drank.

   ![result3](assets/result3.gif)
