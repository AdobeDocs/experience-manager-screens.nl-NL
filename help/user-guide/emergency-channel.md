---
title: Noodkanaal
seo-title: Noodkanaal
description: Volg dit gebruiksvoorbeeld om te leren over het maken en beheren van een noodkanaal dat de auteur van de inhoud van een opeenvolgingskanaal kan overschakelen in het geval van een voorwaarde.
seo-description: Volg dit gebruiksvoorbeeld om te leren over het maken en beheren van een noodkanaal dat de auteur van de inhoud van een opeenvolgingskanaal kan overschakelen in het geval van een voorwaarde.
uuid: 612917c9-a832-453b-970c-f4365f7b105d
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: dbb4fae6-f3fb-496a-9bd6-1151e2862b5b
docset: aem65
feature: Ontwerpschermen
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%

---

# Noodkanaal {#emergency-channel}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruiksvoorbeeld beschreven waarin wordt benadrukt dat de auteur van de inhoud bij het maken en beheren van een noodkanaal kan schakelen van een volgnummer naar een ander kanaal.

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

1. Maak een AEM Screens-project met de naam **EmergencyChannel**, zoals hieronder wordt weergegeven.

   >[!NOTE]
   >Raadpleeg Een project maken voor meer informatie over het maken en beheren van projecten in AEM Screens.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Een volgend kanaal maken**

   1. Selecteer de map **Kanalen** en klik op **Maken** om de wizard te openen en een kanaal te maken.

   1. Selecteer **Sequence Channel** in de wizard en maak het kanaal met de naam **MainAdChannel**.

   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Inhoud toevoegen aan Volgkanaal**

   1. Selecteer het kanaal (**MainAdChannel**).
   1. Klik **Bewerken** van de actiebar om de redacteur te openen. Sleep enkele elementen naar uw kanaal.

   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Noodkanaal maken**

   1. Selecteer **Kanalen** omslag.
   1. Klik op **Maken** om de wizard te openen en een kanaal te maken.
   1. Selecteer **Sequence Channel** in de wizard en maak het kanaal met de naam **EmergencyChannel**.

   >[!NOTE]
   >
   >Normaal, wordt uw noodkanaal toegevoegd aan uw reeds bestaand productieproject.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Inhoud toevoegen aan noodkanaal**

   1. Selecteer het kanaal (**Noodkanaal)**.
   1. Klik **Bewerken** van de actiebar om de redacteur te openen. Sleep het element dat u tijdens een noodsituatie wilt gebruiken naar het kanaal.

   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Een locatie maken**

   1. Navigeer naar de map **Locations**.
   1. Klik **Maken** van de actiebar en creeer een plaats genoemd **Store** van de tovenaar.

   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Weergaven maken op uw locatie**

   Navigeer naar uw locatie (**Store**) en klik op **Create** op de actiebalk. Volg de tovenaar om twee **vertoningen te creëren** die als **StoreFront** en **StoreRear** worden genoemd.

   ![screen_shot_2019-02-22at122556pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Een schema maken**

   1. Navigeer naar de map **Planningen**.
   1. Klik **Maken** van de actiebar. Volg de tovenaar om een programma tot stand te brengen genoemd als **StoreSchedule**.

   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Wijs zowel de Vertoningen aan uw Programma toe en vastgestelde Prioriteiten

   1. Selecteer het schema **(StoreSchedule)** en klik **Dashboard** van de actiebar.

   1. Klik **+ toewijzen Kanaal** van **TOEGEWEZEN KANALEN** paneel.

   1. Vanuit het dialoogvenster **Kanaaltoewijzing**:

      1. Selecteer het pad naar **MainAdChannel**
      1. **Prioriteit** instellen als 2
      1. Stel de ondersteunde gebeurtenissen in op **Eerste Laden** en **Niet-actief scherm**.
      1. Klik **Opslaan**

      Op dezelfde manier zult u de zelfde stappen opnieuw moeten volgen om **EmergencyChannel** toe te wijzen en zijn **Priority** te plaatsen.
   >[!NOTE]
   >
   >Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Klik **+ toewijzen Kanaal** van **TOEGEWEZEN KANALEN** paneel.

1. Vanuit het dialoogvenster **Kanaaltoewijzing**:

   1. Selecteer het pad naar **EmergencyChannel**
   1. **Prioriteit** instellen als 1

   1. Stel de ondersteunde gebeurtenissen in als **Eerste Laden**, **Niet-actief scherm** en **Gebruikersinteractie**

   1. Klik **Opslaan**

   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   U kunt de toegewezen kanalen van **StoreSchedule** dashboard bekijken.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Plan toewijzen aan elke weergave**

   1. Navigeer naar elk scherm, zoals **EmergencyChannel** —> **Locaties** —> **Store** —>**StoreFront**.

   1. Klik **Dashboard** van de actie om het vertoningsdashboard te openen.
   1. Klik **..** van **TOEGEWEZEN KANALEN &amp; SCHEDULES** en klik verder **+Wijs Programma** toe.

   1. Selecteer het pad naar het schema (bijvoorbeeld **EmergencyChannel** —> **Planningen** —>**StoreSchedule**).

   1. Klik **Opslaan**.

   U kunt het toegewezen programma aan de vertoning van **StoreSchedule** dashboard bekijken.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Apparaatregistratie**

   Voltooi het registratieproces voor het apparaat en zodra u zich hebt geregistreerd, bekijkt u de volgende uitvoer op uw AEM Screens-speler.

   ![new30](assets/new30.gif)

## Overschakelen naar noodkanaal {#switching-to-emergency-channel}

Voer in noodgevallen de volgende stappen uit:

1. Navigeer naar **EmergencyChannel** —> **Planningen** —> **StoreSchedule** en selecteer **Dashboard** in de actiebalk.

   ![screen_shot_2019-02-25at10112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Selecteer **EmergencyChannel** van **StoreSchedule** dashboard en klik **Edit Taak**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Werk **Prioriteit** van **EmergencyChannel** aan **3** van **Kanaaltoewijzing** dialoogdoos bij en klik **Save**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. Zodra de prioriteit van het kanaal is bijgewerkt, geeft alle AEM Screens-speler de **EmergencyChannel**-inhoud weer, zoals hieronder wordt weergegeven.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Conclusie {#conclusion}

De **EmergencyChannel** zal zijn inhoud blijven tonen tot de auteur van de inhoud de Prioriteitswaarde aan 1 terugstelt.

Zodra de inhoudauteur de instructies ontvangt dat de noodsituatie is ontruimd, zou hij/zij de prioriteit van **MainAdChannel** moeten bijwerken die normale playback zal veroorzaken om te hervatten.
