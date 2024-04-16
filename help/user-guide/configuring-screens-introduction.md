---
title: AEM Screens configureren en implementeren
description: De AEM Screens-speler is beschikbaar voor Android&trade, Chrome OS, iOS en Windows. Meer informatie over de configuratie en implementatie van AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
role: Admin
level: Intermediate
exl-id: 8cf4240c-1d6c-441d-b8a0-f01516455543
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 0%

---

# AEM Screens configureren en implementeren {#configuring-and-deploying-aem-screens}

Deze pagina laat zien hoe u de schermspelers op uw apparaten kunt installeren en configureren.

## Serverconfiguratie {#server-configuration}

>[!IMPORTANT]
>
>De AEM Screens-speler gebruikt de token Cross-Site Request-vervalsing (CSRF) niet. Als u de AEM server wilt configureren zodat deze klaar is voor gebruik voor AEM Screens, slaat u het verwijzingsfilter over door lege referenties toe te staan.

## Health Check Framework {#health-check-framework}

Met het Health Check-framework kan de gebruiker controleren of twee benodigde configuraties zijn ingesteld voordat een AEM Screens-project wordt uitgevoerd.

Het staat de gebruiker toe om de volgende twee configuratiecontroles te verifiëren om een project van AEM Screens in werking te stellen, namelijk om de staat van de volgende twee filters te controleren:

1. **Lege referentie toestaan**
2. **https**

Volg de onderstaande stappen om te controleren of deze twee vitale configuraties zijn ingeschakeld voor AEM Screens:

1. Navigeren naar [Adobe Experience Manager Web Console Sling Health Check](http://localhost:4502/system/console/healthcheck?tags=screensconfigs&amp;overrideGlobalTimeout=).

   ![elementen](assets/health-check1.png)


2. Klikken **Geselecteerde gezondheidscontroles uitvoeren** zodat u de validatie kunt uitvoeren voor de twee hierboven vermelde eigenschappen.

   Als beide filters zijn ingeschakeld, wordt het dialoogvenster **Screeningconfiguratie Health Service** toont de **Resultaat** als **OK** met beide configuraties zoals toegelaten.

   ![elementen](assets/health-check2.png)

   Als een of beide filters zijn uitgeschakeld, wordt een waarschuwing voor de gebruiker weergegeven, zoals in de onderstaande afbeelding wordt getoond.

   In de volgende waarschuwing wordt aangegeven of beide filters zijn uitgeschakeld:
   ![elementen](assets/health-check3.png)

>[!NOTE]
>
>* Om het **Filter Apache Sling Referrer**, zie [Lege verwijzingsverzoeken toestaan](/help/user-guide/configuring-screens-introduction.md#allow-empty-referrer-requests).
>* Om het **HTTP** service, zie [HTTP-service op basis van Apache Felix Jetty](/help/user-guide/configuring-screens-introduction.md#allow-apache-felix-service).

### Vereisten {#prerequisites}

Met de volgende belangrijke punten hieronder kunt u de server configureren en AEM om klaar te zijn voor gebruik voor AEM Screens.

#### Lege verwijzingsverzoeken toestaan {#allow-empty-referrer-requests}

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** via AEM instantie > hamerpictogram > **Bewerkingen** > **Webconsole**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Configuratie Adobe Experience Manager-webconsole** wordt geopend. Zoeken naar de referentie van de sling.

   Druk op **Command+F** for **Mac** en **Ctrl+F** for **Windows**.

1. Controleer de **Lege waarden toestaan** zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](assets/config/empty-ref2.png)

1. Klikken **Opslaan** om het filter Apache Sling Referrer inschakelen Leeg toestaan.


#### HTTP-service op basis van Apache Felix Jetty {#allow-apache-felix-service}

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** via AEM instantie > hamerpictogram > **Bewerkingen** > **Webconsole**.

   ![afbeelding](assets/config/empty-ref1.png)

1. **Configuratie Adobe Experience Manager-webconsole** wordt geopend. Zoek naar Apache Felix op Jetty gebaseerde HTTP Service.

   Voor het zoeken van deze eigenschap drukt u op **Command+F** for **Mac** en **Ctrl+F** for **Windows**.

1. Controleer de **HTTP INSCHAKEL** zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](assets/config/config-1.png)

1. Klikken **Opslaan** de *http* service.

#### Aanraakinterface inschakelen voor AEM Screens {#enable-touch-ui-for-aem-screens}

AEM Screens vereist TOUCH UI en werkt niet met CLASSIC UI van Adobe Experience Manager (AEM).

1. Navigeren naar `*<yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*`
1. Zorg ervoor dat de **Standaardmodus voor ontwerpgebruikersinterface** is ingesteld op **TOUCH**, zoals weergegeven in onderstaande afbeelding

U kunt ook dezelfde instelling uitvoeren met yourAuthorInstance *>* gereedschappen (hamerpictogram) > **Bewerkingen** > **Webconsole** en zoek naar **WCM Authoring UI Mode Service**.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Met de gebruikersvoorkeuren kunt u altijd de klassieke gebruikersinterface voor specifieke gebruikers inschakelen.

#### AEM in de uitvoermodus NOSAMPLECONTENT {#aem-in-nosamplecontent-runmode}

Als AEM in productie wordt uitgevoerd, worden de **NOSAMPLECONTENT** uitvoeringsmodus. Verwijder de *X-Frame-Options=SAMEORIGIN* header (in de sectie voor extra reacties) van

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

Dit is vereist voor de AEM Screens Player om onlinekanalen af te spelen.

#### Wachtwoordbeperkingen {#password-restrictions}

Met de meest recente wijzigingen in ***DeviceServiceImpl***, hoeft u de wachtwoordbeperkingen niet te verwijderen.

U kunt ***DeviceServiceImpl*** via de onderstaande koppeling om wachtwoordbeperking in te schakelen bij het maken van het wachtwoord voor schermgebruikers:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Voer de onderstaande stappen uit om te configureren ***DeviceServiceImpl***:

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole** via uw AEM > hamerpictogram > **Bewerkingen** > **Webconsole**.

1. **Configuratie Adobe Experience Manager-webconsole** wordt geopend. Zoeken naar `*deviceservice*`. Voor het zoeken van de eigenschap drukt u op **Command+F** voor macOS en **Ctrl+F** voor Microsoft® Windows.

![screen_shot_2019-07-31at92058am](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcher Configuration {#dispatcher-configuration}

Ga voor meer informatie over het configureren van Dispatcher voor een AEM Screens-project naar [Dispatcher configureren voor een AEM Screens-project](dispatcher-configurations-aem-screens.md).

#### Java™-codering {#java-encoding}

Stel de ***Java™-codering*** naar Unicode. Bijvoorbeeld: `*Dfile.encoding=Cp1252*` werkt niet.

>[!NOTE]
>
>Gebruik HTTPS voor AEM Screens Server in productiegebruik.
