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
>Adobe raadt u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). AEM Screens biedt onderhoudsondersteuning voor het AEM 6.3 Screens-platform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 7 uitgebracht.

U kunt het recentste Pak van de Eigenschap voor AEM Screens 6.5.7 Versie van het [ Portaal van de Distributie van de Software ](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer aan het **Adobe Experience Manager** lusje en onderzoek naar **Screens** om het recentste Pak van de Eigenschap te krijgen dat als **wordt genoemd AEM 6.5 Screens FP7**.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202103 is 5 maart 2021.

### Wat is er nieuw? {#what-is-new}

* **AEM Screens Auto Registratie van Players**

  Bulk die duizenden spelers handmatig registreert, is omslachtig en verhoogt tijd en kosten. Om dit proces te vereenvoudigen, kunt u met de functie Automatische registratie van spelers een vooraf gedeelde sleutel in AEM opgeven. Deze sleutel kan in een speler of door een configuratiedossier of een oplossing van het Beheer van het Mobiel Apparaat (MDM) worden voorzien.

  Zie [ Auto Registratie van Players ](/help/user-guide/auto-registration-players.md) voor meer details.


* **BulkLevering van de Speler van Android™ die het Beheer van de Mobiliteit van de Onderneming gebruikt**

  Wanneer u de Android™-speler bulksgewijs inzet, wordt het vervelend om elke speler handmatig te registreren bij AEM. U wordt ten zeerste aangeraden een EMM-oplossing (Enterprise Mobility Management), zoals `VMWare Airwatch` , `MobileIron` of `Samsung Knox` , te gebruiken om uw implementatie op afstand te voorzien en te beheren. AEM Screens Android™-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

  Zie [ BulkLevering van de Speler van Android™ gebruikend het Beheer van de Mobiliteit van de Onderneming ](/help/user-guide/implementing-android-player.md#implementation) voor meer details.


### Opgeloste problemen {#bug-fixes}

* Verbeterde prestaties voor computergebruik `clientlib` en `asset hashes` .

* De migratie van SmartSync zou de speler breken, als het geheime voorgeheugen niet ongeldig werd gemaakt.

* De off-line geheime voorgeheugens werden niet gecreeerd, als de Toewijzing *OfflineConfig* had.

* Updates voor de `Tizen` -speler die zijn verbroken omdat het verwijzingsbeleid &#39;strikte oorsprong-wanneer-kruisoorsprong&#39; niet wordt ondersteund.

* Het veranderen van het programma van het toegewezen kanaal *herhaalt* gebied verbond UI.

* Offline-inhoud bijwerken is mislukt vanwege query-uitzonderingen.

* Het tijdsverschil tussen overgangen tijdens de interactie in een interactieve ervaring is nu opgelost.

* Een mislukte configuratieupdateverzoek veroorzaakte lege schermen.

### Uitgebrachte AEM Screens-spelers

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 7 van de Eigenschap:

* CHROME OS
* Windows
* Linux®

#### Downloads voor AEM Screens Player

Om de recentste Speler van AEM Screens te downloaden en meer over de insectenmoeilijke situaties te leren, zie **[Downloads van de Speler van AEM Screens ](https://download.macromedia.com/screens/index.html)**.
