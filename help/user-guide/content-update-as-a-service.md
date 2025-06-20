---
title: Inhoud bijwerken als service
description: Meer informatie over Inhoud bijwerken als service.
contentOwner: Jyotika syal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: de9f669b-9ce7-4d70-99b4-0b69ef3c1af5
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Inhoud bijwerken als service {#content-update-as-a-service}

In deze sectie worden de volgende onderwerpen over het bijwerken van content-as-a-service besproken:

* **Overzicht**
* **Gebruikend Bulk Offline Update**

<!--
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permission you can download it from Package Share. -->

## Overzicht {#overview}

Met de functie Offline bulkupdate kunt u alle kanalen bulksgewijs bijwerken. Zo voorkomt u de problemen bij het navigeren naar een bepaald kanaal en het bijwerken van de inhoud. In plaats daarvan kunt u alle inhoud in kanalen voor één specifiek project in één keer bijwerken.

U kunt deze activiteit voor een tijd van lager netwerkverkeer ook plannen.

>[!NOTE]
>
>De functie Offlineupdate bulken is geoptimaliseerd en werkt alleen de kanalen bij die zijn gewijzigd.

## Bulk offline bijwerken gebruiken {#using-bulk-offline-update}

U kunt bulkoff-line Update van het Gebruikersinterface (UI) manueel gebruiken of de bulkupdate van de diensten plannen OSGi.

### AEM Screens-gebruikersinterface gebruiken {#using-aem-screens-user-interface}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Ga naar uw AEM Screens-project.
1. Klik het project en klik **Offline Inhoud van de Update** van de actiebar om de kanaalinhoud manueel bij te werken.

   ![ screen_shot_2018-04-24at122256pm ](assets/screen_shot_2018-04-24at122256pm.png)

### Configuratie Adobe Experience Manager-webconsole {#adobe-experience-manager-web-console-configuration}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Configuratie Adobe Experience Manager-webconsole.
1. Zoeken naar bulksgewijs offline updateservices.

   ![ screen_shot_2018-04-24at121428pm ](assets/screen_shot_2018-04-24at121428pm.png)

1. Voeg de volgende eigenschappen toe:

   **Weg van het Project** - specificeert de weg van uw project van AEM Screens. Het pad is meestal `/content/screens/<Name of your project>` .

   *bijvoorbeeld*, `/content/screens/we-retail`. U kunt dit pad vinden in de URL door een willekeurig project te selecteren onder AEM Screens (klik niet op het pictogram).

   >[!NOTE]
   >
   >Geef het projectpad op ten opzichte van het kanaal.

   **Frequentie van het Programma** - specificeert een tijd, bijvoorbeeld, 5:00 P.M. of 17:00 waarbij deze dienst off-line inhoud zou moeten bijwerken.

1. Klik **sparen** zodat kunt u uw montages bewaren. Alle inhoud wordt op het opgegeven tijdstip bijgewerkt.
