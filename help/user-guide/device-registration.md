---
title: Apparaatregistratie
seo-title: Apparaatregistratie
description: Deze pagina beschrijft het proces van de apparatenregistratie in een project van AEM Screens.
seo-description: Deze pagina beschrijft het proces van de apparatenregistratie in een project van AEM Screens.
uuid: 5365e506-1641-4a0c-b34d-c39da02f700b
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
discoiquuid: 523084f6-bd71-4daf-95b7-fc4c481f76dc
docset: aem65
feature: Schermen beheren, apparaatregistratie
role: Administrator
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---


# Apparaatregistratie {#device-registration}

De volgende pagina beschrijft het proces van de apparatenregistratie in een project van AEM Screens.

## Een apparaat {#registering-a-device} registreren

Het registratieproces van het apparaat wordt uitgevoerd op twee aparte computers:

* Het daadwerkelijke apparaat dat moet worden geregistreerd, bijvoorbeeld uw signaalweergave
* De AEM server waarmee het apparaat wordt geregistreerd

>[!NOTE]
>
>Nadat u de nieuwste Windows Player (*.exe*) hebt gedownload, voert u vanuit de pagina [AEM 6.4 Player Downloads](https://download.macromedia.com/screens/) de stappen op de speler uit om de ad-hocinstallatie te voltooien:
>
>1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
>1. Navigeer naar **Configuration** vanuit het linkeractiemenu en voer het locatieadres van de AEM in **Server** in en klik **Save**.
>1. Klik op de koppeling **Registratie** in het linkeractiemenu en de onderstaande stappen om het registratieproces van het apparaat te voltooien.

>



![screen_shot_2018-11-26at12118pm](assets/screen_shot_2018-11-26at12118pm.png)

1. Start AEM Screens Player op uw apparaat. De registratieinterface wordt weergegeven.

   ![screen_shot_2018-11-26at104230am](assets/screen_shot_2018-11-26at104230am.png)

1. Navigeer in AEM naar de map **Devices** van uw project.

   >[!NOTE]
   >
   >Zie [Project voor schermen maken en beheren ](creating-a-screens-project.md) voor meer informatie over het maken van een nieuw project voor schermen in het AEM dashboard.

1. Tik/klik op de knop **Apparaatbeheer** op de actiebalk.

   ![screen_shot_2018-11-26at104702am](assets/screen_shot_2018-11-26at104702am.png)

1. Tik/klik op de knop **Apparaatregistratie** rechtsboven.

   ![screen_shot_2018-11-26at104815am](assets/screen_shot_2018-11-26at104815am.png)

1. Selecteer het gewenste apparaat (zelfde als stap 1) en tik/klik **Apparaat registreren**.

   ![screen_shot_2018-11-26at105112am](assets/screen_shot_2018-11-26at105112am.png)

1. Wacht AEM tot het apparaat de registratiecode heeft verzonden.

   ![screen_shot_2018-11-26at105150am](assets/screen_shot_2018-11-26at105150am.png)

1. Controleer **Registratiecode** in uw apparaat.

   ![screen_shot_2018-11-26at105227am](assets/screen_shot_2018-11-26at105227am.png)

1. Als de **Registratiecode** op beide computers hetzelfde is, tikt u op **Valideren** in AEM, zoals in stap (6).
1. Stel de gewenste naam voor het apparaat in en klik op **Register**.

   ![screen_shot_2018-11-26at105357am](assets/screen_shot_2018-11-26at105357am.png)

1. Tik/klik **Voltooi** om het registratieproces te voltooien.

   ![screen_shot_2018-11-26at105456am](assets/screen_shot_2018-11-26at105456am.png)

   >[!NOTE]
   >
   >Met **Nieuwe registratie** kunt u een nieuw apparaat registreren.
   >
   >Met **Weergave toewijzen** kunt u het apparaat rechtstreeks aan een weergave toevoegen.

   Als u **Voltooien** klikt, zult u het apparaat aan een vertoning moeten toewijzen.

   ![screen_shot_2018-11-26at105740am](assets/screen_shot_2018-11-26at105740am.png)

   >[!NOTE]
   >
   >Voor meer informatie over het creëren van en het beheren van een vertoning voor uw project van het Scherm, gelieve te verwijzen naar [het Creëren van en het Leiden Vertoningen](managing-displays.md).

### Apparaat toewijzen aan een beeldscherm {#assigning-device-to-a-display}

Als u het apparaat niet aan een display hebt toegewezen, voert u de onderstaande stappen uit om uw apparaat aan een weergave in uw AEM Screens-project toe te wijzen:

1. Selecteer het apparaat en klik **Apparaat toewijzen** in de actiebalk.

   ![screen_shot_2018-11-26at111026am](assets/screen_shot_2018-11-26at111026am.png)

1. Selecteer het pad van de weergave in **Pad weergeven/apparaatconfiguratie**.

   ![screen_shot_2018-11-26at111252am](assets/screen_shot_2018-11-26at111252am.png)

1. Klik **Wijs** toe wanneer u de weg selecteert.

   ![screen_shot_2018-11-26at111722am](assets/screen_shot_2018-11-26at111722am.png)

1. Klik **Voltooien** zodra het apparaat met succes is toegewezen, zoals getoond in de hieronder figuur.

   ![screen_shot_2018-11-26at112041am](assets/screen_shot_2018-11-26at112041am.png)

   Daarnaast kunt u het weergavedashboard weergeven door te klikken op **Voltooien**.

   ![screen_shot_2018-11-26at112154am](assets/screen_shot_2018-11-26at112154am.png)

## Een apparaat zoeken vanuit Apparaatbeheer {#search-device}

Nadat u apparaten hebt geregistreerd voor uw speler, kunt u alle apparaten weergeven via de interface van Apparaatbeheer.

1. Navigeer naar de interface van Apparaatbeheer van uw AEM Screens-project, bijvoorbeeld **DemoScreens** —> **Devices**.

1. Selecteer de map **Apparaten** en klik op **Apparaatbeheer** op de actiebalk.

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-1.png)

1. De lijst met geregistreerde apparaten wordt weergegeven.

1. Als u een lange lijst met geregistreerde apparaten hebt, kunt u nu zoeken met het zoekpictogram op de actiebalk

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-2.png)

   Of

   Klik `/` (schuine streep naar voren) om de zoekfunctionaliteit aan te roepen.

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-3.png)


### Beperkingen betreffende zoekfunctionaliteit {#limitations}

* De gebruiker zal om het even welk woord kunnen zoeken bestaand in *Apparaat ID* of *Apparaatnaam*.

   >[!NOTE]
   >Het wordt aanbevolen de apparaatnamen te maken in meerdere woorden, zoals *Boston Store Lobby* in plaats van één *BostonStoreLobby*.

* Als u apparaatnamen maakt, zoals *Boston Store Lobby*, kunt u zoeken naar elk woord *boston*, *store* of *lobby*, maar als de apparaatnaam wordt aangeduid als *BostonStoreLobby* zoekend *boston* zal de resultaten niet tonen.

* Jokerteken, `*` wordt ondersteund voor zoeken. Als u alle apparaten wilt zoeken met namen die beginnen met *boston*, kunt u *boston** gebruiken.

* Als de apparaatnaam *BostonStoreLobby* is en het zoeken naar *boston* zal het resultaat niet retourneren in plaats daarvan wanneer u *boston** in uw zoekcriteria gebruikt, wordt het resultaat geretourneerd.

## Beperkingen betreffende apparaatregistratie {#limitations-on-device-registration}

Beperkingen van wachtwoorden voor gebruikers in het hele systeem kunnen leiden tot een fout in de apparaatregistratie. De apparaatregistratie gebruikt een willekeurig gegenereerd wachtwoord om de apparaatgebruiker te maken.

Als het wachtwoord wordt beperkt door de configuratie *AuthorizableActionProvider*, zou het creëren van de apparatengebruiker kunnen ontbreken.

>[!NOTE]
>
>Het huidige gegenereerde willekeurige wachtwoord bestaat uit 36 ASCII-tekens, variërend van 33 tot 122 (bevat bijna alle speciale tekens).

```java
25.09.2016 16:54:03.140 *ERROR* [59.100.121.82 [1474844043109] POST /content/screens/svc/registration HTTP/1.1] com.adobe.cq.screens.device.registration.impl.RegistrationServlet Error during device registration
javax.jcr.nodetype.ConstraintViolationException: Password violates password constraint (^(?=.*\d).{7,9}$).
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.validatePassword(PasswordValidationAction.java:105)
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.onPasswordChange(PasswordValidationAction.java:76)
        at org.apache.jackrabbit.oak.security.user.UserManagerImpl.onPasswordChange(UserManagerImpl.java:308)
```

### Aanvullende bronnen {#additional-resources}

Zie [AEM Screens Player](working-with-screens-player.md) voor meer informatie over AEM Screens Player.
