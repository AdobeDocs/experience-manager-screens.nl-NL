---
title: Testen en kwaliteitsborging
description: Meer informatie over testen en kwaliteitsborging voor AEM Screens vindt u in de Best Practices Guide.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Testen en kwaliteitsborging {#testing-quality}

>[!NOTE]
>De meest voorkomende belanghebbende bij deze activiteit is A/V-integrator.

Aangezien u dichter aan plaatsing van het digitale signaalnetwerk wordt, creeer een plan van de Test en van QA dat elk element van het netwerk met inbegrip van alle hardwarecomponenten, alle softwarecomponenten, en alle voorzien van een netwerkcomponenten richt.
In de fase moeten volledige testsystemen worden gebouwd en volledig getest.

Er moet een controlelijst worden gemaakt die alle eerder gedefinieerde KPI&#39;s identificeert en de te leveren items op basis daarvan meet.

>[!NOTE]
>
>Deze fase moet ook worden gebruikt als een hulpmiddel voor het maken van een installatie- en gebruikershandleiding die later met de apparatuur kan worden geleverd en ter referentie ter plaatse kan worden bewaard.

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

AEM Screens bevat een Device Control Center-module waarmee u eindpunten van de toepassing Screens Player kunt beheren.

Dit heeft betrekking op *player* hardwareapparaat waarop de toepassing Schermspeler is geïnstalleerd en die is geregistreerd bij een AEM.
Met deze module kunt u:

1. Toepassingsfoutlogboeken van de speler controleren
1. Externe schermafbeeldingen beheren
1. Downloads van inhoud beheren
1. Problemen met het opnieuw opstarten van toepassingen beheren

Meer informatie over ***Device Control Center***, zie [Problemen oplossen in Device Control Center](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) in **AEM Screens-gebruikershandleiding**.

>[!CAUTION]
>
>Gebruik Device Control Center niet om:
>
>* Nieuwe versies van de spelertoepassing installeren
>* Bronnen op systeemniveau controleren
>* Systeemfouten oplossen
>* Toestaan voor externe desktopinterventie


>[!NOTE]
>
> De Adobe beveelt aan dat speciale, externe platforms voor apparaatbeheer worden gebruikt voor alle implementaties.

Het gekozen specifieke platform is afhankelijk van verschillende factoren, waaronder ***doelbesturingssysteem***, ***projectvereisten***, en ***aantal eindpunten***.

Hieronder volgen enkele voorbeelden:

* Google Chrome-apparaatbeheer
* TeamViewer
* AirWatch
* `42Gears`
* AV-integrator-middleware
