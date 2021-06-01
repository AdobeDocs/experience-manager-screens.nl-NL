---
title: Configuraties AEM Platform
seo-title: Configuraties AEM Platform
description: De pagina beschrijft AEM configuraties van Platforms
seo-description: De pagina beschrijft AEM configuraties van Platforms
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 18%

---

# Configuraties van Platforms AEM {#platform-configurations}

>[!NOTE]
>
>De meest gangbare belanghebbenden voor deze activiteit zijn een AEM Implementor.

Volg de onderstaande secties om AEM platformconfiguraties in te stellen om aan de slag te gaan met AEM Screens.

## Serverconfiguraties {#server-configurations}

Raadpleeg [Serverconfiguraties](https://helpx.adobe.com/experience-manager/6-5/screens/using/configuring-screens-introduction.html#ServerConfiguration) voor informatie over het instellen van serverconfiguraties.

## Auteur-Publicatie {#author-publish}

Als u de auteur wilt instellen, gaat u naar [Auteur configureren en publiceren in AEM Screens](https://helpx.adobe.com/nl/experience-manager/6-5/screens/using/author-and-publish.html)

>[!NOTE]
>
>Als er slechts één auteur en één publicatie is, moet u alleen de stappen volgen onder **Replicatieagents op auteur instellen** op de pagina [Auteur en publicatie configureren in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html).

## Dispatcher Configurations {#dispatcher-configurations}

Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen. Door AEM Dispatcher te gebruiken is uw AEM-server ook beter beschermd tegen aanvallen. U kunt de veiligheid van uw AEM-instantie dus verhogen door de Dispatcher samen met een webserver van ondernemingsklasse te gebruiken.

Raadpleeg **[Dispatcher Configurations for AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/dispatcher-configurations-aem-screens.html)** voor richtlijnen voor het configureren van dispatcher voor een AEM Screens-project.

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC codec als experimenteel wordt gemerkt, zullen de omzettingen van ffmpeg ontbreken. Om deze toevoeging te vermijden -strict -2 aan de videoprofielen (/etc/dam/video in AEM 6.3 en verplaatst naar /libs/settings/dam/video in AEM 6.4)
   >[!NOTE]
   >
   > Merk op dat -strict -2 de laatste parameters in de lijst van parameters moet zijn. Daarnaast moet u in AEM 6.4 de knooppunten onder */libs/settings/dam/video* kopiëren naar */conf/global/settings/dam/video* zoals vermeld in [Video-uitvoeringen](https://helpx.adobe.com/experience-manager/6-5/screens/using/generating-renditions.html).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op het AMS-exemplaar worden uitgeschakeld. Dit kan afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst *com.adobe.cq.screens.device.impl.DeviceService*
Zie **Wachtwoordbeperkingen** sectie in[Auteur configureren en publiceren in AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/author-and-publish.html)

## De omgevingen {#setting-up-environments} instellen

Installeer en voer de meest recente versies van de volgende pakketten voor uw versie van Adobe Experience Manager uit (AEM):

* AEM Service Pack
* Schermfunctiepakket
* AEM Cumulatief reparatiepakket

Identificeer, naast het bovenstaande, om het even welke ontwikkelingspakketten (bijvoorbeeld WCM Kern
componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die worden vereist.
Installeer dezelfde softwarepakketten op uw lokale ontwikkelomgevingen. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
>
>Raadpleeg [Opmerkingen bij de release](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html?topic=/experience-manager/6-5/screens/morehelp/release-notes.ug.js) als u het nieuwste Feature Pack voor AEM Screens wilt installeren.

## ACL&#39;s {#setting-up-acls} instellen

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Verwijs naar [Vestiging ACLs](https://helpx.adobe.com/experience-manager/6-5/screens/using/setting-up-acls.html) voor meer details.
