---
title: AEM-platformconfiguraties
seo-title: AEM-platformconfiguraties
description: De pagina beschrijft AEM Platform Configurations
seo-description: De pagina beschrijft AEM Platform Configurations
translation-type: tm+mt
source-git-commit: 5c83a2b59769dfd3736a830f7d7d3cc35137c182

---

# AEM-platformconfiguraties {#platform-configurations}

>[!NOTE]
>
>De meest gangbare belanghebbende bij deze activiteit is een AEM Implementor.

Volg de onderstaande secties om AEM-platformconfiguraties in te stellen om aan de slag te gaan met AEM-schermen.

## Serverconfiguraties {#server-configurations}

Raadpleeg [Serverconfiguraties](https://helpx.adobe.com/experience-manager/6-5/screens/using/configuring-screens-introduction.html#ServerConfiguration)voor informatie over het instellen van serverconfiguraties.

## Auteur publiceren {#author-publish}

Raadpleeg Auteur [configureren en publiceren in AEM-schermen voor informatie over auteur en publicatie](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html)

>[!NOTE]
>
> Als er slechts één auteur en één publicatie is, moet u alleen de stappen volgen onder **Replicatieagents op auteur instellen** op de pagina [Auteur en publicatie configureren in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html).

## Dispatcher Configurations {#dispatcher-configurations}

Dispatcher is het programma voor het in cache plaatsen en/of taakverdeling van Adobe Experience Manager. Het gebruik van de Dispatcher van AEM helpt ook uw AEM-server tegen aanvallen te beschermen. Daarom kunt u de veiligheid van uw instantie verhogen AEM door de Dispatcher samen met een onderneming-klasse Webserver te gebruiken.

Raadpleeg **[Dispatcher Configurations voor AEM-schermen](https://helpx.adobe.com/experience-manager/6-5/screens/using/dispatcher-configurations-aem-screens.html)**waarin de richtlijnen voor het configureren van dispatcher voor een AEM-schermproject worden beschreven.

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC codec als experimenteel wordt gemerkt, zullen de omzettingen van ffmpeg ontbreken. Om deze toevoeging te vermijden -strict -2 aan de videoprofielen (/etc/dam/video in AEM 6.3 en verplaatst naar /libs/settings/dam/video in AEM 6.4)
   >[!NOTE]
   >
   > Merk op dat -strict -2 de laatste parameters in de lijst van parameters moet zijn. Daarnaast moet u in AEM 6.4 de knooppunten onder */libs/settings/dam/video* kopiëren naar */conf/global/settings/dam/video* , zoals vermeld in [Video-uitvoeringen](https://helpx.adobe.com/experience-manager/6-5/screens/using/generating-renditions.html).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op de instantie van AMS worden onbruikbaar gemaakt. Dit kan afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst *com.adobe.cq.screens.device.impl.DeviceService* Verwijs naar de sectie van de Beperkingen **van het** Wachtwoord[in het Vormen Auteur en publiceert in de Schermen van AEM](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html)

## De omgevingen instellen {#setting-up-environments}

Installeer en voer de meest recente versies van de volgende pakketten uit voor uw versie van Adobe Experience Manager (AEM):

* AEM Service Pack
* Schermfunctiepakket
* AEM Cumulative Fix Pack

Identificeer naast het bovenstaande ontwikkelingspakketten (bijvoorbeeld WCM-componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die vereist zijn.
Installeer dezelfde softwarepakketten op uw lokale ontwikkelomgevingen. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
> Raadpleeg [Release-aantekeningen](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html?topic=/experience-manager/6-5/screens/morehelp/release-notes.ug.js)als u het nieuwste elementenpakket voor AEM-schermen wilt installeren.

## ACLs van de vestiging {#setting-up-acls}

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Verwijs naar [Vestiging ACLs](https://helpx.adobe.com/experience-manager/6-5/screens/using/setting-up-acls.html) voor meer details.
