---
title: Apparaatregistratie
description: Meer informatie over het registratieproces van een AEM Screens-project.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens, Device Registration
role: Admin
level: Intermediate
exl-id: b2d3a2cd-263f-4142-80da-29ce54cbf391
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 0%

---

# Apparaatregistratie {#device-registration}

De volgende pagina beschrijft het proces van de apparatenregistratie in een project van AEM Screens.

## Een apparaat registreren {#registering-a-device}

Het registratieproces van het apparaat wordt uitgevoerd op twee aparte computers:

* Het daadwerkelijke apparaat dat moet worden geregistreerd, bijvoorbeeld uw signaalweergave
* De AEM-server waarmee het apparaat wordt geregistreerd

>[!NOTE]
>
>Nadat u de recentste Speler van Vensters (*.exe*) downloadt, van [ AEM 6.4 de Downloads van de Speler ](https://download.macromedia.com/screens/) pagina, volg de stappen op de speler om de ad hoc installatie te voltooien:
>
>1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
>1. Navigeer aan **Configuratie** van het linkeractiemenu en ga het plaatsadres van de instantie van AEM in **Server** in en klik **sparen**.
>1. Klik de **verbinding van de Registratie** van het linkeractiemenu en de stappen hieronder om het proces van de apparatenregistratie te voltooien.
>

![ screen_shot_2018-11-26at12118pm ](assets/screen_shot_2018-11-26at12118pm.png)

1. Start AEM Screens Player op uw apparaat. De registratieinterface wordt weergegeven.

   ![ screen_shot_2018-11-26at104230am ](assets/screen_shot_2018-11-26at104230am.png)

1. In AEM, navigeer aan de **omslag van Apparaten** van uw project.

   >[!NOTE]
   >
   >Om meer informatie te krijgen bij het creëren van een project voor Screens in het dashboard van AEM, zie [ tot stand brengen en het Project van Screens beheren ](creating-a-screens-project.md).

1. Klik de **knoop van de Manager van het Apparaat** in de actiebar.

   ![ screen_shot_2018-11-26at104702am ](assets/screen_shot_2018-11-26at104702am.png)

1. Klik de **knoop van de Registratie van het Apparaat** op het hoogste recht.

   ![ screen_shot_2018-11-26at104815am ](assets/screen_shot_2018-11-26at104815am.png)

1. Klik het vereiste apparaat (het zelfde zoals stap 1) en klik **Apparaat van het Register**.

   ![ screen_shot_2018-11-26at105112am ](assets/screen_shot_2018-11-26at105112am.png)

1. Wacht in AEM tot het apparaat de registratiecode heeft verzonden.

   ![ screen_shot_2018-11-26at105150am ](assets/screen_shot_2018-11-26at105150am.png)

1. In uw apparaat, controleer de **Code van de Registratie**.

   ![ screen_shot_2018-11-26at105227am ](assets/screen_shot_2018-11-26at105227am.png)

1. Als de **Code van de Registratie** het zelfde op beide machines is, klik **bevestigen** knoop in AEM, zoals aangetoond in stap (6).
1. Plaats de gewenste naam voor het apparaat, en klik **Register**.

   ![ screen_shot_2018-11-26at105357am ](assets/screen_shot_2018-11-26at105357am.png)

1. Klik **Afwerking** om het registratieproces te voltooien.

   ![ screen_shot_2018-11-26at105456am ](assets/screen_shot_2018-11-26at105456am.png)

   >[!NOTE]
   >
   >Het **Register Nieuwe** laat u een nieuw apparaat registreren.
   >
   >**wijs Vertoning** toe laat u direct het apparaat aan een vertoning toevoegen.

   Als u **Afwerking** klikt, wijs het apparaat aan een vertoning toe.

   ![ screen_shot_2018-11-26at105740am ](assets/screen_shot_2018-11-26at105740am.png)

   >[!NOTE]
   >
   >Meer leren over het creëren van en het leiden van een vertoning voor uw project van Screens, zie [ Creërend en het Leiden Vertoningen ](managing-displays.md).

### Apparaat toewijzen aan een weergave {#assigning-device-to-a-display}

Als u het apparaat niet aan een display hebt toegewezen, voert u de onderstaande stappen uit om uw apparaat aan een weergave in uw AEM Screens-project toe te wijzen:

1. Klik het apparaat en klik **toewijzen Apparaat** van de actiebar.

   ![ screen_shot_2018-11-26at111026am ](assets/screen_shot_2018-11-26at111026am.png)

1. Klik de weg van de vertoning in **Vertoning/de Weg van Config van het Apparaat**.

   ![ screen_shot_2018-11-26at111252am ](assets/screen_shot_2018-11-26at111252am.png)

1. Klik **toewijzen** wanneer u de weg klikt.

   ![ screen_shot_2018-11-26at111722am ](assets/screen_shot_2018-11-26at111722am.png)

1. Klik **Afwerking** zodra het apparaat met succes, zoals aangetoond in het hieronder cijfer wordt toegewezen.

   ![ screen_shot_2018-11-26at112041am ](assets/screen_shot_2018-11-26at112041am.png)

   Ook, kunt u het vertoningsdashboard bekijken door **Afwerking** te selecteren.

   ![ screen_shot_2018-11-26at112154am ](assets/screen_shot_2018-11-26at112154am.png)

## Een apparaat zoeken vanuit Apparaatbeheer {#search-device}

Wanneer u apparaten bij uw speler hebt geregistreerd, kunt u alle apparaten weergeven via de interface van Apparaatbeheer.

1. Navigeer aan de Manager UI van het Apparaat van uw project van AEM Screens, bijvoorbeeld, **DemoScreens** > **Apparaten**.

1. Klik de **omslag van Apparaten** en klik **Manager van het Apparaat** van de actiebar.

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-1.png)

1. De lijst met geregistreerde apparaten wordt weergegeven.

1. Als u een lange lijst met geregistreerde apparaten hebt, kunt u nu zoeken met het zoekpictogram op de actiebalk

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-2.png)

   Of,

   Selecteer `/` (forward slash) om de zoekfunctionaliteit aan te roepen.

   ![afbeelding](/help/user-guide/assets/device-manager/device-manager-3.png)


### Beperkingen betreffende zoekfunctionaliteit {#limitations}

* De gebruiker kan om het even welk woord zoeken bestaand in *apparatenidentiteitskaart* of *apparatenNaam*.

  >[!NOTE]
  >Het wordt aanbevolen de apparaatnamen te maken in meerdere woorden, zoals *`Boston Store Lobby`* in plaats van in één *`BostonStoreLobby`* .

* Als u apparaatnamen hebt gemaakt, zoals *`Boston Store Lobby`* , zoekt het naar elk woord *`boston`* , *`store`* of *`lobby`* . Als de apparaatnaam echter *`BostonStoreLobby`* is, geeft het zoeken naar *`boston`* geen resultaten.

* Jokerteken, `*` wordt ondersteund voor zoeken. Als u alle apparaten met namen wilt vinden die beginnen met *`boston`*, kunt u * `boston` ** gebruiken.

* Als de apparaatnaam *`BostonStoreLobby`* is en zoeken naar *`boston`* het resultaat niet retourneert, retourneert u het resultaat als u *`boston`** in de zoekcriteria gebruikt.

## Beperkingen betreffende apparaatregistratie {#limitations-on-device-registration}

Beperkingen van gebruikerswachtwoorden voor het hele systeem kunnen leiden tot een fout in de apparaatregistratie. De apparaatregistratie gebruikt een willekeurig gegenereerd wachtwoord om de apparaatgebruiker te maken.

Als de *AuthorizableActionProvider* configuratie het wachtwoord beperkt, zou het creëren van de apparatengebruiker kunnen ontbreken.

>[!NOTE]
>
>Het huidige gegenereerde willekeurige wachtwoord bestaat uit 36 ASCII-tekens tussen 33 en 122 (bevat bijna alle speciale tekens).

```java
25.09.2016 16:54:03.140 *ERROR* [59.100.121.82 [1474844043109] POST /content/screens/svc/registration HTTP/1.1] com.adobe.cq.screens.device.registration.impl.RegistrationServlet Error during device registration
javax.jcr.nodetype.ConstraintViolationException: Password violates password constraint (^(?=.*\d).{7,9}$).
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.validatePassword(PasswordValidationAction.java:105)
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.onPasswordChange(PasswordValidationAction.java:76)
        at org.apache.jackrabbit.oak.security.user.UserManagerImpl.onPasswordChange(UserManagerImpl.java:308)
```

### Overige bronnen {#additional-resources}

Meer over de Speler van AEM Screens leren, zie [ Speler van AEM Screens ](working-with-screens-player.md).
