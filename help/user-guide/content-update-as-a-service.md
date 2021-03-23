---
title: Inhoud bijwerken als service
seo-title: Inhoud bijwerken als service
description: Volg deze pagina om over de Update van de Inhoud als Dienst te leren.
seo-description: Volg deze pagina om over de Update van de Inhoud als Dienst te leren.
uuid: c73126ca-18d0-45b4-bdde-a3653082bfc4
contentOwner: Jyotika syal
feature: Ontwerpschermen
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# Inhoud bijwerken als service {#content-update-as-a-service}

In deze sectie worden de volgende onderwerpen over het bijwerken van content-as-a-service besproken:

* **Overzicht**
* **Bulk offline bijwerken gebruiken**

>[!CAUTION]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.3 Feature Pack 3 of AEM 6.4 Screens Feature Pack 1 hebt geïnstalleerd.
>
>Als u toegang wilt krijgen tot dit pakket functies, moet u contact opnemen met de Adobe Support en toegang aanvragen. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

## Overzicht {#overview}

Bulk offline bijwerken, waarmee u alle kanalen in bulk kunt bijwerken. Zo voorkomt u de problemen bij het navigeren naar een bepaald kanaal en het bijwerken van de inhoud. In plaats daarvan kunt u alle inhoud in kanalen voor één specifiek project in één keer bijwerken.

U kunt deze activiteit voor een tijd van lager netwerkverkeer ook plannen.

>[!NOTE]
>
>De functie Offlineupdate bulken is geoptimaliseerd en werkt alleen de kanalen bij die zijn gewijzigd.

## Bulk offline bijwerken {#using-bulk-offline-update} gebruiken

U kunt bulk off-line update van het Gebruikersinterface (UI) manueel gebruiken of de bulkupdate van de diensten plannen OSGi.

### AEM Screens-gebruikersinterface {#using-aem-screens-user-interface} gebruiken

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Navigeer naar uw AEM Screens-project.
1. Selecteer het project en klik **Offline inhoud bijwerken** van de actiebar om de kanaalinhoud manueel bij te werken.

   ![screen_shot_2018-04-24at122256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Adobe Experience Manager Web Console Configuration {#adobe-experience-manager-web-console-configuration}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM Screens-project:

1. Configuratie Adobe Experience Manager-webconsole.
1. Zoeken naar bulksgewijs offline updateservices.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Voeg de volgende eigenschappen toe:

   **Projectpad** opgevenGeef het pad van uw AEM Screens-project op. Het pad is meestal `/content/screens/<Name of your project>`.

   *Bijvoorbeeld*, `/content/screens/we-retail`. U kunt dit pad vinden in de URL door een willekeurig project te selecteren onder AEM Screens (klik niet op het pictogram).

   >[!NOTE]
   >
   >Geef het projectpad op ten opzichte van het kanaal.

   **Plan** FrequencyGeef een tijd op, bijvoorbeeld 17:00 pm of 5:00 pm, waarop deze service offline-inhoud moet bijwerken.

1. Klik op **Opslaan** om uw instellingen op te slaan en uw inhoud wordt op het opgegeven tijdstip bijgewerkt.

