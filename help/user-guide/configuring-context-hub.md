---
title: ContextHub configureren in AEM Screens
seo-title: Configuring ContextHub in AEM Screens
description: Volg deze pagina om over ContextHub in de het richten motor te leren om gegevensopslag voor het doel van de verandering van de de inhoudsloopvraag van gegevens te bepalen.
seo-description: Follow this page to learn about ContextHub in the targeting engine to define data store for the purpose of data trigger content change.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
source-git-commit: 93e9514ebd25a4d84076174c4d90a0325b167393
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 1%

---

# ContextHub configureren in AEM Screens {#configuring-contexthub-in-aem-screens}

In deze sectie wordt de nadruk gelegd op het maken en beheren van gegevensgestuurde wijzigingen in elementen met behulp van een gegevensopslagruimte.

## Belangrijkste voorwaarden {#key-terms}

Voordat we de details van het maken en beheren van voorraadgestuurde kanalen in uw AEM Screens-project kunnen bekijken, moet u weinig van de belangrijkste termen leren die belangrijk en relevant zijn voor de verschillende scenario&#39;s.

**Merk** Raadpleeg de beschrijving van uw project op hoog niveau.

**Gebied** Verwijst naar uw AEM Screens-projectnaam, zoals Digital Ad Signage

**Activiteit** Bepaalt de regelcategorie zoals Inventory-Gedreven, Weer-Gedreven, Afdeling Beschikbaarheid-Gedreven, etc.

**Publiek** Definieert de regel.

**Segment** Verwijst naar de versie van het element die voor de gegeven regel moet worden afgespeeld, bijvoorbeeld als de temperatuur lager is dan 50 graden frenheit, dan toont het scherm een beeld van een warme koffie anders een koude drank.

Het volgende diagram verstrekt een visuele vertegenwoordiging van hoe de Configuraties ContextHub met Activiteit, Publiek, en Kanalen samenvallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voorwaarden {#preconditions}

Alvorens u begint de Configuraties van de Hub van de Context voor een project van AEM Screens te vormen, moet u opstelling Google Bladen (voor demonstratiedoeleinden).

>[!IMPORTANT]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt als een voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is alleen voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Raadpleeg voor meer informatie [API-sleutel ophalen](https://developers.google.com/maps/documentation/javascript/get-api-key) in Google documentatie.

## Stap 1: Een Data Store instellen {#step-setting-up-a-data-store}

U kunt de gegevensopslag instellen als een lokale I/O-gebeurtenis of als een lokale databasegebeurtenis.

De volgende gegevens van het activaniveau brengen voorbeeld teweeg toont een lokale gegevensbestandgebeurtenis die opstelling een gegevensopslag zoals een Excel blad dat u toestaat om configuraties ContextHub en segmentweg aan het kanaal van AEM Screens te gebruiken.

Nadat u het Google-blad correct hebt ingesteld, bijvoorbeeld zoals hieronder wordt getoond:

![afbeelding](/help/user-guide/assets/context-hub/context-hub1.png)

De volgende validatie wordt weergegeven wanneer u de verbinding controleert door de twee waarden in te voeren. *google sheet ID* en *API-sleutel* in onderstaande notatie:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![afbeelding](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>In het onderstaande specifieke voorbeeld worden de Google-werkbladen weergegeven als een gegevensopslagruimte die een wijziging van het element veroorzaakt wanneer de waarde hoger is dan 100 of lager dan 50.

## Stap 2: Opslagconfiguraties instellen {#step-setting-store-configurations}

1. **Navigeren naar ContextHub**

   Navigeer naar de AEM en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klikken **Sites** —> **ContextHub**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Het creëren van een nieuwe Configuratie van de Opslag ContextHub**

   1. Navigeer naar de configuratiecontainer met de naam **schermen**.

   1. Klikken **Maken** > **Configuratiecontainer maken** en voer de titel in als **ContextHubDemo**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **Navigeren** tot **ContextHubDemo** > **Maken** **ContentHub-configuratie** en klik op **Opslaan**.

      >[!NOTE]
      > Nadat u op **Opslaan** u zult in **ContextHub-configuratie** scherm.

   1. Van de **ContextHub-configuratie** scherm, klikken **Maken** > **Configuratie ContentHub Store..**

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub5.png)

      >[!CAUTION]
      >
      >Als onderdeel van AEM 6.5 Feature Pack 4 of AEM 6.4 Feature Pack 8, dienen klanten een update uit te voeren `/conf/screens/settings/cloudsettings` tot `sling:Folder`.
      >
      >Voer de onderstaande stappen uit:
      >
      >1. Navigeer naar CRXDE Lite en vervolgens naar `/conf/screens/settings/cloudsettings`.
      >1. Controleren of `cloudsettings jcr:primaryType` bevindt zich in `sling:Folder`. Als de `jcr:primaryType` is niet in `sling:folder`, gaat u door met de volgende stappen.
      >1. Rechtsklik ingeschakeld `/conf/screens/settings` en maak een nieuw knooppunt met *name*  als **cloudsettings1** en *Type* als **sling:map** en sla de wijzigingen op.
      >1. Alle knooppunten onder verplaatsen `/conf/screens/settings/cloudsettings` tot `cloudsettings1`.
      >1. Verwijderen `cloudsettings` en opslaan.
      >1. Naam wijzigen `cloudsettings1` tot `cloudsettings` en opslaan.
      >1. U moet nu controleren of /conf/screens/settings/cloudsettings `jcr:primaryType` als `sling:Folder`.
      >
      >Volg deze stappen in auteur en publiceer voor of na de verbetering.

   1. Voer de **Titel** als **Google Sheets**, **Winkelnaam** als **goochelheets**, en **Winkeltype** als **contexthub.generic-jsonp** en klik op **Volgende**.

      >[!CAUTION]
      >Als u Adobe Experience Manager (AEM) 6.4 gebruikt, voert u de **Configuratietitel** als **goochelheets** en de **Winkeltype** als **contexthub.generic-jsonp**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Voer uw specifieke json-configuratie in. U kunt bijvoorbeeld de volgende json gebruiken voor demo-doeleinden en op **Opslaan** en u zult de opslagconfiguratie zien genoemd zoals **Google Sheets** in ContextHub-configuratie.

      >[!IMPORTANT]
      >Zorg ervoor dat u de code vervangt door uw *&lt;sheet id=&quot;&quot;>* en *&lt;api key=&quot;&quot;>*, die je hebt opgehaald tijdens het instellen van de Google Sheets.

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
      >
      In de bovenstaande voorbeeldcode: **pollInterval** definieert de frequentie waarmee de waarden worden vernieuwd (in ms).
      >
      Vervang de code door uw *&lt;sheet id=&quot;&quot;>* en *&lt;api key=&quot;&quot;>*, die je hebt opgehaald tijdens het instellen van de Google Sheets.

      >[!CAUTION]
      >
      Als u uw Google Sheets maakt, slaat u configuraties buiten de algemene map op (bijvoorbeeld in uw eigen projectmap), dan werkt het aanwijzen van doelen niet uit het vak.

1. **Opslagsegmentatie instellen**

   1. Navigeren naar **Configuratie ContentHub Store..** en maak een andere opslagconfiguratie in de container van de schermconfiguratie en stel de **Titel** als **segmentatie-contexthub**, **Winkelnaam** als **segmentatie** en **Winkeltype** als **aem.segmentation**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klikken **Volgende** en vervolgens **Opslaan**.

      >[!NOTE]
U moet het proces van het bepalen van de json overslaan en het als leeg verlaten.


## Stap 3: Segmenten voor het publiek instellen {#setting-up-audience}

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw AEM naar **Personalisatie** > **Soorten publiek** > **schermen**.

   1. Klikken **Maken** > **Maak een Context Hub Segment.** De **Nieuw ContextHub-segment** wordt geopend.

   1. Voer de **Titel** als **Higherthan50** en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam **Lager dan50**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Selecteer het segment **Higherthan50** en klik op **Eigenschappen** in de actiebalk.
      ![afbeelding](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Selecteer de **Personalisatie** van de **Segmenteigenschappen**. Stel de **ContextHub-pad** tot `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` en **Segmentpad** tot `/conf/screens/settings/wcm/segments` en klik op **Opslaan**, zoals weergegeven in onderstaande afbeelding.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Stel op dezelfde manier de **ContextHub-pad** en **Segmentpad** for **Lager dan50** ook segment.

## Stap 4: Opzetten van merk en gebied {#setting-brand-area}

Volg de onderstaande stappen om een merk te maken in uw activiteiten en gebied onder het merk:

1. **Een merk in activiteiten maken**

   1. Navigeer van uw AEM naar **Personalisatie** > **Activiteiten**.

   1. Klikken **Maken** > **Merk maken**.

   1. Selecteren **Merk** van de **Pagina maken** wizard en klik op **Volgende**.

   1. Voer de **Titel** als **SchermenMerk** en klik op **Maken**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      >
      Bekend probleem: als u een gebied wilt toevoegen, verwijdert u het stramien uit de URL, bijvoorbeeld
      `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Een gebied in uw merk maken**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Klikken **Maken** en vervolgens **Gebied maken**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Selecteren **Gebied** van de **Pagina maken** wizard en klik op **Volgende**.

   1. Voer de **Titel** als **ScreensValue** en klik op **Maken**.
Er wordt een gebied in uw merk gemaakt.

## Stap 5: De segmenten in een activiteit maken {#step-setting-up-audience-segmentation}

Nadat u een gegevensopslag hebt ingesteld en uw activiteiten (merk en gebied) hebt gedefinieerd, volgt u onderstaande stappen om segmenten in uw activiteit te maken.

1. **Segmenten maken in activiteiten**

   1. Navigeer van uw AEM naar **Personalisatie** > **Activiteiten** > **SchermenMerk** >**ScreensValue**.

   1. Klikken **Maken** > **Activiteit maken.** De **Wizard Activiteiten configureren** wordt geopend.

   1. Voer de **Titel** als **ValueCheck50** en **Naam** als **taxecheck50**. Selecteer de **Richtingsmotor** als **ContextHub (AEM)** in de vervolgkeuzelijst en klik op **Volgende**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Klikken **Ervaring toevoegen** van de **Wizard Activiteiten configureren**.

   1. Van de **Soorten publiek**, selecteert u de **Higherthan50** en klik op **Ervaring toevoegen** en voert u de **Titel** als **hoger dan50** **Naam** als **hoger dan50**. Klikken **OK**.

   1. Van de **Soorten publiek**, selecteert u de **Lager dan50** en klik op **Ervaring toevoegen** en voert u de **Titel** als **lager dan50** **Naam** als **lager dan50**. Klikken **OK**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Klikken **Volgende** en vervolgens **Opslaan**. **ValueCheck50** activiteit wordt nu gecreeerd en gevormd.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub16.png)

## Stap 5: De segmenten in soorten publiek bewerken{#editing-audience-segmentation}

1. **Segmenten bewerken**

   1. Navigeer van uw AEM naar **Personalisatie** > **Soorten publiek** > **schermen**.

   1. Selecteer het segment **Higherthan50** en klik op **Bewerken** in de actiebalk.

   1. Sleep de **Vergelijking: eigenschap - waarde** aan de redacteur.

   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap met een waarde vergelijken** in.

   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**.

      >[!NOTE]
De **goochelesheets/value/1/0** verwijst naar rij 2 en kolom zoals deze in de google-vellen in de onderstaande afbeelding zijn ingevuld:

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu.

   1. Voer de **Waarde** als **70**.

      >[!NOTE]
      >
      De AEM valideert uw gegevens van het Blad van Google door uw segment als groen te tonen.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub18.png)

   Op dezelfde manier kunt u de eigenschapswaarden bewerken tot **Lager dan50**.

   1. Sleep de **Vergelijking: eigenschap - waarde** aan de redacteur.

   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap met een waarde vergelijken** in.

   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**.

   1. Selecteer de **Operator** als **kleiner dan** in het keuzemenu.

   1. Voer de **Waarde** als **50**.


## Het richten in Kanalen toelaten {#step-enabling-targeting-in-channels}

Voer de onderstaande stappen uit om het activeren van doelwitbestanden in uw kanalen in te schakelen.

1. Ga naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door te gebruiken **DataDrivenChannel** gemaakt in een AEM Screens Channel.

1. Selecteer het kanaal **TargetChannel** en klik op **Eigenschappen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub19.png)

1. Selecteer de **Personalisatie** lusje aan opstelling de configuraties ContextHub.

   1. Stel de **ContextHub-pad** tot `/conf/screens/settings/wcm/segments` en **Segmentpad** tot `/conf/screens/settings/wcm/segments`.
   1. Merk instellen op **SchermenMerk** uit de vervolgkeuzelijst en **Verwijzing gebied instellen** tot **ScreensValue**.

   1. Klikken **Opslaan en sluiten**.

      >[!NOTE]
      >
      Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigeer en selecteer de **TargetChannel** kanaal en klik **Bewerken** in de actiebalk.

      >[!NOTE]
      >
      Als u alles correct hebt ingesteld, ziet u **Targeting** in de drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub21.png)

## Meer informatie: voorbeelden gebruiken {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
