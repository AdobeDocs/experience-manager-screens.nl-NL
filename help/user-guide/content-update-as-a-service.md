---
title: Inhoud bijwerken als service
seo-title: Inhoud bijwerken als service
description: Volg deze pagina om over de Update van de Inhoud als Dienst te leren.
seo-description: Volg deze pagina om over de Update van de Inhoud als Dienst te leren.
uuid: c73126ca-18d0-45b4-bdde-a3653082bfc4
contentOwner: Jyotika syal
translation-type: tm+mt
source-git-commit: 323e2df2419cc65de7bfe88648ffd1dbd3a91aec

---


# Inhoud bijwerken als service {#content-update-as-a-service}

In deze sectie worden de volgende onderwerpen over het bijwerken van content-as-a-service besproken:

* **Overzicht**
* **Bulk offline bijwerken gebruiken**

>[!CAUTION]
>
>Deze AEM-schermfunctionaliteit is alleen beschikbaar als u AEM 6.3 Feature Pack 3 of AEM 6.4 Screens Feature Pack 1 hebt geïnstalleerd.
>
>Neem contact op met de ondersteuning van Adobe om toegang te krijgen tot dit onderdeel. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

## Overzicht {#overview}

Bulk offline bijwerken, waarmee u alle kanalen in bulk kunt bijwerken. Zo voorkomt u de problemen bij het navigeren naar een bepaald kanaal en het bijwerken van de inhoud. In plaats daarvan kunt u alle inhoud in kanalen voor één specifiek project in één keer bijwerken.

U kunt deze activiteit voor een tijd van lager netwerkverkeer ook plannen.

>[!NOTE]
>
>De functie Offlineupdate bulken is geoptimaliseerd en werkt alleen de kanalen bij die zijn gewijzigd.

## Bulk offline bijwerken gebruiken {#using-bulk-offline-update}

U kunt bulk off-line update van het Gebruikersinterface (UI) manueel gebruiken of de bulkupdate van de diensten plannen OSGi.

### Gebruikersinterface voor AEM-schermen gebruiken {#using-aem-screens-user-interface}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM-rasterproject:

1. Navigeer naar uw AEM-rasterproject.
1. Selecteer het project en klik op Offlineinhoud **** bijwerken op de actiebalk om de kanaalinhoud handmatig bij te werken.

   ![screen_shot_2018-04-24at122256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Webconsole-configuratie van Adobe Experience Manager {#adobe-experience-manager-web-console-configuration}

Voer de onderstaande stappen uit om bulksgewijs offline bij te werken voor een AEM-rasterproject:

1. Configuratie van de webconsole van Adobe Experience Manager.
1. Zoeken naar bulksgewijs offline updateservices.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Voeg de volgende eigenschappen toe:

   **Het Weg** van het project specificeert de weg van uw project van de Schermen AEM. Het pad is meestal `/content/screens/<Name of your project>`.

   *Bijvoorbeeld*, `/content/screens/we-retail`. U kunt dit pad vinden in de URL door een project te selecteren onder AEM-schermen (klik niet op het pictogram).

   >[!NOTE]
   >
   >Geef het projectpad op ten opzichte van het kanaal.

   **De Frequentie** van het programma specificeert een tijd, bijvoorbeeld, 5:00 pm of 17:00 waarbij deze dienst off-line inhoud zou moeten bijwerken.

1. Klik op **Opslaan** om uw instellingen op te slaan. De inhoud wordt dan op het opgegeven tijdstip bijgewerkt.

