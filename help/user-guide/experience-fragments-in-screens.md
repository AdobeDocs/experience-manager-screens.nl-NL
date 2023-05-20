---
title: Ervaringsfragmenten gebruiken
seo-title: Using Experience Fragments
description: Volg deze pagina voor meer informatie over het gebruik van Experience Fragments in AEM Screens.
seo-description: Follow this page to learn about using Experience Fragments in AEM Screens.
uuid: 6ee16a94-3c53-43e0-99d5-c35cb9e01120
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 0e88e9e0-a95b-4acd-98ea-499d4d4e3c99
docset: aem65
feature: Authoring Screens, Experience Fragments
role: Admin, Developer
level: Intermediate
exl-id: 13c0d75e-435f-433e-8886-f451df863517
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 0%

---

# Ervaringsfragmenten gebruiken {#using-experience-fragments}

Deze pagina behandelt de volgende onderwerpen:

* **Overzicht**
* **Experience Fragments gebruiken in AEM Screens**
* **Wijzigingen op de pagina doorgeven**

## Overzicht {#overview}

An ***Ervaar fragment*** is een groep van één of meerdere componenten met inbegrip van inhoud en lay-out die binnen pagina&#39;s kunnen worden van verwijzingen voorzien. De fragmenten van de ervaring kunnen om het even welke component, zoals, één of veelvoudige componenten bevatten die om het even wat binnen een paragraafsysteem kunnen bevatten, die in de volledige ervaring zullen worden van verwijzingen voorzien of door een derde eindpunt gevraagd.


## Experience Fragments gebruiken in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>In het volgende voorbeeld wordt **Wij.Detailhandel** als een demo-project van waaruit het ervaringsfragment wordt gebruikt vanuit een **Sites** pagina naar een AEM Screens-project.

Als voorbeeld, toont het volgende werkschema het gebruik van ervaringsfragmenten van We.Retail in Plaatsen. U kunt een webpagina kiezen en die inhoud in uw AEM Screens-kanaal gebruiken in een van uw projecten.

### Voorwaarden {#pre-requisites}

**Een demoproject maken met een kanaal**

***Een project maken***

1. Klikken **Schermproject maken** om een nieuw project te maken.
1. Voer de titel in als **DemoProject**.
1. Klikken **Opslaan**.

A **DemoProject** wordt toegevoegd aan je AEM Screens.

***Een kanaal maken***

1. Ga naar de **DemoProject** u creeerde en selecteert **Kanalen** map.

1. Klikken **Maken** in de actiebalk om de wizard te openen.
1. Kies de optie **Volgekanaal** sjabloon van de wizard en klik op **Volgende**.

1. Voer de **Titel** als **TestChannel** en klik op **Maken**.

A **TestChannel** wordt toegevoegd aan uw **DemoProject**.\
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Een ervaringsfragment maken {#creating-an-experience-fragment}

Voer de onderstaande stappen uit om de inhoud te benutten van **Wij.Detailhandel** aan uw **TestChannel** in **DemoProject**.

1. **Navigeer aan een pagina van Plaatsen in Wij.Retail**

   1. Ga naar sites en selecteer **Wij.Detailhandel** -> **Verenigde Staten** -> **Engels** -> **Apparatuur** en selecteer deze pagina om deze te gebruiken als ervaringsfragment voor uw kanaal van het Scherm.

   1. Klikken **Bewerken** in de actiebalk om de pagina te openen die u als ervaringsfragment voor uw rasterkanaal wilt gebruiken.

1. **De inhoud opnieuw gebruiken**

   1. Selecteer het fragment dat u in het kanaal wilt opnemen.
   1. Klik op het laatste pictogram van rechts om het dialoogvenster **Omzetten in ervaringsfragment** in.

   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Experience-fragment maken**

   1. Kies de optie **Handeling** als **Een nieuw ervaringsfragment maken**.

   1. Selecteer **Bovenliggend pad**.
   1. Selecteer **Sjabloon**. Kies de optie **Ervaring fragment - rastervariatie** sjabloon hier (waarde in veld) `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).

   1. Voer de **Fragmenttitel** als **ScreensFragment**.

   1. Klik op het vinkje om het maken van een nieuw ervaringsfragment te voltooien.

   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

   Opmerking: Als u een optie gemakkelijker wilt selecteren, klikt u op het vinkje rechts van de velden om het dialoogvenster Selecteren te openen.

1. **Actieve kopie van ervaringsfragment maken**

   1. Navigeer naar de AEM startpagina.
   1. Selecteren **Ervaar fragmenten** en de **ScreensFragment** en klik op **Variatie als live-kopie**, zoals weergegeven in onderstaande afbeelding:

   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Selecteer **ScreensFragment** van **Live kopie maken** wizard en klik op **Volgende**.

   d. Voer de **Titel** en **Naam** als **Schermen**.

   e. Klikken **Maken** om de actieve kopie te maken.

   f. Klikken **Gereed** om terug te gaan naar **ScreensFragment** pagina.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nadat u het fragment Schermen hebt gemaakt, kunt u de eigenschappen van het fragment bewerken. Selecteer het fragment en klik op **Eigenschappen** in de actiebalk.

   **Eigenschappen van een rasterfragment bewerken**

   1. Ga naar de **ScreensFragment** (u hebt in de voorgaande stappen gemaakt) en klik op **Eigenschappen** in de actiebalk.

   1. Selecteer **Offlineconfiguratie** zoals weergegeven in de onderstaande afbeelding.

   U kunt de **Client-side bibliotheken** (java en css) en **Statische bestanden** naar uw ervaringsfragment.

   In het volgende voorbeeld ziet u de toevoeging van bibliotheken aan de clientzijde en de lettertypen als onderdeel van statische bestanden aan uw ervaringsfragment.  ![fragment](assets/fragment.gif)

1. **Experience Fragment gebruiken als component in Screenkanaal**

   1. Navigeer naar het kanaal van het Scherm waar u wilt gebruiken **Schermen** fragment.
   1. Selecteer **TestChannel** en klik op **Bewerken** in de actiebalk.

   1. Klik op het componentpictogram op het zijtabblad.
   1. Sleep de **Ervaar fragment** naar uw kanaal.

   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Selecteer **Ervaar fragment** en selecteer het pictogram linksboven om het dialoogvenster **Ervaar fragment** in.

   f. Selecteer **Schermen** live kopie van het fragment dat u hebt gemaakt in *Stap 3* in **Pad**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Selecteer **Schermen** live kopie van het fragment dat u hebt gemaakt in *Stap 3* in de **Ervaar fragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Voer de milliseconden in **Duur**.

   i. Selecteer **Offlineconfiguratie** van de **Ervaar fragmenten** om de bibliotheken aan de clientzijde en de statische bestanden te definiëren.

   >[!NOTE]
   >
   >Als u bibliotheken aan de clientzijde of de statische bestanden wilt toevoegen naast de bestanden die u in stap 4 hebt geconfigureerd, kunt u toevoegen via het menu **Offlineconfiguratie** in de **Ervaar fragment** in.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Klik op het vinkje om het proces te voltooien.

### Het resultaat valideren {#validating-the-result}

Nadat u de vorige stappen hebt uitgevoerd, kunt u het ervaringsfragment valideren in **ChannelOne** door:

1. Navigeren naar de **TestChannel**.
1. Het selecteren van **Voorvertoning** in de actiebalk.

U zult de inhoud van bekijken **Sites** pagina (live kopie van het ervaringsfragment) in uw kanaal, zoals in de onderstaande afbeelding wordt getoond:\
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png)

## Wijzigingen op de pagina doorgeven {#propagating-changes-from-the-master-page}

***Live kopie*** verwijst naar de kopie (van de bron), bijgehouden door synchronisatiehandelingen zoals gedefinieerd door de rollout-configuraties.

Sinds het fragment van de Ervaring hebben wij gecreeerd is een levende kopie van **Sites** pagina&#39;s, dus als u wijzigingen aanbrengt in dat specifieke fragment op de master pagina, zult u de wijzigingen in uw kanaal of de bestemming bekijken waar u het fragment van de Ervaring hebt gebruikt.

>[!NOTE]
>
>Zie Inhoud opnieuw gebruiken voor meer informatie over Live Copy: Beheer van meerdere sites en Live kopie.

Voer de onderstaande stappen uit om wijzigingen van het master kanaal naar het doelkanaal door te geven:

1. Selecteer het fragment van de Ervaring van **Sites** (master) pagina en klik het potloodpictogram om de punten in het Fragment van de Ervaring uit te geven.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Selecteer het fragment van de Ervaring en klik het moersleutelpictogram om de dialoogdoos te openen om de beelden uit te geven.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. De **Productraster** wordt geopend.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. U kunt alle afbeeldingen bewerken. Hier wordt bijvoorbeeld de eerste afbeelding in dit fragment vervangen.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Selecteer het fragment van de Ervaring en klik het pictogram van de Uitvoer om veranderingen in het fragment door te geven dat in uw kanaal wordt gebruikt.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Klik op Uitvoeren om de wijzigingen te bevestigen.

   U zult zien dat de wijzigingen zijn geïmplementeerd.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### De wijzigingen valideren {#validating-the-changes}

Voer de onderstaande stappen uit om de wijzigingen in uw kanaal te bevestigen:

1. Ga naar de **Schermen** -> **Kanalen** -> **TestChannel**.

1. Klikken **Voorvertoning** in de actiebalk om de wijzigingen te bevestigen.

In de volgende afbeelding worden de wijzigingen in uw **TestChannel**:\
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)
