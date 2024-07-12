---
title: Platformconfiguraties AEM
description: De pagina beschrijft AEM platformconfiguraties
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Platformconfiguraties AEM {#platform-configurations}

>[!NOTE]
>
>Een typisch belanghebbende voor deze activiteit is een AEM Implementor.

Ga aan de slag met AEM Screens door de onderstaande secties te volgen en AEM platformconfiguraties in te stellen

## Serverconfiguraties {#server-configurations}

Aan de configuraties van de opstellingsserver, zie {de Configuraties van de Server 0} ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).[

## Auteur-Publish {#author-publish}

Zie [ het Vormen Auteur en Publish in AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Als er slechts één Auteur en één Publish is, kunt u de stappen onder **de Agenten van de Replicatie van de Opstelling op Auteur** in [ slechts volgen Vormend Auteur en Publish in AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) pagina.

## Dispatcher-configuraties {#dispatcher-configurations}

Dispatcher is Adobe Experience Manager-programma voor caching en taakverdeling. Door AEM Dispatcher te gebruiken is uw AEM-server ook beter beschermd tegen aanvallen. Daarom kunt u de veiligheid van uw AEM instantie verhogen door Dispatcher met een onderneming-klasse Webserver te gebruiken.

Zie {de Configuraties van 0} Dispatcher voor AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens) **die richtlijnen voor het vormen van Dispatcher voor een project van AEM Screens benadrukt.**[

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC-codec is gemarkeerd als experimenteel, mislukken mpeg-conversies. Dit voorkomt u door `-strict -2` toe te voegen aan de videoprofielen (/etc/dam/video in AEM 6.3 en te verplaatsen naar /libs/settings/dam/video in AEM 6.4)

   >[!NOTE]
   >
   >De `-strict -2` moet de laatste parameter in de lijst met parameters zijn. Ook, in AEM 6.4, kopieer de knopen onder */libs/settings/dam/video* aan */conf/global/settings/dam/video* zoals vermeld in [ VideoVertoningen ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op de instantie van AMS worden onbruikbaar gemaakt. Het kan ook afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst van Screens *com.adobe.cq.screens.device.impl.DeviceService*
Zie **de Beperkingen van het Wachtwoord** sectie in [ het Vormen Auteur en Publish in AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## De omgevingen instellen {#setting-up-environments}

Installeer en voer de meest recente versies van de volgende pakketten voor uw versie van Adobe Experience Manager uit (AEM):

* AEM Service Pack
* Screens-functiepakket
* AEM Cumulatief reparatiepakket

Identificeer naast het bovenstaande alle ontwikkelingspakketten (bijvoorbeeld WCM Core
componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die worden vereist.
Installeer dezelfde softwarepakketten in uw lokale ontwikkelomgeving. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
>
>Om het recentste Pak van de Eigenschap voor AEM Screens te installeren, zie [ de Nota&#39;s van de Versie ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## ACLs van de vestiging {#setting-up-acls}

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Zie [ Vestiging ACLs ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/setting-up-acls) voor meer details.
