---
title: Temperatuuractivering in het midden van de reis
description: Met AEM Screens leert u hoe u met dit gebruiksgeval het gebruik van lokale temperatuuractivering in het reiscentrum kunt demonstreren op basis van de waarden in Google Sheets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Temperatuuractivering in het midden van de reis {#travel-center-temperature-activation}

Het volgende gebruiksgeval toont het gebruik van de lokale temperatuuractivering van het reiscentrum op basis van de waarden die in Google Sheets worden bevolkt.

## Beschrijving {#description}

Als de waarde in Google Sheets lager is dan 50, wordt in dit geval een afbeelding met warme dranken weergegeven. Als de waarde groter dan of gelijk aan 50 is, wordt een afbeelding met koude dranken weergegeven. Als er een andere waarde of helemaal geen waarde is, geeft de speler een standaardafbeelding weer.

## Voorwaarden {#preconditions}

Alvorens u begint de lokale temperatuuractivering van het reiscentrum uit te voeren, leer hoe te opstelling ***Opslag van Gegevens***, ***Segmentatie van het publiek*** en ***het richten voor Kanalen*** in een Project van AEM Screens toelaten.

Zie [ het Vormen ContextHub in AEM Screens ](configuring-context-hub.md) voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Voer de onderstaande stappen uit om het gebruik-hoofdlettergebruik voor lokale temperatuuractivering van Travel Center te implementeren:

1. **die de Bladen van Google bevolkt**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg een kolom met **`Heading1`** toe met de bijbehorende waarde voor de temperatuur.

   ![ screen_shot_2019-05-08at112911am ](assets/screen_shot_2019-05-08at112911am.png)

1. **Vormend de segmenten in Soorten publiek zoals per de vereisten**

   1. Navigeer aan de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het Publiek van de vestiging*** in **[het Vormen ContextHub in AEM Screens](configuring-context-hub.md)** pagina voor meer details).

   1. Klik de **Bladen A1 1** en klik **uitgeven**.

   1. Klik het vergelijkingsbezit en klik het configuratiepictogram.
   1. Klik **googesheets/value/1/0** van drop-down in **naam van het Bezit**

   1. Klik **Exploitant** als **groter-dan-of-gelijk** van het drop-down menu

   1. Ga de **Waarde** als **in 50**

   1. Op dezelfde manier selecteer de **Bladen A1 2** en klik **uitgeven**.

   1. Klik het **Bezit van de Vergelijking - Waarde** en selecteer het configuratiepictogram.
   1. Klik **googesheets/value/1/0** van drop-down in **naam van het Bezit**

   1. Klik **Exploitant** als **minder-dan** van het drop-down menu

   1. Ga de **Waarde** als **in 50**

1. Navigeer en selecteer uw kanaal () en klik **uitgeven** van de actiebar. In het volgende voorbeeld, **DataDrivenWeather**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Uw kanaal zou reeds een standaardbeeld moeten hebben en het publiek zou pre-gevormd moeten zijn zoals die in [ wordt beschreven het Vormen ContextHub in AEM Screens ](configuring-context-hub.md).

   ![ screen_shot_2019-05-08at113022am ](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Uw **ContextHub** **Configuraties** gebruikend het kanaal **Eigenschappen** > **Personalization** lusje zou reeds opstelling moeten zijn.

   ![ screen_shot_2019-05-08at114106am ](assets/screen_shot_2019-05-08at114106am.png)

1. Klik **richtend** van de redacteur en klik **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.

   ![ new_activity3 ](assets/new_activity3.gif)

1. **die de Voorproef** controleert

   1. Klik **Voorproef.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde in minder dan 50. Je kunt een afbeelding van een koud drankje bekijken. Als de waarde in Google Sheets 50 of hoger is, ziet u een afbeelding van een warme drank.

   ![ result3 ](assets/result3.gif)
