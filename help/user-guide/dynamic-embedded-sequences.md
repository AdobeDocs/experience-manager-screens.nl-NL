---
title: Dynamische ingesloten reeks gebruiken
seo-title: Using Dynamic Embedded Sequence
description: Volg deze pagina voor informatie over het implementeren van Dynamic Embedded Sequences in uw AEM Screens-project.
seo-description: Follow this page to learn how to implement Dynamic Embedded Sequences in your AEM Screens project.
uuid: 1f442489-2eeb-4dd8-b892-911fcccb3377
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: a40eb5bb-fbf7-4c0d-a34a-db79b884de8f
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 3208d058-0812-44e1-83e3-b727b384876a
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '2515'
ht-degree: 0%

---

# Dynamische ingesloten reeks gebruiken {#using-dynamic-embedded-sequence}

Het gebruiken van Dynamische Ingesloten Reeksen behandelt de volgende onderwerpen:

* **Overzicht**
* **Dynamische ingesloten ervaring gebruiken in AEM Screens**
* **De resultaten bekijken**
* **Het beperken van Gebruikers en het Wijzigen van ACLs**

## Overzicht {#overview}

***Dynamische ingesloten reeksen*** worden gecreeerd voor grote projecten die de hiërarchie van het ouderkind volgen, waar het kind binnen een plaatsomslag en niet een kanaalomslag van verwijzingen wordt voorzien. Hiermee kan de gebruiker een reeks in een kanaal insluiten met ***Kanaalrol***. Hiermee kan de gebruiker plaatsspecifieke plaatsaanduidingen voor verschillende kantoren definiëren met behulp van een ingesloten reeks in een hoofdkanaal.

Wanneer u een kanaal toewijst aan een weergave, kunt u het pad van de weergave opgeven of de rol van het kanaal die per context wordt omgezet in een daadwerkelijk kanaal.

Als u Dynamische ingesloten reeks wilt gebruiken, wijst u een kanaal door ***Kanaalrol***. De Rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult. In deze sectie wordt een gebruiksscenario beschreven dat kanalen op rol bepaalt en hoe u die inhoud aan een globaal kanaal kunt gebruiken. U kunt de rol ook zien als een id voor de toewijzing of als een alias voor het kanaal in de context van.

### Voordelen van het gebruik van dynamische ingesloten reeksen {#benefits-of-using-dynamic-embedded-sequences}

Het belangrijkste voordeel van het plaatsen van een opeenvolgingskanaal binnen een plaats in plaats van de kanaalomslag is lokale of regionale auteurs toe te staan om inhoud uit te geven relevant voor hen terwijl het worden beperkt van het uitgeven van kanalen hoger in de hiërarchie.

Verwijzen naar een *Kanaal op rol* kunt u lokale versie van een kanaal maken om locatiespecifieke inhoud dynamisch op te lossen en u kunt ook een globaal kanaal maken dat de inhoud gebruikt voor de locatiespecifieke kanalen.

>[!NOTE]
>
>**Ingesloten reeksen versus dynamische ingesloten reeksen**
>
>Een dynamische ingesloten reeks is vergelijkbaar met een ingesloten reeks, maar de gebruiker kan een hiërarchie volgen waarin wijzigingen/updates die in het ene kanaal zijn aangebracht, aan het andere kanaal worden doorgegeven in relatie tot het andere kanaal. De klasse volgt de bovenliggende-onderliggende hiërarchie en bevat ook elementen zoals afbeeldingen of video&#39;s.
>
>***Dynamische ingesloten reeksen*** kunt u locatie-specifieke inhoud weergeven, terwijl ***Ingesloten reeksen*** alleen een algemene presentatie van de inhoud weergeven. Bovendien, terwijl vestiging Dynamische Ingebedde Reeksen, moet u het kanaal vormen gebruikend kanaalrol en naam. Raadpleeg de onderstaande stappen voor praktische implementatie.
>
>Voor meer informatie over het implementeren van ingesloten reeksen raadpleegt u [Ingesloten reeksen](embedded-sequences.md) in AEM Screens.

In het volgende voorbeeld wordt een oplossing geboden waarbij de nadruk ligt op de volgende sleuteltermen:

* a ***hoofdsequentiekanaal*** voor de algemene reeks
* ***dynamische ingesloten reeks*** componenten voor elk lokaal aanpasbaar deel van de reeks
* ***afzonderlijke volgreekskanalen*** op de respectieve locaties met een *rol* in de weergave die overeenkomt met de **dynamische ingesloten reekscomponenten *rol*.**

>[!NOTE]
>
>Ga voor meer informatie over kanaaltoewijzing naar **[Kanaaltoewijzing](channel-assignment.md)** onder sectie Ontwerpen in de documentatie van AEM Screens.

## Dynamische ingesloten reeks gebruiken {#using-dynamic-embedded-sequence-2}

In de volgende sectie wordt uitgelegd hoe u een dynamische ingesloten reeks maakt in een AEM Screens-kanaal.

### Vereisten {#prerequisites}

Voordat u begint met het implementeren van deze functionaliteit, moet u ervoor zorgen dat u aan de volgende voorwaarden kunt voldoen om dynamische ingesloten reeksen te implementeren:

* Een AEM Screens-project maken (in dit voorbeeld: **Demo**)

* Een kanaal maken als **Algemeen** krachtens **Kanalen** map

* Inhoud toevoegen aan uw **Algemeen** Kanaal (*Controleer **Resources.zip**voor relevante activa*)

In de volgende afbeelding wordt de **Demo** project met **Algemeen** kanaal in **Kanalen** map.
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
>Let tijdens het implementeren van Dynamic Embedded Sequences op het volgende **Naam** en **Titel** velden bij het maken van kanalen onder elke locatie. Volg de instructies op het gebied van nomenclatuur zorgvuldig op.

1. **Maak twee locatiemap.**

   Ga naar uw **Locaties** in uw AEM Screens-project en maak twee locatiemappen als **Gebied A** en **Gebied B**.

   >[!NOTE]
   >
   >Tijdens het maken van de **Gebied A** locatiemap, zorg ervoor u ingaat **Titel** als **Gebied A** en u kunt de **Naam** veld leeg, dus automatisch **regio-a** name is opgepikt.
   >
   >Gelijkaardig, is het geval voor het creëren van locatiemap **Gebied B**, zoals hieronder weergegeven:

   ![screen_shot_2018-09-13at23212pm](assets/screen_shot_2018-09-13at23212pm.png)

   >[!NOTE]
   >Raadpleeg voor meer informatie over het maken van een locatie **[Locaties maken en beheren](managing-locations.md)**.

1. **Maak twee locaties en een kanaal onder elke locatiemap.**

   1. Navigeren naar **Demo** —> **Locaties** —> **Gebied A**.
   1. Selecteren **Gebied A** en klik op **+ Maken** in de actiebalk.
   1. Selecteren **Locatie** van de wizard met **Titel** als **Winkel 1**. Op dezelfde manier creeer een andere plaats van de tovenaar genoemd als **Winkel 2** with **Titel** als **Winkel 2**. U kunt de **Naam** veld leeg tijdens maken **Winkel 1** en **Winkel 2**.
   1. Herhaal stap b) en selecteer nu **Volgekanaal** van de wizard. Voer de **Titel** als **Gebied A** en **Naam** als **regio** voor dit kanaal.

   >[!CAUTION]
   >
   >Zorg ervoor dat u tijdens het maken van het kanaal **Gebied A**, voert u de **Titel** als **Gebied A** en de **Naam** als **regio**.

   ![screen_shot_2018-09-13at22857pm](assets/screen_shot_2018-09-13at22857pm.png)

   Maak op dezelfde manier twee locaties onder **Gebied B** genaamd **Winkel 3** en **Winkel 4**. Maak ook een **Volgekanaal** with **Titel** als **Gebied B** en **Naam** als **regio**.

   >[!CAUTION]
   >
   >Controleer of u dezelfde naam kunt gebruiken voor de kanalen die in **Gebied A** en **Gebied B** als **regio**.

   ![screen_shot_2018-09-13at24408pm](assets/screen_shot_2018-09-13at24408pm.png)

1. **Weergave en kanaal maken onder elke locatie.**

   1. Navigeren naar **Demo** —> **Locaties** —> **Gebied A** —> **Winkel 1**.
   1. Selecteren **Winkel 1** en klik op **+ Maken** in de actiebalk.
   1. Selecteren **Weergave** vanuit de wizard en maak **Store1Display.**
   1. Herhaal stap b) en selecteer deze keer **Volgekanaal** van de wizard. Voer de **Titel** als **Store1Channel** en de **Naam** als **winkel**.

   >[!CAUTION]
   >
   >Het is belangrijk dat u een volgnummer maakt, namelijk **Titel** van het kanaal kan als uw vereiste zijn, maar **Naam** moeten op alle lokale kanalen hetzelfde zijn.
   >In dit voorbeeld worden de kanalen onder **Gebied A** en **Gebied B** delen **Naam** als **regio** en kanalen onder **Winkel 1**, **Winkel 2**, **Winkel 3**, en **Winkel 4** delen **Naam** als **winkel**.

   ![screen_shot_2018-09-19at120206pm](assets/screen_shot_2018-09-19at120206pm.png)

   Op dezelfde manier een weergave maken als **Store2Display** en een kanaal **Store2Channel** krachtens **Winkel 2** (met naam als **winkel**).

   >[!NOTE]
   >Controleer of u dezelfde naam kunt gebruiken voor de kanalen die in **Winkel 1** en **Winkel 2** als **winkel**.

   ![screen_shot_2018-09-19at120329pm](assets/screen_shot_2018-09-19at120329pm.png)

   Ga als volgt te werk om een kanaal te maken en weer te geven in **Winkel 3** en **Winkel 4** krachtens **Gebied B**. Controleer nogmaals of u hetzelfde gebruikt **Naam** als **winkel** terwijl u kanaal maakt **Store3Channel** en **Store4Channel** respectievelijk.

   De volgende afbeelding toont de weergave en het kanaal in **Winkel 3**.

   ![screen_shot_2018-09-19at120448pm](assets/screen_shot_2018-09-19at120448pm.png)

   De volgende afbeelding toont de weergave en het kanaal in **Winkel 4**.

   ![screen_shot_2018-09-19at120552pm](assets/screen_shot_2018-09-19at120552pm.png)

1. **Voeg inhoud aan de Kanalen in hun respectieve Plaatsen toe.**

   Ga naar de **Demo** -> **Locaties** -> **Gebied A** -> **Gebied A** en klik op **Bewerken** in de actiebalk. Sleep de elementen die u aan het kanaal wilt toevoegen en zet deze neer.

   >[!NOTE]
   >U kunt de ***Resources.zip*** bestand van de **Bronnen** hierboven, om de afbeeldingen als elementen voor uw kanaalinhoud te gebruiken.

   ![screen_shot_2018-09-12at12438pm](assets/screen_shot_2018-09-12at12438pm.png)

   Ga op dezelfde manier naar de **Demo** -> **Locaties** -> **Gebied B** -> **Gebied B** en klik op **Bewerken** van de actiebar om de activa aan uw kanaal te slepen en te laten vallen, zoals hieronder getoond:

   ![screen_shot_2018-09-12at13133pm](assets/screen_shot_2018-09-12at13133pm.png)

   Voer de voorgaande stappen en de bronnen uit om inhoud toe te voegen aan de volgende kanalen:

   * **Store1Channel**
   * **Store2Channel**
   * **Store3Channel**
   * **Store4Channel**

1. **Een schema maken**

   Navigeren en selecteren **Planningen** in uw AEM Screens-project en klik op **Maken** van de actiebar om een nieuw programma tot stand te brengen.

   In de volgende afbeelding wordt de **AdSchedule** gemaakt in **Demo** project.

   ![screen_shot_2018-09-13at33307pm](assets/screen_shot_2018-09-13at33307pm.png)

1. **Kanalen toewijzen aan een schema**

   1. Navigeren naar **Demo** —> **Planningen** —> **AdSchedule** en klik op **Dashboard** in de actiebalk.
   1. Klikken **+ Kanaal toewijzen** van **TOEGEWEZEN KANALEN** om het deelvenster **Kanaaltoewijzing** in.
   1. Selecteren **Referentiekanaal**.. per pad.
   1. Selecteer **Kanaalpad** als **Demo** —> ***Kanalen*** —> ***Algemeen***.
   1. Voer de **Kanaalrol** als **GlobalAdSegment**.
   1. Selecteer **Ondersteunde gebeurtenissen** als **Oorspronkelijke belasting**, **Niet-actief scherm**, en **Gebruikersinteractie**.
   1. Klikken **Opslaan**.

   **Kanaal op rol toewijzen voor regio:**

   1. Klikken **+ Kanaal toewijzen** van **TOEGEWEZEN KANALEN** om het deelvenster **Kanaaltoewijzing** in.
   1. Selecteren **Referentiekanaal**.. op naam.
   1. Voer de **Kanaalnaam** als **regio***.
   1. Voer de **Kanaalrol** als **RegionAdSegment**.
   1. Klikken **Opslaan**.

   **Kanaal op rol toewijzen voor winkel:**

   1. Klikken **+ Kanaal toewijzen** van **TOEGEWEZEN KANALEN** om het deelvenster **Kanaaltoewijzing** in.
   1. Selecteren **Referentiekanaal**.. op naam.
   1. Voer de **Kanaalnaam** als **winkel**.
   1. Voer de **Kanaalrol** als **StoreAdSegment**.
   1. Klikken **Opslaan**.

   In de volgende afbeelding worden de toegewezen kanalen weergegeven per pad en per rol.

   ![screen_shot_2018-09-12at21429pm](assets/screen_shot_2018-09-12at21429pm.png)

1. **Dynamische ingesloten reeks configureren naar algemeen kanaal.**

   Ga naar de **Algemeen** Kanaal, oorspronkelijk gemaakt in **Demo** project.

   Klikken **Bewerken** in de handeling om de editor te openen.

   ![screen_shot_2018-09-13at52754pm](assets/screen_shot_2018-09-13at52754pm.png)

   Twee slepen en neerzetten **Dynamische ingesloten reeks** in de kanaaleditor.

   Open de eigenschappen van een van de componenten en voer de **Kanaaltoewijzingsrol** als **RegionAdSegment**.

   Selecteer op dezelfde manier de andere component en open eigenschappen om de **Kanaaltoewijzingsrol** als **StoreAdSegment**.

   ![channeldisplay4](assets/channeldisplay4.gif)

1. **Plan toewijzen aan elke weergave**

   1. Ga naar elke weergave, zoals **Demo** —> **Locaties** —> **Gebied A** —>**Winkel 1** —>**Store1Display**.
   1. Klikken **Dashboard** van de handeling om het weergavedashboard te openen.
   1. Klikken **...** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** en klik vervolgens op **+Plan toewijzen**.
   1. Selecteer het pad naar het schema (bijvoorbeeld hier **Demo** —> **Planningen** —>**AdSchedule**).
   1. Klikken **Opslaan**.

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

Als u het weergavepad toewijst als **Demo** —> **Locaties** —> **Gebied A** —> **Winkel 1** —> **Store1Display**, wordt de volgende inhoud weergegeven op uw AEM Screens-speler.

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

* **Global-Author**: Bestaat uit gebruikers die toegang hebben tot alle locaties en kanalen in de **Demo** en beschikken over alle lees-, schrijf- en bewerkingsmachtigingen.

* **Regionaal-auteur**: Bestaat uit gebruikers die lees-, schrijf- en bewerkingsmachtigingen hebben voor **Gebied A** en **Gebied B**.

* **Winkelauteur**: Bestaat uit gebruikers die alleen lees-, schrijf- en bewerkingsmachtigingen hebben voor **Winkel 1**, **Winkel 2**, **Winkel 3**, en **Winkel 4**.

#### Stappen voor het creëren van Gebruikersgroepen, Gebruikers en vestiging ACLs {#steps-for-creating-user-groups-users-and-setting-up-acls}

>[!NOTE]
>
>Om in detail te leren hoe te om projecten te segregeren die ACLs gebruiken zodat elk individu of team hun eigen project behandelt, gelieve te verwijzen naar **ACLs van de vestiging**.

Volg de stappen hieronder om groepen, gebruikers tot stand te brengen en ACLs volgens de toestemmingen te wijzigen:

1. **Groepen maken**

   1. Navigeren naar **Adobe Experience Manager**.
   1. Klikken **Gereedschappen** —> **Beveiliging** —> **Groepen**.
   1. Klikken **Groep maken** en betreden **Global-Author** in **ID**.
   1. Klikken **Opslaan en sluiten**.

   Maak op dezelfde manier twee andere groepen, zoals **Regionaal-auteur** en **Winkelauteur**.

   ![screen_shot_2018-09-17at34008pm](assets/screen_shot_2018-09-17at34008pm.png)

1. **Gebruikers maken en gebruikers toevoegen aan groepen**

   1. Navigeren naar **Adobe Experience Manager**.
   1. Klikken **Gereedschappen** —> **Beveiliging** —> **Gebruikers**.
   1. Klikken **Gebruiker maken** en betreden **Wereldwijd gebruiker** in **ID**.
   1. Enter **Wachtwoord** en bevestig het wachtwoord voor deze gebruiker.
   1. Klik op de knop **Groepen** en voert u de groepsnaam in **Groep selecteren**, bijvoorbeeld **Global-Author** toevoegen **Wereldwijd gebruiker** aan die specifieke groep.
   1. Klikken **Opslaan en sluiten**.

   Maak op dezelfde manier twee andere gebruikers, zoals **Regio-gebruiker** en **Winkelgebruiker** en voeg **Regionaal-auteur** en **Winkelauteur** respectievelijk.

   >[!NOTE]
   >Het is aan te raden gebruikers toe te voegen aan een groep en vervolgens machtigingen toe te wijzen aan elke specifieke groep gebruikers.

   ![screen_shot_2018-09-17at34412pm](assets/screen_shot_2018-09-17at34412pm.png)

1. **Alle groepen toevoegen aan contribuanten**

   1. Navigeren naar **Adobe Experience Manager**.
   1. Klikken **Gereedschappen** —> **Beveiliging** —> **Groepen**.
   1. Selecteren **Medewerkers** in de lijst en selecteer **Leden** tab.
   1. Selecteer **Groep** zoals **Global-Author**, **Regionaal-auteur,** en **Winkelauteur** aan contribuanten.
   1. Klikken **Opslaan en sluiten**.

1. **Toegang tot machtigingen voor elke groep**

   1. Ga naar de *Useradmin* en gebruik deze interface om de machtigingen voor verschillende groepen te wijzigen.
   1. Zoeken naar **Global-Author** en klik op **Machtigingen** zoals weergegeven in de onderstaande afbeelding.
   1. Op dezelfde manier kunt u tot de toestemmingen voor toegang hebben **Regionaal-auteur** en **Winkelauteur**.

   ![screen_shot_2018-09-18at73523am](assets/screen_shot_2018-09-18at73523am.png)

1. **Machtigingen voor elke groep wijzigen**

   **Voor wereldwijde auteur:**

   1. Ga naar de **Machtigingen** tab
   1. Navigeren naar ***/content/screens/demo*** en controleer alle machtigingen
   1. Navigeren naar ***/content/screens/demo/locations*** en controleer alle machtigingen
   1. Navigeren naar ***/content/screens/demo/locations/region-a*** en controleer alle machtigingen. Controleer op dezelfde manier de machtigingen voor **regio-b**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:
   ![screen_shot_2018-09-18at115752am](assets/screen_shot_2018-09-18at115752am.png)

   In de volgende afbeelding wordt getoond dat nu de **Wereldwijd gebruiker** heeft toegang tot **Globaal kanaal** en zowel de **Gebied A** en **Gebied B** met alle vier de winkels, namelijk **Winkel 1**, **Winkel 2**, **Winkel 3**, en **Winkel 4**.

   ![globaal](assets/global.gif)

   **Voor Regionaal-Auteur:**

   1. Ga naar de **Machtigingen** tab.
   1. Navigeren naar ***/content/screens/demo*** en controleert alleen de **Lezen** machtigingen.
   1. Navigeren naar ***/content/screens/demo/locations*** en controleert alleen de **Lezen** machtigingen.
   1. Navigeren naar ***/content/screens/demo/channel*** en schakel de machtigingen uit voor **Algemeen** kanaal.
   1. Navigeren naar ***/content/screens/demo/locations***/***regio-a*** en controleer alle machtigingen. Controleer op dezelfde manier de machtigingen voor **regio-b**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:

   ![screen_shot_2018-09-18at125158pm](assets/screen_shot_2018-09-18at125158pm.png)

   In de volgende afbeelding ziet u dat de Regio-gebruiker nu toegang heeft tot beide **Gebied A** en **Gebied B** met alle vier de winkels, namelijk **Winkel 1**, **Winkel 2**, **Winkel 3**, en **Winkel 4** maar heeft geen toegang tot **Algemeen** Kanaal.

   ![regio](assets/region.gif)

   **Voor Winkelauteur:**

   1. Ga naar de **Machtigingen** tab.
   1. Navigeren naar ***/content/screens/demo*** en controleert alleen de **Lezen** machtigingen.
   1. Navigeren naar ***/content/screens/demo/locations*** en controleert alleen de **Lezen** machtigingen.
   1. Navigeren naar ***/content/screens/demo/channel*** en schakel de machtigingen uit voor **Algemeen** kanaal.
   1. Navigeren naar ***/content/screens/demo/locations/region-a*** en controleert alleen de **Lezen** machtigingen. Controleer op dezelfde manier alleen de **Lezen** machtigingen voor **regio-b**.
   1. Navigeren naar ***/content/screens/demo/locations***/***region-a /store-1*** en controleer alle machtigingen. Controleer op dezelfde manier de machtigingen voor **store-2, store-3,** en **store-4**.

   Raadpleeg de onderstaande afbeelding voor meer informatie over de stappen:

   ![screen_shot_2018-09-18at12415pm](assets/screen_shot_2018-09-18at12415pm.png)

   In de volgende afbeelding wordt getoond dat nu de **Winkelgebruiker** heeft alleen toegang tot de vier winkels, namelijk **Winkel 1**, **Winkel 2**, **Winkel 3**, en **Winkel 4** maar beschikt niet over toegangsrechten tot de **Algemeen** of de regio (**Gebied A** en **Gebied B**).

   ![winkel](assets/store.gif)

>[!NOTE]
>
>Voor meer informatie over het instellen van machtigingen raadpleegt u [ACLs van de vestiging](setting-up-acls.md).
