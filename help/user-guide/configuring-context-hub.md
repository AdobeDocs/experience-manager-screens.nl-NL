---
title: ContextHub configureren in AEM Screens
description: Leer over ContextHub in het richten motor zodat kunt u een gegevensopslag voor de inhoudsverandering van de gegevenstrekker bepalen.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 1%

---

# ContextHub configureren in AEM Screens {#configuring-contexthub-in-aem-screens}

In deze sectie wordt de nadruk gelegd op het maken en beheren van gegevensgestuurde wijzigingen in elementen met behulp van een gegevensopslag.

## Belangrijkste voorwaarden {#key-terms}

Voordat u de details van het maken en beheren van voorraadgestuurde kanalen in uw AEM Screens-project kunt bekijken, moet u enkele belangrijke termen leren voor de verschillende scenario&#39;s.

**Merk** - Uw high-level projectbeschrijving.

**Gebied** - Uw het projectnaam van AEM Screens zoals Digitale Ad Signage

**Activiteit** - bepaalt de categorieregels zoals inventaris-Gedreven, Weer-Gedreven, of de Beschikbaarheid-Gedreven Afdeling.

**Publiek** - bepaalt de regel.

**Segment** - de versie van een activa om voor de bepaalde regel te spelen. Als de temperatuur bijvoorbeeld lager is dan 50 graden Fahrenheit, wordt op het scherm een afbeelding van een warme drank weergegeven, anders een koude drank.

Het volgende diagram verstrekt een visuele vertegenwoordiging van hoe de configuraties ContextHub met Activiteit, Publiek, en Kanalen samenvallen.

![ screen_shot_2019-05-29at53729pm ](assets/screen_shot_2019-05-29at53729pm.png)

## Voorwaarden {#preconditions}

Alvorens u begint configuraties te vormen ContextHub voor een project van AEM Screens, opstelling Google Bladen (voor demonstratiedoeleinden).

>[!IMPORTANT]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt als een voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is alleen voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Voor meer informatie, zie [ API Sleutel ](https://developers.google.com/maps/documentation/javascript/get-api-key) in de documentatie van Google krijgen.

## Stap 1: Een Data Store instellen {#step-setting-up-a-data-store}

U kunt de gegevensopslag instellen als een lokale I/O-gebeurtenis of als een lokale databasegebeurtenis.

In het volgende voorbeeld van een lokale databasegebeurtenis wordt een activering van gegevens op middelenniveau getoond. De gebeurtenisreeksen - omhoog een gegevensopslag zoals een blad van Excel dat u configuraties ContextHub en segmentweg aan het kanaal van AEM Screens laat gebruiken.

Nadat u het `google` -blad correct hebt ingesteld, zoals in het onderstaande voorbeeld wordt getoond:

![afbeelding](/help/user-guide/assets/context-hub/context-hub1.png)

De volgende validatie wordt weergegeven wanneer u de verbinding controleert door de twee waarden `*google sheet ID*` en `*API key*` in de onderstaande notatie in te voeren:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![afbeelding](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>In het onderstaande specifieke voorbeeld worden de Google-bladen weergegeven als een gegevensopslagruimte die een wijziging van het element activeert wanneer de waarde hoger is dan 100 of lager dan 50.

## Stap 2: Opslagconfiguraties instellen {#step-setting-store-configurations}

1. **die aan ContextHub** navigeren

   Navigeer naar de AEM en klik in de linkerzijbalk op het gereedschapspictogram. Klik **Plaatsen** > **ContextHub**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Creërend een Configuratie van de Winkel ContextHub**

   1. Navigeer aan de configuratiecontainer die als **schermen** wordt genoemd.

   1. Klik **creëren** > **creeer de Container van de Configuratie** en ga de titel als **ContextHubDemo** in.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub4.png)

   1. **navigeer** aan **ContextHubDemo** > **creeer** **Configuratie ContentHub** en klik **sparen**.

      >[!NOTE]
      > Nadat u **&#x200B;**&#x200B;klikt sparen, bent u in het **scherm van de Configuratie ContextHub**.

   1. Van het **scherm van de Configuratie ContextHub**, klik **creeer** > **Configuratie van de Winkel ContentHub**

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub5.png)

   >[!CAUTION]
   >
   >Als onderdeel van AEM 6.5 Feature Pack 4 of AEM 6.4 Feature Pack 8 dienen klanten `/conf/screens/settings/cloudsettings` bij te werken naar `sling:Folder` .
   >
   >Voer de onderstaande stappen uit:
   >
   >1. Navigeer naar CRXDE Lite en vervolgens naar `/conf/screens/settings/cloudsettings` .
   >1. Controleer of `cloudsettings jcr:primaryType` zich in `sling:Folder` bevindt. Ga door met de volgende stappen als `jcr:primaryType` zich niet in `sling:folder` bevindt.
   >1. Klik `/conf/screens/settings` met de rechtermuisknop aan en creeer een knoop met *naam* als **`cloudsettings1`** en *Type* als **`sling:Folder`** en sparen de veranderingen.
   >1. Verplaats alle knooppunten onder `/conf/screens/settings/cloudsettings` naar `cloudsettings1` .
   >1. Verwijderen `cloudsettings` en opslaan.
   >1. Wijzig de naam van `cloudsettings1` in `cloudsettings` en sla het bestand op.
   >1. Merk op dat `/conf/screens/settings/cloudsettings` `jcr:primaryType` as `sling:Folder` heeft.
   >
   >Voer de volgende stappen uit in Auteur en Publish voor of na de upgrade.

   1. Ga de **Titel** als **Bladen van Google**, **Naam van de Opslag** als **`googlesheets`** in, en **Type van Opslag** als **c`ontexthub.generic-jsonp`** en klik **daarna**.

      >[!CAUTION]
      >Als u Adobe Experience Manager (AEM) 6.4 gebruikt, ga de **Titel van de Configuratie** als **`googlesheets`** en het **Type van Opslag** als **c`ontexthub.generic-jsonp`** in.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Voer uw specifieke json-configuratie in. Bijvoorbeeld, kunt u de volgende json voor demodoeleinden gebruiken en **klikken sparen**. U ziet de opslagconfiguratie die als **wordt genoemd Google Bladen** in configuratie ContextHub.

      >[!IMPORTANT]
      >Vervang de code door de `*<Sheet ID>*` en `*<API Key>*` die u hebt opgehaald tijdens het instellen van de Google-bladen.

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
      >In de bovengenoemde steekproefcode, **pollInterval** bepaalt de frequentie waarbij de waarden (in milliseconden) worden verfrist.
      >
      >Vervang de code door de `*<Sheet ID>*` en `*<API Key>*` die u hebt opgehaald tijdens het instellen van de Google-bladen.

      >[!CAUTION]
      >
      >Als u uw Google Sheets maakt om configuraties buiten de algemene map op te slaan (bijvoorbeeld in uw eigen projectmap), werkt het instellen van een doel niet uit de verpakking.

1. **de Segmentatie van de Opslag van de Opstelling**

   1. Navigeer aan **Configuratie van de Opslag ContentHub** en creeer een andere opslagconfiguratie in de de configuratiecontainer van AEM Screens en plaats de **Titel** als **segmentation-contexthub**, **Naam van de Opslag** als **segmentatie** en **Type van de Opslag** als **aem.segmentation.**

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Klik **daarna** en dan **sparen**.

      >[!NOTE]
      >Sla het proces waarbij de zoon wordt gedefinieerd over en laat deze leeg.


## Stap 3: Segmenten voor het publiek instellen {#setting-up-audience}

1. **Creërend Segmenten in Publiek**

   1. Navigeer van uw AEM instantie aan **Personalization** > **Soorten publiek** > **schermen**.

   1. Klik **creeer** > **creëren Segment ContextHub.** Het **Nieuwe de dialoogvakje van het Segment ContextHub** opent.

   1. Ga de **Titel** als `**Higherthan50**` in en klik **creeer**. Maak op dezelfde manier een ander segment met de naam `**Lowerthan50**` .

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub11.png)

   1. Klik het segment `**Higherthan50**` en klik **Eigenschappen** van de actiebar.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub12.png)

   1. Klik het **Personalization** lusje van de **Eigenschappen van het Segment**. Plaats de **Weg ContextHub** aan `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` en **Weg van Segmenten** aan `/conf/screens/settings/wcm/segments` en klik **sparen**, zoals aangetoond in hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub13.png)

   1. Op dezelfde manier plaats de **Weg ContextHub** en **Weg van Segmenten** voor `**Lowerthan50**` ook segment.

## Stap 4: Opzetten van merk en gebied {#setting-brand-area}

Volg de onderstaande stappen om een merk te maken in uw activiteiten en gebieden onder het merk:

1. **Creërend een Merk in Activiteiten**

   1. Navigeer van uw AEM instantie aan **Personalization** > **Activiteiten**.

   1. Klik **creëren** > **merk** creëren.

   1. Klik **Merk** van **creëren de tovenaar van de Pagina** en klik **daarna**.

   1. Ga de **Titel** als **ScreensBrand** in en klik **creeer**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub8.png)


      >[!CAUTION]
      >
      >Bekend probleem:
      >Als u een gebied wilt toevoegen, verwijdert u de primaire URL, bijvoorbeeld
      >`http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Creërend een Gebied in uw Merk**

   Ga als volgt te werk om een gebied in het merk te maken:

   1. Klik **creeer** en dan **creeer Gebied**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub9.png)

   1. Klik **Gebied** van **creëren de tovenaar van de Pagina** en klik **daarna**.

   1. Ga de **Titel** als **ScreensValue** in en klik **creeer**.
Er wordt een gebied gemaakt in uw merk.

## Stap 5: De segmenten in een activiteit maken {#step-setting-up-audience-segmentation}

Nadat u een gegevensopslag hebt ingesteld en uw activiteit (merk en gebied) hebt gedefinieerd, volgt u de onderstaande stappen om segmenten in uw activiteit te maken.

1. **Creërend Segmenten in Activiteiten**

   1. Navigeer van uw AEM instantie aan **Personalization** > **Activiteiten** > **ScreensBrand** > **ScreensValue**.

   1. Klik **creeer** > **creeer Activiteit.** **vormt de Tovenaar van de Activiteit** opent.

   1. Ga de **Titel** als **ValueCheck50** en **Naam** als **valuecheck50** in. Klik de **het richten motor** als **ContextHub (AEM)** van drop-down en klik **daarna**.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub14.png)

   1. Klik **toevoegen Ervaring** van de `**Configure Activity**` tovenaar.

   1. Van het **publiek**, klik `**Higherthan50**` en klik **voeg Ervaring** toe en ga **Titel** als `**higherthan50**` **Naam** in als `**higherthan50**`. Klik **OK**.

   1. Van het **publiek**, klik `**Lowerthan50**` en klik **voeg Ervaring** toe en ga **Titel** als `**lowerthan50**` **Naam** in als `**lowerthan50**`. Klik **OK**.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Klik **daarna** en dan **sparen**. `**ValueCheck50**` -activiteit wordt nu gemaakt en geconfigureerd.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub16.png)

## Stap 5: De segmenten in soorten publiek bewerken{#editing-audience-segmentation}

1. **Uitgevend de Segmenten**

   1. Navigeer van uw AEM instantie aan **Personalization** > **Soorten publiek** > **schermen**.

   1. Klik het segment `**Higherthan50**`, en klik **uitgeven** van de actiebar.

   1. Sleep en laat vallen de **Vergelijking: Bezit - de component van de Waarde** aan de redacteur.

   1. Klik het moersleutelpictogram zodat kunt u **openen die een bezit met waarde** dialoogdoos vergelijkt.

   1. Klik **googesheets/value/1/0** van de drop-down in **naam van het Bezit**.

      >[!NOTE]
      > **googesheets/value/1/0** verwijst naar rij 2 en kolom zoals bevolkt in `google` bladen in het hieronder cijfer:

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub17.png)

   1. Klik de **Exploitant** als **groter-dan** van het drop-down menu.

   1. Ga de **Waarde** als **70** in.

      >[!NOTE]
      >
      >De AEM valideert uw gegevens van het Blad van Google door uw segment als groen te tonen.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub18.png)

   Bewerk op dezelfde manier de eigenschapswaarden in `**Lowerthan50**` .

   1. Sleep en laat vallen de **Vergelijking: Bezit - de component van de Waarde** aan de redacteur.

   1. Klik op het moersleutelpictogram.

   1. In het **Vergelijkend een bezit met waarde** dialoogdoos, klik **googesheets/value/1/0** van de drop-down in **naam van het Bezit**.

   1. Klik de **Exploitant** als **minder-dan** van het drop-down menu.

   1. Ga de **Waarde** als **in 50**.


## Het richten in Kanalen toelaten {#step-enabling-targeting-in-channels}

Voer de onderstaande stappen uit om het activeren van doelwitbestanden in uw kanalen in te schakelen.

1. Ga naar een van de AEM Screens-kanalen. De volgende stappen tonen aan hoe te om het richten toe te laten door **DataDrivenChannel** te gebruiken die in een kanaal van AEM Screens wordt gecreeerd.

1. Klik het kanaal **TargetChannel** en klik **Eigenschappen** van de actiebar.

   ![afbeelding](/help/user-guide/assets/context-hub/context-hub19.png)

1. Klik het **Personalization** lusje zodat kunt u opstelling de configuraties ContextHub.

   1. Plaats de **Weg ContextHub** aan `/conf/screens/settings/wcm/segments` en **Weg van Segmenten** aan `/conf/screens/settings/wcm/segments`.
   1. Plaats merk aan **ScreensBrand** van dropdown en **plaats de Verwijzing van het Gebied** aan **ScreensValue**.

   1. Klik **sparen &amp; Sluiten**.

      >[!NOTE]
      >
      >Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties ContextHub en segmenten bewaarde.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigeer en klik het **kanaal 0&rbrace; TargetChannel &lbrace;en klik** uitgeven **van de actiebar.**

      >[!NOTE]
      >
      >Als u opstelling alles correct hebt, ziet u de **het richten** optie in drop-down van de redacteur, zoals aangetoond in het hieronder cijfer.

      ![afbeelding](/help/user-guide/assets/context-hub/context-hub21.png)

## Meer informatie: voorbeelden gebruiken {#learn-more-example-use-cases}

Nadat u ContextHub voor uw project van AEM Screens hebt gevormd, kunt u de verschillende Gevallen van het Gebruik volgen om te begrijpen hoe de gegevens teweeggebrachte activa een vitale rol in verschillende industrieën spelen:

1. **[Detailhandel gerichte Activering van de Inventaris](retail-inventory-activation.md)**
1. **[de Activering van de Temperatuur van het Centrum van de Reizen](local-temperature-activation.md)**
1. **[Activering van de Voorbehoud van de Ziekenhuis](hospitality-reservation-activation.md)**
