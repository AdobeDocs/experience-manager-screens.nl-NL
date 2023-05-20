---
title: Configuraties AEM Platform
seo-title: AEM Platform Configurations
description: De pagina beschrijft AEM configuraties van Platforms
seo-description: The page describes AEM Platform Configurations
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: 707833ddd8ab2573abcac4e9a77ec88778624435
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 18%

---

# Configuraties AEM Platform  {#platform-configurations}

>[!NOTE]
>
>De meest gangbare belanghebbenden voor deze activiteit zijn een AEM Implementor.

Volg de onderstaande secties om AEM platformconfiguraties in te stellen om aan de slag te gaan met AEM Screens.

## Serverconfiguraties {#server-configurations}

Als u serverconfiguraties wilt instellen, raadpleegt u [Serverconfiguraties](https://helpx.adobe.com/experience-manager/6-5/screens/using/configuring-screens-introduction.html#ServerConfiguration).

## Auteur publiceren {#author-publish}

Raadpleeg voor informatie over het instellen van auteur-publish [Auteur en publicatie configureren in AEM Screens](https://helpx.adobe.com/nl/experience-manager/6-5/screens/using/author-and-publish.html)

>[!NOTE]
>
>Als er slechts één auteur en één publicatie is, moet u alleen de stappen volgen onder **Replicatieagents op auteur instellen** op de pagina [Auteur en publicatie configureren in AEM Screens](https://helpx.adobe.com/nl/experience-manager/6-5/screens/using/author-and-publish.html).

## Dispatcher Configurations {#dispatcher-configurations}

Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen. Door AEM Dispatcher te gebruiken is uw AEM-server ook beter beschermd tegen aanvallen. U kunt de veiligheid van uw AEM-instantie dus verhogen door de Dispatcher samen met een webserver van ondernemingsklasse te gebruiken.

Zie **[Dispatcher Configurations voor AEM Screens](https://helpx.adobe.com/experience-manager/6-5/screens/using/dispatcher-configurations-aem-screens.html)** die richtlijnen voor het vormen van dispatcher voor een project van AEM Screens benadrukt.

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC codec als experimenteel wordt gemerkt, zullen de omzettingen van ffmpeg ontbreken. Om deze toevoeging te vermijden -strict -2 aan de videoprofielen (/etc/dam/video in AEM 6.3 en verplaatst naar /libs/settings/dam/video in AEM 6.4)
   >[!NOTE]
   >
   > Merk op dat -strict -2 de laatste parameters in de lijst van parameters moet zijn. Daarnaast moet u in AEM 6.4 de knooppunten onder kopiëren */libs/settings/dam/video* tot */conf/global/settings/dam/video* zoals vermeld in [Video-uitvoeringen](https://helpx.adobe.com/experience-manager/6-5/screens/using/generating-renditions.html).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op het AMS-exemplaar worden uitgeschakeld. Dit kan afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst van Schermen *com.adobe.cq.screens.device.impl.DeviceService*
Zie **Wachtwoordbeperkingen** sectie in[Auteur en publicatie configureren in AEM Screens](https://helpx.adobe.com/nl/experience-manager/6-5/screens/using/author-and-publish.html)

## De omgevingen instellen {#setting-up-environments}

Installeer en voer de meest recente versies van de volgende pakketten voor uw versie van Adobe Experience Manager uit (AEM):

* AEM Service Pack
* Schermfunctiepakket
* AEM Cumulatief reparatiepakket

Identificeer naast het bovenstaande ontwikkelingspakketten (bijvoorbeeld WCM Core-componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die vereist zijn.
Installeer dezelfde softwarepakketten op uw lokale ontwikkelomgevingen. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
>
>Als u het nieuwste Feature Pack voor AEM Screens wilt installeren, raadpleegt u [Opmerkingen bij de release](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html?topic=/experience-manager/6-5/screens/morehelp/release-notes.ug.js).

## ACLs van de vestiging {#setting-up-acls}

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Zie [ACLs van de vestiging](https://helpx.adobe.com/experience-manager/6-5/screens/using/setting-up-acls.html) voor meer informatie .
