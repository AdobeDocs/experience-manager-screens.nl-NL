---
title: AEM Screens-berichtenservice
seo-title: AEM Screens Notifications Service
description: Volg deze pagina voor meer informatie over hoe u de apparaatactiviteit kunt controleren.
seo-description: Follow this page to learn more about how you can monitor device activity.
uuid: 9843219d-ed39-4e4f-bef4-e500528ff9f1
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 8879e510-4f0e-46da-87d2-77c5aaacb26e
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 205235d7-e621-4134-975c-257ae60939bc
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# AEM Screens-berichtenservice{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens-berichtenservice***, beschrijft de functie waarmee u de apparaatactiviteit kunt controleren.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **E-mailinstellingen configureren**
* **E-mailmelding**
* **Voorbeeld: hoofdletter gebruiken**

>[!CAUTION]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.3.2 Feature Pack 3 of AEM 6.4.1 Screens Feature Pack 1 hebt geïnstalleerd.
>
>Als u toegang wilt krijgen tot dit pakket functies, moet u contact opnemen met de Adobe Support en toegang aanvragen. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

## Overzicht {#overview}

***AEM Screens-berichtenservice***, stelt beheerders in staat een e-mail te ontvangen als een AEM schermspeler niet pingelt gedurende een configureerbare periode.

Deze dienst kan in de OSGi Webconsole worden gevormd.

## E-mailinstellingen configureren {#configuring-email-settings}

Voer de onderstaande stappen uit om de instellingen voor e-mailmeldingen te configureren:

1. Openen **Configuratie Adobe Experience Manager-webconsole**.
1. Openen **E-mailbewakingsservice van apparaat weergeven**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieer de volgende velden om uw instellingen voor de e-mail te configureren:

   **Pad naar apparaat** Voer het pad in naar de schermprojecten die u wilt controleren. Het pad is meestal `/home/users/screens/<Name of your project>`.

   Als uw project bijvoorbeeld **Wij.Detailhandel**, gebruikt u het projectpad als ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Geef het projectpad op waarin de apparaatgebruikers zich bevinden.

   **Planningsfrequentie** Geef een tijd (bijv. 17:00 uur of 15:00 uur) of frequentie op in uren (bijv. 1) waarop deze monitor e-mails moet verzenden.

   **Time-out pingel** Dit specificeert het interval in notulen waarna een apparaat als niet bereikbaar zou moeten worden beschouwd.

   **SMTP-server** Specificeert de Server SMTP die voor het verzenden van e-mails wordt gebruikt.

   **SMTP-poort** Ga de Haven SMTP in.

   **TLS gebruiken** De Veiligheid van de Laag van het vervoer (TLS) laat u toe om een veilige communicatie met de Server te gebruiken SMTP.

   Het wordt aanbevolen TLS te gebruiken voor een veilige verbinding met bedrijfsmailservers. Vraag uw e-mailbeheerder om de juiste waarden.

   **gebruikersnaam** Geef de gebruikersnaam op voor het verzenden van e-mails.

   **password** Geef het wachtwoord op voor het verzenden van e-mails.

   **Ontvanger** Geef het e-mailadres van de ontvanger op.

   >[!NOTE]
   >
   >U kunt slechts één e-mailadres invoeren. Als u een grote hoeveelheid e-mail wilt verzenden, maakt u een groep- of distributielijst met de relevante gebruikers.

1. Klikken **Opslaan** om de monitoractiviteit door een e-mail voor uw AEM Screens apparaat te vormen.

## E-mailmelding {#email-notification}

Nadat u de configuratie voor uw e-mailberichten hebt ingesteld, ontvangt u een e-mailmelding met daarin de koppeling naar het daadwerkelijke apparaat dat van inactiviteit wordt gemeld.

Als u deze koppeling opent, gaat u rechtstreeks naar het dashboard van het apparaat.

E-mails worden alleen verzonden als er ten minste één apparaat is dat niet is gepingeld voor de opgegeven pingelt-time-out en dat nog steeds niet pingelt op het moment dat de e-mail wordt gegenereerd.

### Voorbeelden {#example-use-cases}

In het volgende voorbeeld worden enkele referentiescenario&#39;s beschreven om de eigenschappen van de E-mailbewakingsservice van het schermapparaat te configureren.

**Scenario 1**:

Als u de planningsfrequentie als 1:00 am plaatst en pingelt onderbreking als 60, dan als uw apparaat van de Schermen niet tussen 12:00 pm tot 13:00 pm pingelt, zult u een e-mailbericht ontvangen die apparateninactiviteit bevestigt.

**Scenario 2**:

Als u de planningsfrequentie als 1 plaatst en pingelt onderbreking als 60, dan als uw apparaat van de Schermen niet tussen één op een bepaald tijdstip van de dag pingelt, zult u een e-mailbericht ontvangen die apparateninactiviteit bevestigen.
