---
title: Activering van ziekenhuisreservering
seo-title: Activering van ziekenhuisreservering
description: Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.
seo-description: Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.
uuid: 7692d616-2b00-4d9a-9d3f-211c089b29af
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
discoiquuid: ef3e5dce-e36a-45d3-ad5e-db01430477c6
docset: aem65
translation-type: tm+mt
source-git-commit: 209a9a833957d9a8bb7c7ec70ff421514f5b974c

---


# Activering van ziekenhuisreservering {#hospitality-reservation-activation}

Het volgende gebruiksgeval toont het gebruik van activering van ziekenhuisreserveringen op basis van de waarden in Google Sheets.

## Beschrijving {#description}

In dit geval wordt op het Google-blad een reserveringspercentage vermeld voor twee restaurants **Restaurant1** en **Restaurant2**. Een formule wordt toegepast gebaseerd op waarden van Restaurant1 en Restaurant2 en gebaseerd op de formule, wordt waarde 1 of 2 toegewezen aan de Kolom **AdTarget** .

Als de waarde van **Restaurant1** > **Restaurant2**, dan wordt **AdTaget** toegewezen waarde **1** anders **AdTarget** **** wordt toegewezen waarde2. Waarde 1 genereert de optie *Steak food* en waarde 2 resulteert in de weergave van de optie *Thai food* op het scherm.

## Voorwaarden {#preconditions}

Voordat u begint met het implementeren van reserveringsactivering, moet u leren hoe u ***Gegevensopslag***, ***Audience Segmentation*** en ***Enable Targeting for Channels*** in een AEM-schermproject instelt.

Verwijs naar het [Vormen ContextHub in Schermen](configuring-context-hub.md) AEM voor gedetailleerde informatie.

## Basisstroom {#basic-flow}

Voer de onderstaande stappen uit om de activeringsaanvraag voor ziekenhuisreservering te implementeren voor uw AEM Screens-project:

1. **De Google Sheets vullen en de formule toevoegen.**

   Pas bijvoorbeeld de formule toe op de derde kolom **AdTarget**, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (zie ***Stap 2: De Segmentatie*** van het publiek van de vestiging in het **[Vormen ContextHub in AEM de pagina van Schermen](configuring-context-hub.md)**voor meer details).

   1. Selecteer de **bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **Operator** als **gelijk** in het keuzemenu

   1. Voer de **waarde** in als **1**

   1. Selecteer op dezelfde manier de bladen A1 2 **en klik op** Bewerken ****.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. De **operator** selecteren als **2**

1. Navigeer en selecteer het kanaal () en klik op **Bewerken** op de actiebalk. In het volgende voorbeeld, **DataDrivenRestaurant**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   >
   >Uw kanaal zou reeds een standaardbeeld moeten hebben en het publiek zou pre-gevormd moeten zijn zoals die in het [Vormen ContextHub in de Schermen](configuring-context-hub.md)van AEM wordt beschreven.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Selecteer **Doel** in de editor en selecteer **Merk** en **Activiteit** in het keuzemenu en klik op **Doelstelling** starten.
1. **De voorvertoning controleren**

   1. Klik op **Voorvertoning.** Open ook uw Google Sheets en werk de waarde ervan bij.
   1. Werk de waarde bij in de kolommen **Restaurant1** en **Restaurant2** . Als **Restaurant1** > **Restaurant2,** zou u een beeld van *Steak* voedsel anders moeten kunnen bekijken, *Thai* voedselvertoningen op uw scherm.
   ![result5](assets/result5.gif)

