---
title: AEM Screens-berichtenservice
description: Meer informatie over hoe u de apparaatactiviteiten voor AEM Screens kunt controleren.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 205235d7-e621-4134-975c-257ae60939bc
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# AEM Screens-berichtenservice{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens-berichtenservice*** beschrijft de activiteit van het monitorapparaat.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **E-mailinstellingen configureren**
* **E-mailmelding**
* **Voorbeeld van gebruik**

<!-- OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3.2 Feature Pack 3 or AEM 6.4.1 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. After you have permissions you can download it from Package Share. -->

## Overzicht {#overview}

***AEM Screens-berichtenservice*** Hiermee kunnen beheerders een e-mail ontvangen als een AEM Screens Player niet pingelt gedurende een configureerbare tijd.

Deze dienst kan in de OSGi Webconsole worden gevormd.

## E-mailinstellingen configureren {#configuring-email-settings}

Voer de onderstaande stappen uit om de instellingen voor e-mailmeldingen te configureren:

1. Openen **Configuratie Adobe Experience Manager-webconsole**.
1. Openen **E-mailbewakingsservice van apparaat weergeven**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieer de volgende velden zodat u de instellingen voor de e-mail kunt configureren:

   **Pad naar apparaat** Ga de weg aan de Projecten van het Scherm in die u wilt controleren. Het pad is meestal `/home/users/screens/<Name of your project>`.

   Als uw project bijvoorbeeld **`We.Retail`**, gebruikt u het projectpad als ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Geef het projectpad op waarin de apparaatgebruikers zich bevinden.

   **Planningsfrequentie** - Geef een tijd (bijvoorbeeld 17:00 of 17:00) of frequentie op in uren (bijvoorbeeld 1) waarop deze monitor e-mails moet verzenden.

   **Pingetijd uit** - Dit specificeert het interval in notulen waarna een apparaat als niet bereikbaar zou moeten worden beschouwd.

   **SMTP-server** - Geeft de SMTP-server op die wordt gebruikt voor het verzenden van e-mails.

   **SMTP-poort** - Ga de Haven SMTP in.

   **TLS gebruiken** - De Veiligheid van de Laag van het Vervoer (TLS) laat u een veilige mededeling met de Server gebruiken SMTP.

   Adobe raadt u aan TLS te gebruiken voor een veilige verbinding met bedrijfsmailservers. Vraag uw e-mailbeheerder om de juiste waarden.

   **gebruikersnaam** - Geef de gebruikersnaam op voor het verzenden van e-mails.

   **password** - Geef het wachtwoord op voor het verzenden van e-mails.

   **Ontvanger** - Geef het e-mailadres van de ontvanger op.

   >[!NOTE]
   >
   >U kunt slechts één e-mailadres invoeren. Als u een grote hoeveelheid e-mail wilt verzenden, maakt u een groep- of distributielijst met de relevante gebruikers.

1. Klikken **Opslaan** om de monitoractiviteit door een e-mail voor uw AEM Screens apparaat te vormen.

## E-mailmelding {#email-notification}

Nadat u de configuratie voor uw e-mailberichten hebt ingesteld, ontvangt u een e-mailbericht met de koppeling naar het daadwerkelijke apparaat dat wordt gemeld dat het niet actief is.

Als u deze koppeling opent, gaat u rechtstreeks naar het dashboard van het apparaat.

E-mails worden alleen verzonden als er ten minste één apparaat is dat niet pingelt voor de opgegeven pingelt-time-out en dat nog steeds niet pingelt op het moment dat de e-mail wordt gegenereerd.

### Voorbeelden van gevallen {#example-use-cases}

In het volgende voorbeeld worden enkele referentiescenario&#39;s beschreven om de eigenschappen van de E-mailcontroledienst van het Apparaat van het Scherm te configureren.

**Scenario 1**

U plaatst de planningsfrequentie als 1:00 A.M. en pingelt onderbreking als 60. Vervolgens ontvangt u een e-mailmelding waarin wordt bevestigd dat het AEM Screens-apparaat niet tussen 12:00 uur &#39;s middags pingelt.

**Scenario 2**

U plaatst de planningsfrequentie als 1 en pingelt onderbreking als 60. Als uw AEM Screens-apparaat vervolgens niet tussen één keer op een bepaald tijdstip van de dag pingelt, ontvangt u een e-mailmelding waarin de inactiviteit van het apparaat wordt bevestigd.
