---
title: Noodkanaal
description: Leer over het creëren van en het leiden van een noodkanaal dat de inhoudauteur van een opeenvolgingskanaal kan schakelen als er een voorwaarde is.
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
source-git-commit: ba5327077e4a2d30cc7b77f02123da5a240c67ae
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Noodkanaal {#emergency-channel}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruiksvoorbeeld beschreven waarin wordt benadrukt dat de auteur van de inhoud bij het maken en beheren van een noodkanaal kan schakelen van een volgnummer als er een voorwaarde is.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[Kanalen maken en beheren](managing-channels.md)**
* **[Locaties maken en beheren](managing-locations.md)**
* **[Planningen maken en beheren](managing-schedules.md)**
* **[Apparaatregistratie](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Basisstroom: Het project instellen {#basic-flow-setting-up-the-project}

Voer de onderstaande stappen uit om een noodkanaal in te stellen:

1. Een AEM Screens-project maken met de naam **EmergencyChannel**, zoals hieronder weergegeven.

   >[!NOTE]
   >Zie Een project maken voor meer informatie over het maken en beheren van projecten in AEM Screens.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Een volgend kanaal maken**

   1. Selecteer de **Kanalen** map en klik op **Maken**.

   1. Selecteren **Volgekanaal** van de wizard en maakt u het kanaal met de naam **MainAdChannel**.

   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Inhoud toevoegen aan Volgkanaal**

   1. Selecteer het kanaal (**MainAdChannel**).
   1. Klikken **Bewerken** in de actiebalk.
   1. Sleep enkele elementen naar het kanaal.

   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Noodkanaal maken**

   1. Selecteer de **Kanalen** map.
   1. Klikken **Maken**.
   1. Selecteren **Volgekanaal** van de wizard en maakt u het kanaal met de naam **EmergencyChannel**.

   >[!NOTE]
   >
   >Normaal, wordt uw noodkanaal toegevoegd aan uw reeds bestaand productieproject.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Inhoud toevoegen aan noodkanaal**

   1. Selecteer het kanaal (**Noodkanaal)**.
   1. Klikken **Bewerken** in de actiebalk.
   1. Sleep het element dat u tijdens een noodsituatie wilt gebruiken naar het kanaal en zet het neer.

   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Een locatie maken**

   1. Navigeren naar **Locaties** map.
   1. Klikken **Maken** op de actiebalk en maak een locatie met de naam **Winkel** van de wizard.

   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Weergaven maken op uw locatie**

   Ga naar uw locatie (**Winkel**) en klik op **Maken** in de actiebalk. Na de wizard maakt u twee **Weergaven** getiteld als **StoreFront** en **StoreRear**.

   ![screen_shot_2019-02-22at12255pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Een schema maken**

   1. Ga naar uw **Planningen** map.
   1. Klikken **Maken** in de actiebalk.
   1. Na de tovenaar, creeer een programma genoemd als **StoreSchedule**.

   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Wijs zowel de Vertoningen aan uw Programma toe en vastgestelde Prioriteiten

   1. Selecteer het schema **(StoreSchedule)** en klik op **Dashboard** in de actiebalk.

   1. Klikken **+ Kanaal toewijzen** van de **TOEGEWEZEN KANALEN** deelvenster.

   1. Van de **Kanaaltoewijzing** dialoogvenster:

      1. Selecteer het pad naar de **MainAdChannel**
      1. Stel de **Prioriteit** 2
      1. Ondersteunde gebeurtenissen instellen als **Oorspronkelijke belasting** en **Niet-actief scherm**.
      1. Klikken **Opslaan**

      Voer dezelfde stappen opnieuw uit om de opdracht **EmergencyChannel** en stelt **Prioriteit**.

   >[!NOTE]
   >
   >Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Klikken **+ Kanaal toewijzen** van de **TOEGEWEZEN KANALEN** deelvenster.

1. Van de **Kanaaltoewijzing** dialoogvenster:

   1. Selecteer het pad naar de **EmergencyChannel**
   1. Stel de **Prioriteit** als 1

   1. Ondersteunde gebeurtenissen instellen als **Oorspronkelijke belasting**, **Niet-actief scherm**, en **Gebruikersinteractie**

   1. Klikken **Opslaan**

   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   U kunt de toegewezen kanalen weergeven via de **StoreSchedule** dashboard.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Plan toewijzen aan elke weergave**

   1. Ga naar elke weergave, zoals **EmergencyChannel** > **Locaties** > **Winkel** >**StoreFront**.

   1. Klikken **Dashboard** in de actiebalk.
   1. Klikken **...** van de **TOEGEWEZEN KANALEN EN SCHEMA&#39;S** deelvenster en klik vervolgens op **+Plan toewijzen**.

   1. Selecteer het pad naar het schema (bijvoorbeeld hier **EmergencyChannel** > **Planningen** >**StoreSchedule**).

   1. Klikken **Opslaan**.

   U kunt het toegewezen schema aan de vertoning van bekijken **StoreSchedule** dashboard.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Apparaatregistratie**

   Voltooi het registratieproces van het apparaat. Wanneer u zich hebt geregistreerd, kunt u de volgende uitvoer weergeven op uw AEM Screens-speler.

   ![new30](assets/new30.gif)

## Overschakelen naar noodkanaal {#switching-to-emergency-channel}

Voer in geval van nood de volgende stappen uit:

1. Navigeren naar **EmergencyChannel** > **Planningen** > **StoreSchedule** en selecteert u **Dashboard** in de actiebalk.

   ![screen_shot_2019-02-25at10112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Selecteer de **EmergencyChannel** van de **StoreSchedule** dashboard en klik op **Toewijzing bewerken**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Werk de **Prioriteit** van de **EmergencyChannel** tot **3** van de **Kanaaltoewijzing** en klik op **Opslaan**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. Wanneer de prioriteit van het kanaal wordt bijgewerkt, geeft alle AEM Screens-speler de **EmergencyChannel** inhoud.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Conclusie {#conclusion}

De **EmergencyChannel** gaat verder met het weergeven van de inhoud totdat de auteur van de inhoud de Prioriteitswaarde herstelt naar 1.

Wanneer de auteur van de inhoud de instructies ontvangt dat de noodsituatie is gewist, moet hij of zij de prioriteit van het **MainAdChannel** waardoor het afspelen wordt hervat.
