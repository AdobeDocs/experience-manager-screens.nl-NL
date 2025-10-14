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
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# AEM Screens-berichtenservice{#aem-screens-notifications-service}

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***de Berichtendienst van AEM Screens*** beschrijft de activiteit van het monitorapparaat.

In deze sectie worden de volgende onderwerpen behandeld:

* **Overzicht**
* **Vormend E-mailmontages**
* **E-mailbericht**
* **het gebruiksgeval van het Voorbeeld**

<!-- OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3.2 Feature Pack 3 or AEM 6.4.1 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. After you have permissions you can download it from Package Share. -->

## Overzicht {#overview}

***de Dienst van de Meldingen van AEM Screens*** laat beheerders een e-mail ontvangen als een Speler van AEM Screens niet voor een configureerbare tijd pingelt.

Deze dienst kan in de OSGi Webconsole worden gevormd.

## E-mailinstellingen configureren {#configuring-email-settings}

Voer de onderstaande stappen uit om de instellingen voor e-mailmeldingen te configureren:

1. Open **Configuratie van de Console van het Web van Adobe Experience Manager**.
1. Open **E-mailcontroledienst van het Apparaat van Screens**.

   ![&#x200B; screen_shot_2018-04-26at44602pm &#x200B;](assets/screen_shot_2018-04-26at44602pm.png)

1. Definieer de volgende velden zodat u de instellingen voor de e-mail kunt configureren:

   **Weg van Apparaten** - ga de weg aan de Projecten van Screens in die u wilt controleren. Het pad is meestal `/home/users/screens/<Name of your project>` .

   Bijvoorbeeld, als uw project **`We.Retail`** is, gebruik de projectweg als ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Geef het projectpad op waarin de apparaatgebruikers zich bevinden.

   **Frequentie van het Programma** - specificeer een tijd (bijvoorbeeld, 5:00 P.M. of 17:00) of frequentie in uren (bijvoorbeeld, 1) waarop deze monitor e-mail zou moeten verzenden.

   **pingelt Tijd uit** - Dit gebied specificeert het interval in notulen waarna een apparaat als niet bereikbaar zou moeten worden beschouwd.

   **Server SMTP** - specificeert de Server SMTP die voor het verzenden van e-mails wordt gebruikt.

   **Haven SMTP** - ga de Haven SMTP in.

   **Gebruik TLS** - de Veiligheid van de Laag van het Vervoer (TLS) laat u een veilige mededeling met de Server gebruiken SMTP.

   Adobe raadt u aan TLS te gebruiken voor een veilige verbinding met bedrijfspostservers. Vraag uw e-mailbeheerder om de juiste waarden.

   **gebruikersbenaming** - specificeer de gebruikersbenaming voor het verzenden van e-mails.

   **wachtwoord** - specificeer het wachtwoord voor het verzenden van e-mails.

   **Ontvanger** - specificeer het e-mailadres van de ontvanger.

   >[!NOTE]
   >
   >U kunt slechts één e-mailadres invoeren. Als u een grote hoeveelheid e-mail wilt verzenden, maakt u een groep- of distributielijst met de relevante gebruikers.

1. Klik **sparen** om de monitoractiviteit door e-mail voor uw apparaat van AEM Screens te vormen.

## E-mailmelding {#email-notification}

Nadat u de configuratie voor uw e-mailberichten hebt ingesteld, ontvangt u een e-mailbericht met de koppeling naar het daadwerkelijke apparaat dat wordt gemeld dat het niet actief is.

Als u deze koppeling opent, gaat u rechtstreeks naar het dashboard van het apparaat.

E-mails worden alleen verzonden als:

* er is minstens één apparaat dat niet voor bepaald pingel timeout heeft gepingeld, en
* blijft niet pingelen op het tijdstip van het genereren van de e-mail.

### Voorbeelden van gevallen {#example-use-cases}

In het volgende voorbeeld worden een aantal scenario&#39;s ter referentie beschreven, waarmee u de eigenschappen kunt configureren via de Screens Device Email Monitoring Service.

**Scenario 1**

U plaatst de planningsfrequentie als 1:00 A.M. en pingelt onderbreking als 60. Vervolgens ontvangt u een e-mailmelding waarin wordt bevestigd dat het AEM Screens-apparaat niet tussen 12:00 uur &#39;s middags pingelt.

**Scenario 2**

U plaatst de planningsfrequentie als 1 en pingelt onderbreking als 60. Als uw AEM Screens-apparaat vervolgens niet op een bepaald tijdstip van de dag pingelt, ontvangt u een e-mailmelding waarin de inactiviteit van het apparaat wordt bevestigd.
