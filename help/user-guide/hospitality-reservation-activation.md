---
title: Activering van ziekenhuisreservering
description: Leer hoe dit gebruiksgeval het gebruik van activering van ziekenhuisreservering aantoont op basis van de waarden in Google Sheets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: ae032042-fa2b-49cd-91fe-ce50f3ce9867
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Activering van ziekenhuisreservering {#hospitality-reservation-activation}

Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.

## Beschrijving {#description}

In dit geval wordt op het Google-blad een reserveringspercentage voor twee restaurants **`Restaurant1`** en **`Restaurant2`** weergegeven. Een formule wordt toegepast gebaseerd op waarden van `Restaurant1` en `Restaurant2` en, gebaseerd op de formule, wordt waarde 1 of 2 toegewezen aan de **AdTarget** Kolom.

Als de waarde van **`Restaurant1`** > **`Restaurant2`**, dan **AdTaget** wordt toegewezen waarde **1** anders **AdTarget** wordt toegewezen waarde **2**. Waarde 1 produceert de voedsel van de a *Stapel* optie en Waarde twee resultaten in een vertoning van *Thaise voedsel* optie op uw vertoningsscherm.

## Voorwaarden {#preconditions}

Alvorens u begint de reserveringsactivering uit te voeren, leer hoe te opstelling ***Opslag van Gegevens***, ***Segmentatie van het publiek*** en ***het richten voor Kanalen*** in een Project van AEM Screens toelaten.

Zie [ het Vormen ContextHub in AEM Screens ](configuring-context-hub.md) voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Volg onderstaande stappen in het gebruiksgeval om de activering van de ziekenhuisreservering voor uw AEM Screens-project te implementeren:

1. **die de Bladen van Google bevolkt en de formule** toevoegt.

   Bijvoorbeeld, pas de formule op de derde kolom **AdTarget** toe, zoals aangetoond in het hieronder cijfer.

   ![ screen_shot_2019-04-29at94132am ](assets/screen_shot_2019-04-29at94132am.png)

1. **Vormend de segmenten in Soorten publiek zoals per de vereisten**

   1. Navigeer aan de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het Publiek van de vestiging*** in **[het Vormen ContextHub in AEM Screens](configuring-context-hub.md)** pagina voor meer details).
   1. Klik de **Bladen A1 1** en klik **uitgeven**.
   1. Klik het vergelijkingsbezit en klik het **pictogram van de Configuratie**.
   1. Klik **googesheets/value/1/2** van de drop-down in **naam van het Bezit**.
   1. Klik de **Exploitant** als **gelijk** van het drop-down menu.
   1. Ga de **Waarde** als **1** in.
   1. Op dezelfde manier klik de **Bladen A1 2** en klik **uitgeven**.
   1. Klik het vergelijkingsbezit en klik het **pictogram van de Configuratie**.
   1. Klik **googesheets/value/1/2** van de drop-down in **naam van het Bezit**.
   1. Klik de **Exploitant** als **&#x200B;**.

1. Navigeer en klik uw kanaal () en klik **uitgeven** van de actiebar. In het volgende voorbeeld, **DataDrivenRestaurant**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Uw kanaal zou reeds een standaardbeeld moeten hebben en het publiek zou pre-gevormd moeten zijn zoals die in [ wordt beschreven het Vormen ContextHub in AEM Screens ](configuring-context-hub.md).

   ![ screen_shot_2019-05-08at14652pm ](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >Uw **ContextHub** **Configuraties** gebruikend het kanaal **Eigenschappen** > **Personalization** lusje zou reeds opstelling op dit punt moeten zijn geweest.

   ![ screen_shot_2019-05-08at114106am ](assets/screen_shot_2019-05-08at114106am.png)

1. Klik **richtend** van de redacteur en klik **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.
1. **die de Voorproef** controleert

   1. Klik **Voorproef.** Open ook uw Google-bladen en werk de waarde ervan bij.
   1. Werk de waarde in **`Restaurant1`** en **`Restaurant2`** kolommen bij. Als **`Restaurant1`** > **`Restaurant2`,** u een beeld van *zou moeten kunnen bekijken Steak* anders voedsel, *Thaise* vertoningen van het voedselbeeld op uw scherm.

   ![ result5 ](assets/result5.gif)
