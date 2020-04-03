---
title: ContextHub configureren in AEM-schermen
seo-title: ContextHub configureren in AEM-schermen
description: Volg deze pagina om over ContextHub in de het richten motor te leren om gegevensopslag voor het doel van de verandering van de de inhoudsloopvraag van gegevens te bepalen.
seo-description: Volg deze pagina om over ContextHub in de het richten motor te leren om gegevensopslag voor het doel van de verandering van de de inhoudsloopvraag van gegevens te bepalen.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65
translation-type: tm+mt
source-git-commit: f5062a0610f7258240c3ed698e0c4c276b0823a2

---


# ContextHub configureren in AEM-schermen {#configuring-contexthub-in-aem-screens}

In deze sectie wordt de nadruk gelegd op het maken en beheren van gegevensgestuurde wijzigingen in elementen met behulp van een gegevensopslag.

## Belangrijkste voorwaarden {#key-terms}

Voordat we de details van het maken en beheren van voorraadgestuurde kanalen in uw AEM Screens-project kunnen bekijken, moet u weinig van de belangrijkste termen leren die belangrijk en relevant zijn voor de verschillende scenario&#39;s.

**Merk** verwijst naar uw projectbeschrijving op hoog niveau.

**Het gebied** verwijst naar uw AEM Schermen projectnaam zoals Digitale Ad Signage

**De activiteit** bepaalt de regelcategorie zoals Inventory-Gedreven, Weer-Gedreven, Afdeling Beschikbaarheid-Gedreven, etc.

**Het publiek** bepaalt de regel.

**Segment** verwijst naar de versie van het element die voor de gegeven regel moet worden afgespeeld, bijvoorbeeld als de temperatuur lager is dan 50 graden frenheit, dan geeft het scherm een beeld van een warme koffie, anders een koude drank.

Het volgende diagram verstrekt een visuele vertegenwoordiging van hoe de Configuraties ContextHub met Activiteit, Publiek, en Kanalen samenvallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voorwaarden {#preconditions}

Voordat u de Configuratie van de Hub van de Context voor een project van het Schermen AEM begint te vormen, moet u opstelling Google Bladen (voor demonstratiedoeleinden).

>[!IMPORTANT]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt als een voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is uitsluitend voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Raadpleeg de API-sleutel [](https://developers.google.com/maps/documentation/javascript/get-api-key) ophalen in de documentatie van Google voor meer informatie.

## Stap 1: Een gegevensopslag instellen {#step-setting-up-a-data-store}

U kunt de gegevensopslag instellen als een lokale I/O-gebeurtenis of als een lokale databasegebeurtenis.

De volgende gegevens van het activaniveau brengen voorbeeld teweeg toont een lokale gegevensbestandgebeurtenis die opstelling een gegevensopslag zoals een Excel blad dat u toestaat om configuraties ContextHub en segmentweg aan het kanaal van de Schermen van AEM te gebruiken.

Nadat u het Google-blad correct hebt ingesteld, bijvoorbeeld zoals hieronder wordt getoond:

![image](/help/user-guide/assets/context-hub/context-hub1.png)

De volgende validatie wordt weergegeven wanneer u de verbinding controleert door de twee waarden, de *Google-werkblad-id* en de *API-sleutel* , in de onderstaande notatie in te voeren:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![image](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
> In het onderstaande specifieke voorbeeld worden de Google-werkbladen weergegeven als een gegevensopslagruimte die een wijziging van het element veroorzaakt wanneer de waarde hoger is dan 100 of lager dan 50.

## Stap 2: Opslagconfiguraties instellen {#step-setting-store-configurations}

1. **Navigeren naar ContextHub**

   Navigeer naar de AEM-instantie en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klik **Plaatsen** -> **ContextHub**, zoals aangetoond in het hieronder cijfer.

   ![image](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Het creëren van een nieuwe Configuratie van de Opslag ContextHub**

   1. Navigeer naar de configuratiecontainer met de naam **screens**.

   1. Klik **creëren** > **creeer de Container** van de Configuratie en ga de titel als **ContextHubDemo** in.

      ![image](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **Navigeer** aan **ContextHubDemo** > **creeer** **Configuratie** ContentHub en klik **sparen**.

      >[!NOTE]
      > Nadat u **sparen** klikt zult u in het scherm van de Configuratie **van** ContextHub zijn.

   1. Van het **scherm van de Configuratie** ContextHub, leidt de klik **tot** > de Configuratie van de Opslag **ContentHub.**

      ![image](/help/user-guide/assets/context-hub/context-hub5.png)

   1. Voer de **titel** in als **Google Sheets**, de **winkelnaam** als **gumesheets** en het **winkeltype** **** ****als contexthub.generic-jsonp en klik op Next.
      ![image](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Voer uw specifieke json-configuratie in. Bijvoorbeeld, kunt u de volgende json voor demodoeleinden gebruiken en **sparen** klikken en u zult de opslagconfiguratie zien die als **Bladen** van Google in configuratie ContextHub wordt genoemd.

      >[!IMPORTANT]
      >Vervang de code door uw *&lt;Sheet ID>* en *&lt;API Key>*, die u hebt opgehaald tijdens het instellen van de Google Sheets.

      ```
       {
        "service": {
        "host": "sheets.googleapis.com",
        "port": 80,
        "path": "/v4/spreadsheets/<your google sheets id>/values/Sheet1",
        "jsonp": false,
        "secure": true,
        "params": {
        "key": "<your Google API key>"
       }
      },
      "pollInterval": 10000
      }
      ```

      >[!NOTE]
      In de bovenstaande voorbeeldcode definieert **pollInterval** de frequentie waarmee de waarden worden vernieuwd (in ms).
Vervang de code door uw *&lt;Sheet ID>* en *&lt;API Key>*, die u hebt opgehaald tijdens het instellen van de Google Sheets.

      >[!CAUTION]
      Als u uw Google Sheets-opslagconfiguraties buiten de algemene map maakt (bijvoorbeeld in uw eigen projectmap), werkt het aanwijzen van doelen niet uit de doos.

1. **Opslagsegmentatie instellen**

   1. Navigeer aan de Configuratie van de Opslag **ContentHub..** en maak een andere opslagconfiguratie in de container van de het schermconfiguratie en plaats de **Titel** als **segmentatie-contexthub**, **Naam** van de Opslag als **segmentatie** en Type **van** **** Opslag als aem.segmentation.

      ![image](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klik op **Volgende** en **Opslaan**.

      >[!NOTE]
U moet het proces van het bepalen van de json overslaan en het als leeg verlaten.


## Stap 3: Publiek instellen {#setting-up-audience}

In behandeling: om eigenschappen toe te voegen

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Publiek** > de **schermen**.

   1. Klik op **Maken** > Context Hub Segment **maken.** Het **Nieuwe de dialoogvakje van het Segment** ContextHub opent.

   1. Voer de **titel** in als **TargetValue1** en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam **TargetValue2**.

      ![image](/help/user-guide/assets/context-hub/context-hub10.png)



## Stap 4: Segmentering publiek instellen {#step-setting-up-audience-segmentation}

In behandeling om bewerking toe te voegen

Nadat u een gegevensopslagruimte hebt ingesteld en uw activiteit (merk en gebied) hebt gedefinieerd, volgt u de onderstaande stappen om publiekssegmenten in te stellen:

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Publiek** > de **schermen**.

   1. Klik op **Maken** > Context Hub Segment **maken.** Het **Nieuwe de dialoogvakje van het Segment** ContextHub opent.

   1. Voer de **titel** in als **TargetValue1** en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam **TargetValue2**.

      ![image](/help/user-guide/assets/context-hub/context-hub10.png)


1. **Segmenten bewerken**

   1. Selecteer het segment **TargetValue1**, en klik **uitgeven** van de actiebar.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer de **operator** als **gelijk** in het keuzemenu.

   1. Voer de **waarde** in als **1**.
   >[!NOTE]
   De AEM valideert uw gegevens van Google Sheet door uw segment als groen te tonen.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Op dezelfde manier geef de bezitswaarden aan **TargetValue2** uit.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer **Operator** als **Gelijk** van het drop-down menu.

   1. Voer de **waarde** in als **2**.



## Stap 5: Merk en gebied instellen {#setting-brand-area}

Volg de onderstaande stappen om een merk te maken in uw activiteiten en gebied onder het merk:

1. **Een merk in activiteiten maken**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Activiteiten**.

   1. Klik op **Maken** > Merk **maken**.

   1. Selecteer **Merk** in de wizard **Pagina** maken en klik op **Volgende**.

   1. Voer de **titel** in als **ScreensBrand** en klik op **Maken**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.

      ![image](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      Bekend probleem:
Als u een gebied wilt toevoegen, verwijdert u het stramien uit de URL, bijvoorbeeld
      `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Een gebied in uw merk maken**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Klik op **Maken** en vervolgens **Gebied** maken.

      ![image](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Selecteer **Gebied** in de wizard **Pagina** maken en klik op **Volgende**.

   1. Voer de **titel** in als **ScreensValue** en klik op **Maken**.
Er wordt een gebied in uw merk gemaakt.

## Stap 6: De activiteit instellen {#step-setting-up-activity}

Ga als volgt te werk om een gebied in het merk te maken:

1. Navigeer naar **ScreensValue** (gemaakt in de vorige stap) en klik op **Maken** > **Activiteit** maken.

1. De wizard **Activiteit** configureren wordt geopend. Voer de **titel** in als **controle** van de doelwaarde en **Naam** als controle van de **doelwaarde**. Selecteer de **Doelmotor** als **ContextHub (AEM)** van drop-down en klik **daarna**.

1. Klik **Add Ervaring** van de Tovenaar **van de Activiteit** vormen.

1. Van het **publiek**, selecteer **TargetValue1** en klik **voeg Ervaring** toe en ga de **titel** als **waardecontrole** **** **** Name asvaluecheck in.

1. Op dezelfde manier, van het **publiek**, selecteer **TargetValue2** en klik **voeg Ervaring** toe en ga de **titel** als **valuecheck** **** **** Name asvaluecheck2 in.

1. Klik op **Volgende** en **Opslaan**.

## Het richten in Kanalen toelaten {#step-enabling-targeting-in-channels}

Voer de onderstaande stappen uit om het activeren van uw doelbestanden in te schakelen.

1. Navigeer naar een van de kanalen voor AEM-schermen. De volgende stappen tonen aan hoe te om het richten toe te laten door **DataDrivenRetail** te gebruiken die in een Kanaal van de Schermen AEM wordt gecreeerd.

1. Selecteer het kanaal **DataDrivenRetail** en klik op **Eigenschappen** op de actiebalk.

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Selecteer het lusje van de **Personalisatie** aan opstelling de configuraties ContextHub.

   1. Selecteer het **ContextHub-pad** als **bibliotheken** > **instellingen** > **cloudinstellingen** > **standaard** **** ****> ContextHub Configurations en klik opSelect.

   1. Selecteer het **Segmentpad** als **conf** > **Wij.Detailhandel** > **instellingen** > **wcm** **** ****> segments en klik op Select.

   1. Klik op **Opslaan en sluiten**.
   >[!NOTE]
   Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigeer en selecteer **DataDrivenRetail** van **DataDrivenAssets** > **Kanalen** en klik **uitgeven** van de actiebar.

   >[!NOTE]
   Als u opstelling alles correct hebt, zult u het **richten** optie in drop-down van de redacteur zien, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   Zodra u de configuraties ContextHub voor uw kanaal hebt gevormd, zorg ervoor u voorafgaande stappen van 1 door 4 volgt, voor de andere drie opeenvolgingskanalen te als u alle hieronder gebruiksgevallen wilt volgen.

## Meer informatie: Voorbeelden {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van het Scherm AEM hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
