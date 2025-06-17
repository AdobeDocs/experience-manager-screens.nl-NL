---
title: De afstandsbediening implementeren
description: Meer informatie over de functie Screens Remote Control in AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 6cb2705e-83e6-46f3-bd71-6688d7edc11f
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# De afstandsbediening van Screens gebruiken {#implementing-remote-control}

Met de functie voor besturing op afstand hebt u gemakkelijker toegang tot de interface van Admin, de kanaalswitch of andere functies, zoals Cache wissen en opnieuw laden. Ook, voorziet het u van een methode om de lokale ingebouwde programmatuurversie en systeeminformatie over de speler te zien. Deze mogelijkheid is vooral handig omdat het lastig kan zijn om een muis aan te sluiten. U kunt ook werken op apparaten die buiten het bereik van de fabrikant vallen, en nog veel meer als de speler de verbinding met AEM heeft verbroken. Het is ook handig wanneer u Samsung RMS gebruikt, omdat het vanwege het verschil in resolutie moeilijk kan zijn om de interface van de beheerder met de muis te vinden en te openen.

## Algemene combinaties van afstandsbedieningen {#using-common-remote-control}

Op alle spelers kunt u de volgende zeer belangrijke combinaties in de Verre Controle van Screens gebruiken:

1. Gebruikersinterface van beheerder in-/uitschakelen - CTRL + 1
1. Kanaalschakelaar in-/uitschakelen - CTRL + 2
1. Cache wissen - CTRL + ALT + 3
1. Speler opnieuw laden - CTRL + 4

## Specifieke toetsencombinaties voor afstandsbediening met lagen {#using-tizen-remote-control}

U kunt de externe hardware of de externe software die beschikbaar is in Samsung RMS gebruiken om toegang te krijgen tot deze functies, die specifiek zijn voor de Tizen-speler:

1. A - Beheerdersinterface in-/uitschakelen
1. B - Kanaalschakelaar in-/uitschakelen
1. C - Cache wissen
1. D - speler opnieuw laden

## Meer gebruiksnotities {#using-additional-remote-control}

1. Als de beheerinterface is geopend, kunt u de pijlen omhoog en omlaag gebruiken om door de tabbladen te navigeren en informatie over de tabbladen weer te geven.
1. Met de open kanaalschakelaar, kunt u de op en neer pijlsleutels gebruiken om de kanalen te navigeren. U kunt ook op de toets `Enter` (of op de knop in het midden van de pijlen op de afstandsbediening) drukken om te schakelen tussen kanalen.

In het volgende diagram wordt het sleutelgebruik op een Samsung-afstandsbediening geïllustreerd:
![ beeld ](assets/tizen/remote.png)

>[!NOTE]
>Als u de configuratiewaarden voor het apparaat van enableAdminUI en/of enableOSD instelt op false, schakelt de externe server de interface van Admin en de kanaalschakelaar niet in. U kunt niet met de pijltoetsen door de interface van Admin of kanalen navigeren. U kunt de cache echter wel wissen en de speler opnieuw laden. U kunt de functie voor besturing op afstand uitschakelen als een van de toetsenbordcombinaties conflicteert met uw interactieve inhoud met deze code:

```
require(['util/ScreensDisplay'], function() {window.ScreensDisplay.ignoreRemoteControl = true;}); 
```
