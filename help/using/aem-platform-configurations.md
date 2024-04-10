---
title: Platformconfiguraties AEM
description: De pagina beschrijft AEM platformconfiguraties
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Platformconfiguraties AEM  {#platform-configurations}

>[!NOTE]
>
>De meest gangbare belanghebbenden voor deze activiteit zijn een AEM Implementor.

Ga aan de slag met AEM Screens door de onderstaande secties te volgen en AEM platformconfiguraties in te stellen

## Serverconfiguraties {#server-configurations}

Zie voor informatie over het instellen van serverconfiguraties [Serverconfiguraties](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Auteur publiceren {#author-publish}

Zie [Auteur en publicatie configureren in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>Als er slechts één auteur en één publicatiebewerking zijn, voert u alleen de volgende stappen uit **Replication Agents instellen op auteur** in [Auteur en publicatie configureren in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) pagina.

## Dispatcher Configurations {#dispatcher-configurations}

Dispatcher is een Adobe Experience Manager-programma voor caching en taakverdeling. Door AEM Dispatcher te gebruiken is uw AEM-server ook beter beschermd tegen aanvallen. Daarom kunt u de veiligheid van uw AEM instantie verhogen door Dispatcher met een onderneming-klasse Webserver te gebruiken.

Zie **[Dispatcher Configurations voor AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens)** dat richtlijnen voor het vormen van Dispatcher voor een project van AEM Screens benadrukt.

## FFMpeg- en video-uitvoeringen installeren {#installing-ffmpeg}

Installeer FFMpeg volgens de stappen voor het juiste besturingssysteem (gewoonlijk RHEL):

1. Als u de installatie uitvoert door EPEL en RPMFfusion in te schakelen, kunt u alle gstreamer-codecs installeren om de ondersteuning voor Mpeg-conversies te verbreden
1. Als de AAC-codec is gemarkeerd als experimenteel, mislukken mpeg-conversies. Om deze toevoeging te voorkomen `-strict -2` naar de videoprofielen (/etc/dam/video in AEM 6.3 en verplaatst naar /libs/settings/dam/video in AEM 6.4)

   >[!NOTE]
   >
   >De `-strict -2` moet de laatste parameter in de lijst met parameters zijn. In AEM 6.4 moet u ook de knooppunten onder kopiëren */libs/settings/dam/video* tot */conf/global/settings/dam/video* zoals vermeld in [Video-uitvoeringen](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Controleer of video-conversies plaatsvinden en of uitvoeringen worden gemaakt.

## Wachtwoordbeperkingen {#password-restrictions}

Het wachtwoordbeleid van AEM moet op de instantie van AMS worden onbruikbaar gemaakt. Dit kan afwisselend in de Webconsole worden gevormd gebruikend de het apparatendienst van Schermen *com.adobe.cq.screens.device.impl.DeviceService*
Zie **Wachtwoordbeperkingen** sectie in[Auteur en publicatie configureren in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## De omgevingen instellen {#setting-up-environments}

Installeer en voer de meest recente versies van de volgende pakketten voor uw versie van Adobe Experience Manager uit (AEM):

* AEM Service Pack
* Schermfuncties
* AEM Cumulatief reparatiepakket

Identificeer naast het bovenstaande ontwikkelingspakketten (bijvoorbeeld WCM Core-componenten) of toolkits van derden (bijvoorbeeld SAP Hybris) die vereist zijn.
Installeer dezelfde softwarepakketten op uw lokale ontwikkelomgeving. Geef uw client de opdracht dezelfde configuratie op alle QA-, Stage- en Production-servers toe te passen. Niet-overeenkomende serverconfiguraties veroorzaken problemen bij de implementatie en het testen.

>[!NOTE]
>
>Als u het nieuwste Feature Pack voor AEM Screens wilt installeren, raadpleegt u [Opmerkingen bij de release](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## ACLs van de vestiging {#setting-up-acls}

De vestiging ACLs verklaart hoe te om projecten te segregeren zodat elk individu of team hun eigen project behandelt.

Zie [ACLs van de vestiging](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/setting-up-acls) voor meer informatie .
