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
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 0%

---

# Beleidsfragmenten gebruiken {#using-experience-fragments}

Deze pagina behandelt de volgende onderwerpen:

* **Overzicht**
* **Gebruikend de Fragmenten van de Ervaring in AEM Screens**
* **het Doorgeven verandert in de Pagina**

## Overzicht {#overview}

Een ***Fragment van de Ervaring*** is een groep van één of meerdere componenten met inbegrip van inhoud en lay-out die binnen pagina&#39;s van verwijzingen kunnen worden voorzien. De Fragmenten van de ervaring kunnen om het even welke component bevatten. Bijvoorbeeld, kan het één of veelvoudige componenten bevatten die om het even wat binnen een paragraafsysteem kunnen bevatten dat in de volledige ervaring van verwijzingen wordt voorzien of door een derde eindpunt wordt gevraagd.


## Experience Fragments gebruiken in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>Het volgende voorbeeld gebruikt **`We.Retail`** als demoproject van waar het Fragment van de Ervaring van de pagina van a **Plaatsen** aan een project van AEM Screens wordt toegepast.

De volgende workflow toont bijvoorbeeld het gebruik van Experience Fragments van `We.Retail` in Sites. U kunt een webpagina kiezen en die inhoud in uw AEM Screens-kanaal gebruiken in een van uw projecten.

### Voorwaarden {#pre-requisites}

**Creërend een Project van de Demo met een Kanaal**

***Creërend een Project***

1. Om een project tot stand te brengen, klik **creëren het Project van Screens**.
1. Ga de Titel als **DemoProject** in.
1. Klik **sparen**.

A **DemoProject** wordt toegevoegd aan uw AEM Screens.

***Creërend een Kanaal***

1. Navigeer aan **DemoProject** u creeerde en klik de **omslag van Kanalen**.

1. Klik **creëren** van de actiebar zodat kunt u de tovenaar openen.
1. Kies het **malplaatje van het Kanaal van de Opeenvolging 1&rbrace; van de tovenaar en klik** daarna **.**

1. Ga de **Titel** als **TestChannel** in en klik **creeer**.

A **TestChannel** wordt toegevoegd aan uw **DemoProject**.\
![&#x200B; screen_shot_2019-07-29at105101am &#x200B;](assets/screen_shot_2019-07-29at105101am.png)


### Een ervaringsfragment maken {#creating-an-experience-fragment}

Volg hieronder de stappen om de inhoud van **`We.Retail`** op uw **TestChannel** in **DemoProject** toe te passen.

1. **navigeer aan een pagina van Plaatsen in Wij.Retail**

   1. Navigeer aan Plaatsen en klik **`We.Retail`** > **Verenigde Staten** > **Engels** > **Apparatuur** en klik deze pagina zodat kunt u het als Fragment van de Ervaring voor uw kanaal van Screens gebruiken.

   1. Klik **uitgeven** van de actiebar zodat kunt u de pagina openen u als Fragment van de Ervaring voor uw kanaal van Screens wilt gebruiken.

1. **opnieuw gebruikend de Inhoud**

   1. Klik op het fragment dat u in het kanaal wilt opnemen.
   1. Klik het laatste pictogram van het recht zodat kunt u **Bekeerling in de dialoogdoos van het Fragment van de Ervaring** openen.

   ![&#x200B; screen_shot_2019-07-29at105314am &#x200B;](assets/screen_shot_2019-07-29at105314am.png)

1. **Creërend een Fragment van de Ervaring**

   1. Kies de **Actie** aangezien **tot een nieuw Fragment van de Ervaring** leidt.

   1. Klik de **weg van de Ouder**.
   1. Klik het **Malplaatje**. Kies het **Fragment van de Ervaring - het malplaatje van de Variatie van Screens** hier (waarde op het gebied `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).

   1. Ga de **Titel van het Fragment** als **ScreensFragment** in.

   1. Klik op het vinkje om het maken van een nieuw ervaringsfragment te voltooien.

   ![&#x200B; screen_shot_2019-07-29at105918am &#x200B;](assets/screen_shot_2019-07-29at105918am.png)

   Als u een eenvoudigere optie wilt selecteren, klikt u op het vinkje rechts van het veld, zodat u het dialoogvenster Selecteren kunt openen.

1. **Creërend Levend Exemplaar van het Fragment van de Ervaring**

   1. Navigeer naar de AEM startpagina.
   1. Klik **Fragmenten van de Ervaring** en benadruk **ScreensFragment** en klik **Variatie als levende-exemplaar**, zoals aangetoond in het hieronder cijfer:

   ![&#x200B; screen_shot_2019-07-29at110443am &#x200B;](assets/screen_shot_2019-07-29at110443am.png)

   c. Klik **ScreensFragment** van **creeer Levende tovenaar van het Exemplaar** en klik **daarna**.

   d. Ga de **Titel** en **Naam** in als **Screens**.

   e. Klik **creëren** zodat kunt u Levende Exemplaar tot stand brengen.

   f. Klik **Gedaan** zodat kunt u zich naar de **ScreenFragment** pagina bewegen.

   ![&#x200B; screen_shot_2019-07-29at110616am &#x200B;](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Nadat u een AEM Screens-fragment hebt gemaakt, kunt u de eigenschappen van het fragment bewerken. Klik het fragment en klik **Eigenschappen** van de actiebar.

   **het Uitgeven Eigenschappen van een Fragment van Screens**

   1. Navigeer aan **ScreensFragment** (u creeerde in de voorafgaande stappen) en klik **Eigenschappen** van de actiebar.

   1. Klik het **Off-line Config** lusje, zoals aangetoond in het hieronder cijfer.

   U kunt de **cliënt-zijBibliotheken** (Java™ en CSS) en **Statische Dossiers** aan uw Fragment van de Ervaring toevoegen.

   In het volgende voorbeeld ziet u de toevoeging van bibliotheken aan de clientzijde en de lettertypen als onderdeel van statische bestanden aan uw Experience Fragment.  ![&#x200B; fragment &#x200B;](assets/fragment.gif)

1. **Gebruikend het Fragment van de Ervaring als Component in het Kanaal van Screens**

   1. Navigeer aan het kanaal van Screens waar u het **Screens** fragment wilt gebruiken.
   1. Klik **TestChannel** en klik **uitgeven** van de actiebar.

   1. Klik op het componentpictogram op het zijtabblad.
   1. De belemmering en laat vallen het **Fragment van de Ervaring** aan uw kanaal.

   ![&#x200B; screen_shot_2019-07-29at123115pm &#x200B;](assets/screen_shot_2019-07-29at123115pm.png)

   e. Klik de **component van het Fragment van de Ervaring 0&rbrace; &lbrace;en klik het hoogste linker (moersleutel) pictogram zodat kunt u het** de dialoogvakje van het Fragment van de Ervaring **openen.**

   f. Klik het **Levende Exemplaar van Screens** van het fragment dat u in *Stap 3* in **Weg** creeerde.

   ![&#x200B; screen_shot_2019-07-26at82650pm &#x200B;](assets/screen_shot_2019-07-26at82650pm.png)

   f. Klik het **Levende Exemplaar van Screens** van het fragment dat u in *Stap 3* in het **Fragment van de Ervaring** creeerde.

   ![&#x200B; screen_shot_2019-07-26at82509pm &#x200B;](assets/screen_shot_2019-07-26at82509pm.png)

   h. Ga de milliseconden in **Duur** in.

   i. Klik **Offline Config** van het **de dialoogvakje van de Fragmenten van de Ervaring** zodat kunt u de cliënt-zijbibliotheken en de statische dossiers bepalen.

   >[!NOTE]
   >
   >Om cliënt-zijbibliotheken, of de statische dossiers naast toe te voegen wat u in stap (4) vormde, kunt u van het **Off-line lusje Config** in het **de dialoogvakje van het Fragment van de Ervaring** toevoegen.

   ![&#x200B; screen_shot_2019-07-26at82844pm &#x200B;](assets/screen_shot_2019-07-26at82844pm.png)

   j. Klik op het vinkje zodat u het proces kunt voltooien.

### Het resultaat valideren {#validating-the-result}

Na voltooiing van de voorafgaande stappen, kunt u uw Fragment van de Ervaring in **ChannelOne** bevestigen door:

1. Het navigeren aan **TestChannel**.
1. Het selecteren van **Voorproef** van de actiebar.

Bekijk de inhoud van de **pagina van Plaatsen** (levend-exemplaar van het Fragment van de Ervaring) in uw kanaal, zoals aangetoond in het hieronder cijfer:\
![&#x200B; screen_shot_2018-06-08at120739pm &#x200B;](assets/screen_shot_2018-06-08at120739pm.png)

## Wijzigingen op de pagina doorgeven {#propagating-changes-from-the-master-page}

***Levende Exemplaar*** verwijst naar het exemplaar (van de bron), dat door synchronisatieacties zoals die door de rollout configuraties worden bepaald wordt gehandhaafd.

Omdat het Fragment van de Ervaring u creeerde een Levende Exemplaar van de **Pagina&#39;s van Plaatsen** is, en u dat specifiek fragment van de primaire pagina verandert, bekijkt u de veranderingen in uw kanaal. Of bekijk de bestemming waar u het fragment van de Ervaring hebt gebruikt.

>[!NOTE]
>
>Zie Inhoud hergebruiken: Multisite Manager en Live Copy voor meer informatie over Live Copy.

Voer de onderstaande stappen uit om wijzigingen van het primaire kanaal naar het doelkanaal door te geven:

1. Klik het Fragment van de Ervaring van de **(primaire) pagina van Plaatsen** en klik het potloodpictogram zodat kunt u de punten in het Fragment van de Ervaring uitgeven.

   ![&#x200B; screen_shot_2018-06-08at122655pm &#x200B;](assets/screen_shot_2018-06-08at122655pm.png)

1. Klik op het fragment Ervaring en klik op het moersleutelpictogram zodat u het dialoogvenster kunt openen om de afbeeldingen te bewerken.

   ![&#x200B; screen_shot_2018-06-08at25031pm &#x200B;](assets/screen_shot_2018-06-08at25031pm.png)

1. Het **de dialoogvakje van het Net van het Product van 0&rbrace; &lbrace;opent.**

   ![&#x200B; screen_shot_2018-06-08at25306pm &#x200B;](assets/screen_shot_2018-06-08at25306pm.png)

1. U kunt alle afbeeldingen bewerken. Hier wordt bijvoorbeeld de eerste afbeelding in dit fragment vervangen.

   ![&#x200B; screen_shot_2018-06-08at25608pm &#x200B;](assets/screen_shot_2018-06-08at25608pm.png)

1. Klik op het fragment Ervaring en klik op het pictogram Uitvoer, zodat u wijzigingen kunt doorgeven aan het fragment dat in het kanaal wordt gebruikt.

   ![&#x200B; screen_shot_2018-06-08at31352pm &#x200B;](assets/screen_shot_2018-06-08at31352pm.png)

1. Klik op Uitvoeren.

   De wijzigingen worden uitgevoerd.

   ![&#x200B; screen_shot_2018-06-08at32148pm &#x200B;](assets/screen_shot_2018-06-08at32148pm.png)

### De wijzigingen valideren {#validating-the-changes}

Voer de onderstaande stappen uit om de wijzigingen in uw kanaal te bevestigen:

1. Navigeer aan **Screens** > **Kanalen** > **TestChannel**.

1. Klik **Voorproef** van de actiebar.

Het volgende beeld illustreert de veranderingen in uw **TestChannel**:\
![&#x200B; screen_shot_2018-06-08at33351pm &#x200B;](assets/screen_shot_2018-06-08at33351pm.png)
