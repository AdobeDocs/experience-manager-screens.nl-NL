---
title: De afstandsbediening implementeren
description: Meer informatie over de functie voor afstandsbediening van schermen in AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 6cb2705e-83e6-46f3-bd71-6688d7edc11f
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# De afstandsbediening voor schermen gebruiken  {#implementing-remote-control}

Met de functie voor besturing op afstand hebt u gemakkelijker toegang tot de beheerinterface, de kanaalswitch of andere functies, zoals Cache wissen en opnieuw laden. Ook, voorziet het u van een methode om de lokale ingebouwde programmatuurversie en systeeminformatie over de speler te zien. Dit is vooral nuttig omdat het moeilijk kan zijn om een muis aan te sluiten en op productieapparaten te werken die buiten bereik zijn en nog meer als de speler verbinding met AEM heeft verloren. Dit is ook handig wanneer u Samsung RMS gebruikt, omdat het vanwege het verschil in resolutie moeilijk kan zijn om de interface van de beheerder met de muis te vinden en te openen.

## Algemene combinaties van afstandsbedieningen {#using-common-remote-control}

Op alle spelers kunt u de volgende zeer belangrijke combinaties in de Verre Controle van de Schermen gebruiken:

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
1. Met de open kanaalschakelaar, kunt u de op en neer pijlsleutels gebruiken om de kanalen te navigeren. U kunt ook op de knop `Enter` (of de knoop bij het centrum van de pijlen op ver) om kanalen te schakelen.

In het volgende diagram wordt het sleutelgebruik op een Samsung-afstandsbediening geïllustreerd:
![image](assets/tizen/remote.png)

>[!NOTE]
>Als u de configuratiewaarden voor het apparaat van enableAdminUI en/of enableOSD instelt op false, schakelt de afstandsbediening de interface voor beheerders en de kanaalswitch niet in of uit. U kunt de pijltoetsen niet gebruiken om door de interface van de beheerder of kanalen te navigeren. U kunt de cache echter wel wissen en de speler opnieuw laden. U kunt de functie voor besturing op afstand uitschakelen als een van de toetsenbordcombinaties conflicteert met uw interactieve inhoud met deze code:

```
require(['util/ScreensDisplay'], function() {window.ScreensDisplay.ignoreRemoteControl = true;}); 
```
