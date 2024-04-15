---
title: Beleidsfragmenten gebruiken
description: Meer informatie over het gebruik van Experience Fragments in AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Experience Fragments
role: Admin, Developer
level: Intermediate
exl-id: 13c0d75e-435f-433e-8886-f451df863517
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---

# Beleidsfragmenten gebruiken {#using-experience-fragments}

Deze pagina behandelt de volgende onderwerpen:

* **Overzicht**
* **Experience Fragments gebruiken in AEM Screens**
* **Wijzigingen op de pagina doorgeven**

## Overzicht {#overview}

An ***Ervaar fragment*** is een groep van één of meerdere componenten met inbegrip van inhoud en lay-out die binnen pagina&#39;s kunnen worden van verwijzingen voorzien. De fragmenten van de ervaring kunnen om het even welke component, zoals één of veelvoudige componenten bevatten die om het even wat binnen een paragraafsysteem kunnen bevatten dat in de volledige ervaring van verwijzingen wordt voorzien of door een derde eindpunt wordt gevraagd.


## Experience Fragments gebruiken in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>In het volgende voorbeeld wordt **`We.Retail`** als een demoproject van waar het Fragment van de Ervaring van een wordt toegepast **Sites** pagina naar een AEM Screens-project.

De volgende workflow toont bijvoorbeeld het gebruik van ervaringsfragmenten uit `We.Retail` in sites. U kunt een webpagina kiezen en die inhoud in uw AEM Screens-kanaal gebruiken in een van uw projecten.

### Voorwaarden {#pre-requisites}

**Een demoproject maken met een kanaal**

***Een project maken***

1. Als u een project wilt maken, selecteert u **Schermproject maken**.
1. Voer de titel in als **DemoProject**.
1. Selecteren **Opslaan**.

A **DemoProject** wordt toegevoegd aan je AEM Screens.

***Een kanaal maken***

1. Ga naar de **DemoProject** u creeerde en selecteert **Kanalen** map.

1. Selecteren **Maken** in de actiebalk, zodat u de wizard kunt openen.
1. Kies de optie **Volgekanaal** sjabloon in de wizard en selecteer **Volgende**.

1. Voer de **Titel** als **TestChannel** en selecteert u **Maken**.

A **TestChannel** wordt toegevoegd aan uw **DemoProject**.\
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Een ervaringsfragment maken {#creating-an-experience-fragment}

Voer de onderstaande stappen uit om de inhoud toe te passen van **`We.Retail`** aan uw **TestChannel** in **DemoProject**.

1. **Navigeer aan een pagina van Plaatsen in Wij.Retail**

   1. Ga naar sites en selecteer **`We.Retail`** > **Verenigde Staten** > **Engels** > **Apparatuur** en selecteert u deze pagina zodat u deze kunt gebruiken als een ervaringsfragment voor uw rasterkanaal.

   1. Selecteren **Bewerken** op de actiebalk, zodat u de pagina kunt openen die u als ervaringsfragment voor het kanaal Schermen wilt gebruiken.

1. **De inhoud opnieuw gebruiken**

   1. Selecteer het fragment dat u in het kanaal wilt opnemen.
   1. Selecteer het laatste pictogram aan de rechterkant zodat u het dialoogvenster **Omzetten in ervaringsfragment** in.

   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Een ervaringsfragment maken**

   1. Kies de optie **Handeling** als **Een nieuw ervaringsfragment maken**.

   1. Selecteer de **Bovenliggend pad**.
   1. Selecteer de **Sjabloon**. Kies de optie **Ervaring fragment - rastervariatie** sjabloon hier (waarde in veld) `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).

   1. Voer de **Fragmenttitel** als **ScreensFragment**.

   1. Selecteer het vinkje om het maken van een nieuw ervaringsfragment te voltooien.

   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

   Opmerking: als u een eenvoudigere optie wilt selecteren, selecteert u het vinkje rechts van het veld, zodat u het dialoogvenster Selecteren kunt openen.

1. **Actieve kopie van ervaringsfragment maken**

   1. Navigeer naar de AEM startpagina.
   1. Selecteren **Ervaar fragmenten** en de **ScreensFragment** en selecteert u **Variatie als live-kopie**, zoals weergegeven in onderstaande afbeelding:

   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Selecteer de **ScreensFragment** van **Live kopie maken** wizard en selecteert u **Volgende**.

   d. Voer de **Titel** en **Naam** als **Schermen**.

   e. Selecteren **Maken** zodat u de Live kopie kunt maken.

   f. Selecteren **Gereed** zodat u kunt terugkeren naar **ScreensFragment** pagina.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nadat u een AEM Screens-fragment hebt gemaakt, kunt u de eigenschappen van het fragment bewerken. Selecteer het fragment en selecteer **Eigenschappen** in de actiebalk.

   **Eigenschappen van een rasterfragment bewerken**

   1. Ga naar de **ScreensFragment** (u hebt in de voorgaande stappen gemaakt) en selecteert u **Eigenschappen** in de actiebalk.

   1. Selecteer de **Offline configuratie** zoals weergegeven in de onderstaande afbeelding.

   U kunt de **Client-side bibliotheken** (Java™ en css) en **Statische bestanden** naar uw ervaringsfragment.

   In het volgende voorbeeld ziet u de toevoeging van bibliotheken aan de clientzijde en de lettertypen als onderdeel van statische bestanden aan uw Experience Fragment.  ![fragment](assets/fragment.gif)

1. **Experience Fragment gebruiken als component in Screenkanaal**

   1. Navigeer naar het kanaal van het Scherm waar u wilt gebruiken **Schermen** fragment.
   1. Selecteer de **TestChannel** en selecteert u **Bewerken** in de actiebalk.

   1. Selecteer het componentenpictogram van de zijtabel.
   1. Sleep de **Ervaar fragment** naar uw kanaal.

   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Selecteer de **Ervaar fragment** en selecteer het pictogram linksboven zodat u het dialoogvenster **Ervaar fragment** in.

   f. Selecteer de **Schermen** live kopie van het fragment dat u hebt gemaakt in *Stap 3* in **Pad**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Selecteer de **Schermen** live kopie van het fragment dat u hebt gemaakt in *Stap 3* in de **Ervaar fragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Voer de milliseconden in **Duur**.

   i. Selecteer de optie **Offline configuratie** van de **Ervaar fragmenten** zodat u de bibliotheken aan de clientzijde en de statische bestanden kunt definiëren.

   >[!NOTE]
   >
   >Als u clientbibliotheken of statische bestanden wilt toevoegen naast de bestanden die u in stap 4 hebt geconfigureerd, kunt u toevoegen via het menu **Offline configuratie** in de **Ervaar fragment** in.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Selecteer het vinkje zodat u het proces kunt voltooien.

### Het resultaat valideren {#validating-the-result}

Nadat u de vorige stappen hebt uitgevoerd, kunt u het fragment van uw ervaring valideren in **ChannelOne** door:

1. Navigeren naar de **TestChannel**.
1. De **Voorvertoning** in de actiebalk.

De inhoud weergeven vanuit de **Sites** pagina (live kopie van het Experience Fragment) in uw kanaal, zoals in de onderstaande afbeelding wordt getoond:\
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png)

## Wijzigingen op de pagina doorgeven {#propagating-changes-from-the-master-page}

***Live kopie*** verwijst naar de kopie (van de bron), bijgehouden door synchronisatiehandelingen zoals gedefinieerd door de rollout-configuraties.

Omdat het ervaringsfragment dat u hebt gemaakt, een live kopie is van het dialoogvenster **Sites** pagina&#39;s, en u verandert dat bepaalde fragment van de primaire pagina, bekijkt u de veranderingen in uw kanaal. Of bekijk de bestemming waar u het fragment van de Ervaring hebt gebruikt.

>[!NOTE]
>
>Zie Inhoud hergebruiken: Multisite Manager en Live Copy voor meer informatie over Live Copy.

Voer de onderstaande stappen uit om wijzigingen van het primaire kanaal naar het doelkanaal door te geven:

1. Selecteer het fragment van de Ervaring van **Sites** (primaire) pagina en selecteer het potloodpictogram zodat u de items in het ervaringsfragment kunt bewerken.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Selecteer het fragment van de Ervaring en selecteer het moersleutelpictogram zodat kunt u de dialoogdoos openen om de beelden uit te geven.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. De **Productraster** wordt geopend.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. U kunt alle afbeeldingen bewerken. Hier wordt bijvoorbeeld de eerste afbeelding in dit fragment vervangen.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Selecteer het fragment van de Ervaring en selecteer het pictogram van de Uitvoer zodat kunt u veranderingen in het fragment verspreiden dat in uw kanaal wordt gebruikt.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Selecteer Uitvoer.

   De wijzigingen worden uitgevoerd.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### De wijzigingen valideren {#validating-the-changes}

Voer de onderstaande stappen uit om de wijzigingen in uw kanaal te bevestigen:

1. Ga naar de **Schermen** > **Kanalen** > **TestChannel**.

1. Selecteren **Voorvertoning** in de actiebalk.

In de volgende afbeelding ziet u de wijzigingen in uw **TestChannel**:\
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)
