---
cloud: Experience Cloud
product: experience manager
audience: end-user
user-guide-title: Adobe Experience Manager Screens Help
breadcrumb-title: Handleiding AEM Screens
user-guide-description: Leer hoe u een Digital Signage-oplossing kunt gebruiken om dynamische en interactieve digitale ervaringen en interacties te publiceren.
feature-set: Experience Manager Screens
feature: Content
role: User
source-git-commit: 1bd79ed3a0a610efb12f9ff1030a33978ccccf1e
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 5%

---


# AEM Screens-gebruikershandleiding {#user-guide}

+ [Inleiding tot schermen](aem-screens-introduction.md)
+ Overzicht en Kickstart Guide {#overview}
   + [Kickstart Guide](kickstart-for-aem-screens.md)
   + [Schermen Best Practices Guide](https://experienceleague.adobe.com/en/docs/experience-manager-screens/using/about-guide)
   + [Belangrijkste voorwaarden](screens-glossary.md)
+ Basisprincipes van digitale-signaalnetwerken {#digital-signage-network}
   + [Deel 1: Projectrollen en -verantwoordelijkheden](project-roles-responsibilities.md)
   + [Deel 2: Aandachtspunten als projecten](project-considerations.md)
   + [Deel 3: Testen, concepttest, piloten en rollouts](testing-pocs-pilots-rollouts.md)
   + [Deel 4: Projectbeheer en -implementatie](project-management-and-deployment.md)
   + [Deel 5: Overwegingen bij de ondersteuning](support-considerations.md)
+ Configuratie en beheer {#administering}
   + [Schermserver configureren](configuring-screens-introduction.md)
   + [Dispatcher-configuraties instellen](dispatcher-configurations-aem-screens.md)
   + [Schermspeler installeren](installing-screens-player.md)
   + [Schermspeler verbinden](working-with-screens-player.md)
   + [Apparaatregistratie](device-registration.md)
   + [ACLs van de vestiging](setting-up-acls.md)
   + [AEM Screens Security Checklist](security-checklist.md)
   + [Overstappen van ContentSync naar SmartSync](smartsync.md)
   + [Nieuwe importmodule voor project uit bestand](project-importer.md)
   + [Gegevenstriggers repliceren naar publicatieservers](replicating-data-triggers.md)
   + [Replicatieagents configureren op schermen](configure-screens-replication.md)
   + Clientspecifieke overwegingen {#installing-client}
      + [Chrome OS Player](implementing-chrome-os-player.md)
      + [Chrome Player gebruiken als extensie voor het oplossen van problemen](using-chrome-player-as-an-extension.md)
      + [Android](implementing-android-player.md)
      + [Windows Player](implementing-windows-player.md)
      + [Tizen Player](tizen-player.md)
      + [Cloud Player](implementing-cloud-player.md)
      + [Automatische registratie van spelers](auto-registration-players.md)
      + [De afstandsbediening gebruiken](implementing-remote-control.md)
   + Auteur publiceren {#author-publish}
      + [Author-Publish Architecture-overzicht](author-publish-architecture-overview.md)
      + [Auteur en publicatie configureren](author-and-publish.md)
   + Analyseintegratie met AEM Screens {#analytics-integration}
      + [Adobe Analytics-integratie](adobe-analytics-integration-aem-screens.md)
      + [Adobe Analytics configureren met AEM Screens](configuring-adobe-analytics-aem-screens.md)
+ Voorbeelden van ontwerpen en gebruik {#authoring}
   + Een schermproject instellen {#setting-up-projects}
      + [Projecten maken en beheren](creating-a-screens-project.md)
      + [Kanalen maken en beheren](managing-channels.md)
      + [Weergaven maken en beheren](managing-displays.md)
      + [Locaties maken en beheren](managing-locations.md)
      + [Planningen maken en beheren](managing-schedules.md)
      + [Apparaten beheren](managing-devices.md)
      + Kanalen toewijzen {#assigning-channels}
         + [Kanaaltoewijzing](channel-assignment-latest-fp.md)
         + [Kanaaltoewijzing: oudere AEM Screens-functiepakketten](channel-assignment.md)
   + Basisproductfuncties gebruiken {#product-features}
      + [Tekstbedekking](text-overlay.md)
      + [Bulk offline bijwerken](bulk-offline-update.md)
      + [AEM Screens-berichtenservice](screens-notifications-service.md)
      + [Beleidsfragmenten gebruiken](experience-fragments-in-screens.md)
      + [Activering van middelenniveau](asset-level-scheduling.md)
      + [Activering op kanaalniveau](channel-level-activation.md)
      + [Een live kopie maken en beheren](managing-livecopy.md)
      + [Workflow voor het opvullen van video&#39;s maken](creating-a-video-padding-workflow.md)
      + [Componenten toevoegen aan een kanaal](adding-components-to-a-channel.md)
      + [Ingesloten reeksen](embedded-sequences.md)
      + [Layout meerdere zones](multi-zone-layout-aem-screens.md)
      + [Video-uitvoeringen](generating-renditions.md)
      + [Dynamische ingesloten reeks](dynamic-embedded-sequences.md)
      + [Duur van afspelen van bulkafbeelding op kanaalniveau](channel-level-image-playback.md)
      + [Opdrachtsynchronisatie](using-command-sync.md)
      + [Authoring met gegevenstriggers](authoring-data-triggers.md)
      + [Tags gebruiken](tagging.md)
      + [Spraakherkenning](voice-recognition.md)
      + [Rapport Inhoudstoewijzing](content-assignment-report.md)
      + [Ondersteuning van miniaturen voor video&#39;s](thumbnail-support.md)
      + [Adaptieve uitvoeringen gebruiken in AEM Screens](using-adaptive-renditions.md)
   + Updates van inhoud beheren {#content-updates}
      + [Update voor on-demand inhoud](on-demand-content.md)
      + [Inhoud als service-update](content-update-as-a-service.md)
      + [Inhoud bijwerken met Schermen starten](launches.md)
   + Voorbeelden van hoofdletters gebruiken {#use-case-examples}
      + [Noodkanalen](emergency-channel.md)
      + [Temperatuuractivering in het midden van de reis](local-temperature-activation.md)
      + [Activering van ziekenhuisreservering](hospitality-reservation-activation.md)
      + [Gerichte activering in de detailhandel](retail-inventory-activation.md)
      + [Overgangen toepassen](applying-transitions.md)
      + [Overgangen van meerdere zones naar één zone](multizone-to-singlezone.md)
      + [Single-Use TakeOver Channel](single-use-takeover-channel.md)
      + [Perpetual Use of TakeOver Channel](perpetual-takeover-channel.md)
+ Developer and API Resources {#developing}
   + [REST API&#39;s](rest-api.md)
   + [Een aangepaste component voor AEM Screens ontwikkelen](developing-custom-component-tutorial-develop.md)
   + [Offlinekanalen](offline-channels.md)
   + [Een AEM Screens-component uitbreiden](extending-component-tutorial-develop.md)
   + [Componenten maken](creating-components.md)
   + [Een REACT-toepassing insluiten met AEM SPA Editor en integreren met AEM Screens Analytics](embedding-react-app.md)
   + [ContextHub configureren in AEM Screens](configuring-context-hub.md)
   + [Aangepaste sjablonen maken voor MultiZone-layouts](creating-custom-templates-multizone-layouts.md)
   + [Aangepaste branding en opmaak toepassen voor tekstbedekkingen](custom-branding-text-overlays.md)
   + [Adaptieve uitvoeringen: Overzicht van architectuur en configuraties](/help/user-guide/adaptive-renditions.md)
+ Problemen oplossen en veelgestelde vragen {#troubleshooting}
   + [Veelgestelde vragen over AEM Screens](aem-screens-faqs.md)
   + [Problemen oplossen in Device Control Center](monitoring-screens.md)
   + [Configuratie videoweergave](troubleshoot-videos.md)
+ Opmerkingen bij de release {#release-notes}
   + [Opmerkingen bij de release voor Feature Pack 202401](release-notes-fp-202401.md)
   + [Opmerkingen bij de release voor Feature Pack 20240116](release-notes-fp-20240116.md)
   + [Opmerkingen bij de release voor Feature Pack 20240215](release-notes-fp-20240215.md)
   + [Opmerkingen bij de release voor Feature Pack 202204](release-notes-fp-202204.md)
   + [Opmerkingen bij de release voor Feature Pack 202203](release-notes-fp-202203.md)
   + [Opmerkingen bij de release voor Feature Pack 202112](release-notes-fp-202112.md)
   + [Opmerkingen bij de release voor Feature Pack 202109](release-notes-fp-202109.md)
   + [Opmerkingen bij de release voor Feature Pack 202105](release-notes-fp-202105.md)
   + [Opmerkingen bij de release voor Feature Pack 202103](release-notes-fp-202103.md)
   + [Opmerkingen bij de release voor Feature Pack 202011](release-notes-fp-202011.md)
   + [Opmerkingen bij de release voor Feature Pack 202008](release-notes-fp-202008.md)
   + [Opmerkingen bij de release voor Feature Pack 20204](release-notes-fp-202004.md)
   + [Opmerkingen bij de release voor Feature Pack 202001](release-notes-fp-202001.md)
   + [Opmerkingen bij de release voor Feature Pack 201909](release-notes-fp-201909.md)
   + [Opmerkingen bij de release voor Feature Pack 201907](release-notes-fp-201907.md)
   + [Opmerkingen bij de release voor Feature Pack 201905](screens-release-notes-fp-201905.md)
   + [Opmerkingen bij de release voor Feature Pack 201812](release-notes-fp-201812.md)
   + [Opmerkingen bij de release voor Feature Pack 201809](screens-release-notes.md)
