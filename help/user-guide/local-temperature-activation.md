---
title: Temperatuuractivering in het midden van de reis
seo-title: Temperatuuractivering in het midden van de reis
description: Het volgende gebruiksscenario toont het gebruik van lokale temperatuuractivering in het reiscentrum op basis van de waarden die in Google Sheets zijn ingevuld.
seo-description: Het volgende gebruiksscenario toont het gebruik van lokale temperatuuractivering in het reiscentrum op basis van de waarden die in Google Sheets zijn ingevuld.
uuid: b35286d2-79be-4c36-b72e-c40ffc1a0ca0
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: 9d58b971-4540-4007-968d-2a1d94d1fd38
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---


# Temperatuuractivering in het midden van de reis {#travel-center-temperature-activation}

Het volgende gebruiksscenario toont het gebruik van lokale temperatuuractivering in het reiscentrum op basis van de waarden die in Google Sheets zijn ingevuld.

## Beschrijving {#description}

Als uw Google-bladen voor dit geval een waarde van minder dan 50 hebben, wordt een afbeelding met warme dranken weergegeven en als de waarde groter dan of gelijk is aan 50, wordt de afbeelding met koude dranken weergegeven. In het geval van een andere of geen waarde geeft de speler een standaardafbeelding weer.

## Voorwaarden {#preconditions}

Voordat u begint met het implementeren van de lokale temperatuuractivering van het reiscentrum, moet u leren hoe u ***Gegevensopslag***, Segmentatie ***van het*** publiek en ***Doelstelling voor kanalen*** inschakelen in een AEM Screens-project instelt.

Verwijs naar het [Vormen ContextHub in AEM Screens](configuring-context-hub.md) voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Voer de onderstaande stappen uit om het gebruik-hoofdlettergebruik voor lokale temperatuuractivering van Travel Center te implementeren:

1. **De Google Sheets vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg een kolom met **Kop1** met overeenkomstige waarde voor temperatuur toe.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie*** van het Publiek van de vestiging in het **[Vormen ContextHub in de pagina van AEM Screens](configuring-context-hub.md)** voor meer details).

   1. Selecteer de **bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **operator** als **groter dan of gelijk aan** in het keuzemenu

   1. Voer de **waarde** in als **50**

   1. Selecteer op dezelfde manier de bladen A1 2 **en klik op** Bewerken ****.

   1. Selecteer het bezit van de **Vergelijking - Waarde** en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **operator** als **kleiner dan** in het keuzemenu

   1. Voer de **waarde** in als **50**

1. Navigeer en selecteer het kanaal () en klik op **Bewerken** op de actiebalk. In het volgende voorbeeld, **DataDrivenWeather**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Uw kanaal zou reeds een standaardbeeld moeten hebben en het publiek zou pre-gevormd moeten zijn zoals die in het [Vormen ContextHub in AEM Screens](configuring-context-hub.md)wordt beschreven.

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Selecteer **Doel** in de editor en selecteer **Merk** en **Activiteit** in het keuzemenu en klik op **Doelstelling** starten.

   ![new_activity3](assets/new_activity3.gif)

1. **De voorvertoning controleren**

   1. Klik op **Voorvertoning.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Als u de waarde wijzigt in minder dan 50, kunt u de afbeelding van zomerdranken bekijken. Als de waarde in het Google-blad 50 of hoger is dan zou moeten kunnen worden bekeken of er een afbeelding van warme drank is.

   ![result3](assets/result3.gif)

