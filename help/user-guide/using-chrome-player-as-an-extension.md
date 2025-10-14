---
title: Chrome Player gebruiken als extensie
description: Meer informatie over het installeren van de Chrome-speler als een browserextensie voor AEM Screens.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Chrome Player gebruiken als extensie {#using-chrome-player}

De ChromeOS-speler kan worden geïnstalleerd als een Chrome-browserplug-in in de modus voor ontwikkelaars zonder dat een echt Chrome-spelerapparaat nodig is.

>[!CAUTION]
>
> Het gebruik van de Chrome-speler als extensie voor probleemoplossing wordt aanbevolen voor snelle demo&#39;s, foutopsporing en ook voor het oplossen van problemen met klanten. Gebruik dit mechanisme niet voor productieplaatsingen die kiosk wijze en centraal beheer zouden vereisen.

Volg deze pagina voor informatie over het installeren van de Chrome-speler als een browserextensie.

1. Klik [&#x200B; hier &#x200B;](https://download.macromedia.com/screens/) om de recentste speler van Chrome te downloaden.

1. Pak het uit en sla het op de schijf op.

1. Open browser van Chrome en klik het 3 dots menu en klik **Meer Hulpmiddelen** van **Uitbreidingen** in de hoogste juiste hoek of navigeer direct aan `chrome://extensions`.

1. Schakelaar op de **1&rbrace; wijze van de Ontwikkelaar &lbrace;van de top-juiste hoek.**

1. Klik **Lading Onverpakte** van de hoogste-linkerhoek en laad de unzipped speler van Chrome.

1. Schakel de insteekmodule AEM Screens Chrome Player in als deze beschikbaar is in de lijst met extensies.

1. Open een nieuw tabblad en klik in de linkerbovenhoek op het pictogram Apps of navigeer rechtstreeks naar `chrome://apps` .

1. Klik **Insteekmodule van AEM Screens** zodat kunt u de speler van Chrome lanceren.

   >[!NOTE]
   >
   > Standaard wordt de speler gestart in de modus Volledig scherm. Pers **Esc** om volledige het schermwijze weg te gaan.


## Geavanceerde tips voor foutopsporing {#advanced-debugging-tips}

1. Wanneer de speler inhoud lokaal heeft gedownload, kunt u naar `http://localhost:24502` bladeren door lokaal gedownloade inhoud te bladeren.

   >[!NOTE]
   >
   > Als de bovenstaande URL niet werkt, betekent dit dat aan de speler geen weergave is toegewezen of dat de inhoud niet is gedownload. Controleer het netwerklusje voor speler config JSON om te zien of verkrijgt de speler de correcte details en voor om het even welke netwerkkwesties in download.

1. Klik met de rechtermuisknop en inspecteer drie lagen van de Chrome-speler.
   **zuivert inhoud**: Klik en inspecteer op de inhoud met de rechtermuisknop aan om de lopende inhoud te zuiveren (Er zou één enkel punt &quot;Inspect&quot;in het contextmenu moeten zijn)

   **zuivert ingebouwde programmatuur**: Breng omhoog admin UI en klik dan met de rechtermuisknop aan en inspecteer om de ingebouwde programmatuur (speler) code te zuiveren. (U kunt de achtergrondpagina beter inspecteren en inspecteren en het opnieuw starten van de browser simuleren.)

   **zuivert achtergrondpagina**: Breng omhoog admin UI en dan klik met de rechtermuisknop aan en inspecteer de achtergrondpagina (voor achtergronddiensten zoals de server van http).

## De Player-extensie bijwerken {#upgrading-player}

Voer de onderstaande stappen uit om de Player-extensie bij te werken als er een nieuwe versie van de speler wordt uitgebracht. U kunt ook de onderstaande instructies volgen om upgradescenario&#39;s te testen:

1. Alle actieve Chrome- en spelerinstanties sluiten
1. De naam van de oude map wijzigen met spelerbestanden
1. Het nieuwe ritje extraheren op dezelfde locatie als de oude map
1. Chrome starten en naar `chrome://extensions` navigeren
1. Controleer het spelerpictogram en klik op de knop Vernieuwen of Opnieuw laden
