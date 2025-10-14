---
title: AEM Platform Configurations
description: De pagina beschrijft AEM Platform Configurations
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 2%

---

# AEM Platform Configurations {#platform-configurations}

>[!NOTE]
>
>Doorgaans is AEM Implementor een belanghebbende bij deze activiteit.

Ga aan de slag met AEM Screens door de onderstaande secties te volgen en AEM-platformconfiguraties in te stellen

## Serverconfiguraties {#server-configurations}

Aan de configuraties van de opstellingsserver, zie {de Configuraties van de Server 0} [&#128279;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Auteur publiceren {#author-publish}

Zie [&#x200B; Vormend Auteur en publiceer in AEM Screens &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Als er slechts één Auteur en één is publiceren, kunt u de stappen onder **de Agenten van de Replicatie van de Opstelling op Auteur** in [&#x200B; slechts volgen Vormend Auteur en publiceer in AEM Screens &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) pagina.

## Dispatcher-configuraties {#dispatcher-configurations}

Dispatcher is Adobe Experience Manager-programma voor caching en taakverdeling. Door AEM Dispatcher te gebruiken is uw AEM-server ook beter beschermd tegen aanvallen. Daarom kunt u de beveiliging van uw AEM-instantie verhogen door de Dispatcher te gebruiken met een webserver op bedrijfsniveau.

Zie {de Configuraties van 0} Dispatcher voor AEM Screens [&#128279;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens) **die richtlijnen voor het vormen van Dispatcher voor een project van AEM Screens benadrukt.**

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC-codec is gemarkeerd als experimenteel, mislukken mpeg-conversies. U voorkomt dit probleem door `-strict -2` toe te voegen aan de videoprofielen ( `/etc/dam/video` in AEM 6.3 en naar `/libs/settings/dam/video in AEM 6.4` te verplaatsen)

   >[!NOTE]
   >
   >De `-strict -2` moet de laatste parameter in de lijst met parameters zijn. Ook, in AEM 6.4, kopieer de knopen onder */libs/settings/dam/video* aan */conf/global/settings/dam/video* zoals vermeld in [&#x200B; VideoVertoningen &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op het AMS-exemplaar worden uitgeschakeld. Het kan ook afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst van Screens *com.adobe.cq.screens.device.impl.DeviceService*
Zie **de Beperkingen van het Wachtwoord** sectie in [&#x200B; het Vormen Auteur en publiceren in AEM Screens &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## De omgevingen instellen {#setting-up-environments}

Installeer en voer de meest recente versies van de volgende pakketten uit voor uw versie van Adobe Experience Manager (AEM):

* AEM Service Pack
* Screens-functiepakket
* AEM Cumulative Fix Pack

Identificeer naast het bovenstaande alle ontwikkelingspakketten (bijvoorbeeld WCM Core
componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die worden vereist.
Installeer dezelfde softwarepakketten in uw lokale ontwikkelomgeving. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
>
>Om het recentste Pak van de Eigenschap voor AEM Screens te installeren, zie [&#x200B; de Nota&#39;s van de Versie &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## ACLs van de vestiging {#setting-up-acls}

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Zie [&#x200B; Vestiging ACLs &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/setting-up-acls) voor meer details.
