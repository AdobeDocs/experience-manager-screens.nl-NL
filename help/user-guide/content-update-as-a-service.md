---
title: Inhoud bijwerken als service
description: Meer informatie over Inhoud bijwerken als service.
contentOwner: Jyotika syal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: de9f669b-9ce7-4d70-99b4-0b69ef3c1af5
source-git-commit: b65e59473e175e7c1b31fba900bb7e47eff3a263
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Inhoud bijwerken als service {#content-update-as-a-service}

In deze sectie worden de volgende onderwerpen over het bijwerken van content-as-a-service besproken:

* **Overzicht**
* **Bulk offline bijwerken gebruiken**

<!--
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permission you can download it from Package Share. -->

## Overzicht {#overview}

Bulk offline bijwerken, waarmee u alle kanalen in bulk kunt bijwerken. Zo voorkomt u de problemen bij het navigeren naar een bepaald kanaal en het bijwerken van de inhoud. In plaats daarvan kunt u alle inhoud in kanalen voor één specifiek project in één keer bijwerken.

U kunt deze activiteit voor een tijd van lager netwerkverkeer ook plannen.

>[!NOTE]
>
>De functie Offlineupdate bulken is geoptimaliseerd en werkt alleen de kanalen bij die zijn gewijzigd.

## Bulk offline bijwerken gebruiken {#using-bulk-offline-update}

U kunt bulk off-line update van het Gebruikersinterface (UI) manueel gebruiken of de bulkupdate van de diensten plannen OSGi.

### AEM Screens-gebruikersinterface gebruiken {#using-aem-screens-user-interface}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Ga naar uw AEM Screens-project.
1. Selecteer het project en klik op **Offline inhoud bijwerken** in de actiebalk om de kanaalinhoud handmatig bij te werken.

   ![screen_shot_2018-04-24at12256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Configuratie Adobe Experience Manager-webconsole {#adobe-experience-manager-web-console-configuration}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Configuratie Adobe Experience Manager-webconsole.
1. Zoeken naar bulksgewijs offline updateservices.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Voeg de volgende eigenschappen toe:

   **Projectpad** Geef het pad van uw AEM Screens-project op. Het pad is meestal `/content/screens/<Name of your project>`.

   *Bijvoorbeeld*, `/content/screens/we-retail`. U kunt dit pad vinden in de URL door een willekeurig project te selecteren onder AEM Screens (klik niet op het pictogram).

   >[!NOTE]
   >
   >Geef het projectpad op ten opzichte van het kanaal.

   **Planningsfrequentie** Geef een tijd op, bijvoorbeeld 5:00 p.m. of 17:00, waarop deze service offline-inhoud moet bijwerken.

1. Selecteren **Opslaan** zodat u uw instellingen kunt opslaan. Alle inhoud wordt op het opgegeven tijdstip bijgewerkt.
