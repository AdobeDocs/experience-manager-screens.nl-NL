---
title: Testen en kwaliteitsborging
description: Meer informatie over testen en kwaliteitsborging voor AEM Screens vindt u in de Best Practices Guide.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
source-git-commit: 2a51258ffe7b969962378dcd0558bd001b616ba1
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Testen en kwaliteitsborging {#testing-quality}

>[!NOTE]
>Een typisch belanghebbende voor deze activiteit is een Audio-Video Integrator.

Aangezien u dichter aan plaatsing van het digitale signaalnetwerk wordt, creeer een plan van de Test en van QA dat elk element van het netwerk met inbegrip van alle hardwarecomponenten, alle softwarecomponenten, en alle voorzien van een netwerkcomponenten richt.
In de fase moeten volledige testsystemen worden gebouwd en volledig getest.

Er moet een controlelijst worden gemaakt die alle eerder gedefinieerde KPI&#39;s identificeert en de te leveren items op basis daarvan meet.

>[!NOTE]
>
>Deze fase moet ook worden gebruikt als hulpmiddel voor het maken van een installatie en gebruikershandleiding. Beide kunnen later met de apparatuur worden geleverd en ter referentie op de locatie worden gehouden.

De volgende elementen moeten in overweging worden genomen:

## 1. Mechanische overwegingen {#mechanical-considerations}

De volgende mechanische overwegingen worden aanbevolen:

* schermmontage
* speler monteren
* ventilatie
* randapparatuur
* kabelbeheer
* apparaatnetwerken

## 2. Softwareoverwegingen {#software-considerations}

De volgende softwareoverwegingen worden geadviseerd:

* apparaatregistratie
* media publiceren
* afspelen
* databaseafhankelijkheden (voorheen gedefinieerd)


## 3. Overwegingen voor apparaatbeheer {#device-management-considerations}

AEM Screens bevat een Device Control Center-module waarmee u eindpunten van Screens Player-toepassingen kunt beheren.

Het verwijst naar om het even welk *speler* hardwareapparaat dat de de spelertoepassing van Screens heeft geïnstalleerd en aan een geval van AEM wordt geregistreerd.
Met deze module kunt u:

1. Toepassingsfoutlogboeken van de speler controleren
1. Externe schermafbeeldingen beheren
1. Downloads van inhoud beheren
1. Problemen met het opnieuw opstarten van toepassingen beheren

Om in detail over het ***Centrum van de Controle van het Apparaat*** te leren, zie [&#x200B; Centrum van de Controle van het Apparaat van het Oplossen van problemen &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) in **Gids van de Gebruiker van AEM Screens**.

>[!CAUTION]
>
>Gebruik het Device Control Center niet om:
>
>* Nieuwe versies van de spelertoepassing installeren
>* Bronnen op systeemniveau controleren
>* Systeemfouten oplossen
>* Toestaan voor externe desktopinterventie


>[!NOTE]
>
> De Adobe beveelt aan dat speciale, externe platforms voor apparaatbeheer worden gebruikt voor alle implementaties.

Het specifieke gekozen platform hangt van verscheidene factoren met inbegrip van het ***doel werkende systeem***, ***projectvereisten***, en ***aantal eindpunten*** af.

Hieronder volgen enkele voorbeelden:

* Google Chrome-apparaatbeheer
* TeamViewer
* AirWatch
* `42Gears`
* Middleware, bedrijfseigen audio-video-integrator
