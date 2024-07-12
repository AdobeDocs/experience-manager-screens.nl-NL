---
title: AEM Screens configureren en implementeren
description: De AEM Screens Player is beschikbaar voor Android&trade;, Chrome OS, iOS en Windows. Meer informatie over de configuratie en implementatie van AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
role: Admin
level: Intermediate
exl-id: 8cf4240c-1d6c-441d-b8a0-f01516455543
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# AEM Screens configureren en implementeren {#configuring-and-deploying-aem-screens}

Deze pagina laat zien hoe u de Screens-spelers op uw apparaten kunt installeren en configureren.

## Serverconfiguratie {#server-configuration}

>[!IMPORTANT]
>
>AEM Screens Player gebruikt niet de token Cross-Site Request Svervalsing (CSRF). Als u de AEM server wilt configureren zodat deze klaar is voor gebruik voor AEM Screens, slaat u het verwijzingsfilter over door lege referenties toe te staan.

## Health Check Framework {#health-check-framework}

Met het Health Check Framework kan de gebruiker controleren of twee benodigde configuraties zijn ingesteld voordat een AEM Screens-project wordt uitgevoerd.

Het staat de gebruiker toe om de volgende twee configuratiecontroles te verifiëren om een project van AEM Screens in werking te stellen, namelijk om de staat van de volgende twee filters te controleren:

1. **staat Lege Referateur** toe
2. **https**

Volg de onderstaande stappen om te controleren of deze twee vitale configuraties zijn ingeschakeld voor AEM Screens:

1. Navigeer aan [ Adobe Experience Manager de Console Sling Health Check ](http://localhost:4502/system/console/healthcheck?tags=screensconfigs&amp;overrideGlobalTimeout=).

   ![ activa ](assets/health-check1.png)


2. Klik **uitvoeren de geselecteerde gezondheidscontroles** zodat kunt u de bevestiging voor twee hierboven vermelde eigenschappen in werking stellen.

   Als beide filters worden toegelaten, dan toont de **Dienst van de Gezondheid van de Configuratie van Screens** het **Resultaat** als **O.K.** met beide configuraties zoals toegelaten.

   ![ activa ](assets/health-check2.png)

   Als een of beide filters zijn uitgeschakeld, wordt een waarschuwing voor de gebruiker weergegeven, zoals in de onderstaande afbeelding wordt getoond.

   In de volgende waarschuwing wordt aangegeven of beide filters zijn uitgeschakeld:
   ![ activa ](assets/health-check3.png)

>[!NOTE]
>
>* Om de **Apache het Verdelen Filter van de Referateur** toe te laten, zie [ Lege Verzoeken van de Referentieverwijzingen ](/help/user-guide/configuring-screens-introduction.md#allow-empty-referrer-requests) toestaan.
>* Om de **dienst van HTTP** toe te laten, zie [ Apache Felix Jetty Gebaseerde Dienst van HTTP ](/help/user-guide/configuring-screens-introduction.md#allow-apache-felix-service).

### Vereisten {#prerequisites}

Met de volgende belangrijke punten hieronder kunt u de server configureren en AEM om klaar te zijn voor gebruik voor AEM Screens.

#### Lege verwijzingsverzoeken toestaan {#allow-empty-referrer-requests}

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager** als AEM instantie > hamerpictogram > **Verrichtingen** > **Console van het Web**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **de Configuratie van de Console van het Web van Adobe Experience Manager** opent. Zoeken naar de referentie van de sling.

   Voor het zoeken van het het rangschikken verwijzersbezit, druk **Command+F** voor **Mac** en **Control+F** voor **Vensters**.

1. Controleer **Lege** optie, zoals aangetoond in het hieronder cijfer toestaat.

   ![afbeelding](assets/config/empty-ref2.png)

1. Klik **sparen** om de Filter van de Verwijzer van de Rand toe te laten Apache leeg toestaat.


#### HTTP-service op basis van Apache Felix Jetty {#allow-apache-felix-service}

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager** als AEM instantie > hamerpictogram > **Verrichtingen** > **Console van het Web**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **de Configuratie van de Console van het Web van Adobe Experience Manager** opent. Zoek naar Apache Felix op Jetty gebaseerde HTTP Service.

   Voor het zoeken van dit bezit, druk **Command+F** voor **Mac** en **Control+F** voor **Vensters**.

1. Controleer **toelaten de optie van HTTP**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](assets/config/config-1.png)

1. Klik **sparen** om de *dienst van HTTP* toe te laten.

#### Aanraakinterface inschakelen voor AEM Screens {#enable-touch-ui-for-aem-screens}

AEM Screens vereist TOUCH UI en werkt niet met de Klassieke UI van Adobe Experience Manager (AEM).

1. Navigeren naar `*<yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*`
1. Zorg ervoor dat de **Standaard auteurswijze UI** aan **TOUCH** wordt geplaatst, zoals aangetoond in het hieronder cijfer.

Alternatief, kunt u het zelfde plaatsen ook uitvoeren gebruikend yourAuthorInstance *>* hulpmiddelen (hamerpictogram) > **Verrichtingen** > **Console van het Web** en onderzoek naar **WCM Authoring UI van de Wijze van de Wijze**.

![ screen_shot_2018-12-04at22425pm ](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Met de gebruikersvoorkeuren kunt u altijd de klassieke gebruikersinterface voor specifieke gebruikers inschakelen.

#### AEM in de uitvoermodus NOSAMPLECONTENT {#aem-in-nosamplecontent-runmode}

Het lopende AEM in productie gebruikt **NOSAMPLECONTENT** looppaswijze. Verwijder *x-kader-Options=SAMEORIGIN* kopbal (in de extra sectie van de reactiekop) uit

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

Deze verwijdering is vereist voor AEM Screens Player om onlinekanalen af te spelen.

#### Wachtwoordbeperkingen {#password-restrictions}

Met de recentste veranderingen in ***DeviceServiceImpl***, moet u niet de wachtwoordbeperkingen verwijderen.

U kunt ***DeviceServiceImpl*** van de verbinding hieronder vormen om wachtwoordbeperking toe te laten terwijl het creëren van het wachtwoord voor de gebruikers van het het schermapparaat:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Volg hieronder de stappen om ***DeviceServiceImpl*** te vormen:

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager** als uw AEM instantie > hamerpictogram > **Verrichtingen** > **Console van het Web**.

1. **de Configuratie van de Console van het Web van Adobe Experience Manager** opent. Zoeken naar `*deviceservice*` . Voor het zoeken van het bezit, druk **Command+F** voor macOS en **Control+F** voor Microsoft® Vensters.

![ screen_shot_2019-07-31at92058am ](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcher-configuratie {#dispatcher-configuration}

Leren hoe te om Dispatcher voor een project van AEM Screens te vormen, zie [ Vormend Dispatcher voor een project van AEM Screens ](dispatcher-configurations-aem-screens.md).

#### Java™-codering {#java-encoding}

Plaats het ***coderen Java™*** aan Unicode. `*Dfile.encoding=Cp1252*` werkt bijvoorbeeld niet.

>[!NOTE]
>
>Gebruik HTTPS voor AEM Screens Server in productiegebruik.
