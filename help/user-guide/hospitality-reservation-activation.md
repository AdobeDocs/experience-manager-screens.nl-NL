---
title: Activering van ziekenhuisreservering
seo-title: Hospitality Reservation Activation
description: Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.
seo-description: The following use case demonstrates the usage of hospital reservation activation based on the values populated in Google Sheets.
uuid: 7692d616-2b00-4d9a-9d3f-211c089b29af
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: ef3e5dce-e36a-45d3-ad5e-db01430477c6
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: ae032042-fa2b-49cd-91fe-ce50f3ce9867
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 0%

---

# Activering van ziekenhuisreservering {#hospitality-reservation-activation}

Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.

## Beschrijving {#description}

Voor dit geval van Gebruik, is het Blad van Google bevolkt met percentage van reserve op twee restaurants **Restaurant1** en **Restaurant2**. Er wordt een formule toegepast op basis van de waarden van Restaurant1 en Restaurant2 en op basis van de formule, de waarde 1 of 2 wordt toegewezen aan de **AdTarget** Kolom.

Als de waarde van **Restaurant1** > **Restaurant2** vervolgens **Advertentietag** is toegewezen waarde **1** anders **AdTarget** is toegewezen waarde **2**. Waarde 1 genereert *Steekvoedsel* optie en waarde 2 resulteert in weergave van *Thais voedsel* op het scherm.

## Voorwaarden {#preconditions}

Voordat u de activering van de reservering gaat implementeren, moet u leren hoe u de activering kunt instellen ***Gegevensopslag***, ***Auditiesegmentatie*** en ***Doelstelling voor kanalen inschakelen*** in een AEM Screens-project.

Zie [ContextHub configureren in AEM Screens](configuring-context-hub.md) voor nadere informatie.

## Basisstroom {#basic-flow}

Voer de onderstaande stappen uit om de activeringsaanvraag voor de ziekenhuisreservering te implementeren voor uw AEM Screens-project:

1. **De Google Sheets vullen en de formule toevoegen.**

   Pas bijvoorbeeld de formule toe op de derde kolom **AdTarget**, zoals weergegeven in onderstaande afbeelding.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (raadpleeg ***Stap 2: De Segmentatie van het publiek instellen*** in **[ContextHub configureren in AEM Screens](configuring-context-hub.md)** voor meer informatie).

   1. Selecteer de **Bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Eigenschapnaam**

   1. Selecteer de **Operator** als **gelijk** in het keuzemenu

   1. Voer de **Waarde** als **1**

   1. Selecteer op dezelfde manier de **Bladen A1 2** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteren **googesheets/value/1/2** in de vervolgkeuzelijst **Eigenschapnaam**

   1. Selecteer de **Operator** als **2**

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
   1. De waarde bijwerken in **Restaurant1** en **Restaurant2** kolommen. Indien **Restaurant1** > **Restaurant2,** u zou een beeld van moeten kunnen bekijken *Steak* anders voedsel, *Thai* voedselafbeeldingen worden op het scherm weergegeven.

   ![result5](assets/result5.gif)
