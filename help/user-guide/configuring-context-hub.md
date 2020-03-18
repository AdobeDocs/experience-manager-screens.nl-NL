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
source-git-commit: 69dd2238562c00ab83e63e268515e24dee55f5ee

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

>[!CAUTION]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt als een voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is uitsluitend voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Raadpleeg de API-sleutel [](https://developers.google.com/maps/documentation/javascript/get-api-key) ophalen in de documentatie van Google voor meer informatie.

## Stap 1: Een gegevensopslag instellen {#step-setting-up-a-data-store}

U kunt de gegevensopslag instellen als een lokale I/O-gebeurtenis of als een lokale databasegebeurtenis.

### Lokale I/O-gebeurtenis {#local-io-event}

Volg de stappen hieronder aan opstelling een gegevensopslag zoals een gebeurtenis ASCII die u toestaat om configuraties ContextHub en segmentweg aan het kanaal van de Schermen van AEM te gebruiken.

### Lokale databasegebeurtenis {#local-db-event}

Volg de stappen hieronder aan opstelling een gegevensopslag zoals een Excel blad dat u toestaat om configuraties ContextHub en segmentweg aan het kanaal van de Schermen van AEM te gebruiken.

1. **Navigeren naar ContextHub**

   Navigeer naar de AEM-instantie en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klik **Plaatsen** -> **ContextHub**, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Het creëren van een nieuwe Configuratie van de Opslag ContextHub**

   1. Navigeer aan **globaal** > **gebrek** > Configuratie **** ContextHub.

   1. Klik **creëren** > de Container **van de** Configuratie en ga de titel als **ContextHubDemo** in.

   1. **Navigeer** aan **ContextHubDemo** > de Configuratie van de Opslag **ContentHub...** om de **Configure tovenaar** te openen.

   1. Voer de **titel** in als **Google Sheets**, **Winkelnaam** als **gumesheets** en **Winkeltype** **als ContextOffset.generic-jsonp**

   1. Click **Next**
   1. Voer uw specifieke json-configuratie in. U kunt bijvoorbeeld de volgende json gebruiken voor demodoeleinden.
   1. Click **Save**.

   ```
   {
     "service": {
       "host": "sheets.googleapis.com",
       "port": 80,
       "path": "/v4/spreadsheets/<your sheet it>/values/Sheet1",
       "jsonp": false,
       "secure": true,
       "params": {
         "key": "<your API key>"
       }
     },
     "pollInterval": 3000
   }
   ```

   >[!NOTE]
   >
   >In de bovenstaande voorbeeldcode definieert **pollInterval** de frequentie waarmee de waarden worden vernieuwd (in ms).
   >
   >
   >Vervang de code door uw *&lt;Sheet ID>* en *&lt;API Key>*, die u hebt opgehaald tijdens het instellen van de Google Sheets.

   >[!CAUTION]
   Als u uw Google Sheets-opslagconfiguraties maakt buiten de oude map (bijvoorbeeld in uw eigen projectmap), werkt het aanwijzen van doelen niet uit de doos.
   Als u de Google Sheets-opslagconfiguraties buiten de algemene oudere map wilt configureren, moet u de **winkelnaam** instellen als **segmentatie** en **winkeltype** als **aem.segmentation**. Daarnaast moet u het proces voor het definiëren van de JSON, zoals hierboven gedefinieerd, overslaan.

1. **Een merk in activiteiten maken**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Activiteiten**

   1. Klik op **Maken** > Merk **maken**

   1. Selecteer **Merk** in de wizard **Pagina** maken en klik op **Volgende**

   1. Ga de **Titel** als **ContextHubDemo** in en klik **creëren**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.
   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)


   >[!CAUTION]
   Bekend probleem:
   Als u een gebied wilt toevoegen, verwijdert u het stramien uit de URL, bijvoorbeeld
   `https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master`

1. **Een gebied in uw merk maken**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Klik op **Maken** en vervolgens **Gebied maken**

   1. Selecteer **Gebied** in de wizard **Pagina** maken en klik op Volgende

   1. Voer de **titel** in als **GoogleSheets** en klik op **Maken**.
Uw gebied wordt gemaakt in uw activiteiten.

## Stap 2: Segmentering publiek instellen {#step-setting-up-audience-segmentation}

Nadat u een gegevensopslagruimte hebt ingesteld en uw merk hebt gedefinieerd, volgt u de onderstaande stappen om publiekssegmenten in te stellen.

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Soorten** > **Wij.Detailhandel**.

   1. Klik op **Maken** > Context Hub Segment **maken.** Het **Nieuwe de dialoogvakje van het Segment** ContextHub opent.

   1. Voer de **titel** in als **werkblad A1 1** en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam **SheetA2 2**.

1. **Segmenten bewerken**

   1. Selecteer de segmentbladen **A1 1** (gemaakt in stap (5)) en klik op **Bewerken** op de actiebalk.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer **Operator** als **Gelijk** van het drop-down menu.

   1. Voer de **waarde** in als **1**.
   >[!NOTE]
   De AEM valideert uw gegevens van Google Sheet door uw segment als groen te tonen.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Bewerk op dezelfde manier de eigenschapswaarden in **Bladen A1 2**.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer **Operator** als **Gelijk** van het drop-down menu.

   1. Voer de **waarde** in als **2**.
   >[!NOTE]
   De regels die in de voorafgaande stappen worden toegepast zijn enkel een voorbeeld van hoe u opstellingssegmenten voor het uitvoeren van de volgende gebruiksgevallen.

## Stap 3: Het richten in Kanalen toelaten {#step-enabling-targeting-in-channels}

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
