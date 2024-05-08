---
title: Opmerkingen bij de release voor Feature Pack 202103
description: Meer weten over het AEM Screens Feature Pack 202103 dat op 5 maart 2021 werd uitgebracht?
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: a8741cc7-de4f-4e5a-b69e-852a43597123
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Opmerkingen bij de release voor Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). AEM Screens biedt ondersteuning voor onderhoud voor het AEM 6.3-schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 7 uitgebracht.

U kunt de nieuwste versie van het Feature Pack voor de AEM Screens 6.5.7 downloaden van de [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) met uw Adobe ID. Ga naar de **Adobe Experience Manager** tabblad en zoeken naar **Schermen** om het nieuwste elementenpakket met de titel **AEM 6.5 Schermen FP7**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202103 is 5 maart 2021.

### Wat is er nieuw? {#what-is-new}

* **AEM Screens Auto Registration of Players**

  Bulk die duizenden spelers handmatig registreert, is omslachtig en verhoogt tijd en kosten. Om dit proces te vereenvoudigen, kunt u met de functie Automatische registratie van spelers een vooraf gedeelde sleutel in AEM opgeven. Deze sleutel kan in een speler of door een configuratiedossier of een oplossing van het Beheer van het Mobiel Apparaat (MDM) worden voorzien.

  Zie [Automatische registratie van spelers](/help/user-guide/auto-registration-players.md) voor meer informatie .


* **Bulkprovisioning van Android™ Player via Enterprise Mobility Management**

  Wanneer u de Android™-speler bulksgewijs inzet, wordt het vervelend om elke speler handmatig te registreren bij AEM. Het wordt ten zeerste aanbevolen een EMM-oplossing (Enterprise Mobility Management) te gebruiken, zoals `VMWare Airwatch`, `MobileIron`, of `Samsung Knox` om uw implementatie op afstand te voorzien en te beheren. AEM Screens Android™-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

  Zie [Bulkprovisioning van Android™ Player via Enterprise Mobility Management](/help/user-guide/implementing-android-player.md#implementation) voor meer informatie .


### Opgeloste problemen {#bug-fixes}

* Verbeterde prestaties voor computergebruik `clientlib` en `asset hashes`.

* De migratie van SmartSync zou de speler breken, als het geheime voorgeheugen niet ongeldig werd gemaakt.

* Er zijn geen offlinekaarten gemaakt als de toewijzing *OfflineConfig*.

* Updates voor `Tizen` De speler die brak omdat het verwijzingsbeleid strikt-oorsprong-wanneer-dwars-oorsprong niet wordt gesteund.

* Het programma van het toegewezen kanaal wijzigen *Herhalingen* het veld verbreekt de interface.

* Offline-inhoud bijwerken is mislukt vanwege query-uitzonderingen.

* Het tijdsverschil tussen overgangen tijdens de interactie in een interactieve ervaring is nu opgelost.

* Een mislukte configuratieupdateverzoek veroorzaakte lege schermen.

### Uitgebrachte AEM Screens-spelers

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 7 van de Eigenschap:

* Chrome-besturingssysteem
* Windows
* Linux®

#### Downloads voor AEM Screens Player

Als u de nieuwste AEM Screens Player wilt downloaden en meer wilt weten over de opgeloste problemen, raadpleegt u **[Downloads voor AEM Screens Player](https://download.macromedia.com/screens/index.html)**.
