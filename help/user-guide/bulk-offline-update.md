---
title: Bulk offline bijwerken
description: Leer hoe u alle kanalen bulksgewijs kunt bijwerken.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d0a0b065-798e-4108-86ac-0a1f4e211cfc
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Bulk offline bijwerken {#bulk-offline-update}

Deze sectie behandelt de volgende onderwerpen op Bulk Offline Update:

* **Overzicht**
* **Gebruikend Bulk Offline Update**

<!-- OBSOLETE VERSIONS
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permissions you can download it from Package Share. -->

## Overzicht {#overview}

Bulk offline bijwerken, waarmee u alle kanalen in bulk kunt bijwerken. Zo voorkomt u de problemen bij het navigeren naar een bepaald kanaal en het bijwerken van de inhoud. In plaats daarvan kunt u alle inhoud in kanalen voor één specifiek project in één keer bijwerken.

U kunt deze activiteit voor een tijd van lager netwerkverkeer ook plannen.

>[!NOTE]
>
>De functie Offlineupdate bulken is geoptimaliseerd en werkt alleen de kanalen bij die zijn gewijzigd.

## Bulk offline bijwerken gebruiken {#using-bulk-offline-update}

U kunt Bulk Offline Update van het Gebruikersinterface (UI) manueel gebruiken of de bulkupdate van de diensten plannen OSGi.

### AEM Screens-gebruikersinterface gebruiken {#using-aem-screens-user-interface}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Ga naar uw AEM Screens-project.
1. Klik het project, dan klik **Offline Inhoud van de Update** van de actiebar zodat kunt u de kanaalinhoud manueel bijwerken.

   ![ screen_shot_2018-04-24at122256pm ](assets/screen_shot_2018-04-24at122256pm.png)

### Configuratie Adobe Experience Manager-webconsole {#adobe-experience-manager-web-console-configuration}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Configuratie Adobe Experience Manager-webconsole.
1. Zoeken naar services voor offline bijwerken van bulkbestanden.

   ![ screen_shot_2018-04-24at121428pm ](assets/screen_shot_2018-04-24at121428pm.png)

1. Voeg de volgende eigenschappen toe:

   **Weg van het Project** - specificeert de weg van uw project van AEM Screens. Het pad is meestal `/content/screens/<Name of your project>` .

   *bijvoorbeeld*, `/content/screens/we-retail`. U kunt dit pad vinden in de URL door een willekeurig project te selecteren onder AEM Screens (klik niet op het pictogram).

   >[!NOTE]
   >
   >Geef het projectpad op ten opzichte van het kanaal.

   **Frequentie van het Programma** - specificeert een tijd, bijvoorbeeld, 5:00 P.M. of 17:00 waarbij deze dienst off-line inhoud zou moeten bijwerken.

1. Klik **sparen** om uw montages te bewaren. Uw inhoud wordt op het opgegeven tijdstip bijgewerkt.
