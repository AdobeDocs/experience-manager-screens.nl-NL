---
title: ContextHub configureren in AEM Screens
description: Leer over ContextHub in het richten motor zodat kunt u gegevensopslag voor de inhoudsverandering van de gegevenstrekker bepalen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
source-git-commit: 2b865165793b1c0f90f1351518e41096a57ea2ff
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 1%

---

# ContextHub configureren in AEM Screens {#configuring-contexthub-in-aem-screens}

In deze sectie wordt de nadruk gelegd op het maken en beheren van gegevensgestuurde wijzigingen in elementen met behulp van een gegevensopslag.

## Belangrijkste voorwaarden {#key-terms}

Voordat u de details van het maken en beheren van voorraadgestuurde kanalen in uw AEM Screens-project kunt bekijken, moet u enkele belangrijke termen leren voor de verschillende scenario&#39;s.

**Merk** - Uw projectomschrijving op hoog niveau.

**Gebied** - Uw AEM Screens-projectnaam, zoals Digital Ad Signage

**Activiteit** - Definieert de categorieregels zoals inventariseren-Gedreven, Weer-Gedreven, of Departement Beschikbaarheid-Gedreven.

**Publiek** - Definieert de regel.

**Segment** - De versie van het element dat voor de opgegeven regel moet worden afgespeeld. Als de temperatuur bijvoorbeeld lager is dan 50 graden Fahrenheit, wordt op het scherm een afbeelding van een warme drank weergegeven, anders een koude drank.

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

De volgende gegevens van het activaniveau brengen voorbeeld teweeg toont een lokale gegevensbestandgebeurtenis die opstelling een gegevensopslag zoals een Excel blad dat u configuraties ContextHub en segmentweg aan het kanaal van AEM Screens laat gebruiken.

Nadat u de `google` correct blad, zoals in het onderstaande voorbeeld wordt getoond:

![afbeelding](/help/user-guide/assets/context-hub/context-hub1.png)

De volgende validatie wordt weergegeven wanneer u de verbinding controleert door de twee waarden in te voeren. `*google sheet ID*` en `*API key*` in onderstaande notatie:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![afbeelding](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>In het onderstaande specifieke voorbeeld worden de Google-werkbladen weergegeven als een gegevensopslagruimte die een wijziging van het element activeert wanneer de waarde hoger is dan 100 of lager dan 50.

## Stap 2: Opslagconfiguraties instellen {#step-setting-store-configurations}

1. **Navigeren naar ContextHub**

   Navigeer naar de AEM en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klikken **Sites** > **ContextHub**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Een ContextHub Store-configuratie maken**

   1. Navigeer naar de configuratiecontainer met de naam **schermen**.

   1. Selecteren **Maken** > **Configuratiecontainer maken** en voer de titel in als **ContextHubDemo**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **Navigeren** tot **ContextHubDemo** > **Maken** **ContentHub-configuratie** en klik op **Opslaan**.

      >[!NOTE]
      > Nadat u **Opslaan**, u bevindt zich in de **ContextHub-configuratie** scherm.

   1. Van de **ContextHub-configuratie** scherm, selecteren **Maken** > **Configuratie van ContentHub Store**

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub5.png)

   >[!CAUTION]
   >
   >Als onderdeel van AEM 6.5 Feature Pack 4 of AEM 6.4 Feature Pack 8, dienen klanten een update uit te voeren `/conf/screens/settings/cloudsettings` tot `sling:Folder`.
   >
   >Voer de onderstaande stappen uit:
   >
   >1. Navigeer naar CRXDE Lite en vervolgens naar `/conf/screens/settings/cloudsettings`.
   >1. Controleren of `cloudsettings jcr:primaryType` bevindt zich in `sling:Folder`. Als de `jcr:primaryType` is niet in `sling:folder`, gaat u door met de volgende stappen.
   >1. Klikken met rechtermuisknop `/conf/screens/settings` en maak een knooppunt met *name* als **cloudsettings1** en *Type* als **sling:map** en sla de wijzigingen op.
   >1. Alle knooppunten onder verplaatsen `/conf/screens/settings/cloudsettings` tot `cloudsettings1`.
   >1. Verwijderen `cloudsettings` en opslaan.
   >1. Naam wijzigen `cloudsettings1` tot `cloudsettings` en opslaan.
   >1. Waarnemen dat `/conf/screens/settings/cloudsettings` heeft `jcr:primaryType` als `sling:Folder`.
   >
   >Voer de volgende stappen uit in Auteur en Publiceren voor of na de upgrade.

   1. Voer de **Titel** als **Google Sheets**, **Winkelnaam** als **goochelheets**, en **Winkeltype** als **contexthub.generic-jsonp** en klik op **Volgende**.

      >[!CAUTION]
      >Als u Adobe Experience Manager (AEM) 6.4 gebruikt, voert u de **Configuratietitel** als **goochelheets** en de **Winkeltype** als **contexthub.generic-jsonp**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Voer uw specifieke json-configuratie in. U kunt bijvoorbeeld de volgende json gebruiken voor demo-doeleinden en **Opslaan**. U ziet de opslagconfiguratie met de naam **Google Sheets** in ContextHub-configuratie.

      >[!IMPORTANT]
      >Zorg ervoor dat u de code vervangt door uw `*<Sheet ID>*` en `*<API Key>*`, die je hebt opgehaald tijdens het instellen van de Google Sheets.

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
      >In de bovenstaande voorbeeldcode: **pollInterval** definieert de frequentie waarmee de waarden worden vernieuwd (in milliseconden).
      >
      >Vervang de code door uw `*<Sheet ID>*` en `*<API Key>*`, die je hebt opgehaald tijdens het instellen van de Google Sheets.

      >[!CAUTION]
      >
      >Als u uw Google Sheets maakt, slaat u configuraties buiten de algemene map op (bijvoorbeeld in uw eigen projectmap), dan werkt het instellen van een doel niet uit de verpakking.

1. **Opslagsegmentatie instellen**

   1. Navigeren naar **Configuratie van ContentHub Store** en maak een andere opslagconfiguratie in de AEM Screens-configuratiecontainer en stel de **Titel** als **segmentatie-contexthub**, **Winkelnaam** als **segmentatie** en **Winkeltype** als **aem.segmentation**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klikken **Volgende** en vervolgens **Opslaan**.

      >[!NOTE]
      >Sla het proces waarbij de zoon wordt gedefinieerd over en laat deze leeg.


## Stap 3: Segmenten voor het publiek instellen {#setting-up-audience}

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw AEM naar **Personalisatie** > **Soorten publiek** > **schermen**.

   1. Klikken **Maken** > **Maak een Context Hub Segment.** De **Nieuw ContextHub-segment** wordt geopend.

   1. Voer de **Titel** als `**Higherthan50**` en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam `**Lowerthan50**`.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Selecteer het segment `**Higherthan50**` en klik op **Eigenschappen** in de actiebalk.
      ![afbeelding](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Selecteer de **Personalisatie** van de **Segmenteigenschappen**. Stel de **ContextHub-pad** tot `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` en **Segmentpad** tot `/conf/screens/settings/wcm/segments` en klik op **Opslaan**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Stel op dezelfde manier de **ContextHub-pad** en **Segmentpad** for `**Lowerthan50**` ook segment.

## Stap 4: Opzetten van merk en gebied {#setting-brand-area}

Volg de onderstaande stappen om een merk te maken in uw activiteiten en gebieden onder het merk:

1. **Een merk in activiteiten maken**

   1. Navigeer van uw AEM naar **Personalisatie** > **Activiteiten**.

   1. Selecteren **Maken** > **Merk maken**.

   1. Selecteren **Merk** van de **Pagina maken** wizard en klik op **Volgende**.

   1. Voer de **Titel** als **SchermenMerk** en klik op **Maken**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      >
      >Bekend probleem:
      >Als u een gebied wilt toevoegen, verwijdert u de primaire URL, bijvoorbeeld
      >`http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Een gebied in uw merk maken**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Selecteren **Maken** en vervolgens **Gebied maken**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Selecteren **Gebied** van de **Pagina maken** wizard en selecteert u **Volgende**.

   1. Voer de **Titel** als **ScreensValue** en selecteert u **Maken**.
Er wordt een gebied gemaakt in uw merk.

## Stap 5: De segmenten in een activiteit maken {#step-setting-up-audience-segmentation}

Nadat u een gegevensopslag hebt ingesteld en uw activiteit (merk en gebied) hebt gedefinieerd, volgt u onderstaande stappen om segmenten in uw activiteit te maken.

1. **Segmenten maken in activiteiten**

   1. Navigeer van uw AEM naar **Personalisatie** > **Activiteiten** > **SchermenMerk** >**ScreensValue**.

   1. Selecteren **Maken** > **Activiteit maken.** De **Wizard Activiteiten configureren** wordt geopend.

   1. Voer de **Titel** als **ValueCheck50** en **Naam** als **taxecheck50**. Selecteer de **Richtingsmotor** als **ContextHub (AEM)** in de vervolgkeuzelijst en selecteert u **Volgende**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Selecteren **Ervaring toevoegen** van de `**Configure Activity**` wizard.

   1. Van de **Soorten publiek**, selecteert u de `**Higherthan50**` en selecteert u **Ervaring toevoegen** en voert u de **Titel** als `**higherthan50**` **Naam** als `**higherthan50**`. Selecteren **OK**.

   1. Van de **Soorten publiek**, selecteert u de `**Lowerthan50**` en selecteert u **Ervaring toevoegen** en voert u de **Titel** als `**lowerthan50**` **Naam** als `**lowerthan50**`. Selecteren **OK**.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Selecteren **Volgende** en vervolgens **Opslaan**. `**ValueCheck50**` activiteit wordt nu gecreeerd en gevormd.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub16.png)

## Stap 5: De segmenten in soorten publiek bewerken{#editing-audience-segmentation}

1. **Segmenten bewerken**

   1. Navigeer van uw AEM naar **Personalisatie** > **Soorten publiek** > **schermen**.

   1. Selecteer het segment `**Higherthan50**`en selecteert u **Bewerken** in de actiebalk.

   1. Sleep de **Vergelijking: eigenschap - waarde** aan de redacteur.

   1. Klik op het moersleutelpictogram zodat u het dialoogvenster **Een eigenschap met een waarde vergelijken** in.

   1. Selecteren **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**.

      >[!NOTE]
      > De **goochelesheets/value/1/0** verwijst naar rij 2 en kolom zoals ingevuld in `google` vellen in onderstaande afbeelding:

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Selecteer de **Operator** als **groter dan** in het keuzemenu.

   1. Voer de **Waarde** als **70**.

      >[!NOTE]
      >
      >De AEM valideert uw gegevens van het Blad van Google door uw segment als groen te tonen.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub18.png)

   Op dezelfde manier kunt u de eigenschapswaarden bewerken tot `**Lowerthan50**`.

   1. Sleep de **Vergelijking: eigenschap - waarde** aan de redacteur.

   1. Selecteer het moersleutelpictogram.

   1. In de **Een eigenschap met een waarde vergelijken** dialoogvenster selecteert u **goochelesheets/value/1/0** in de vervolgkeuzelijst **Eigenschapnaam**.

   1. Selecteer de **Operator** als **kleiner dan** in het keuzemenu.

   1. Voer de **Waarde** als **50**.


## Het richten in Kanalen toelaten {#step-enabling-targeting-in-channels}

Voer de onderstaande stappen uit om het activeren van doelwitbestanden in uw kanalen in te schakelen.

1. Ga naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door te gebruiken **DataDrivenChannel** gemaakt in een AEM Screens Channel.

1. Selecteer het kanaal **TargetChannel** en klik op **Eigenschappen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub19.png)

1. Selecteer de **Personalisatie** lusje zodat kunt u opstelling de configuraties ContextHub.

   1. Stel de **ContextHub-pad** tot `/conf/screens/settings/wcm/segments` en **Segmentpad** tot `/conf/screens/settings/wcm/segments`.
   1. Merk instellen op **SchermenMerk** uit de vervolgkeuzelijst en **Verwijzing gebied instellen** tot **ScreensValue**.

   1. Klikken **Opslaan en sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigeer en selecteer de **TargetChannel** kanaal en klik **Bewerken** in de actiebalk.

      >[!NOTE]
      >
      >Als u alles correct hebt ingesteld, ziet u **Targeting** in de drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub21.png)

## Meer informatie: voorbeelden gebruiken {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Gerichte activering in de detailhandel](retail-inventory-activation.md)**
1. **[Temperatuuractivering in het midden van de reis](local-temperature-activation.md)**
1. **[Activering van ziekenhuisreservering](hospitality-reservation-activation.md)**
