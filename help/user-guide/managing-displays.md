---
title: Weergaven maken en beheren
seo-title: Managing Displays
description: Volg deze pagina om over het creëren van een nieuwe vertoning en apparaat config te leren. Meer informatie over het weergavedashboard.
seo-description: Follow this page to learn about creating a new display and device config. Additionally, learn about the display dashboard.
uuid: dfde0740-5c8b-4e6c-bc83-bf8fbb31a16a
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: f8e2e7a3-f3a1-4c35-b055-166752c3fb86
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c55dc128-208d-4379-95a8-60a39d495dc0
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

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
>U moet een locatie maken voordat u een weergave maakt. Zie voor meer informatie over het maken van een locatie [Locaties maken en beheren](managing-locations.md) voor meer informatie .

Voer de onderstaande stappen uit om een nieuwe weergave op uw locatie te maken:

1. Ga bijvoorbeeld naar de juiste locatie `http://localhost:4502/screens.html/content/screens/TestProject`.
1. Selecteer uw locatiemap en tik/klik op **Maken** naast het plusteken in de actiebalk. Er wordt een wizard geopend.
1. Selecteren **Weergave** van de **Maken** wizard en klik op **Volgende**.

1. Enter **Naam** en **Titel** voor uw weergavelocatie.

1. Onder de **Weergave** kiest, kiest u de details van de layout. Kies het gewenste **Resolutie** (bijvoorbeeld als **Volledige HD**). Bovendien kunt u het aantal apparaten horizontaal en verticaal kiezen.

1. Klikken **Maken**.

De weergave (*StoreDisplay*) wordt gemaakt en toegevoegd aan de locatie (*SanJose*).

![display](assets/display.gif)

Zodra u in positie hebt tonen, zal de volgende stap een apparaat config voor die bepaalde vertoning zijn tot stand brengen. Volg de onderstaande sectie om een nieuwe apparaatconfiguratie te maken.

>[!NOTE]
>
>**De volgende stap**:
>
>Wanneer u een weergave voor uw locatie hebt gemaakt, moet u een kanaal aan uw scherm toewijzen om de inhoud te benutten.
>
>Zie [Kanalen toewijzen](channel-assignment.md) voor meer informatie over het toewijzen van een kanaal aan de weergave.

## Een nieuwe apparaatconfiguratie maken {#creating-a-new-device-config}

Een apparaat config dienst als placeholder voor een echt digitaal signaalapparaat dat nog niet geïnstalleerd is.

Voer de onderstaande stappen uit om een nieuwe apparaatconfiguratie te maken:

1. Navigeer naar de juiste weergave, bijvoorbeeld `http://localhost:4502/screens.html/content/screens/TestProject/locations/newlocation`.
1. Selecteer de weergavemap en tik/klik op **Dashboard weergeven** in de actiebalk.
1. Tik/klik op de knop **+ Apparaatconfiguratie toevoegen** in de rechterbovenhoek van het **Apparaten** deelvenster.

1. Selecteer **Apparaatconfiguratie** als de vereiste sjabloon en tik/klik **Volgende**.

1. Voer de vereiste eigenschappen in en tik/klik op **Maken**.

Het apparaat config wordt gecreeerd en aan de huidige vertoning toegevoegd (in de volgende demonstratie, wordt het nieuwe apparaat config gecreeerd *DeviceConfig*).

![deviceconfig](assets/deviceconfig.gif)

Zodra een apparaat config aan uw vertoning in de plaats wordt geplaatst, zal de volgende stap een kanaal aan uw vertoning moeten toewijzen.

>[!NOTE]
>
>Zodra een apparaat config aan uw vertoning in de plaats wordt geplaatst, zal de volgende stap een kanaal aan uw vertoning moeten toewijzen.
>
>Zoals aangetoond in het hieronder cijfer, als het apparaat config als niet toegewezen in wordt getoond **APPARATEN** paneel, als geen kanaal aan dat bepaalde apparaat config wordt toegewezen.
>
>U zou voorafgaand inzicht in het creëren en het beheren van kanalen moeten hebben. Zie [Kanalen maken en beheren](managing-channels.md) voor meer informatie .

![chlimage_1-9](assets/chlimage_1-9.png)

## Het dashboard weergeven {#display-dashboard}

Het weergavedashboard biedt u verschillende deelvensters voor het beheer van weergaveapparaten en apparaatconfiguraties voor uw apparaat.

![screen_shot_2018-08-23at42810pm](assets/screen_shot_2018-08-23at42810pm.png)

>[!NOTE]
>
>U kunt de dashboardlijsten selecteren en bulkacties voor items activeren in plaats van elk item afzonderlijk te doorlopen.
>
>De volgende afbeelding laat bijvoorbeeld zien hoe u meerdere kanalen van het weergavedashboard kunt selecteren.

![cqdoc9456](assets/cqdoc9456.gif)

### Deelvenster Informatie weergeven {#display-information-panel}

De **INFORMATIE OVER WEERGAVE** Het deelvenster bevat de weergave-eigenschappen.

Klik op de knop (**...**) in de rechterbovenhoek in de **INFORMATIE OVER WEERGAVE** om de eigenschappen weer te geven en een voorvertoning van de weergave weer te geven.


#### Eigenschappen weergeven {#viewing-properties}

Klikken **Eigenschappen** om de eigenschappen van de weergave weer te geven of te wijzigen.

Bovendien kunt u de waarde van de gebeurtenistimer voor uw interactieve kanaal aanpassen in **Niet-actieve time-out** eigendom onder **Weergave** tab. De standaardwaarde is ingesteld op *300 seconden*.

Gebruiken **CRXDE Lite**, om toegang te krijgen tot **idleTimeout** eigenschap, dat wil zeggen: `http://localhost:4502/crx/de/index.jsp#/content/screens/we-retail/locations/demo/flagship/single/jcr%3Acontent/channels` .


### Deelvenster Toegewezen kanalen {#assigned-channels-panel}

De **TOEGEWEZEN KANALEN** toont de toegewezen kanalen aan dit apparaat.


### Deelvenster Apparaten {#devices-panel}

De **APPARATEN** Het paneel verstrekt informatie over de apparatenvormen.

Klik op de knop (**...**) in de rechterbovenhoek in de **APPARATEN** om apparaten toe te voegen, configureert en bijwerkt.

Bovendien, klik op het apparaat config om eigenschappen te bekijken, een apparaat toe te wijzen, of het volledig te schrappen.

![chlimage_1-13](assets/chlimage_1-13.png)

#### De volgende stappen {#the-next-steps}

Wanneer u klaar bent met het maken van een weergave voor uw locatie, moet u een kanaal toewijzen voor uw weergave.

Zie [Kanalen toewijzen](channel-assignment.md) voor meer informatie .
