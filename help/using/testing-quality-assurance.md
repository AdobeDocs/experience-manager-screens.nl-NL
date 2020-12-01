---
title: Testen en kwaliteitsborging
seo-title: Testen en kwaliteitsborging voor AEM Screens
description: De pagina beschrijft Testing and Quality Assurance for AEM Screens Best Practices Guide
seo-description: De pagina beschrijft Testing and Quality Assurance for AEM Screens Best Practices Guide
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---


# Testen en kwaliteitsborging {#testing-quality}

>[!NOTE]
>De meest voorkomende belanghebbende bij deze activiteit is A/V-integrator.

Aangezien wij dichter aan daadwerkelijke plaatsing van het digitale signaalnetwerk worden, zouden wij een Plan van de Test en van QA moeten creëren dat elk element van het netwerk met inbegrip van alle hardwarecomponenten, alle softwarecomponenten en alle voorzien van een netwerkcomponenten richt.
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

## 2. Overwegingen voor software {#software-considerations}

De volgende softwareoverwegingen worden geadviseerd:

* apparaatregistratie
* media publiceren
* afspelen
* databaseafhankelijkheden (voorheen gedefinieerd)


## 3. Overwegingen voor apparaatbeheer {#device-management-considerations}

AEM Screens bevat een Device Control Center-module waarmee u eindpunten van de toepassing Screens Player kunt beheren.

Dit verwijst naar elk *player*-hardwareapparaat waarop de toepassing Schermspeler is geïnstalleerd en dat is geregistreerd bij een instantie van AEM.
Met deze module kunt u:

1. Toepassingsfoutlogboeken van de speler controleren
1. Externe schermafbeeldingen beheren
1. Downloads van inhoud beheren
1. Problemen met het opnieuw opstarten van toepassingen beheren

Als u meer informatie wilt over ***Device Control Center***, raadpleegt u [Troubleshooting Device Control Center](https://helpx.adobe.com/experience-manager/6-5/screens/using/monitoring-screens.html) in **AEM Screens User Guide**.

>[!CAUTION]
>
> Gebruik Device Control Center niet om:
> 1. Nieuwe versies van de spelertoepassing installeren
> 1. Bronnen op systeemniveau controleren
> 1. Systeemfouten oplossen
> 1. Toestaan voor externe desktopinterventie



>[!NOTE]
>
> Adobe raadt aan dat speciale, externe apparaatbeheerplatforms worden gebruikt voor alle implementaties.

Het gekozen specifieke platform is afhankelijk van een aantal factoren, zoals het ***doelbesturingssysteem***, ***projectvereisten*** en ***aantal eindpunten***.

Enkele voorbeelden zijn:

* Google Chrome-apparaatbeheer
* TeamViewer
* AirWatch
* 42Tandwiel
* AV Integrator Middleware
