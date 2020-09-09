---
title: Dynamische ingesloten reeks gebruiken
seo-title: Dynamische ingesloten reeks gebruiken
description: Volg deze pagina voor informatie over het implementeren van Dynamic Embedded Sequences in uw AEM Screens-project.
seo-description: Volg deze pagina voor informatie over het implementeren van Dynamic Embedded Sequences in uw AEM Screens-project.
uuid: 1f442489-2eeb-4dd8-b892-911fcccb3377
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: a40eb5bb-fbf7-4c0d-a34a-db79b884de8f
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '2535'
ht-degree: 0%

---


# Dynamische ingesloten reeks gebruiken {#using-dynamic-embedded-sequence}

Het gebruiken van Dynamische Ingesloten Reeksen behandelt de volgende onderwerpen:

* **Overzicht**
* **Dynamische ingesloten ervaring gebruiken in AEM Screens**
* **De resultaten bekijken**
* **Het beperken van Gebruikers en het Wijzigen van ACLs**

## Overzicht {#overview}

***Dynamische ingesloten reeksen*** worden gemaakt voor grote projecten die de onderliggende bovenliggende hiërarchie volgen, waarbij naar het onderliggende item wordt verwezen in een locatiemap en niet in een kanaalmap. Hiermee kan de gebruiker een reeks via ***kanaalrol*** insluiten in een kanaal. Hiermee kan de gebruiker plaatsspecifieke plaatsaanduidingen voor verschillende kantoren definiëren met behulp van een ingesloten reeks in een hoofdkanaal.

Wanneer u een kanaal toewijst aan een weergave, kunt u het pad van de weergave opgeven of de rol van het kanaal die per context wordt omgezet in een daadwerkelijk kanaal.

Om Dynamische Ingesloten Opeenvolging te gebruiken, wijst u een kanaal door de Rol ***van het*** Kanaal toe. De Rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult. In deze sectie wordt een gebruiksscenario beschreven dat kanalen op rol bepaalt en hoe u die inhoud aan een globaal kanaal kunt gebruiken. U kunt de rol ook zien als een id voor de toewijzing of als een alias voor het kanaal in de context van.

### Voordelen van het gebruik van dynamische ingesloten reeksen {#benefits-of-using-dynamic-embedded-sequences}

Het belangrijkste voordeel van het plaatsen van een opeenvolgingskanaal binnen een plaats in plaats van de kanaalomslag is lokale of regionale auteurs toe te staan om inhoud uit te geven relevant voor hen terwijl het worden beperkt van het uitgeven van kanalen hoger in de hiërarchie.

Wanneer u naar een *Kanaal op rol* verwijst, kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen en kunt u ook een globaal kanaal maken dat de inhoud voor de locatie-specifieke kanalen gebruikt.

>[!NOTE]
>
>**Ingesloten reeksen versus dynamische ingesloten reeksen**
>
>Een dynamische ingesloten reeks is vergelijkbaar met een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in het ene kanaal zijn aangebracht, aan het andere kanaal worden doorgegeven in relatie tot het andere kanaal. De klasse volgt de bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s.
>
>***Met dynamische ingesloten reeksen*** kunt u locatie-specifieke inhoud weergeven, terwijl met ***ingesloten reeksen*** alleen de algemene presentatie van de inhoud wordt weergegeven. Bovendien, terwijl vestiging Dynamische Ingebedde Reeksen, moet u het kanaal vormen gebruikend kanaalrol en naam. Raadpleeg de onderstaande stappen voor praktische implementatie.
>
>Raadpleeg [Ingesloten reeksen](embedded-sequences.md) in AEM Screens voor meer informatie over het implementeren van ingesloten reeksen.

In het volgende voorbeeld wordt een oplossing geboden waarbij de nadruk ligt op de volgende sleuteltermen:

* een ***hoofdvolgordekanaal*** voor de algemene reeks
* ***dynamische ingesloten reekscomponenten*** voor elk lokaal aanpasbaar deel van de reeks
* ***afzonderlijke opeenvolgingskanalen*** in de respectieve plaatsen met een *rol* in de vertoning die de **dynamische ingebedde *rol*van de opeenvolgingscomponent aanpast.**

>[!NOTE]
>
>Zie **[Kanaaltoewijzing](channel-assignment.md)** onder sectie Ontwerpen in AEM Screens-documentatie voor meer informatie over kanaaltoewijzing.

## Dynamische ingesloten reeks gebruiken {#using-dynamic-embedded-sequence-2}

In de volgende sectie wordt uitgelegd hoe u een dynamische ingesloten reeks maakt in een AEM Screens-kanaal.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u aan de volgende voorwaarden kunt voldoen om dynamische ingesloten reeksen te implementeren:

* Een AEM Screens-project maken (in dit voorbeeld **Demo**)

* Een kanaal maken als **globaal** onder de map **Kanalen**

* Inhoud toevoegen aan uw **Global** Channel (*Controleer **Resources.zip**voor relevante middelen*)

In de volgende afbeelding ziet u het **Demo** -project met het **algemene** kanaal in de map **Kanalen** .
![screen_shot_2018-09-07at21032pm](assets/screen_shot_2018-09-07at21032pm.png)

### Bronnen {#resources}

U kunt de volgende bronnen downloaden (afbeeldingen en deze toevoegen aan elementen) en deze verder gebruiken als kanaalinhoud voor demonstratiedoeleinden.

[Bestand ophalen](assets/resources.zip)

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over het maken van een project en het maken van een volgnummer:
>
>* **[Projecten maken en beheren](creating-a-screens-project.md)**
>* **[Een kanaal beheren](managing-channels.md)**

>



Het uitvoeren van Dynamische Ingebedde Opeenvolging in een project van AEM Screens omvat drie belangrijke taken:

1. **Projecttaxonomie instellen, waaronder Kanalen, Locaties en Weergaven**
1. **Een schema maken**
1. **Plan toewijzen aan elke weergave**

Voer de volgende stappen uit om de functionaliteit te implementeren:

>[!CAUTION]
>
>Tijdens het implementeren van dynamische ingesloten reeksen moet u voorzichtig zijn met de velden **Naam** en **Titel** terwijl u kanalen onder elke locatie maakt. Volg de instructies op het gebied van nomenclatuur zorgvuldig op.

1. **Maak twee locatiemap.**

   Navigeer naar de map **Locations** in uw AEM Screens-project en maak twee locatiemappen als **Gebied A** en **Gebied B**.

   >[!NOTE]
   >
   >Zorg tijdens het maken van de locatiemap **Gebied A** dat u de **Titel** opgeeft als **Gebied A** en dat u het veld **Naam** leeg laat, zodat automatisch de naam **regio-a** wordt opgehaald.
   >
   >Hetzelfde geldt voor het maken van een locatiemap in **Gebied B**, zoals hieronder wordt getoond:

   ![screen_shot_2018-09-13at23212pm](assets/screen_shot_2018-09-13at23212pm.png)

   >[!NOTE]
   >Zie Locaties **[maken en beheren voor meer informatie over het maken van een locatie](managing-locations.md)**.

1. **Maak twee locaties en een kanaal onder elke locatiemap.**

   1. Navigeer naar **demo** —> **Locaties** —> **Gebied A**.
   1. Selecteer **Gebied A** en klik op **+ Maken** in de actiebalk.
   1. Selecteer **Locatie** in de wizard met **Titel** als **Winkel 1**. Maak op dezelfde manier een andere locatie via de wizard **Winkel 2** met **Titel** als **Winkel 2**. U kunt het veld **Naam** leeg laten terwijl u **Winkel 1** en **Winkel 2** maakt.
   1. Herhaal stap b) en selecteer nu **Volgkanaal** in de wizard. Voer de **titel** in als **Gebied A** en **Naam** als **gebied** voor dit kanaal.

   >[!CAUTION]
   >
   >Zorg ervoor dat bij het maken van **kanaalgebied A** de **titel** wordt ingevoerd als **gebied A** en de **naam** als **gebied**.

   ![screen_shot_2018-09-13at22857pm](assets/screen_shot_2018-09-13at22857pm.png)

   Maak op dezelfde manier twee locaties onder **Gebied B** met de naam **Winkel 3** en **Winkel 4**. Maak ook een **sequentiekanaal** met **Titel** als **Gebied B** en **Naam** als **gebied**.

   >[!CAUTION]
   >
   >Controleer of u dezelfde naam kunt gebruiken voor de kanalen die in **Gebied A** en **Gebied B** zijn gemaakt als **regio**.

   ![screen_shot_2018-09-13at24408pm](assets/screen_shot_2018-09-13at24408pm.png)

1. **Weergave en kanaal maken onder elke locatie.**

   1. Navigeer naar **Demo** —> **Locaties** —> **Regio A** —> **Winkel 1**.
   1. Selecteer **Winkel 1** en klik op **+ Maken** in de actiebalk.
   1. Selecteer **Weergeven** in de wizard en maak **Store1Display.**
   1. Herhaal stap b) en selecteer dit keer **Volgnummer** in de wizard. Voer de **titel** in als **Store1Channel** en de **naam** als **winkel**.

   >[!CAUTION]
   >
   >Het is belangrijk wanneer u een opeenvolgingskanaal creeert, kan de **Titel** van het kanaal als uw vereiste zijn, maar de **Naam** zou het zelfde in alle lokale kanalen moeten zijn.
   >In dit voorbeeld delen de kanalen onder **Gebied A** en **Gebied B** dezelfde **naam** als **regio** en kanalen onder **Opslag 1************** **** ****,Store 2,Store 3, enStore 4dezelfde naamNaam alsstore.

   ![screen_shot_2018-09-19at120206pm](assets/screen_shot_2018-09-19at120206pm.png)

   Maak op dezelfde manier een display als **Store2Display** en een kanaal **Store2Channel** onder **Store 2** (met naam als **winkel**).

   >[!NOTE]
   >Zorg ervoor dat je dezelfde naam kunt gebruiken voor de kanalen die in **winkel 1** en **winkel 2** zijn gemaakt als in de **winkel**.

   ![screen_shot_2018-09-19at120329pm](assets/screen_shot_2018-09-19at120329pm.png)

   Ga als volgt te werk om een kanaal en weergave in **winkel 3** en **winkel 4** onder **Gebied B** te maken. Controleer opnieuw of u dezelfde **naam** gebruikt als **winkel** bij het maken van kanaal **Store3Channel** en **Store4Channel** .

   In de volgende afbeelding ziet u de weergave en het kanaal in **Store 3**.

   ![screen_shot_2018-09-19at120448pm](assets/screen_shot_2018-09-19at120448pm.png)

   De volgende afbeelding toont de weergave en het kanaal in **Store 4**.

   ![screen_shot_2018-09-19at120552pm](assets/screen_shot_2018-09-19at120552pm.png)

1. **Voeg inhoud aan de Kanalen in hun respectieve Plaatsen toe.**

   Navigeer naar de **demo** -> **Locaties** -> **Gebied A** -> **Gebied A** en klik op **Bewerken** op de actiebalk. Sleep de elementen die u aan het kanaal wilt toevoegen en zet deze neer.

   >[!NOTE]
   >U kunt het bestand ***Resources.zip*** uit de bovenstaande sectie **Resources** gebruiken om de afbeeldingen als elementen voor uw kanaalinhoud te gebruiken.

   ![screen_shot_2018-09-12at12438pm](assets/screen_shot_2018-09-12at12438pm.png)

   Navigeer op dezelfde manier naar de **demo** -> **Locaties** -> **Gebied B** -> **Gebied B** en klik op **Bewerken** op de actiebalk om de middelen naar uw kanaal te slepen, zoals hieronder wordt getoond:

   ![screen_shot_2018-09-12at13133pm](assets/screen_shot_2018-09-12at13133pm.png)

   Voer de voorgaande stappen en de bronnen uit om inhoud toe te voegen aan de volgende kanalen:

   * **Store1Channel**
   * **Store2Channel**
   * **Store3Channel**
   * **Store4Channel**

1. **Een schema maken**

   Navigeer en selecteer de map **Planningen** in uw AEM Screens-project en klik op **Maken** in de actiebalk om een nieuw schema te maken.

   De volgende afbeelding toont het **AdSchedule** dat in het **Demo** -project is gemaakt.

   ![screen_shot_2018-09-13at33307pm](assets/screen_shot_2018-09-13at33307pm.png)

1. **Kanalen toewijzen aan een schema**

   1. Navigeer naar **Demo** —> **Planningen** —> **AdSchedule** en klik op **Dashboard** op de actiebalk.
   1. Klik op **+ Kanaal** toewijzen vanuit het deelvenster **TOEGEWEZEN KANALEN** om het dialoogvenster **Kanaaltoewijzing** te openen.
   1. Referentiekanaal **** selecteren.. per pad.
   1. Selecteer het **Kanaalpad** als **demo** —> ***Kanalen*** —> ***Globaal***.
   1. Voer de rol **** Kanaal in als **GlobalAdSegment**.
   1. Selecteer de **Ondersteunde gebeurtenissen** als **Eerste Laden**, **Niet-actief scherm** en **Gebruikersinteractie**.
   1. Click **Save**.

   **Kanaal op rol toewijzen voor regio:**

   1. Klik op **+ Kanaal** toewijzen vanuit het deelvenster **TOEGEWEZEN KANALEN** om het dialoogvenster **Kanaaltoewijzing** te openen.
   1. Referentiekanaal **** selecteren.. op naam.
   1. Voer de **kanaalnaam** in als **gebied***.
   1. Voer de rol **** Kanaal in als **RegionAdSegment**.
   1. Click **Save**.

   **Kanaal op rol toewijzen voor winkel:**

   1. Klik op **+ Kanaal** toewijzen vanuit het deelvenster **TOEGEWEZEN KANALEN** om het dialoogvenster **Kanaaltoewijzing** te openen.
   1. Referentiekanaal **** selecteren.. op naam.
   1. Voer de **kanaalnaam** in als **opslagruimte**.
   1. Voer de **Kanaalrol** in als **StoreAdSegment**.
   1. Click **Save**.

   In de volgende afbeelding worden de toegewezen kanalen weergegeven per pad en per rol.

   ![screen_shot_2018-09-12at21429pm](assets/screen_shot_2018-09-12at21429pm.png)

1. **Dynamische ingesloten reeks configureren naar algemeen kanaal.**

   Navigeer naar het **globale** Kanaal, u creeerde aanvankelijk in **Demo** project.

   Klik op **Bewerken** in de handeling om de editor te openen.

   ![screen_shot_2018-09-13at52754pm](assets/screen_shot_2018-09-13at52754pm.png)

   Sleep twee **dynamische ingesloten reekscomponenten** naar de kanaaleditor.

   Open de eigenschappen van één van de componenten en ga de Rol **van de Toewijzing van het** Kanaal als **RegioAdSegment** in.

   Op dezelfde manier selecteer de andere component en open eigenschappen om de Rol **van de Toewijzing van het** Kanaal als **StoreAdSegment** in te gaan.

   ![channeldisplay4](assets/channeldisplay4.gif)

1. **Plan toewijzen aan elke weergave**

   1. Navigeer naar elk scherm, zoals **Demo** —> **Locaties** —> **Regio A** —>**Store 1** —>**Store1Display**.
   1. Klik op **Dashboard** in de handeling om het weergavedashboard te openen.
   1. Klik **...** in het **venster TOEGEWEZEN KANALEN EN SCHADUWEN** en klik vervolgens op **+Plan** toewijzen.
   1. Selecteer het pad naar het schema (bijvoorbeeld **Demo** —> **Planningen** —>**AdSchedule**).
   1. Click **Save**.

## De resultaten bekijken {#viewing-the-results}

Wanneer u de instellingen voor kanalen hebt ingesteld en de weergave voltooid is, start u de AEM Screens-speler om de inhoud weer te geven.

>[!NOTE]
>
>Raadpleeg de volgende bronnen voor meer informatie over AEM Screen Player:
>
>* [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/)
>* [Werken met AEM Screens Player](working-with-screens-player.md)



De volgende uitvoer bevestigt de inhoud van uw kanaal in de AEM Screens-speler, afhankelijk van het weergavepad.

**Scenario 1**:

Als u het weergavepad toewijst als **Demo** —> **Locaties** —> **Regio A** —> **Winkel 1** —> **Store1Display**, wordt de volgende inhoud weergegeven op uw AEM Screens-speler.

![channeldisplay1](assets/channeldisplay1.gif)

**Scenario 1**:

Als u het weergavepad toewijst als **Demo** —> **Locaties** —> **Gebied B** —> **Winkel 3** —> **Store3Display**, wordt de volgende inhoud weergegeven op uw AEM Screens-speler.

![channeldisplay2](assets/channeldisplay2.gif)

## Het beperken van Gebruikers en het Wijzigen van ACLs {#restricting-users-and-modifying-the-acls}

U kunt globale, regionale of lokale auteurs maken om inhoud die voor hen van belang is, te bewerken, terwijl u de mogelijkheid hebt om kanalen hoger in de hiërarchie te bewerken.

U moet ACLs wijzigen om de gebruikers toegang tot de inhoud te beperken die op hun plaats wordt gebaseerd.

### Voorbeeld: hoofdletter gebruiken {#example-use-case}

In het volgende voorbeeld kunt u drie gebruikers voor het bovenstaande demoproject maken.

De bevoegdheden worden aan elke groep toegewezen als volgt:

**Groepen**:

* **Globale auteur**: Bestaat uit gebruikers die toegang tot alle plaatsen en kanalen in het project van de **Demo** hebben en alle lees hebben, schrijven, en uitgeven toestemmingen.

* **Regionaal-auteur**: Bestaat uit gebruikers die lees-, schrijf- en bewerkmachtigingen hebben voor **Gebied A** en **Gebied B**.

* **Winkelauteur**: Bestaat uit gebruikers die alleen lees-, schrijf- en bewerkingsmachtigingen hebben voor **Store 1**, **Store 2**, **Store 3** en **Store 4**.

#### Stappen voor het creëren van Gebruikersgroepen, Gebruikers en vestiging ACLs {#steps-for-creating-user-groups-users-and-setting-up-acls}

>[!NOTE]
>
>Om in detail te leren hoe te om projecten te segregeren die ACLs gebruiken zodat elk individu of team hun eigen project behandelt, gelieve te verwijzen naar **Vestiging ACLs**.

Volg de stappen hieronder om groepen, gebruikers tot stand te brengen en ACLs volgens de toestemmingen te wijzigen:

1. **Groepen maken**

   1. Navigeer naar **Adobe Experience Manager**.
   1. Klik op **Gereedschappen** —> **Beveiliging** —> **Groepen**.
   1. Klik op Groep **** maken en voer **Global-Author** in de **id** in.
   1. Klik op **Opslaan en sluiten**.

   Maak op dezelfde manier twee andere groepen, zoals **Regionaal auteur** en **Winkelauteur**.

   ![screen_shot_2018-09-17at34008pm](assets/screen_shot_2018-09-17at34008pm.png)

1. **Gebruikers maken en gebruikers toevoegen aan groepen**

   1. Navigeer naar **Adobe Experience Manager**.
   1. Klik op **Gereedschappen** —> **Beveiliging** —> **Gebruikers**.
   1. Klik op Gebruiker **** maken en voer **Globale gebruiker** in de **id** in.
   1. Voer het **wachtwoord** in en bevestig het wachtwoord voor deze gebruiker.
   1. Klik op het tabblad **Groepen** en voer de naam van de groep in **Groep** selecteren in. Voer bijvoorbeeld **Global-Author** in om **Global-User** aan die specifieke groep toe te voegen.
   1. Klik op **Opslaan en sluiten**.

   Maak op dezelfde manier twee andere gebruikers, zoals **Regio-gebruiker** en **Winkelgebruiker** , en voeg deze toe aan **Gebied-Auteur** en **Opslagauteur** .

   >[!NOTE]
   >Het is aan te raden gebruikers toe te voegen aan een groep en vervolgens machtigingen toe te wijzen aan elke specifieke groep gebruikers.

   ![screen_shot_2018-09-17at34412pm](assets/screen_shot_2018-09-17at34412pm.png)

1. **Alle groepen toevoegen aan contribuanten**

   1. Navigeer naar **Adobe Experience Manager**.
   1. Klik op **Gereedschappen** —> **Beveiliging** —> **Groepen**.
   1. Selecteer **Medewerkers** in de lijst en selecteer het tabblad **Leden** .
   1. Selecteer de **Groep** zoals **Global-Author**, **Gebied-Auteur,** en **Opslagauteur** aan contribuanten.
   1. Klik op **Opslaan en sluiten**.

1. **Toegang tot machtigingen voor elke groep**

   1. Navigeer naar de *gebruikersbeheerder* en gebruik deze interface om de machtigingen voor verschillende groepen te wijzigen.
   1. Zoek naar **globaal-auteur** en klik **Toestemmingen** tabel, zoals aangetoond in het hieronder cijfer.
   1. Op dezelfde manier hebt u toegang tot de machtigingen voor **Regionaal auteur** en **Winkelauteur**.

   ![screen_shot_2018-09-18at73523am](assets/screen_shot_2018-09-18at73523am.png)

1. **Machtigingen voor elke groep wijzigen**

   **Voor wereldwijde auteur:**

   1. Navigate to the **Permissions** tab
   1. Navigeer naar ***/content/screens/demo*** en controleer alle machtigingen
   1. Navigeer naar ***/content/screens/demo/locations*** en controleer alle machtigingen
   1. Navigeer naar ***/content/screens/demo/locations/region-a*** en controleer alle machtigingen. Controleer op dezelfde manier de machtigingen voor **region-b**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:
   ![screen_shot_2018-09-18at115752am](assets/screen_shot_2018-09-18at115752am.png)

   De volgende afbeelding laat zien dat de **Global-User** nu toegang heeft tot het **Global Channel** en zowel **Region A** als **Region B** met alle vier winkels: **Store 1**************,Store 2,Store 3,Store 4.

   ![global](assets/global.gif)

   **Voor Regionaal-Auteur:**

   1. Navigate to the **Permissions** tab.
   1. Navigeer naar ***/content/screens/demo*** en controleer alleen de **leesmachtigingen** .
   1. Navigeer naar ***/content/screens/demo/locations*** en controleer alleen de **Leesmachtigingen** .
   1. Navigeer naar ***/content/screens/demo/channel*** en schakel de machtigingen voor **Global** channel uit.
   1. Navigeer naar ***/content/screens/demo/locations***/***region-a*** en controleer alle machtigingen. Controleer op dezelfde manier de machtigingen voor **region-b**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:

   ![screen_shot_2018-09-18at125158pm](assets/screen_shot_2018-09-18at125158pm.png)

   De volgende afbeelding laat zien dat de Regio-gebruiker nu toegang heeft tot zowel **Gebied A** als **Gebied B** met alle vier winkels: **Winkel 1**, **Winkel 2**, **Winkel 3****** **** enStore 4, maar geen toegang heeft tot hetGlobalChannel.

   ![regio](assets/region.gif)

   **Voor Winkelauteur:**

   1. Navigate to the **Permissions** tab.
   1. Navigeer naar ***/content/screens/demo*** en controleer alleen de **leesmachtigingen** .
   1. Navigeer naar ***/content/screens/demo/locations*** en controleer alleen de **Leesmachtigingen** .
   1. Navigeer naar ***/content/screens/demo/channel*** en schakel de machtigingen voor **Global** channel uit.
   1. Navigeer naar ***/content/screens/demo/locations/region-a*** en controleer alleen de **leesmachtigingen** . Op dezelfde manier controleer slechts de **Gelezen** toestemmingen voor **gebied-b**.
   1. Navigeer naar ***/content/screens/demo/locations***/***region-a /store-1*** en controleer alle machtigingen. Op dezelfde manier controleer de toestemmingen voor **store-2, store-3,** en **store-4**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:

   ![screen_shot_2018-09-18at12415pm](assets/screen_shot_2018-09-18at12415pm.png)

   De volgende afbeelding laat zien dat de **winkel-gebruiker** nu alleen toegang heeft tot de vier winkels, namelijk **Store 1**, **Store 2**, **Store 3** en **Store 4** ******** ****, maar geen toegangsrechten heeft tot de kanalenGlobal of region (Region A enRegion B).

   ![winkel](assets/store.gif)

>[!NOTE]
>
>Om in detail over opstellingstoestemmingen te leren, gelieve te verwijzen naar [Instelling ACLs](setting-up-acls.md).

