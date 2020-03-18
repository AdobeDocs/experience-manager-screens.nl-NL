---
title: Weergaven maken en beheren
seo-title: Weergaven beheren
description: Volg deze pagina om over het creëren van een nieuwe vertoning en apparaat config te leren. Meer informatie over het weergavedashboard.
seo-description: Volg deze pagina om over het creëren van een nieuwe vertoning en apparaat config te leren. Meer informatie over het weergavedashboard.
uuid: dfde0740-5c8b-4e6c-bc83-bf8fbb31a16a
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: f8e2e7a3-f3a1-4c35-b055-166752c3fb86
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Weergaven maken en beheren {#creating-and-managing-displays}

Een weergave is een virtuele groep schermen die gewoonlijk naast elkaar worden geplaatst. Het beeldscherm is gewoonlijk permanent ten opzichte van een installatie. Dit zijn de objecten inhoudsauteurs waarmee en verwijzen altijd naar logische weergave in plaats van naar hun fysieke tegenonderdelen.

Nadat u een locatie hebt gemaakt, moet u een nieuwe weergave voor uw locatie maken.

Op deze pagina ziet u hoe u beeldschermen maakt en beheert.

**Voorwaarden**:

* [Schermen configureren en implementeren](configuring-screens-introduction.md)
* [Schermproject maken en beheren](creating-a-screens-project.md)
* [Kanalen maken en beheren](managing-channels.md)
* [Locaties maken en beheren](managing-locations.md)

## Een nieuwe weergave maken {#creating-a-new-display}

>[!NOTE]
>
>U moet een locatie maken voordat u een weergave maakt. Zie Locaties [maken en beheren voor meer informatie. Zie Locaties](managing-locations.md) maken en beheren.

Voer de onderstaande stappen uit om een nieuwe weergave op uw locatie te maken:

1. Navigeer bijvoorbeeld naar de juiste locatie `http://localhost:4502/screens.html/content/screens/TestProject`.
1. Selecteer de locatiemap en tik op **Maken** /klik op het plusteken op de actiebalk. Er wordt een wizard geopend.
1. Selecteer **Weergave** in de wizard **Maken** en klik op **Volgende**.

1. Voer **Naam** en **Titel** in voor de weergavelocatie.

1. Kies onder het tabblad **Weergave** de details van de layout. Kies de gewenste **resolutie** (bijvoorbeeld als **Full HD**). Bovendien kunt u het aantal apparaten horizontaal en verticaal kiezen.

1. Klik op **Maken**.

De weergave (*StoreDisplay*) wordt gemaakt en toegevoegd aan de locatie (*SanJose*).

![display](assets/display.gif)

Zodra u in positie hebt tonen, zal de volgende stap een apparaat config voor die bepaalde vertoning zijn tot stand brengen. Volg de onderstaande sectie om een nieuwe apparaatconfiguratie te maken.

>[!NOTE]
>
>**De volgende stap**:
>
>Wanneer u een weergave voor uw locatie hebt gemaakt, moet u een kanaal aan uw scherm toewijzen om de inhoud te benutten.
>
>Zie De sectie Kanalen [](channel-assignment.md) toewijzen voor meer informatie over het toewijzen van een kanaal aan de weergave.

## Een nieuwe apparaatconfiguratie maken {#creating-a-new-device-config}

Een apparaat config dienst als placeholder voor een werkelijk digitaal signaalapparaat dat nog niet geïnstalleerd is.

Voer de onderstaande stappen uit om een nieuwe apparaatconfiguratie te maken:

1. Navigeer bijvoorbeeld naar de juiste weergave `http://localhost:4502/screens.html/content/screens/TestProject/locations/newlocation`.
1. Selecteer de weergavemap en tik op het dashboard **** weergeven of klik op de actiebalk.
1. Tik/klik op **+ Apparaatconfiguratie** toevoegen rechtsboven in het deelvenster **Apparaten** .

1. Selecteer **Apparaatconfiguratie** als de vereiste sjabloon en tik op **Volgende**.

1. Voer de gewenste eigenschappen in en tik op **Maken**/klik op Maken.

Het apparaat config wordt gecreeerd en aan de huidige vertoning toegevoegd (in de volgende demonstratie, is het nieuwe apparaat config *DeviceConfig*).

![deviceconfig](assets/deviceconfig.gif)

Zodra een apparaat config aan uw vertoning in de plaats wordt geplaatst, zal de volgende stap een kanaal aan uw vertoning moeten toewijzen.

>[!NOTE]
>
>Zodra een apparaat config aan uw vertoning in de plaats wordt geplaatst, zal de volgende stap een kanaal aan uw vertoning moeten toewijzen.
>
>Zoals aangetoond in het hieronder cijfer, als apparaat config als niet toegewezen in het paneel van **APPARATEN** wordt getoond, als geen kanaal aan dat bepaalde apparaat config wordt toegewezen.
>
>U zou voorafgaand inzicht in het creëren en het beheren van kanalen moeten hebben. Zie Kanalen [maken en beheren](managing-channels.md) voor meer informatie.

![chlimage_1-9](assets/chlimage_1-9.png)

## Het dashboard weergeven {#display-dashboard}

Het weergavedashboard biedt u verschillende deelvensters voor het beheer van weergaveapparaten en apparaatconfiguraties voor uw apparaat.

![screen_shot_2018-08-23at42810pm](assets/screen_shot_2018-08-23at42810pm.png)

>[!NOTE]
>
>U kunt de dashboardlijsten selecteren en bulkacties voor items activeren in plaats van elk item afzonderlijk te doorlopen.
>
>In de volgende afbeelding ziet u bijvoorbeeld hoe u meerdere kanalen van het weergavedashboard kunt selecteren.

![cqdoc9456](assets/cqdoc9456.gif)

### Deelvenster Informatie weergeven {#display-information-panel}

Het deelvenster **WEERGAVEINFORMATIE** bevat de weergave-eigenschappen.

Klik op de (**...**) in de rechterbovenhoek in het deelvenster **WEERGAVEINFORMATIE **om de eigenschappen weer te geven en een voorvertoning van de weergave te bekijken.

![chlimage_1-10](assets/chlimage_1-10.png)

#### Eigenschappen weergeven {#viewing-properties}

Klik op **Eigenschappen** om de eigenschappen van de weergave weer te geven of te wijzigen.

Bovendien kunt u de waarde van de gebeurtenistijdopnemer voor uw interactief kanaal in **Niet-actieve onderbreking **bezit onder het lusje van de **Vertoning** aanpassen. De standaardwaarde wordt ingesteld op *300 seconden*.

Gebruik **CRXDE Lite** om toegang te krijgen tot de eigenschap **idleTimeout** , dat wil zeggen, `http://localhost:4502/crx/de/index.jsp#/content/screens/we-retail/locations/demo/flagship/single/jcr%3Acontent/channels` .

![chlimage_1-1](assets/chlimage_1-1.gif)

### Deelvenster Toegewezen kanalen {#assigned-channels-panel}

In het deelvenster **TOEGEWEZEN KANALEN** worden de aan dit apparaat toegewezen kanalen weergegeven.

![chlimage_1-11](assets/chlimage_1-11.png)

### Deelvenster Apparaten {#devices-panel}

Het deelvenster **APPARATEN** biedt informatie over de apparaatconfiguraties.

Klik op de (**...**) in de hoogste juiste hoek in het **DEVICES **paneel om apparatenconfiguraties toe te voegen en apparaten bij te werken.

![chlimage_1-12](assets/chlimage_1-12.png)

Bovendien, klik op het apparaat config om eigenschappen te bekijken, een apparaat toe te wijzen, of het volledig te schrappen.

![chlimage_1-13](assets/chlimage_1-13.png)

#### De volgende stappen {#the-next-steps}

Wanneer u klaar bent met het maken van een weergave voor uw locatie, moet u een kanaal toewijzen voor uw weergave.

Zie Kanalen [](channel-assignment.md) toewijzen voor meer informatie.
