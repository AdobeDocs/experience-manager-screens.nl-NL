---
title: Spraakherkenning in AEM Screens
description: Meer weten over stemherkenning en hoe je deze kunt gebruiken in AEM Screens?
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 6cf0aa9f-7bac-403f-a113-51727c1f5374
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 1%

---

# Spraakherkenning in AEM Screens {#voice-recognition}

>[!IMPORTANT]
>
>**Belangrijke privacygegevens**
>
>Wanneer het gebruiken van de eigenschap van de stemerkenning, volg alle toepasselijke wettelijke en ethische richtlijnen voor uw regio (met inbegrip van maar niet beperkt tot het verstrekken van een zichtbare kennisgeving aan eind - gebruikers dat de speler de Erkenning van de Stem gebruikt). De Adobe ontvangt, slaat, of verwerkt geen van de op stem betrekking hebbende informatie op. De AEM Screens-spelers gebruiken de standaard webspraak-API die in de bladerengine is ingebouwd. Achter de schermen verzendt deze API een golfvorm van uw toespraak naar Google-servers voor conversie van spraak naar tekst en deze tekst wordt door de speler vergeleken met geconfigureerde trefwoorden.
>
>Zie [Google Privacy White paper on web speech API](https://www.google.com/chrome/privacy/whitepaper.html#speech) voor meer informatie .


De eigenschap van de stemerkenning staat inhoudsverandering in een kanaal van AEM Screens toe dat door steminteractie wordt gedreven.

Een inhoudauteur kan een vertoning vormen om toegelaten stem te zijn. Het doel van deze eigenschap is klanten toespraak als methode te laten gebruiken om met hun vertoningen in wisselwerking te staan. Tot andere gebruiksgevallen behoren het vinden van productaanbevelingen in winkels, het bestellen van menu-items in restaurants en diners. Deze functie vergroot de toegankelijkheid voor gebruikers en kan de gebruikerservaring aanzienlijk verbeteren.

>[!NOTE]
>De spelerhardware moet audio-invoer, zoals een microfoon, ondersteunen.

## Spraakherkenning implementeren {#implementing}

>[!IMPORTANT]
> De functie voor spraakherkenning is alleen beschikbaar voor Chrome OS- en Windows-spelers.

Om stemerkenning in uw project van AEM Screens uit te voeren, laat de stemerkenning voor de Vertoning toe en associeer elk kanaal met een unieke markering om een kanaalovergang teweeg te brengen.

In de volgende sectie wordt beschreven hoe u de functie voor spraakherkenning in een AEM Screens-project kunt inschakelen en gebruiken.

## Inhoud weergeven in Volledig scherm of Kanaalschakelaar splitsen {#sequence-channel}

Alvorens u de eigenschap van de stemerkenning gebruikt, zorg ervoor u een project en een kanaal met inhoud hebt opstelling voor uw project.

1. In het volgende voorbeeld ziet u een demo-project met de naam **VoiceDemo** en drie volgordekanalen **Hoofd**, **ColdDrinks**, en **HotDrinks**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](assets/voice-recognition/vr-1.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over het maken van een kanaal of het toevoegen van inhoud aan een kanaal naar [Kanalen maken en beheren](/help/user-guide/managing-channels.md)

   Of,

   U kunt drie volgordekanalen maken **Hoofd**, **ColdDrinks**, en **HotDrinks** en een ander kanaal met 1 x 2 gesplitste schermen **SplitScreen** zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](assets/voice-recognition/vr-emb-1.png)

1. Navigeer naar elk kanaal en voeg inhoud toe. Blader bijvoorbeeld naar **VoiceDemo** > **Kanalen** > **Hoofd** en klik op het kanaal. Klikken **Bewerken** voegt u vervolgens naar wens inhoud (afbeeldingen/video&#39;s) toe op de actiebalk. Voeg op dezelfde manier inhoud toe aan beide **ColdDrinks** en de **HotDrinks** kanaal.

   De kanalen bevatten nu elementen (afbeeldingen), zoals in de onderstaande afbeeldingen wordt getoond.

   **Hoofd**:

   ![afbeelding](assets/voice-recognition/vr-4.png)

   **ColdDrinks**:

   ![afbeelding](assets/voice-recognition/vr-3.png)

   **HotDrinks**:

   ![afbeelding](assets/voice-recognition/vr-2.png)

   Als u het kanaal Gesplitste schermen aan uw project hebt toegevoegd, navigeert u naar **SplitScreen** en twee ingesloten reeksen slepen en neerzetten en paden toevoegen aan beide **ColdDrinks** en **HotDrinks** kanaal zoals weergegeven in de onderstaande afbeelding.
   ![afbeelding](assets/voice-recognition/vr-emb-6.png)


### Labels instellen voor kanalen {#setting-tags}

Nadat u inhoud aan uw kanalen hebt toegevoegd, navigeer aan elk van de kanalen en voeg aangewezen markeringen toe die de stemerkenning zouden teweegbrengen.

Voer de onderstaande stappen uit om codes aan uw kanaal toe te voegen:

1. Navigeer naar elk kanaal en voeg inhoud toe. Blader bijvoorbeeld naar **VoiceDemo** > **Kanalen** > **Hoofd** en klik op het kanaal.

1. Klikken **Eigenschappen** in de actiebalk.

   ![afbeelding](assets/voice-recognition/vr-5.png)

1. Ga naar de **Basisbeginselen** klikt u vervolgens op een bestaande tag in het menu **Tags** of maak er een.

   U kunt een tag maken door een nieuwe naam voor de tag in te voeren en op `return` sleutel, zoals weergegeven in onderstaande afbeelding:

   ![afbeelding](assets/voice-recognition/vr-6.png)

   Of,

   U kunt ook van tevoren voor uw project tags maken van uw AEM en op deze tags klikken. Nadat u de in [Tags maken](#creating-tags)kunt u op de tag klikken vanaf de locatie en deze toevoegen aan het kanaal, zoals in de onderstaande afbeelding wordt getoond:

   ![afbeelding](assets/voice-recognition/vr-tag1.png)

1. U kunt ook tag toevoegen met de naam **heet** aan de **HotDrinks** kanaal.

1. Als u een kanaal voor gesplitste schermen gebruikt, voegt u beide tags toe (**heet** en **koud**) aan de **SplitScreen** kanaaleigenschappen, zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](assets/voice-recognition/vr-emb-7.png)

1. Klikken **Opslaan en sluiten** als u klaar bent.


### Tags maken {#creating-tags}

Ga als volgt te werk om labels te maken:

1. Navigeer naar de AEM.

1. Klik op het pictogram Gereedschappen > **Tags**.
   ![afbeelding](assets/voice-recognition/vr-7.png)

1. Klikken **Maken** > **Naamruimte maken**.
   ![afbeelding](assets/voice-recognition/vr-tag3.png)

1. Voer bijvoorbeeld de naam van het project in. **VoiceDemo** en klik op **Maken**.

1. Klik op de knop **VoiceDemo** project en klik **Tag maken** in de actiebalk.
   ![afbeelding](assets/voice-recognition/vr-tag4.png)

1. Voer de naam van de tag in en klik op **Verzenden**.
   ![afbeelding](assets/voice-recognition/vr-tag5.png)

U kunt deze labels nu gebruiken in uw AEM Screens-project.

### Het toewijzen van Kanaal aan een Vertoning en het toelaten van de Erkenning van de Stem {#channel-assignment}

1. Een weergave maken in het dialoogvenster **Locaties** map, zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](assets/voice-recognition/vr-loc.png)

   >[!NOTE]
   >Ga voor meer informatie over het toewijzen van een kanaal aan een weergave naar [Weergaven maken en beheren](/help/user-guide/managing-displays.md).

1. Kanalen toewijzen **Hoofd**, **ColdDrinks**, en **HotDrinks** aan uw **LobbyDisplay**. Ook als u de **SplitScreen** kanaal voor uw project, zorg ervoor u dat ook aan de vertoning toewijst.

   >[!NOTE]
   >Als u een gesplitst-rasterkanaal hebt gemaakt, wijst u het **SplitScreen** naar het scherm.

1. Stel de volgende eigenschappen in voor elk kanaal terwijl u het kanaal toewijst.

   | **Kanaalnaam** | **Prioriteit** | **Ondersteunde gebeurtenissen** |
   |---|---|---|
   | Hoofd | 2 | Eerste belasting, inactief scherm, Timer |
   | HotDrinks | 1 | Gebruikersinteractie |
   | ColdDrinks | 1 | Gebruikersinteractie |
   | SplitScreen | 1 | Gebruikersinteractie |

   >[!NOTE]
   >
   >Ga voor meer informatie over het toewijzen van een kanaal aan een weergave naar [Weergaven maken en beheren](/help/user-guide/managing-displays.md).

1. Nadat u kanalen aan een vertoning hebt toegewezen, navigeer aan **LobbyDisplay** en klikt u op de weergave. Klikken **Eigenschappen** in de actiebalk.

1. Ga naar de **Weergave** tab en enable **Voice ingeschakeld** optie onder **Inhoud**.

   ![afbeelding](assets/voice-recognition/vr-disp.png)

   >[!IMPORTANT]
   >Het is verplicht om de functie voor spraakherkenning vanuit de weergave in te schakelen.

### De inhoud weergeven in de Chrome Player {#viewing-content}

Wanneer de voorgaande stappen zijn voltooid, kunt u het chroomapparaat registreren om de uitvoer weer te geven.

>[!NOTE]
>Zie [Apparaatregistratie](device-registration.md).

**Gewenste uitvoer voor sequentiekanaal**

De **Hoofd** kanaal speelt zijn inhoud af, maar wanneer u woorden met sleutelwoord gebruikt **heet** zoals *Ik zou graag een warme drank hebben*, wordt de inhoud van het **HotDrinks** kanaal.

Op dezelfde manier als u woord met een sleutelwoord gebruikt **koud** zoals *Ik zou graag iets kouds hebben*, wordt de inhoud van het **ColdDrinks** kanaal.

**Gewenste uitvoer voor gesplitste schermkanalen**

De **Hoofd** kanaal wordt de inhoud ervan afgespeeld. Wanneer u echter woorden met trefwoorden gebruikt **heet** en **koud** samen *Ik zou graag het menu voor warme en koude dranken zien*, speelt het kanaal de inhoud van **SplitScreen** kanaal. Als je zegt *terug naar hoofdmenu*, wordt de **Hoofd** kanaal.
