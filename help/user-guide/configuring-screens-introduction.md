---
title: AEM Screens configureren en implementeren
seo-title: Schermen configureren en implementeren
description: De AEM Screens-speler is beschikbaar voor Android, Chrome OS, iOS en Windows. Deze pagina beschrijft de configuratie en implementatie van AEM Screens en geeft ook een overzicht van de richtlijnen voor h/w-selectie voor spelerapparaten.
seo-description: De AEM Screens-speler is beschikbaar voor Android, Chrome OS, iOS en Windows. Deze pagina beschrijft de configuratie en implementatie van AEM Screens en geeft ook een overzicht van de richtlijnen voor h/w-selectie voor spelerapparaten.
uuid: bf730d0f-e590-4c0d-a554-e1ff914eb420
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 0c7d6248-8ac0-4387-8725-57ed941f28f7
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---


# AEM Screens configureren en implementeren {#configuring-and-deploying-aem-screens}

Deze pagina laat zien hoe u de schermspelers op uw apparaten kunt installeren en configureren.

## Server Configuration {#server-configuration}

>[!NOTE]
>
>**Belangrijk**:
>
>De AEM Screens-speler maakt geen gebruik van de token Cross-Site Request Smeery (CSRF). Als u de server wilt configureren en AEM klaar voor gebruik voor AEM Screens, slaat u het verwijzingsfilter over door lege referenties toe te staan.

## Health Check Framework {#health-check-framework}

Met het Health Check-framework kan de gebruiker controleren of twee benodigde configuraties zijn ingesteld voordat een AEM Screens-project wordt uitgevoerd.

Het staat de gebruiker toe om de volgende twee configuratiecontroles te verifiëren om een project van AEM Screens in werking te stellen, namelijk om de staat van de volgende twee filters te controleren:

1. **Lege referentie toestaan**
2. **https**

Volg de onderstaande stappen om te controleren of deze twee vitale configuraties zijn ingeschakeld voor AEM Screens:

1. Navigeer naar de [Adobe Experience Manager Web Console Sling Health Check](http://localhost:4502/system/console/healthcheck?tags=screensconfigs&amp;overrideGlobalTimeout=).

   ![elementen](assets/health-check1.png)


2. Klik op Geselecteerde health checks **uitvoeren** om de validatie voor twee hierboven vermelde eigenschappen uit te voeren.

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

Met de volgende belangrijke punten hieronder kunt u de server configureren en AEM om klaar te zijn voor gebruik voor AEM Screens.

#### Lege verwijzingsverzoeken toestaan {#allow-empty-referrer-requests}

1. Ga naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Configuratie** van Adobe Experience Manager-webconsole wordt geopend. Zoeken naar de referentie van de sling.

   Voor het zoeken van het het rangschikken verwijzend bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

1. Schakel de optie Lege **** waarden toestaan in, zoals in de onderstaande afbeelding.

   ![afbeelding](assets/config/empty-ref2.png)

1. Klik op **Opslaan** om het filter Leeg toestaan voor Apache-schuifverwijzing in te schakelen.


#### HTTP-service op basis van Apache Felix Jetty {#allow-apache-felix-service}

1. Ga naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Configuratie** van Adobe Experience Manager-webconsole wordt geopend. Zoek naar Apache Felix op Jetty Gebaseerde Dienst van HTTP.

   Voor het zoeken van dit bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

1. Schakel de optie **HTTP** INSCHAKELEN in, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](assets/config/config-1.png)

1. Klik op **Opslaan** om de service *http* in te schakelen.

#### Aanraakinterface inschakelen voor AEM Screens {#enable-touch-ui-for-aem-screens}

AEM Screens vereist TOUCH UI en werkt niet met CLASSIC UI of Adobe Experience Manager (AEM).

1. Navigeer naar *&lt;yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*
1. Zorg ervoor dat de **standaardontwerpmodus** is ingesteld op **TOUCH**, zoals in de onderstaande afbeelding wordt getoond

U kunt ook dezelfde instelling uitvoeren met de gereedschappen AuteurInstance *->* (hamerpictogram) -> **Bewerkingen** -> **Webconsole** en zoeken naar de **WCM Authoring UI Mode Service**.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Met de gebruikersvoorkeuren kunt u altijd de klassieke gebruikersinterface voor specifieke gebruikers inschakelen.

#### AEM in de runmode NOSAMPLECONTENT {#aem-in-nosamplecontent-runmode}

Bij het uitvoeren van AEM in productie wordt de **runmode NOSAMPLECONTENT** gebruikt. Verwijder de *X-Frame-Options=SAMEORIGIN* -header (in de extra sectie voor de responsheader)

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

Dit is vereist voor de AEM Screens Player om onlinekanalen af te spelen.

#### Wachtwoordbeperkingen {#password-restrictions}

Met de recentste veranderingen in ***DeviceServiceImpl***, moet u niet de wachtwoordbeperkingen verwijderen.

U kunt ***DeviceServiceImpl*** vanuit de onderstaande koppeling configureren om wachtwoordbeperking in te schakelen bij het maken van het wachtwoord voor schermapparaatgebruikers:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Voer de onderstaande stappen uit om ***DeviceServiceImpl*** te configureren:

1. Ga naar **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

1. **Adobe Experience Manager Web Console Configuration **wordt geopend. Zoeken naar *apparaatservice*. Voor het zoeken van het bezit, druk **Command+F** voor **MAC** en **Control+F** voor **Vensters**.

![screen_shot_2019-07-31at92058am](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcher Configuration {#dispatcher-configuration}

Leren hoe te om verzender voor een project van AEM Screens te vormen, verwijs naar het [Vormen van Verzender voor een project](dispatcher-configurations-aem-screens.md)van AEM Screens.

#### Java-codering {#java-encoding}

Stel de ***Java-codering*** in op Unicode. Dfile. *encoding=Cp1252* werkt bijvoorbeeld niet.

>[!NOTE]
>
>**Aanbeveling:**
>
>Het wordt aanbevolen HTTPS te gebruiken voor AEM Screens Server in productiegebruik.








