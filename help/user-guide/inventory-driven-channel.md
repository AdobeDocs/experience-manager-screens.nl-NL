---
title: Voorraadgestuurd kanaal
seo-title: Voorraadgestuurd kanaal
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: a7e7aa08-8f9e-4458-bdce-225cf29a6da4
contentOwner: jsyal
discoiquuid: 9989ef4c-9fdd-4bf2-9f7c-0c74a9cc4e7f
docset: aem65
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Voorraadgestuurd kanaal{#inventory-driven-channel}

## Aan de slag met de voorraad gestuurde kanalen {#getting-started-with-inventory-driven-channels}

In deze sectie wordt een gebruiksvoorbeeld beschreven waarin de nadruk wordt gelegd op het maken en beheren van een gegevensgestuurde wijziging van bedrijfsmiddelen met behulp van Google Sheets.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

### Terminolgies {#terminolgies}

Volg onderstaande termen die een belangrijke rol spelen bij het begrijpen en opzetten van het project in de verschillende gebruiksgevallen:

**Activiteit** verwijst naar de categorie.

**Hoofdproject van** gebied

**Publiek** Locatie van de gegevens

**Merk** verwijst naar

**Segment** Segment verwijst naar een container met elementen die u als doel wilt instellen.

### Basisstroom: Het project instellen {#basic-flow-setting-up-the-project}

>[!NOTE]
>
>**Vereiste:**
>
>Voordat u dieper in details duikt over het instellen en gebruiken van gegevensgestuurde wijziging van elementen in uw project, moet u een AEM-schermproject maken met een volgnummer. Voor demo-doeleinden wordt het project **DataDrivenAsset** gemaakt en worden volgordekanalen met de naam **DataDrivenRestaurant**, **DataDrivenTextOverlay**, **DataDrivenWeather** en **DataDrivenRetail** aan het project toegevoegd, zoals in de onderstaande afbeelding wordt getoond.
>
>Het creëren van vier verschillende kanalen is slechts voor demonstratiedoeleinden en om vier verschillende gebruiksgevallen in verschillende kanalen te laten zien. Als u slechts één gebruiksgeval als uw vereiste wilt volgen, gelieve te voelen vrij om slechts één opeenvolgingskanaal tot stand te brengen.

![screen_shot_2019-05-01at42043pm](assets/screen_shot_2019-05-01at42043pm.png)

Volg de onderstaande secties om een voorbeeldproject te maken voor het maken en beheren van een gegevensgestuurde wijziging van elementen met behulp van Google Sheets in een AEM Screens-project:

## Stap 1: Database instellen {#step-setting-up-database}

>[!CAUTION]
>
>Google Sheets wordt gebruikt in het volgende voorbeelddatabasesysteem van waaruit de waarden worden opgehaald en is uitsluitend bedoeld voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.
>
>Raadpleeg de API-sleutel [](https://developers.google.com/maps/documentation/javascript/get-api-key) ophalen in de documentatie van Google voor meer informatie.

1. Meld u aan bij Google Docs.

   >[!NOTE]
   >
   >U moet een account hebben in Google Drive voordat u een nieuw Google-werkblad maakt.

1. Een nieuw leeg spreadsheet starten. Voeg inhoud toe aan uw Google-pagina en sla deze op. Voor demo-doeleinden wordt het Google-blad genoemd als **ContextHubDemo**.
1. Klik op **Delen** in de rechterbovenhoek van het Google-blad om het dialoogvenster **Delen met anderen** te openen. Klik op de optie **Geavanceerd** en wijzig de instellingen in **Aan - iedereen met de koppeling**, zoals in de onderstaande afbeelding wordt getoond.

   Met deze stap hebt u toegang tot waarden in het hoekblad.

   ![screen_shot_2019-04-22at115829am](assets/screen_shot_2019-04-22at115829am.png)

1. Wanneer u in de vorige stap op **Opslaan** klikt, wordt de koppeling naar het Google-werkblad weergegeven. Sla de klik op voor toekomstige verwijzingen en klik op **Gereed**.

   ![screen_shot_2019-04-22at120242pm](assets/screen_shot_2019-04-22at120242pm.png)

>[!CAUTION]
>
>Google Sheets wordt in het volgende voorbeeld gebruikt voor educatieve doeleinden. Adobe biedt geen ondersteuning voor het gebruik van Google Sheets voor productieomgevingen.

## Stap 2: Google Sheets REST API&#39;s inschakelen {#step-enabling-the-google-sheets-rest-apis}

Nadat u Google Sheet hebt ingesteld, moet u de Google Sheet REST API inschakelen voor toegang tot de waarden.

Raadpleeg de documentatie van Google API&#39;s voor meer informatie over het inschakelen van de REST API&#39;s voor Google Sheets.

1. Ga naar [Google API Console](https://console.developers.google.com/apis/credentials). Klik op **MAKEN** om een nieuw project te maken.

   ![screen_shot_2019-04-22at125028pm](assets/screen_shot_2019-04-22at125028pm.png)

1. Voer de **projectnaam** in als **AssetChange** en klik op **CREATE**.
1. Nadat u het project hebt gemaakt, moet u de API-sleutel instellen. Klik **creeer geloofsbrieven** en selecteer **API sleutel **om API sleutel voor uw project te produceren. Sla de API-sleutel op voor toekomstige verwijzingen.

   >[!NOTE]
   >
   >In dit demoproject wordt de gratis Google API-sleutel gebruikt. Op de Google-website **Get API Key** wilt u mogelijk prijzen en beperkingen vermelden voor meer informatie.

### De installatie van Google Sheets controleren {#verifying-the-setup-of-google-sheets}

```
Verify the data in your Google Sheets using the steps below
```

[https://sheets.googleapis.com/v4/spreadsheets/](https://sheets.googleapis.com/v4/spreadsheets/)&lt;your sheet id>/values/Sheet1?key=&lt;your API key>

Bijvoorbeeld:

Als de link** Google Sheets** *als volgt is:*

`https://docs.google.com/spreadsheets/d/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/edit?usp=sharing`en de

**Werkblad-id** is: `1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M`

**API-sleutel** is: `AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

Beide waarden in de bovenstaande syntaxis toevoegen:

`https://sheets.googleapis.com/v4/spreadsheets/1Ksd125lAsDd0_wnMWgLNUiEpKOUPaok7xfh64s-VO7M/values/Sheet1?key=AIzaSyAfoANOeLkFCCyohjL8cOdJLhrhGefqEy8`

U moet nu uw gegevens in het blad kunnen bekijken.

## Stap 2: AEM configureren om de inhoud van de Google Sheets op te halen {#step-configuring-aem-to-fetch-the-content-of-the-google-sheets}

In de volgende sectie wordt beschreven hoe u Adobe Experience Manager (AEM) configureert om inhoud op te halen van de Google Sheets.

1. Navigeer naar de AEM-instantie en klik vanuit de linkerzijbalk op het gereedschapspictogram. Klik **Plaatsen** -> **ContextHub**, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Creeer een nieuwe Configuratie van de Opslag ContextHub**

   1. Navigeer aan **globaal** > **gebrek** > Configuratie **** ContextHub.

   1. Klik** creeer > de Container van de Configuratie **en ga de titel als** ContextHubDemo* in.

   1. **Navigeer** aan **ContextHubDemo** > de Configuratie van de Opslag **ContentHub...** om de **Configure tovenaar te openen**
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
   >Vervang de code met uw *&lt;Sheet ID>* en *&lt;API Sleutel>*, die u van **Stap 1 haalde: Database instellen.**

   >[!CAUTION]
   Als u uw Google Sheets-opslagconfiguraties maakt buiten de oude map (bijvoorbeeld in uw eigen projectmap), werkt het aanwijzen van doelen niet uit de doos.
   Als u de Google Sheets-opslagconfiguraties buiten de algemene oudere map wilt configureren, moet u de **winkelnaam** instellen als **segmentatie** en **winkeltype** als **aem.segmentation**. Daarnaast moet u het proces voor het definiëren van de JSON, zoals hierboven gedefinieerd, overslaan.

1. **Een merk in activiteiten maken**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Activiteiten**

   1. Klik op** Maken** > Merk **maken**

   1. Selecteer **Merk** in de wizard **Pagina** maken en klik op **Volgende**

   1. Ga de **Titel** als **ContextHubDemo** in en klik **creëren**. Je merk wordt nu gemaakt zoals hieronder wordt weergegeven.
   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)

1. 

>[!CAUTION]
Bekend probleem:
Als u een gebied wilt toevoegen, verwijdert u het stramien uit de URL, bijvoorbeeld
[https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master](https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master)

1. Een gebied in uw merk maken**

   1. Klik op **Maken** > Gebied **maken**

   1. Selecteer **Gebied** in de wizard* Create Page** en klik op Next

   1. Voer de **titel** in als **GoogleSheets** en klik op **Maken**. Uw gebied wordt gemaakt in uw activiteiten.

1. **Segmenten maken voor het publiek**

   1. Navigeer van uw instantie AEM aan **Personalisatie** > **Soorten** > **Wij.Detailhandel**.
   1. Klik op **Maken** > Context Hub Segment **maken**. Het nieuwe de dialoogvakje van het Segment ContextHub opent.
   1. Voer de **titel** in als **werkblad A1 1** en klik op **Maken**. Maak op dezelfde manier een ander segment met de naam **SheetA2 2**.

1. **Segmenten bewerken**

   1. Selecteer de segmentbladen **A1 1** (gemaakt in stap (5)) en klik op **Bewerken** op de actiebalk.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer **Operator** als **Gelijk **van het drop-down menu.

   1. Voer de **waarde** in als **1**.
   >[!NOTE]
   De AEM valideert uw gegevens van Google Sheet door uw segment als groen te tonen.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Bewerk op dezelfde manier de eigenschapswaarden in **Bladen A1 2**.

   1. Sleep en zet de **vergelijking neer: Eigenschap - de component van de Waarde** aan de redacteur.
   1. Klik op het moersleutelpictogram om het dialoogvenster **Een eigenschap vergelijken met een waarde** te openen.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**.

   1. Selecteer **Operator** als **Gelijk **van het drop-down menu.

   1. Voer de **waarde** in als **2**.
   >[!NOTE]
   De regels die in de voorafgaande stappen worden toegepast zijn enkel een voorbeeld van hoe u opstellingssegmenten voor het uitvoeren van de volgende gebruiksgevallen.

## Stap 3: Configuratie van de Hub van de Opstelling van de Context in het Kanaal van de Schermen AEM {#step-setting-up-context-hub-configurations-in-aem-screens-channel}

Volg de stappen hieronder aan opstellingsContextHub configuraties en segmentweg aan AEM het kanaal van Schermen.

1. Navigeer als voorwaarde naar een van de AEM Screens-kanalen (**DataDrivenRetail**) die u hebt gemaakt.
1. Selecteer het kanaal (**DataDrivenRetail**) en klik op **Eigenschappen** in de actiebalk.

   ![screen_shot_2019-05-01at4332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Selecteer het lusje van de **Personalisatie** aan opstelling de configuraties ContextHub.

   1. Selecteer het **ContextHub-pad** als **bibliotheken** > **instellingen** > **cloudinstellingen** > **standaard** **** ****> ContextHub Configurations en klik opSelect.

   1. Selecteer het **Segmentpad** als **conf** > **We.Retail **> **instellingen** > **wcm** > **segmenten** **** en klik op Select.

   1. Klik op **Opslaan en sluiten**.
   >[!NOTE]
   Gebruik ContextHub en de weg van Segmenten, waar u aanvankelijk uw configuraties en segmenten van de contexthub bewaarde.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

   >[!NOTE]
   Als u niet het **Merk** onder **Doelconfiguratie** van de dialoogdoos hierboven selecteert, zult u het Merk en de Activiteit moeten selecteren wanneer u het proces van het richten begint.

1. Navigeer en selecteer **DataDrivenRetail** van **DataDrivenAssets** > **Kanalen **en klik **uitgeven** van de actiebar.

   >[!NOTE]
   Als u opstelling alles correct hebt, zult u het **richten** optie in drop-down van de redacteur zien, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   Zodra u de configuraties ContextHub voor uw kanaal hebt gevormd, zorg ervoor u voorafgaande stappen van 1 door 4 volgt, voor de andere drie opeenvolgingskanalen te als u alle hieronder gebruiksgevallen wilt volgen.

## Hoofdlettergebruik 1: Winkelvoorraad activeren {#use-case-retail-inventory-activation}

In het volgende gebruiksgeval worden drie verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-werkblad.

### Beschrijving {#description}

In deze Use Case wordt de voorraad voor de detailhandel getoond voor drie verschillende gekleurde sweatshirts. Afhankelijk van het aantal sweatshirts dat beschikbaar is in voorraad en dat is opgenomen in Google Sheets, wordt de afbeelding (rood, groen of blauw sweatshirt) met het hoogste aantal weergegeven op het scherm.

Voor dit geval van Gebruik, zal de Rood, Groen, of Blauwe trui op uw scherm tonen die op de hoogste waarde van aantal sweaters wordt gebaseerd die beschikbaar is.

### Procedure {#procedure}

Volg de onderstaande stappen om de Gebruiksscenario voor de activering van de Retail Inventory te implementeren:

1. **De Google Sheets vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg drie kolommen (Rood, Groen en Blauw) toe met de bijbehorende waarden voor drie verschillende sweatshirts.
   ![screen_shot_2019-05-06at101755am](assets/screen_shot_2019-05-06at101755am.png)

1. **Het publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (gemaakt in stap (5) van sectie ***Stap 2: AEM configureren om de inhoud van de Google Sheets*** op te halen).
   1. Voeg drie nieuwe segmenten **voor_rood**, **voor_groen**, en **voor_blauw** toe.

   1. Selecteer **For_Red** en klik op **Bewerken** op de actiebalk.

   1. Sleep en zet de **vergelijking neer: Bezit - Bezit** aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst in de naam van de **vooreigenschap**

   1. Selecteer de **exploitant** als **groter-dan **van het drop-down menu

   1. Selecteer **Gegevenstype** als **nummer**

   1. Selecteer **gumesheets/value/1/1** in de vervolgkeuzelijst in de naam van de **tweede eigenschap**

   1. Slepen en neerzetten **een andere vergelijking: Bezit - Bezit **aan de redacteur en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst in de naam van de **vooreigenschap**

   1. Selecteer de **exploitant** als **groter-dan **van het drop-down menu

   1. Selecteer **Gegevenstype** als **nummer**

   1. Selecteer **gumesheets/value/1/0** in het keuzemenu met de naam van de **tweede eigenschap**
   ![screen_shot_2019-05-06at102600am](assets/screen_shot_2019-05-06at102600am.png)

   Op dezelfde manier geef en voeg vergelijkingsbezitsregels aan segment **For_Blue** toe zoals aangetoond in het hieronder cijfer:

   ![screen_shot_2019-05-06at103728am](assets/screen_shot_2019-05-06at103728am.png)

   Op dezelfde manier geef en voeg vergelijkingsbezitsregels aan* voor_Groen **segment toe zoals aangetoond in het hieronder cijfer:

   ![screen_shot_2019-05-06at103418am](assets/screen_shot_2019-05-06at103418am.png)

   >[!NOTE]
   U zult merken dat voor segmenten **For_Green** en **For_Green** geen gegevens in de editor kunnen worden geladen omdat alleen de eerste vergelijking nu geldig is volgens de waarden in het Google-blad.

1. Navigeer en selecteer uw **DataDrivenRetail **kanaal (een opeenvolgend kanaal) en klik **uitgeven** van de actiebar.

   ![screen_shot_2019-05-06at104257am](assets/screen_shot_2019-05-06at104257am.png)

   >[!CAUTION]
   U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-06at105214am](assets/screen_shot_2019-05-06at105214am.png)

   >[!NOTE]
   Als u niet het **Merk** onder het **richten Configuraties** terwijl het opzetten van **Configuraties** ContextHub voor uw project, zoals aangetoond in het beeld hierboven toevoegt, moet u het **Merk** en de **Activiteit** selecteren terwijl het beginnen van het proces om zich, in de volgende stap te richten.

1. **Een standaardafbeelding toevoegen**

   1. Voeg een standaardafbeelding toe aan uw kanaal en klik op **Doel**.
   1. Selecteer **Merk** en de **Activiteit** van het drop-down menu en klik **Begin richtend**.

   1. Klik op **Doelstelling** starten.
   ![screen_shot_2019-05-06at121253pm](assets/screen_shot_2019-05-06at121253pm.png)

   >[!NOTE]
   Voordat u de focus begint te plaatsen, moet u de segmenten (**For_Green**, **For_Red** en **For_Blue**) toevoegen door op **+ te klikken. Voeg ervaringen toe die gericht** zijn vanaf de zijspoor, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-05-06at123554pm](assets/screen_shot_2019-05-06at123554pm.png)

1. Voeg de afbeeldingen toe aan alle drie de verschillende scenario&#39;s, zoals hieronder wordt weergegeven.

   ![retail_targeting](assets/retail_targeting.gif)

1. **De voorvertoning controleren**

   1. Klik op **Voorvertoning.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde voor alle drie de kolommen en u ziet hoe de afbeelding van de weergave wordt bijgewerkt volgens de hoogste inventariswaarde.
   ![retail_result](assets/retail_result.gif)

## Hoofdlettergebruik 2: Weatheractivering in het midden van de reis {#use-case-travel-center-weather-activation}

In het volgende gebruiksgeval worden twee verschillende afbeeldingen gedemonstreerd op basis van de waarden in uw Google-blad.

### Beschrijving {#description-1}

Als uw Google-bladen voor dit geval een waarde van minder dan 50 hebben, wordt een afbeelding met warme dranken weergegeven en als de waarde groter dan of gelijk is aan 50, wordt de afbeelding met koude dranken weergegeven. In het geval van een andere of geen waarde geeft de speler een standaardafbeelding weer.

### Procedure {#procedure-1}

Voer de onderstaande stappen uit om het gebruik van het weeractiveringsargument voor uw AEM Screens-project voor het reiscentrum te implementeren:

1. **De Google Sheets vullen**

   1. Navigeer naar het Google-werkblad ContextHubDemo.
   1. Voeg een kolom met **Kop1** met overeenkomstige waarde voor temperatuur toe.
   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (gemaakt in stap (5) van sectie ***Stap 2: AEM configureren om de inhoud van de Google Sheets*** op te halen).
   1. Selecteer de **bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **exploitant** als **groter-dan-of-gelijk **van het drop-down menu

   1. Voer de **waarde** in als **50**

   1. Selecteer op dezelfde manier de ** Bladen A1 2 **en klik **uitgeven**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/0** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **exploitant** als **minder-dan **van het drop-down menu

   1. Voer de **waarde** in als **50**

1. Navigeer en selecteer het kanaal () en klik op **Bewerken** op de actiebalk. In het volgende voorbeeld, **DataDrivenWeather**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   Uw kanaal zou reeds een standaardbeeld moeten hebben en het publiek zou moeten worden pre-gevormd zoals die in Stap (3) wordt beschreven

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

   >[!NOTE]
   Als u niet het **Merk** onder het **richten Configuraties** terwijl het opzetten van **Configuraties** ContextHub voor uw project, zoals aangetoond in het beeld hierboven toevoegt, moet u het **Merk** en de **Activiteit** selecteren terwijl het beginnen van het proces om zich, in de volgende stap te richten.

1. Selecteer **Doel** in de editor en selecteer **Merk** en **Activiteit** in het keuzemenu en klik op **Doelstelling** starten.

   >[!NOTE]
   Als u het **Merk** onder het **richten van Configuraties** terwijl het opzetten van **Configuratie** ContextHub voor uw project toevoegde, te hoeven u niet om het **Merk** en de **Activiteit** in deze stap te selecteren.

   ![new_activity3](assets/new_activity3.gif)

1. De voorvertoning controleren

   1. Klik op **Voorvertoning.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Als u de waarde wijzigt in minder dan 50, kunt u de afbeelding van zomerdranken bekijken. Als de waarde in het Google-blad 50 of hoger is dan zou moeten kunnen worden bekeken of er een afbeelding van warme drank is.
   ![result3](assets/result3.gif)

## Hoofdlettergebruik 3: Activering van ziekenhuisreservering {#use-case-hospitality-reservation-activation}

In het volgende gebruiksgeval worden twee verschillende afbeeldingen gedemonstreerd op basis van de waarden en de formule die in het Google-werkblad zijn toegepast.

### Beschrijving {#description-2}

In dit geval wordt op het Google-blad een reserveringspercentage vermeld voor twee restaurants **Restaurant1** en **Restaurant2**. Een formule wordt toegepast gebaseerd op waarden van Restaurant1 en Restaurant2 en gebaseerd op de formule, wordt waarde 1 of 2 toegewezen aan de Kolom **AdTarget** .

Als **Restaurant1** > **Restaurant2**, dan is de **waarde AdTaget** 1 anders **AdTarget** wordt toegewezen waarde 2. Waarde 1 genereert de optie *Steak food* en waarde 2 resulteert in de weergave van de optie *Thai food* op het scherm.

### Procedurele aanpak {#procedural-approach}

Voer de onderstaande stappen uit om de activeringsaanvraag voor ziekenhuisreservering te implementeren voor uw AEM Screens-project:

1. De Google Sheets vullen en de formule toevoegen.

   Pas bijvoorbeeld de formule toe op de derde kolom **AdTarget**, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **De segmenten in soorten publiek configureren volgens de vereisten**

   1. Navigeer naar de segmenten in uw publiek (gemaakt in stap (5) van sectie ***Stap 2: AEM configureren om de inhoud van de Google Sheets*** op te halen).
   1. Selecteer de **bladen A1 1** en klik op **Bewerken**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. Selecteer de **operator** als **equal **vanuit het keuzemenu

   1. Voer de **waarde** in als **1**

   1. Selecteer op dezelfde manier de ** Bladen A1 2 **en klik **uitgeven**.

   1. Selecteer het vergelijkingsbezit en klik vormen pictogram om de eigenschappen uit te geven.
   1. Selecteer **gumesheets/value/1/2** in de vervolgkeuzelijst met **eigenschapsnaam**

   1. De **operator** selecteren als **2**

1. Navigeer en selecteer het kanaal () en klik op **Bewerken** op de actiebalk. In het volgende voorbeeld, **DataDrivenRestaurant**, wordt een opeenvolgend kanaal gebruikt om de functionaliteit te tonen.

   >[!NOTE]
   Het kanaal moet al een standaardafbeelding hebben en het publiek moet vooraf worden geconfigureerd zoals wordt beschreven in Stap 3.

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   U zou opstelling uw **Configuratie** ContextHub **gebruikend de** Eigenschappen **van het kanaal ->** Personalisatie **** tabel moeten hebben.

   ![screen_shot_2019-05-08at14903pm](assets/screen_shot_2019-05-08at14903pm.png)

   >[!NOTE]
   Als u niet het **Merk** onder het **richten Configuraties** terwijl het opzetten van **Configuraties** ContextHub voor uw project, zoals aangetoond in het beeld hierboven toevoegt, moet u het **Merk** en de **Activiteit** selecteren terwijl het beginnen van het proces om zich, in de volgende stap te richten.

1. Selecteer **Doel** in de editor en selecteer **Merk** en **Activiteit** in het keuzemenu en klik op **Doelstelling** starten.
1. De voorvertoning controleren

   1. Klik op **Voorvertoning.** Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde in Restaurant1 > Restaurant2. U kunt dan de afbeelding van een biefstuk en Restaurant1 &lt; Restaurant12 bekijken. U kunt dan de afbeelding van een Thai-stuk op uw scherm bekijken.
   ![result5](assets/result5.gif)

## Hoofdlettergebruik 4: Tekstbedekking Digital Menu Board {#use-case-digital-menu-board-text-overlay}

Het volgende gebruiksgeval toont een digitaal gebruik van de menubalk aan dat veel voorkomt in restaurants en fast food gewrichten.

### Beschrijving {#description-3}

In het volgende voorbeeld wordt het gebruik van tekstbedekking in een opeenvolgend kanaal beschreven en wordt aangegeven hoe de prijsupdate van de waarde in de Google Sheets een update in de update van de component text overlay activeert.

### Procedurele aanpak {#procedural-approach-1}

Voer de onderstaande stappen uit om het digitale menubord met tekstbedekking te implementeren voor uw AEM Screens-project:

1. **De Google Sheets vullen**

   1. Navigeer naar uw Google Sheets.
   1. Voeg een kolom met prijswaarde voor het gebruiksgeval, zoals aangetoond in hieronder cijfer toe.
   ![screen_shot_2019-05-05at111344am](assets/screen_shot_2019-05-05at111344am.png)

1. **Een afbeelding toevoegen aan het kanaal Volgorde**

   1. Navigeer en selecteer uw kanaal (**DataDrivenAssets** —> **Kanalen** —> **DataDrivenTextOverlay**).

   1. Klik op **Bewerken** op de actiebalk om de editor te openen.
   1. Sleep een afbeelding van de appeltaart naar de editor.
   ![screen_shot_2019-05-05at112933am](assets/screen_shot_2019-05-05at112933am.png)

1. **Tekstbedekking toevoegen aan de afbeelding**

   1. Selecteer het beeld in de redacteur en de klik vormt.
   1. Navigeer naar het tabblad **Tekstbedekking** en voeg de tekstbedekking toe aan de afbeelding. Om de waarde van uw Google Sheets te krijgen, zorg ervoor de waarde in de krullende takken wordt ingesloten. De prijs wordt bijvoorbeeld opgehaald uit de hoekbladen en wordt bij het definiëren van de tekstbedekking **{price}** genoemd.

   1. Navigeer aan het lusje **ContextHub** en vorm de waarde die van de google bladen moet worden gehaald, zoals aangetoond in het hieronder cijfer.
   ![textoverlay_result](assets/textoverlay_result.gif)

1. **De voorvertoning controleren**

   <!-- Edit text in steps below. wonky-->

   1. Klik op **Voorvertoning**. Open ook uw Google-werkblad en werk de waarde ervan bij.
   1. Wijzig de waarde onder **Prijs** en de waarde die in de tekstbedekking wordt gebruikt, wordt dienovereenkomstig bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.
   ![textoverlay_result-1](assets/textoverlay_result-1.gif)
