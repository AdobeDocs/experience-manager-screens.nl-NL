---
title: Update voor on-demand inhoud
seo-title: Update voor on-demand inhoud
description: 'Volg deze pagina voor meer informatie over het bijwerken van inhoud op aanvraag.  '
seo-description: 'Volg deze pagina voor meer informatie over het bijwerken van inhoud op aanvraag.  '
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
feature: Ontwerpschermen
role: Developer
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---


# Update {#on-demand} voor on-demand inhoud

In deze sectie wordt on-demand-inhoud voor het beheer van publicaties beschreven.

## Publicatie beheren: Inhoudsupdates van auteur leveren voor publicatie op apparaat {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

U kunt inhoud vanuit AEM Screens publiceren en de publicatie ervan ongedaan maken. Met de functie Publicatie beheren kunt u inhoud-updates van de auteur leveren en op het apparaat publiceren. U kunt inhoud publiceren/unpublish voor uw volledige AEM Screens-project of slechts voor één van uw kanaal, plaats, apparaat, toepassing, of een programma.

### Publicatie beheren voor een AEM Screens-project {#managing-publication-for-an-aem-screens-project}

Voer de onderstaande stappen uit om inhoud-updates van auteur te leveren voor publicatie naar apparaat voor een AEM Screens-project:

1. Navigeer naar uw AEM Screens-project.
1. Klik **Publicatie beheren** van de actiebar om het project te publiceren om instantie te publiceren.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. De wizard **Publicatie beheren** wordt geopend. U kunt de **Actie** selecteren en ook de publicatietijd voor nu of later plannen. Klik op **Next**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Controleer de doos om het volledige project van **Manage Publication** tovenaar te selecteren.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Klik **+ omvat Kinderen** van de actiebar en uncheck alle opties om alle modules in uw project te publiceren en **te klikken toevoegen** om te publiceren.

   >[!NOTE]
   >
   >Door gebrek, zullen alle dozen worden gecontroleerd en u zult manueel uncheck de dozen moeten om alle modules in uw project te publiceren.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Inzicht in het dialoogvenster Inclusief onderliggende elementen**

   In de bovenstaande stap ziet u hoe u de volledige inhoud kunt publiceren. Als u de andere drie beschikbare alternatieven wilt gebruiken, moet u die optie controleren.
Met de volgende afbeelding kunt u bijvoorbeeld alleen de gewijzigde pagina&#39;s in uw project beheren en bijwerken:
   ![afbeelding](assets/author-publish-manage.png)

   Volg de onderstaande uitleg voor meer informatie over de beschikbare opties:

   1. **Alleen directe onderliggende** elementen opnemen: Met deze optie kunt u alleen updates voor de subknooppunten in uw projectstructuur beheren.
   1. **Alleen gewijzigde pagina**&#39;s opnemen: Met deze optie kunt u alleen updates beheren voor de gewijzigde pagina&#39;s van het project waar de wijzigingen zich bevinden in de projectstructuur.
   1. **Alleen reeds gepubliceerde pagina**&#39;s opnemen: Met deze optie kunt u alleen updates beheren voor de pagina&#39;s die eerder zijn gepubliceerd.


1. Klik **Publiceren** van **De tovenaar van de Publicatie beheren.**

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Wacht een paar seconden/minuten, zodat de inhoud de instantie publish bereikt.
   >
   >
   >    1. De workflow werkt niet als het project geen wijzigingen bevat en niets voor **Offlineinhoud bijwerken**.
   >    1. De workflow werkt niet als de auteur het replicatieproces niet voltooit (inhoud wordt nog geüpload naar een publicatieexemplaar) nadat deze op de knop **Publiceren** in de publicatieworkflow heeft geklikt.


   >[!CAUTION]
   >Als u als auteur of inhoudsmaker de wijzigingen wilt zien in de apparaten die aan de auteurinstantie zijn gekoppeld, klikt u op **Offlineinhoud bijwerken** vanaf het kanaaldashboard of door het project te selecteren. In dit geval wordt de update offline-inhoud alleen uitgevoerd in de auteurinstantie.

1. Navigeer naar het project en klik **Offline inhoud bijwerken** op de actiebalk. Deze handeling stuurt dezelfde opdracht door naar de publicatie-instantie, zodat de offline ritten ook in de publicatie-instantie worden gemaakt.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)


   >[!NOTE]
   >
   >Nadat u de publicatieworkflow voor beheren hebt voltooid en een speler naar de instantie van de auteur verwijst, moet u de update offline activeren in de auteur. De update wordt dan offline op de instantie van de auteur gemaakt.

   >[!CAUTION]
   >
   >U moet de update offline inhoud in auteursinstantie teweegbrengen, als u een speler hebt die bij de auteursserver wordt geregistreerd. Offline inhoud bijwerken is niet vereist voor de speler die is geregistreerd bij de publicatie-instantie.

### Publicatie beheren voor een kanaal {#managing-publication-for-a-channel}

Voer de onderstaande stappen uit om inhoudsupdates van auteur te leveren voor publicatie naar apparaat voor een Kanaal in een AEM Screens-project:

>[!NOTE]
>
>Volg deze sectie alleen als er wijzigingen zijn in een kanaal. Als er na de vorige update geen wijzigingen zijn aangebracht in een kanaal, werkt de publicatieworkflow voor een afzonderlijk kanaal niet.

1. Navigeer naar het project Schermen en selecteer het kanaal.
1. Klik **Publicatie beheren** van de actiebar om het kanaal te publiceren om instantie te publiceren.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. De wizard **Publicatie beheren** wordt geopend. U kunt de **Actie** selecteren en ook de publicatietijd voor nu of later plannen. Klik op **Next**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Klik **Publiceren** van **De tovenaar van de Publicatie beheren.**

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Wacht een paar seconden/minuten, zodat de inhoud de instantie publish bereikt.

1. Trigger **Offline inhoud bijwerken** in het kanaaldashboard zal de offline inhoud alleen naar de auteurinstantie duwen, maar niet instantie publiceren. De stappen 1-4 zijn voor het drukken van off-line inhoud om instantie te publiceren.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >U moet eerst de update offline inhoud publiceren en vervolgens activeren, zoals samengevat in de voorgaande stappen.

### Opnieuw toewijzen kanaal en apparaat: {#channel-and-device-re-assignment}

Als u een apparaat opnieuw hebt toegewezen, moet u zowel de eerste weergave als de nieuwe weergave publiceren zodra het apparaat opnieuw is toegewezen aan de nieuwe weergave.

Als u een kanaal opnieuw hebt toegewezen, moet u ook zowel de eerste weergave als de nieuwe weergave publiceren zodra het kanaal opnieuw is toegewezen aan de nieuwe weergave.