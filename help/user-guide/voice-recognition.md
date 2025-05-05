---
title: Spraakherkenning in AEM Screens
description: Meer weten over stemherkenning en hoe je deze kunt gebruiken in AEM Screens?
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 6cf0aa9f-7bac-403f-a113-51727c1f5374
source-git-commit: 6720e20f5254e869bde814bd167730e426d0f8fe
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# Spraakherkenning in AEM Screens {#voice-recognition}

>[!IMPORTANT]
>
>**Belangrijke Informatie van de Privacy**
>
>Wanneer het gebruiken van de eigenschap van de stemerkenning, volg alle toepasselijke wettelijke en ethische richtlijnen voor uw regio. Deze richtlijnen omvatten, maar niet beperkt tot, het verstrekken van een zichtbare kennisgeving aan eindgebruikers dat de speler stemerkenning gebruikt). De Adobe ontvangt, slaat, of verwerkt geen van de op stem betrekking hebbende informatie op. De AEM Screens-spelers gebruiken de standaard API voor webspraak die in de bladerengine is ingebouwd. Achter de schermen verzendt deze API een golfvorm van uw toespraak naar Google-servers voor conversie van spraak naar tekst. De speler past de tekst aan gevormde sleutelwoorden aan.
>
>Zie [ Witboek van de Privacy van Google op de toespraak API van het Web ](https://www.google.com/chrome/privacy/whitepaper.html#speech) voor meer details.


De eigenschap van de stemerkenning staat inhoudsverandering in een kanaal van AEM Screens toe dat door steminteractie wordt gedreven.

Een tevreden Auteur kan een vertoning vormen om toegelaten stem te zijn. Het doel van deze eigenschap is klanten toespraak als methode te laten gebruiken om met hun vertoningen in wisselwerking te staan. Tot andere gebruiksgevallen behoren het vinden van productaanbevelingen in winkels, het bestellen van menu-items in restaurants en diners. Deze functie vergroot de toegankelijkheid voor gebruikers en kan de gebruikerservaring aanzienlijk verbeteren.

>[!NOTE]
>De spelerhardware moet audio-invoer, zoals een microfoon, ondersteunen.

## Spraakherkenning implementeren {#implementing}

>[!IMPORTANT]
> De functie voor spraakherkenning is alleen beschikbaar voor Chrome OS- en Windows-spelers.

Om stemerkenning in uw project van AEM Screens uit te voeren, laat de stemerkenning voor de Vertoning toe en associeer elk kanaal met een unieke markering om een kanaalovergang teweeg te brengen.

In de volgende sectie wordt beschreven hoe u de functie voor spraakherkenning in een AEM Screens-project kunt inschakelen en gebruiken.

## Inhoud weergeven in Volledig scherm of Kanaalschakelaar splitsen {#sequence-channel}

Alvorens u een eigenschap van de stemerkenning gebruikt, zorg ervoor u een project en een kanaal met inhoud hebt opstelling voor uw project.

1. Het volgende voorbeeld toont een demoproject genoemd **VoiceDemo** en drie opeenvolgingskanalen **Hoofd**, **ColdDrinks**, en **HotDrinks**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](assets/voice-recognition/vr-1.png)

   >[!NOTE]
   >
   >Leren hoe te om een kanaal tot stand te brengen of inhoud aan een kanaal toe te voegen, zie [ Creërend en het Leiden Kanalen ](/help/user-guide/managing-channels.md)

   Of,

   U kunt drie opeenvolgingskanalen **Hoofd** tot stand brengen, **ColdDrinks**, en **HotDrinks**, en één meer 1x2 Gesplitste het kanaal van Screens **SplitScreen** zoals aangetoond in het hieronder cijfer.

   ![afbeelding](assets/voice-recognition/vr-emb-1.png)

1. Navigeer naar elk kanaal en voeg inhoud toe. Bijvoorbeeld, navigeer aan **VoiceDemo** > **Kanalen** > **Hoofd** en klik het kanaal. Klik **uitgeven** van de actiebar, dan voeg inhoud (beelden/video&#39;s) toe zoals uw vereiste. Op dezelfde manier voeg inhoud aan zowel **ColdDrinks** als **HotDrinks** kanaal toe.

   De kanalen bevatten nu elementen (afbeeldingen), zoals in de onderstaande afbeeldingen wordt getoond.

   **Hoofd**:

   ![afbeelding](assets/voice-recognition/vr-4.png)

   **ColdDrinks**:

   ![afbeelding](assets/voice-recognition/vr-3.png)

   **HotDrinks**:

   ![afbeelding](assets/voice-recognition/vr-2.png)

   Als u het Gesplitste kanaal van Screens aan uw project toevoegde, navigeer aan **SplitScreen** en belemmering-en-daling twee ingebedde opeenvolgingen. Voeg wegen aan zowel het **ColdDrinks** als **HotDrinks** kanaal zoals aangetoond in het hieronder cijfer toe.
   ![afbeelding](assets/voice-recognition/vr-emb-6.png)


### Labels instellen voor kanalen {#setting-tags}

Nadat u inhoud aan uw kanalen hebt toegevoegd, navigeer aan elk van de kanalen en voeg aangewezen markeringen toe die de stemerkenning zouden teweegbrengen.

Voer de onderstaande stappen uit om codes aan uw kanaal toe te voegen:

1. Navigeer naar elk kanaal en voeg inhoud toe. Bijvoorbeeld, navigeer aan **VoiceDemo** > **Kanalen** > **Hoofd** en klik het kanaal.

1. Klik **Eigenschappen** van de actiebar.

   ![afbeelding](assets/voice-recognition/vr-5.png)

1. Navigeer aan de **Grondbeginselen** tabel, dan klik een bestaande markering van het **gebied van Markeringen**, of creeer één.

   U kunt een tag maken door een nieuwe naam voor de tag in te voeren en op de toets `return` te drukken, zoals in de onderstaande afbeelding wordt getoond:

   ![afbeelding](assets/voice-recognition/vr-6.png)

   Of,

   U kunt ook van tevoren tags maken voor uw AEM en deze selecteren. Nadat u de stappen volgt die in [ worden verklaard Creërend Markeringen ](#creating-tags), kunt u de markering van de plaats klikken en het toevoegen aan uw kanaal, zoals aangetoond in het hieronder cijfer:

   ![afbeelding](assets/voice-recognition/vr-tag1.png)

1. Op dezelfde manier voeg een markering genoemd als **heet** aan het **HotDrinks** kanaal toe.

1. Als u een Gesplitst kanaal van Screens gebruikt, voeg zowel de markeringen (**heet** en **koud**) aan **SplitScreen** kanaaleigenschappen, zoals aangetoond in het hieronder cijfer toe.

   ![afbeelding](assets/voice-recognition/vr-emb-7.png)

1. Klik **sparen &amp; dicht** zodra u wordt gedaan.


### Tags maken {#creating-tags}

Ga als volgt te werk om labels te maken:

1. Navigeer naar de AEM.

1. Klik het hulpmiddelpictogram > **Tags**.
   ![afbeelding](assets/voice-recognition/vr-7.png)

1. Klik **creeer** > **creeer Namespace**.
   ![afbeelding](assets/voice-recognition/vr-tag3.png)

1. Ga de naam van uw project in, bijvoorbeeld, **VoiceDemo** en klik **creeer**.

1. Klik het **VoiceDemo** project en klik **creeer Markering** van de actiebar.
   ![afbeelding](assets/voice-recognition/vr-tag4.png)

1. Ga de naam van uw markering in en klik **voorleggen**.
   ![afbeelding](assets/voice-recognition/vr-tag5.png)

U kunt deze labels nu gebruiken in uw AEM Screens-project.

### Het toewijzen van Kanaal aan een Vertoning en het toelaten van de Erkenning van de Stem {#channel-assignment}

1. Creeer een vertoning in de **omslag van Plaatsen**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](assets/voice-recognition/vr-loc.png)

   >[!NOTE]
   >Leren hoe te om een kanaal aan een vertoning toe te wijzen, zie [ Creërend en het Leiden Vertoningen ](/help/user-guide/managing-displays.md).

1. Wijs de kanalen **Hoofd**, **ColdDrinks**, en **HotDrinks** aan uw **LobbyDisplay** toe. Ook, als u het **SplitScreen** kanaal voor uw project gebruikt, zorg ervoor u dat aan de vertoning toewijst.

   >[!NOTE]
   >Als u een gespleten het schermkanaal hebt gecreeerd, wijs het **&#x200B;**&#x200B;kanaal SplitScreen aan uw vertoning toe.

1. Stel de volgende eigenschappen in voor elk kanaal terwijl u het kanaal toewijst.

   | **Naam van het Kanaal** | **Prioriteit** | **Ondersteunde Gebeurtenissen** |
   |---|---|---|
   | Hoofd | 2 | Eerste belasting, inactief scherm, Timer |
   | HotDrinks | 1 | Gebruikersinteractie |
   | ColdDrinks | 1 | Gebruikersinteractie |
   | SplitScreen | 1 | Gebruikersinteractie |

   >[!NOTE]
   >
   >Leren hoe te om een kanaal aan een vertoning toe te wijzen, zie [ Creërend en het Leiden Vertoningen ](/help/user-guide/managing-displays.md).

1. Nadat u kanalen aan een vertoning hebt toegewezen, navigeer aan **LobbyDisplay** en klik de vertoning. Klik **Eigenschappen** van de actiebar.

1. Navigeer aan het **lusje van de Vertoning** en laat de **Toegelaten Stem** optie onder **Inhoud** toe.

   ![afbeelding](assets/voice-recognition/vr-disp.png)

   >[!IMPORTANT]
   >Het is verplicht om de functie voor spraakherkenning vanuit de weergave in te schakelen.

### De inhoud weergeven in de Chrome Player {#viewing-content}

Wanneer de voorgaande stappen zijn voltooid, kunt u het Chrome-apparaat registreren om de uitvoer weer te geven.

>[!NOTE]
>Zie [ Registratie van het Apparaat ](device-registration.md).

**Gewenste Output voor Kanaal van de Opeenvolging**

Het **Belangrijkste** kanaal speelt zijn inhoud af. Nochtans, wanneer u woorden met het sleutelwoord **heet**, zoals *gebruikt zou ik een hete drank* willen hebben, begint het kanaal de inhoud van het **HotDrinks** kanaal te spelen.

Op dezelfde manier als u een woord met een sleutelwoord **kou** zoals *gebruikt zou ik iets koude* willen hebben, begint het kanaal de inhoud van het **ColdDrinks** kanaal te spelen.

**Gewenst Output voor Gesplitste Kanaal van Screens**

Het **Belangrijkste** kanaal speelt zijn inhoud af. Nochtans, wanneer u woorden met het sleutelwoord **heet** en **koud** samen, zoals *gebruikt zou ik het menu voor hete en koude dranken* willen zien, speelt het kanaal de inhoud van het **SplitScreen** kanaal. Als u *terug naar het belangrijkste menu* zegt, keert het aan het **Belangrijkste** kanaal terug.
