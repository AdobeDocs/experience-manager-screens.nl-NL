---
title: ContextHub configureren in AEM Screens
seo-title: ContextHub configureren in AEM Screens
description: Volg deze pagina om over ContextHub in de het richten motor te leren om gegevensopslag voor het doel van de verandering van de de inhoudsloopvraag van gegevens te bepalen.
seo-description: Volg deze pagina om over ContextHub in de het richten motor te leren om gegevensopslag voor het doel van de verandering van de de inhoudsloopvraag van gegevens te bepalen.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65
feature: Schermen ontwikkelen
role: Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 1%

---


# ContextHub configureren in AEM Screens {#configuring-contexthub-in-aem-screens}

In deze sectie wordt de nadruk gelegd op het maken en beheren van gegevensgestuurde wijzigingen in elementen met behulp van een gegevensopslag.

## Belangrijke termen {#key-terms}

Voordat we de details van het maken en beheren van voorraadgestuurde kanalen in uw AEM Screens-project kunnen bekijken, moet u weinig van de belangrijkste termen leren die belangrijk en relevant zijn voor de verschillende scenario&#39;s.

**** MerkVerwijst naar uw projectbeschrijving op hoog niveau.

**** AreaVerwijst naar de naam van uw AEM Screens-project, zoals Digital Ad Signage

**** ActivityDefinieert de regelcategorie zoals Inventory-Gedreven, Weather-Gedreven, Afdeling Beschikbaarheid-Gedreven, etc.

**** PubliekDefinieert de regel.

**** SegmentVerwijst naar de versie van het element die voor de gegeven regel moet worden afgespeeld, bijvoorbeeld als de temperatuur lager is dan 50 graden frenheit, dan toont het scherm een beeld van een warme koffie anders een koude drank.

Het volgende diagram verstrekt een visuele vertegenwoordiging van hoe de Configuraties ContextHub met Activiteit, Publiek, en Kanalen samenvallen.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Voorwaarden {#preconditions}

Voordat u de Configuratie van de Hub van de Context voor een project van AEM Screens begint te vormen, moet u opstelling Google Bladen (voor demonstratiedoeleinden).

>[!IMPORTANT]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt als een voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is uitsluitend voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Raadpleeg [API-sleutel ophalen](https://developers.google.com/maps/documentation/javascript/get-api-key) in Google-documentatie voor meer informatie.

## Stap 1: Een gegevensarchief {#step-setting-up-a-data-store} instellen

U kunt de gegevensopslag instellen als een lokale I/O-gebeurtenis of als een lokale databasegebeurtenis.

De volgende gegevens van het activaniveau brengen voorbeeld teweeg toont een lokale gegevensbestandgebeurtenis die opstelling een gegevensopslag zoals een Excel blad dat u toestaat om configuraties ContextHub en segmentweg aan het kanaal van AEM Screens te gebruiken.

Nadat u het Google-blad correct hebt ingesteld, bijvoorbeeld zoals hieronder wordt getoond:

![afbeelding](/help/user-guide/assets/context-hub/context-hub1.png)

De volgende validatie wordt weergegeven wanneer u de verbinding controleert door de twee waarden *google sheet ID* en *API key* in de onderstaande notatie in te voeren:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![afbeelding](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>In het onderstaande specifieke voorbeeld worden de Google-werkbladen weergegeven als een gegevensopslagruimte die een wijziging van het element veroorzaakt wanneer de waarde hoger is dan 100 of lager dan 50.

## Stap 2: Opslagconfiguraties instellen {#step-setting-store-configurations}

1. **Navigeren naar ContextHub**

   Navigeer naar de AEM en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klik **Sites** —> **ContextHub**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Het creëren van een nieuwe Configuratie van de Opslag ContextHub**

   1. Navigeer naar de configuratiecontainer met de naam **screens**.

   1. Klik **Create** > **Create de Container van de Configuratie** en ga de titel als **ContextHubDemo** in.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **** Navigeer aan  **ContextHubDemo** >  **** **CreateContentHub** Configuratie en klik  **sparen**.

      >[!NOTE]
      > Nadat u **sparen** klikt zult u in het **scherm ContextHub Configuration** zijn.

   1. Van het **scherm van de Configuratie ContextHub**, klik **Create** > **Configuratie van de Opslag ContentHub..**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub5.png)

      >[!CAUTION]
      >
      >Als onderdeel van AEM 6.5 Feature Pack 4 of AEM 6.4 Feature Pack 8, dienen klanten `/conf/screens/settings/cloudsettings` bij te werken naar `sling:Folder`.
      >
      >Voer de onderstaande stappen uit:
      >
      >1. Navigeer naar CRXDE Lite en vervolgens naar `/conf/screens/settings/cloudsettings`.
      >1. Controleer of `cloudsettings jcr:primaryType` zich in `sling:Folder` bevindt. Als `jcr:primaryType` niet in `sling:folder` is, ga aan de volgende stappen te werk.
      >1. Klik met de rechtermuisknop op `/conf/screens/settings` en maak een nieuw knooppunt met *name* als **cloudsettings1** en *Type* als **sling:Folder** en sla de wijzigingen op.
      >1. Verplaats alle knooppunten onder `/conf/screens/settings/cloudsettings` naar `cloudsettings1`.
      >1. `cloudsettings` verwijderen en opslaan.
      >1. Wijzig de naam `cloudsettings1` in `cloudsettings` en sla op.
      >1. U zou nu moeten merken dat /conf/screens/settings/cloudsettings `jcr:primaryType` als `sling:Folder` heeft.

      >
      >Volg deze stappen in auteur en publiceer voor of na de verbetering.

   1. Voer **Title** in als **Google Sheets**, **Store Name** als **googlesheets** en **Store Type** als **contexthub.generic-jsonp** en klik a12/>Volgende **.**

      >[!CAUTION]
      >Als u Adobe Experience Manager (AEM) 6.4 gebruikt, ga **Titel** als **googlesheets** en **Type** als **contexthub.generic-jsonp** in.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Voer uw specifieke json-configuratie in. Bijvoorbeeld, kunt u de volgende json voor demodoeleinden gebruiken en **sparen** klikken en u zult de opslagconfiguratie zien die als **Google Sheets** in configuratie ContextHub wordt genoemd.

      >[!IMPORTANT]
      >Vervang de code door de *&lt;Sheet ID>* en *&lt;API Key>*, die u hebt opgehaald tijdens het instellen van de Google Sheets.

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
      Vervang de code door de *&lt;Sheet ID>* en *&lt;API Key>*, die u hebt opgehaald tijdens het instellen van de Google Sheets.

      >[!CAUTION]
      Als u uw Google Sheets-opslagconfiguraties buiten de algemene map maakt (bijvoorbeeld in uw eigen projectmap), werkt het aanwijzen van doelen niet uit de doos.


1. **Opslagsegmentatie instellen**

   1. Navigeer aan **Configuratie van de Opslag ContentHub..** en maak een andere archiefconfiguratie in de container van de het schermconfiguratie en plaats  **** Titleas  **segmentation-contexthub**,  **sla** Naam als  **** segmentatie op en  **sla** Typeas  **aem.segmentation** op.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klik **Volgende** en dan **sparen**.

      >[!NOTE]
U moet het proces van het bepalen van de json overslaan en het als leeg verlaten.


## Stap 3: Segmenten instellen in publiek {#setting-up-audience}

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw AEM instantie aan **Personalisatie** > **Soorten publiek** > **screens**.

   1. Klik **Create** > **Create het Segment van de Hub van de Context.** Het  **Nieuwe** de dialoogvakje van het Segmenteren ContextHub opent.

   1. Voer **Title** in als **Higherthan50** en klik **Create**. Maak op dezelfde manier een ander segment met de naam **Lowerthan50**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Selecteer het segment **Higherthan50** en klik **Eigenschappen** van de actiebar.
      ![afbeelding](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Selecteer het **tabblad Personalisatie** in het **Segmenteigenschappen**. Plaats **ContextHub Weg** aan `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` en **De Weg van Segmenten** aan `/conf/screens/settings/wcm/segments` en klik **sparen**, zoals aangetoond in het hieronder cijfer.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Op dezelfde manier plaats **ContextHub Weg** en **De Weg van Segmenten** voor **Lowerthan50** ook segment.

## Stap 4: Merk en gebied instellen {#setting-brand-area}

Volg de onderstaande stappen om een merk te maken in uw activiteiten en gebied onder het merk:

1. **Een merk in activiteiten maken**

   1. Navigeer van uw AEM instantie aan **Personalisatie** > **Activiteiten**.

   1. Klik **Maken** > **Merk maken**.

   1. Selecteer **Merk** van **Create Pagina** tovenaar en klik **Next**.

   1. Typ de **Titel** als **ScreensBrand** en klik **Create**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      Bekend probleem:
Als u een gebied wilt toevoegen, verwijdert u het master item uit de URL, zoals
      `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Een gebied in uw merk maken**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Klik **Create** en **Create Area**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Selecteer **Gebied** in de wizard **Pagina maken** en klik op **Volgende**.

   1. Voer de **Titel** in als **ScreensValue** en klik op **Create**.
Er wordt een gebied in uw merk gemaakt.

## Stap 5: Segmenten maken in een activiteit {#step-setting-up-audience-segmentation}

Nadat u een gegevensopslag hebt ingesteld en uw activiteiten (merk en gebied) hebt gedefinieerd, volgt u onderstaande stappen om segmenten in uw activiteit te maken.

1. **Segmenten maken in activiteiten**

   1. Navigeer van uw AEM instantie aan **Personalisatie** > **Activiteiten** > **ScreensMerk** >**ScreensValue**.

   1. Klik **Maken** > **Activiteit maken.** De  **Configure** tovenaars van de Activiteit.

   1. Voer **Title** in als **ValueCheck50** en **Name** als **valuecheck50**. Selecteer **Richtend motor** als **ContextHub (AEM)** van drop-down en klik **Volgende**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Klik **Voeg Ervaring** van **Vorm Tovenaar van de Activiteit** toe.

   1. Selecteer **Soorten publiek** **Higherthan50** en klik **Ervaring toevoegen** en voer **Titel** in als **higherthan50** **Naam** als **hoger dan50**. Klik **Ok**.

   1. Selecteer **Soorten publiek** **Kleiner dan50** en klik **Ervaring toevoegen** en voer **Titel** in als **lager dan50** **Naam** als a12/>lager dan50 **.** Klik **Ok**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Klik **Volgende** en dan **sparen**. **ValueCheck50** activity wordt nu gemaakt en geconfigureerd.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub16.png)

## Stap 5: Segmenten bewerken in soorten publiek{#editing-audience-segmentation}

1. **Segmenten bewerken**

   1. Navigeer van uw AEM instantie aan **Personalisatie** > **Soorten publiek** > **screens**.

   1. Selecteer het segment **Higherthan50**, en klik **Edit** van de actiebar.

   1. Sleep de **vergelijking: Eigenschap - Waarde** component aan de redacteur.

   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met waarde** te openen.

   1. Selecteer **googlesheets/value/1/0** in de vervolgkeuzelijst in **Eigenschapnaam**.

      >[!NOTE]
De  **ganzen/waarde/1/0** verwijst naar rij 2 en kolom zoals ingevuld in de google-vellen in de onderstaande afbeelding:

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Selecteer **Operator** als **groter-dan** van het drop-down menu.

   1. Voer de **Waarde** in als **70**.

      >[!NOTE]
      De AEM valideert uw gegevens vanaf Google Sheet door uw segment als groen weer te geven.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub18.png)
   Bewerk op dezelfde manier de eigenschapswaarden in **Lowerthan50**.

   1. Sleep de **vergelijking: Eigenschap - Waarde** component aan de redacteur.

   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met waarde** te openen.

   1. Selecteer **googlesheets/value/1/0** in de vervolgkeuzelijst in **Eigenschapnaam**.

   1. Selecteer **Operator** als **kleiner-dan** van het drop-down menu.

   1. Voer de **Waarde** in als **50**.



## Het toelaten van het richten in Kanalen {#step-enabling-targeting-in-channels}

Voer de onderstaande stappen uit om het activeren van uw doelbestanden in te schakelen.

1. Navigeer naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door **DataDrivenChannel** te gebruiken die in een Kanaal van AEM Screens wordt gecreeerd.

1. Selecteer het kanaal **TargetChannel** en klik **Eigenschappen** van de actiebar.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub19.png)

1. Selecteer **Personalization** lusje om de configuraties te plaatsen ContextHub.

   1. Stel het **ContextHub-pad** in op `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` en **Segmentpad** op `/conf/screens/settings/wcm/segments` en klik op **Opslaan**.

   1. Klik **Opslaan en sluiten**.

      >[!NOTE]
      Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub20.png)

   1. Navigeer en selecteer **TargetChannel** kanaal en klik **Edit** van de actiebar.

      >[!NOTE]
      Als u opstelling alles correct hebt geplaatst, zult u **het richten** optie in drop-down van de redacteur zien, zoals aangetoond in het hieronder cijfer.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub21.png)

## Meer informatie: Voorbeeld van gebruik van gevallen {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
