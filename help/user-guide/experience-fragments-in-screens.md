---
title: Ervaringsfragmenten gebruiken
seo-title: Ervaringsfragmenten gebruiken
description: 'Volg deze pagina voor meer informatie over het gebruik van Experience Fragments in AEM-schermen. '
seo-description: 'Volg deze pagina voor meer informatie over het gebruik van Experience Fragments in AEM-schermen. '
uuid: 6ee16a94-3c53-43e0-99d5-c35cb9e01120
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 0e88e9e0-a95b-4acd-98ea-499d4d4e3c99
docset: aem65
translation-type: tm+mt
source-git-commit: 87961076fd756c8bd018ded08d493e4024992738
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---


# Ervaringsfragmenten gebruiken {#using-experience-fragments}

Deze pagina behandelt de volgende onderwerpen:

* **Overzicht**
* **Experience Fragments gebruiken in AEM-schermen**
* **Wijzigingen doorgeven vanaf de stramienpagina**

## Overzicht {#overview}

Een fragment ***van de*** Ervaring is een groep van één of meerdere componenten met inbegrip van inhoud en lay-out die binnen pagina&#39;s van verwijzingen kunnen worden voorzien. De fragmenten van de ervaring kunnen om het even welke component, zoals, één of veelvoudige componenten bevatten die om het even wat binnen een paragraafsysteem kunnen bevatten, die in de volledige ervaring zullen worden van verwijzingen voorzien of door een derde eindpunt gevraagd.


## Experience Fragments gebruiken in AEM-schermen {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>
>Het volgende voorbeeld gebruikt **We.Retail** als demoproject van waar het Fragment van de Ervaring van een pagina van **Plaatsen** aan een project van het Scherm AEM wordt gebruikt.

Als voorbeeld, toont het volgende werkschema het gebruik van ervaringsfragmenten van We.Retail in Plaatsen. U kunt een webpagina kiezen en die inhoud gebruiken in uw AEM-rasterkanaal in een van uw projecten.

### Voorwaarden {#pre-requisites}

**Een demoproject maken met een kanaal**

***Een project maken***

1. Klik op Schermproject **** maken om een nieuw project te maken.
1. Voer de titel in als **DemoProject**.
1. Click **Save**.

Er wordt een **DemoProject** toegevoegd aan uw AEM-schermen.

***Een kanaal maken***

1. Navigeer naar het **DemoProject** dat u hebt gemaakt en selecteer de map **Kanalen** .

1. Klik op **Maken** op de actiebalk om de wizard te openen.
1. Kies de sjabloon **Volgkanaal** in de wizard en klik op **Volgende**.

1. Voer de **titel** in als **TestChannel** en klik op **Maken**.

Er wordt een **TestChannel** toegevoegd aan uw **DemoProject**.\
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Een ervaringsfragment maken {#creating-an-experience-fragment}

Volg de onderstaande stappen om de inhoud van **We.Retail** naar uw **TestChannel** in **DemoProject** te gebruiken.

1. **Navigeer aan een pagina van Plaatsen in Wij.Retail**

   1. Navigeer naar Sites en selecteer **We.Retail In-Store** -> **Verenigde Staten** ->**Engels** en selecteer de pagina **Apparatuur** om dit als ervaringsfragment voor uw kanaal van het Scherm te gebruiken.

   1. Klik op **Bewerken** op de actiebalk om de pagina te openen die u wilt gebruiken als ervaringsfragment voor het kanaal Schermen.

      ![screen_shot_2018-06-06at105309am](assets/screen_shot_2018-06-06at105309am.png)

1. **De inhoud opnieuw gebruiken**

   1. Selecteer het fragment dat u in het kanaal wilt opnemen.
   1. Klik op het laatste pictogram aan de rechterkant om het dialoogvenster **Omzetten in ervaring met fragmenten** te openen.
   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Experience-fragment maken**

   1. Kies de **handeling** als **Een nieuw ervaringsfragment** maken.

   1. Selecteer het **bovenliggende pad**.
   1. Select the **Template**. Kies hier het fragment **Ervaring - de sjabloon Variatie** van schermen.

   1. Voer de titel **van het** fragment in als **rasterfragment**.

   1. Klik op het vinkje om het maken van een nieuw ervaringsfragment te voltooien.
   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

1. **Actieve kopie van ervaringsfragment maken**

   1. Navigeer naar de AEM-startpagina.
   1. Selecteer Fragmenten **van de** Ervaring en benadruk het **Schermfragment** en klik **Variatie als levende exemplaar**, zoals aangetoond in het hieronder cijfer:
   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Selecteer de wizard* ScreensFragment** van de wizard **Create Live Copy** en klik op **Volgende**.

   d. Voer de **titel** en de **naam** in als **schermen**.

   e. Klik op **Maken** om de actieve kopie te maken.

   f. Klik op **Gereed** om terug te gaan naar de pagina **ScreensFragment** .

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nadat u het fragment Schermen hebt gemaakt, kunt u de eigenschappen van het fragment bewerken. Selecteer het fragment en klik op **Eigenschappen** op de actiebalk.

   **Eigenschappen van een rasterfragment bewerken**

   1. Navigeer naar het **ScreenFragment** (u hebt in de voorgaande stappen gemaakt) en klik op **Eigenschappen** op de actiebalk.

   1. Selecteer het tabblad **Offlineconfig** , zoals in de onderstaande afbeelding wordt getoond.
   U kunt de bibliotheken **aan de** clientzijde (Java en css) en de **statische bestanden** toevoegen aan het ervaringsfragment.

   In het volgende voorbeeld ziet u de toevoeging van bibliotheken aan de clientzijde en de lettertypen als onderdeel van statische bestanden aan uw ervaringsfragment.  ![fragment](assets/fragment.gif)

1. **Experience Fragment gebruiken als component in Screenkanaal**

   1. Navigeer naar het kanaal Schermen waar u het fragment **Screens** wilt gebruiken.
   1. Selecteer **TestChannel** en klik **uitgeven** van de actiebar.

   1. Klik op het componentpictogram op het zijtabblad.
   1. Sleep het fragment **van de** Ervaring naar uw kanaal.
   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Selecteer de component Fragment **van de** Ervaring en selecteer het hoogste linker (sleutel) pictogram om de de dialoogdoos van het Fragment **van de** Ervaring te openen.

   f. Selecteer de live **schermkopie** van het fragment dat u hebt gemaakt in *stap 3* in **pad**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Selecteer de live **schermkopie** van het fragment dat u hebt gemaakt in *stap 3* in het **ervaringsfragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Voer de milliseconden in in **Duur**.

   i. Selecteer de **Offlineconfig** van de de dialoogdoos van de Fragmenten **van de** Ervaring om de cliënt-zijbibliotheken en de statische dossiers te bepalen.

   >[!NOTE]
   >
   >Als u bibliotheken aan de clientzijde of de statische bestanden wilt toevoegen naast de bestanden die u hebt geconfigureerd in stap 4, kunt u toevoegen via het tabblad **Offlineconfig** in het dialoogvenster **Ervingsfragment** .

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Klik op het vinkje om het proces te voltooien.

### Het resultaat valideren {#validating-the-result}

Nadat u de vorige stappen hebt uitgevoerd, kunt u het ervaringsfragment in **ChannelOne** valideren door:

1. Navigeer naar **TestChannel**.
1. De **voorvertoning** selecteren in de actiebalk.

U geeft de inhoud van de pagina **Sites** (live kopie van het ervaringsfragment) in uw kanaal weer, zoals in de onderstaande afbeelding wordt getoond:\
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png)

## Wijzigingen doorgeven vanaf de stramienpagina {#propagating-changes-from-the-master-page}

***Live Copy*** verwijst naar de kopie (van de bron), onderhouden door synchronisatiehandelingen zoals gedefinieerd door de rollout-configuraties.

Omdat het ervaringsfragment een live kopie van de **sitepagina&#39;s** is, kunt u de wijzigingen in het desbetreffende fragment bekijken op de stramienpagina of op de bestemming waar u het ervaringsfragment hebt gebruikt.

>[!NOTE]
>
>Zie Inhoud opnieuw gebruiken voor meer informatie over Live Copy: Beheer van meerdere sites en Live kopie.

Voer de onderstaande stappen uit om wijzigingen van het hoofdkanaal naar het doelkanaal door te geven:

1. Selecteer het fragment van de Ervaring van de pagina van **Plaatsen** (Hoofd) en klik het potloodpictogram om de punten in het Fragment van de Ervaring uit te geven.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Selecteer het fragment van de Ervaring en klik het moersleutelpictogram om de dialoogdoos te openen om de beelden uit te geven.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. Het dialoogvenster **Productraster** wordt geopend.

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

1. Navigeer naar de **rasters** -> **Kanalen** -> **TestChannel**.

1. Klik op **Voorvertoning** op de actiebalk om de wijzigingen te bevestigen.

De volgende afbeelding illustreert de wijzigingen in uw **TestChannel**:\
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)

