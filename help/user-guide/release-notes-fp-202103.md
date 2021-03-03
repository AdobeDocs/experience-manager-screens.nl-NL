---
title: Opmerkingen bij de release voor Feature Pack 202103
description: De pagina markeert de Nota's van de Versie voor de Pak 202103 van de Eigenschap.
translation-type: tm+mt
source-git-commit: 34f93df3fa212eaae713b0c8686d95beeb0c7b67
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# Opmerkingen bij de release voor Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>We raden u aan een upgrade uit te voeren naar de nieuwste versie van Adobe Experience Manager (AEM). Schermen bieden onderhoudsondersteuning voor AEM 6.3 Schermplatform.

## Beschikbaarheid {#availability}

AEM Screens heeft AEM 6.5 Feature Pack 7 uitgebracht.

U kunt het recentste eigenschappak voor AEM Screens 6.5.7 Versie van [het Portaal van de Distributie van de Software](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) downloaden gebruikend uw Adobe ID. Navigeer naar **Adobe Experience Manager** tabblad en zoek **Screens** om het nieuwste functiepakket met de naam **AEM 6.5 Screens FP7** te krijgen.

## Releasedatum {#release-date}

De releasedatum voor AEM Screens Feature Pack 202103 is 8 maart 2021.

### Wat is er nieuw?{#what-is-new}

* **AEM Screens Bulkregistratie en -toewijzing**

   Bulk die duizenden spelers handmatig registreert, is erg omslachtig en verhoogt tijd en kosten. Om dit proces te vereenvoudigen, staat de Bulk eigenschap van de Registratie u toe om een pre-gedeelde sleutel in AEM te specificeren die in een speler of door een configuratiedossier of een Mobiel Apparaatbeheer (MDM) oplossing kan worden voorzien.

* **Bulkprovisioning van Android Player via Enterprise Mobility Management**

   Wanneer u de Android-speler bulksgewijs implementeert, wordt het vervelend om elke speler handmatig te registreren bij AEM. Het wordt ten zeerste aanbevolen om een EMM-oplossing (Enterprise Mobility Management), zoals VMWare Airwatch, MobileIron of Samsung Knox, te gebruiken om uw implementatie op afstand te voorzien en te beheren. AEM Screens Android-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.


### Opgeloste problemen {#bug-fixes}

* Verbeterde prestaties voor computergebruik `clientlib` en `asset hashes`.

* De migratie van SmartSync zou de speler breken, als het geheime voorgeheugen niet ongeldig werd gemaakt.

* Offline caches zijn niet gemaakt als de toewijzing *OfflineConfig* had.

* Problemen met Tizen Player worden bijgewerkt omdat het verwijzingsbeleid &#39;strict-origin-wanneer-cross-origin&#39; niet wordt ondersteund.

* Het wijzigen van het schema &quot;Repeats&quot;-veld van het toegewezen kanaal heeft de interface verbroken.

* Offline-inhoud bijwerken is mislukt vanwege query-uitzonderingen.

* SmartSync-migratie heeft de speler verbroken als de cache niet ongeldig is gemaakt


### Uitgebrachte AEM Screens-spelers {#released-aem-screens-players}

De volgende AEM Screens Players worden vrijgegeven voor AEM 6.5 Pak 7 van de Eigenschap:

* Chrome-besturingssysteem
* Windows
* Android
* Tizen
* Linux

#### AEM Screens Player-downloads {#aem-screens-player-downloads}

Raadpleeg **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)** voor meer informatie over de opgeloste problemen.
