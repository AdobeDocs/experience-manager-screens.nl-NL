---
title: AEM-schermen configureren en implementeren
seo-title: Schermen configureren en implementeren
description: De AEM-schermspeler is beschikbaar voor Android, Chrome OS, iOS en Windows. Deze pagina beschrijft de configuratie en implementatie van AEM-schermen en geeft ook een overzicht van de w/w-selectierichtlijnen voor spelerapparaten.
seo-description: De AEM-schermspeler is beschikbaar voor Android, Chrome OS, iOS en Windows. Deze pagina beschrijft de configuratie en implementatie van AEM-schermen en geeft ook een overzicht van de w/w-selectierichtlijnen voor spelerapparaten.
uuid: bf730d0f-e590-4c0d-a554-e1ff914eb420
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 0c7d6248-8ac0-4387-8725-57ed941f28f7
docset: aem65
translation-type: tm+mt
source-git-commit: 389a44e3f6175e0a43a6e99edd3048f2b8455d0b

---


# AEM-schermen configureren en implementeren {#configuring-and-deploying-aem-screens}

Deze pagina laat zien hoe u de schermspelers op uw apparaten kunt installeren en configureren.

## Serverconfiguratie {#server-configuration}

>[!NOTE]
>
>**Belangrijk**:
>
>De AEM Screens-speler maakt geen gebruik van de token Cross-Site Request-smeedmachine (CSRF). Om de AEM-server te configureren en klaar te maken voor gebruik voor AEM-schermen, slaat u het verwijzingsfilter over door lege referenties toe te staan.

## Health Check Framework {#health-check-framework}

Met het Health Check-framework kan de gebruiker controleren of twee noodzakelijke configuraties zijn ingesteld voordat een AEM Screens-project wordt uitgevoerd.

Het staat de gebruiker toe om de volgende twee configuratiecontroles te verifiëren om een project in werking te stellen AEM van de Schermen, namelijk om de staat van de volgende twee filters te controleren:

1. **Lege referentie toestaan**
2. **https**

Voer de onderstaande stappen uit om te controleren of deze twee essentiële configuraties zijn ingeschakeld voor AEM-schermen:

1. Ga naar [Adobe Experience Manager Web ConsoleSling Health Check](http://localhost:4502/system/console/healthcheck?tags=screensconfigs&overrideGlobalTimeout=).

   ![elementen](assets/health-check1.png)


2. Klik op Geselecteerde **gezondheidscontroles** uitvoeren om de validatie voor twee hierboven vermelde eigenschappen uit te voeren.

   Als beide filters worden toegelaten, dan toont de Dienst **van de Gezondheid van de Configuratie van de** Schermen het **Resultaat** zoals **OK** met beide configuraties zoals toegelaten.

   ![elementen](assets/health-check2.png)

   Als een of beide filters zijn uitgeschakeld, wordt een waarschuwing voor de gebruiker weergegeven, zoals in de onderstaande afbeelding wordt getoond.

   In de volgende waarschuwing wordt aangegeven of beide filters zijn uitgeschakeld:
   ![elementen](assets/health-check3.png)

>[!NOTE]
>
>* Als u het filter **Apache-verwijzingsverwijzing wilt inschakelen**, raadpleegt u [Lege verwijzingsverzoeken](/help/user-guide/configuring-screens-introduction.md#allow-empty-referrer-requests)toestaan.
>* Om de **dienst van HTTP** toe te laten, verwijs naar [Apache Felix op Jetty Gebaseerde Dienst](/help/user-guide/configuring-screens-introduction.md#allow-apache-felix-service)van HTTP.


### Vereisten {#prerequisites}

De volgende belangrijke punten hieronder helpen om server te vormen en AEM klaar voor gebruik voor schermen te zijn AEM.

#### Lege verwijzingsverzoeken toestaan {#allow-empty-referrer-requests}

1. Navigeer naar de webconsoleconfiguratie **van** Adobe Experience Manager via AEM-instantie —> hamerpictogram —> **Bewerkingen** —> **Webconsole**.

   ![screen_shot_2019-07-31at91253am](assets/screen_shot_2019-07-31at91253am.png)

1. **Configuratie** van de webconsole van Adobe Experience Manager wordt geopend. Zoeken naar de referentie van de sling.

   Voor het zoeken van het het rangschikken verwijzend bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

   ![screen_shot_2019-07-31at91728am](assets/screen_shot_2019-07-31at91728am.png)

1. Schakel de optie Lege **** waarden toestaan in, zoals in de onderstaande afbeelding.

   ![screen_shot_2019-07-31at91807am](assets/screen_shot_2019-07-31at91807am.png)

1. Klik op **Opslaan** om het filter Leeg toestaan voor Apache-schuifverwijzing in te schakelen.

#### HTTP-service op basis van Apache Felix Jetty {#allow-apache-felix-service}

1. Navigeer naar de webconsoleconfiguratie **van** Adobe Experience Manager via AEM-instantie —> hamerpictogram —> **Bewerkingen** —> **Webconsole**.

   ![screen_shot_2019-07-31at91253am](assets/screen_shot_2019-07-31at91253am.png)

1. **Configuratie** van de webconsole van Adobe Experience Manager wordt geopend. Zoek naar Apache Felix op Jetty Gebaseerde Dienst van HTTP.

   Voor het zoeken van dit bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

1. Schakel de optie **HTTP** INSCHAKELEN in, zoals in de onderstaande afbeelding wordt getoond.

   ![screen_shot_2019-07-31at91807am](assets/http-image.png)

1. Klik op **Opslaan** om de service *http* in te schakelen.

#### Aanraakinterface inschakelen voor AEM-schermen {#enable-touch-ui-for-aem-screens}

Voor AEM-schermen is een TOUCH-gebruikersinterface vereist en deze werken niet met de CLASSIC-gebruikersinterface van Adobe Experience Manager (AEM).

1. Navigeer naar *&lt;yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*
1. Zorg ervoor dat de **standaardontwerpmodus** is ingesteld op **TOUCH**, zoals in de onderstaande afbeelding wordt getoond

U kunt ook dezelfde instelling uitvoeren met *&lt;yourAuthorInstance>*->*tools (hamerpictogram)* -> **Bewerkingen** -> **Webconsole** en zoeken naar **WCM Authoring UI Mode Service**.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Met de gebruikersvoorkeuren kunt u altijd de klassieke gebruikersinterface voor specifieke gebruikers inschakelen.

#### AEM in de runmode NOSAMPLECONTENT {#aem-in-nosamplecontent-runmode}

Bij het uitvoeren van AEM in productie wordt de **runmode NOSAMPLECONTENT** gebruikt. De header *X-Frame-Options=SAMEORIGIN* verwijderen (in de sectie voor de extra responsheader)

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

Dit is vereist voor AEM Screens Player om online kanalen te spelen.

#### Wachtwoordbeperkingen {#password-restrictions}

Met de recentste veranderingen in ***DeviceServiceImpl***, moet u niet de wachtwoordbeperkingen verwijderen.

U kunt ***DeviceServiceImpl*** vanuit de onderstaande koppeling configureren om wachtwoordbeperking in te schakelen bij het maken van het wachtwoord voor schermapparaatgebruikers:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Voer de onderstaande stappen uit om ***DeviceServiceImpl*** te configureren:

1. Navigeer naar de webconsoleconfiguratie **van** Adobe Experience Manager via AEM-instantie —> hamerpictogram —> **Bewerkingen** —> **Webconsole**.

1. **Adobe Experience Manager Webconsole Configuration **wordt geopend. Zoeken naar apparaatservice. Voor het zoeken van het bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

![screen_shot_2019-07-31at92058am](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcher Configuration {#dispatcher-configuration}

Leren hoe te om verzender voor een project van het Schermen te vormen AEM, verwijs naar het [Vormen van Verzender voor een project](dispatcher-configurations-aem-screens.md)van het Scherm AEM.

#### Java-codering {#java-encoding}

Stel de ***Java-codering*** in op Unicode. Dfile. *encoding=Cp1252* werkt bijvoorbeeld niet.

>[!NOTE]
>
>**Aanbeveling:**
>
>Het wordt aanbevolen HTTPS te gebruiken voor AEM Screens Server in productiegebruik.








