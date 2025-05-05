---
title: Noodkanaal
description: Leer over het creëren van en het leiden van een noodkanaal dat de Inhoudsauteur van een opeenvolgingskanaal kan schakelen als er een voorwaarde is.
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
source-git-commit: 1cf90de7892d051b2b94b4dd57de7135269b1ee8
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 0%

---

# Noodkanaal {#emergency-channel}

## Omschrijving hoofdletter gebruiken {#use-case-description}

In deze sectie wordt een gebruiksvoorbeeld beschreven. Het benadrukt het creëren van en het leiden van een noodkanaal dat de Inhoudsauteur van een opeenvolgingskanaal kan schakelen, als er een voorwaarde is.

### Voorwaarden {#preconditions}

Voordat u met dit gebruik begint, moet u controleren hoe u dit kunt doen:

* **[creeer en beheer Kanalen](managing-channels.md)**
* **[creeer en beheer Plaatsen](managing-locations.md)**
* **[creeer en beheer Programma&#39;s](managing-schedules.md)**
* **[Registratie van het Apparaat](device-registration.md)**

### Primaire acteurs {#primary-actors}

Inhoudsauteurs

## Basisstroom: Het project instellen {#basic-flow-setting-up-the-project}

Voer de onderstaande stappen uit om een noodkanaal in te stellen:

1. Creeer een Project van AEM Screens dat als **wordt genoemd EmergencyChannel**, zoals hieronder getoond.

   >[!NOTE]
   >Zie Een project maken voor meer informatie over het maken en beheren van projecten in AEM Screens.

   ![ screen_shot_2019-02-21at35809pm ](assets/screen_shot_2019-02-21at35809pm.png)

1. **Creërend een Kanaal van de Opeenvolging**

   1. Klik de **omslag van Kanalen** en klik **creëren**.

   1. Klik het Kanaal van de Opeenvolging **van de tovenaar en creeer het kanaal als** MainAdChannel **wordt genoemd.**

   ![ screen_shot_2019-02-21at35932pm ](assets/screen_shot_2019-02-21at35932pm.png)

1. **Toevoegend Inhoud aan het Kanaal van de Opeenvolging**

   1. Klik het kanaal (**MainAdChannel**).
   1. Klik **uitgeven** van de actiebar.
   1. Sleep een aantal elementen naar het kanaal.

   ![ screen_shot_2019-02-21at40053pm ](assets/screen_shot_2019-02-21at40053pm.png)

1. **Creërend een Kanaal van de Noodsituatie**

   1. Klik de **omslag van Kanalen**.
   1. Klik **creëren**.
   1. Klik het Kanaal van de Opeenvolging **van de tovenaar en creeer het kanaal dat als** wordt genoemd EmergencyChannel **.**

   >[!NOTE]
   >
   >Normaal, wordt uw noodkanaal toegevoegd aan uw reeds bestaand productieproject.

   ![ screen_shot_2019-02-21at40151pm ](assets/screen_shot_2019-02-21at40151pm.png)

1. **Toevoegend Inhoud aan het Kanaal van de Noodsituatie**

   1. Klik het kanaal (**Noodkanaal)**.
   1. Klik **uitgeven** van de actiebar.
   1. Sleep het element dat u tijdens een noodsituatie wilt gebruiken naar het kanaal en zet het neer.

   ![ screen_shot_2019-02-21at40516pm ](assets/screen_shot_2019-02-21at40516pm.png)

1. **Creërend een Plaats**

   1. Navigeer aan de **omslag van Plaatsen**.
   1. Klik **creëren** van de actiebar en creeer een plaats genoemd **Opslag** van de tovenaar.

   ![ screen_shot_2019-02-22at121638pm ](assets/screen_shot_2019-02-22at121638pm.png)

1. **Creërend Vertoningen in uw Plaats**

   Navigeer aan uw plaats (**Winkel**) en klik **creeer** van de actiebar. Na de tovenaar, creeer twee **Vertoningen** titled als **StoreFront** en **StoreRear**.

   ![ screen_shot_2019-02-22at122556pm ](assets/screen_shot_2019-02-22at122556pm.png)

1. **Creërend een Programma**

   1. Navigeer aan uw **Planningen** omslag.
   1. Klik **creëren** van de actiebar.
   1. Na de tovenaar, creeer een programma genoemd als **StoreSchedule**.

   ![ screen_shot_2019-02-22at122845pm ](assets/screen_shot_2019-02-22at122845pm.png)

1. Wijs zowel de Vertoningen aan uw Programma toe en vastgestelde Prioriteiten

   1. Klik programma **(StoreSchedule)** en klik **Dashboard** van de actiebar.

   1. Klik **+ wijs Kanaal** van het **TOEGEWEZEN paneel van KANALEN** toe.

   1. Van het **de dialoogvakje van de Toewijzing van het Kanaal**:

      1. Klik de weg aan **MainAdChannel**
      1. Plaats de **Prioriteit** als 2
      1. Plaats de Gesteunde Gebeurtenissen als **Aanvankelijke Lading** en **het Niet-actieve Scherm**.
      1. Klik **sparen**

      Op dezelfde manier volg opnieuw de zelfde stappen om **EmergencyChannel** toe te wijzen en zijn **Prioriteit** te plaatsen.

   >[!NOTE]
   >
   >Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. De waarde met de hoogste waarde heeft altijd voorrang op lagere waarden.

   ![ screen_shot_2019-03-04at104636am ](assets/screen_shot_2019-03-04at104636am.png)

1. Klik **+ wijs Kanaal** van het **TOEGEWEZEN paneel van KANALEN** toe.

1. Van het **de dialoogvakje van de Toewijzing van het Kanaal**:

   1. Klik de weg aan **EmergencyChannel**
   1. Plaats de **Prioriteit** als 1

   1. Plaats de Ondersteunde Gebeurtenissen als **Begeleidende Lading**, **IdleScreen**, en **Interactie van de Gebruiker**

   1. Klik **sparen**

   ![ screen_shot_2019-03-04at104741am ](assets/screen_shot_2019-03-04at104741am.png)

   U kunt de toegewezen kanalen van het **StoreSchedule** dashboard bekijken.

   ![ screen_shot_2019-02-25at93658pm ](assets/screen_shot_2019-02-25at93658pm.png)

1. **Toewijzend Programma aan elke Vertoning**

   1. Navigeer aan elke vertoning, zoals **EmergencyChannel** > **Plaatsen** > **Opslag** > **StoreFront**.

   1. Klik **Dashboard** van de actiebar.
   1. Klik **...** van **TOEGEWEZEN KANALEN &amp; SCHADUWEN** paneel en klik verder **+ wijs Programma** toe.

   1. Klik de weg aan het Programma (bijvoorbeeld, hier, **EmergencyChannel** > **Programma&#39;s** > **StoreSchedule**).

   1. Klik **sparen**.

   U kunt het toegewezen programma aan de vertoning van het **StoreSchedule** dashboard bekijken.
   ![ screen_shot_2019-03-04at122003pm ](assets/screen_shot_2019-03-04at122003pm.png)

1. **Registratie van het Apparaat**

   Voltooi het registratieproces van het apparaat. Wanneer u zich hebt geregistreerd, kunt u de volgende uitvoer weergeven op uw AEM Screens Player.

   ![ new30 ](assets/new30.gif)

## Overschakelen naar noodkanaal {#switching-to-emergency-channel}

Voer in geval van nood de volgende stappen uit:

1. Navigeer aan **EmergencyChannel** > **Programma&#39;s** > **StoreSchedule** en klik **Dashboard** van de actiebar.

   ![ screen_shot_2019-02-25at101112pm ](assets/screen_shot_2019-02-25at101112pm.png)

1. Klik **EmergencyChannel** van **StoreSchedule** dashboard en klik **geef Toewijzing** uit.

   ![ screen_shot_2019-02-25at101239pm ](assets/screen_shot_2019-02-25at101239pm.png)

1. Werk de **Prioriteit** van **EmergencyChannel** aan **3** van de **7&rbrace; dialoogdoos van de Toewijzing van het Kanaal bij en klik** sparen **.**

   ![ screen_shot_2019-02-25at101622pm ](assets/screen_shot_2019-02-25at101622pm.png)

1. Wanneer de prioriteit van het kanaal wordt bijgewerkt, toont al Speler van AEM Screens de **&#x200B;**&#x200B;inhoud EmergencyChannel.

   ![ screen_shot_2019-02-25at101742pm ](assets/screen_shot_2019-02-25at101742pm.png)

### Conclusie {#conclusion}

**EmergencyChannel** blijft zijn inhoud tonen tot de Inhoudsauteur de Prioritaire Waarde aan 1 terugstelt.

Wanneer de Inhoudsauteur de instructies ontvangt dat de noodsituatie is ontruimd, zouden zij de prioriteit van **MainAdChannel** moeten bijwerken. Hierdoor wordt het normale afspelen hervat.
