---
title: Implementatie van de afstandsbediening
seo-title: Impementing the Remote Control
description: Volg deze pagina om meer te weten te komen over de functie voor afstandsbediening van schermen.
seo-description: Follow  this page to learn about using the Screens Remote Control Feature.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
source-git-commit: ff59c3748ea69a37ca68e81e5bf753881e8464b0
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---

# De afstandsbediening voor schermen gebruiken  {#implementing-remote-control}

Met de functie voor besturing op afstand hebt u gemakkelijker toegang tot de interface van Admin, de kanaalswitch of andere functies, zoals Cache wissen en opnieuw laden. Bovendien, voorziet het u van een methode om de lokale ingebouwde programmatuurversie en systeeminformatie over de speler te zien. Dit is vooral nuttig omdat het moeilijk kan zijn om een muis aan te sluiten en op productieapparaten te werken die buiten bereik zijn en nog meer als de speler verbinding met AEM heeft verloren. Dit is ook handig bij het gebruik van Samsung RMS, omdat het vanwege het verschil in resolutie erg moeilijk kan zijn om de interface van Admin met de muis te vinden en te openen.

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

## Aanvullende gebruiksaantekeningen {#using-additional-remote-control}

1. Als de beheerinterface is geopend, kunt u de pijlen omhoog en omlaag gebruiken om door de tabbladen te navigeren om informatie over de tabbladen weer te geven.
1. Met de open kanaalschakelaar, kunt u de op en neer pijlsleutels gebruiken om de kanalen te navigeren en u kunt de Enter sleutel (of de knoop bij het centrum van de pijlen op ver) drukken om kanalen te schakelen.

In het volgende diagram wordt het sleutelgebruik op een Samsung-afstandsbediening geïllustreerd:
![image](assets/tizen/remote.png)

>[!NOTE]
>Als u de waarden voor apparaatconfiguratie van enableAdminUI en/of enableOSD instelt op false, schakelt de externe server de interface van de beheerder en de kanaalswitch niet in of uit. U kunt ook niet met de pijltoetsen door de interface(s) van de beheerder navigeren. U kunt de cache echter wel wissen en de speler opnieuw laden. U kunt de functie voor besturing op afstand uitschakelen als een van de toetsenbordcombinaties conflicteert met uw interactieve inhoud met deze code:

```javascript require(/['util/ScreensDisplay'/], function() /{window.ScreensDisplay.ignoreRemoteControl = true;/}); ```
