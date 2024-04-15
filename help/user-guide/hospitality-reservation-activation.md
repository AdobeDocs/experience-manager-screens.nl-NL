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
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# Activering van ziekenhuisreservering {#hospitality-reservation-activation}

Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.

## Beschrijving {#description}

Voor dit geval van Gebruik, is het Blad van Google bevolkt met percentage reserveringen op twee restaurants **`Restaurant1`** en **`Restaurant2`**. Een formule wordt toegepast op basis van waarden van `Restaurant1` en `Restaurant2` en op basis van de formule wordt waarde 1 of 2 toegewezen aan de **AdTarget** Kolom.

Als de waarde van **`Restaurant1`** > **`Restaurant2`** vervolgens **Advertentietag** is toegewezen waarde **1** anders **AdTarget** is toegewezen waarde **2**. Waarde 1 genereert *Steekvoedsel* optie en waarde twee resulteert in weergave van *Thais voedsel* op het scherm.

## Voorwaarden {#preconditions}

Voordat u de activering van reserveringen gaat implementeren, moet u leren hoe u de instelling ***Gegevensopslag***, ***Auditiesegmentatie*** en ***Doelstelling voor kanalen inschakelen*** in een AEM Screens-project.

Zie [ContextHub configureren in AEM Screens](configuring-context-hub.md) voor nadere informatie.

## Basisstroom {#basic-flow}

Volg onderstaande stappen in het gebruiksgeval om de activering van de ziekenhuisreservering voor uw AEM Screens-project te implementeren:

1. **Google Sheets vullen en de formule toevoegen**.

   Pas bijvoorbeeld de formule toe op de derde kolom **AdTarget**, zoals weergegeven in onderstaande afbeelding.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie van het publiek instellen*** in **[ContextHub configureren in AEM Screens](configuring-context-hub.md)** voor meer informatie).
   1. Selecteer de **Bladen A1 1** en klik op **Bewerken**.
   1. Selecteer de vergelijkingseigenschap en klik op de knop **Configuratie** pictogram.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Eigenschapnaam**.
   1. Selecteer de **Operator** als **gelijk** in het keuzemenu.
   1. Voer de **Waarde** als **1**.
   1. Selecteer op dezelfde manier de **Bladen A1 2** en klik op **Bewerken**.
   1. Selecteer de vergelijkingseigenschap en klik op de knop **Configuratie** pictogram.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Eigenschapnaam**.
   1. Selecteer de **Operator** als **2**.

1. Navigeer en selecteer het kanaal () en klik **Bewerken** in de actiebalk. In het volgende voorbeeld: **DataDrivenRestaurant**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Het kanaal moet al een standaardafbeelding hebben en het publiek moet vooraf zijn geconfigureerd zoals beschreven in [ContextHub configureren in AEM Screens](configuring-context-hub.md).

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >U moet uw **ContextHub** **Configuraties** het kanaal gebruiken **Eigenschappen** > **Personalisatie** tab.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Selecteren **Targeting** in de editor en selecteer **Merk** en de **Activiteit** in het keuzemenu en klik op **Doelstelling starten**.
1. **De voorvertoning controleren**

   1. Klikken **Voorvertoning.** Open ook uw Google-bladen en werk de waarde ervan bij.
   1. De waarde bijwerken in **`Restaurant1`** en **`Restaurant2`** kolommen. Indien **`Restaurant1`** > **`Restaurant2`,** u zou een beeld van moeten kunnen bekijken *Steak* anders voedsel, *Thai* voedselafbeeldingen worden op het scherm weergegeven.

   ![result5](assets/result5.gif)
