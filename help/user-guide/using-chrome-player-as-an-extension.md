---
title: Chrome Player gebruiken als een extensie
description: Leer hoe u de chroomspeler installeert als een browserextensie voor AEM Screens.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# Chrome Player gebruiken als een extensie {#using-chrome-player}

De ChromeOS-speler kan als Chrome-browserplug-in worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een apparaat met een chrome speler nodig is.

>[!CAUTION]
>
> Het gebruik van de Speler van Chrome als uitbreiding voor het oplossen van problemen wordt geadviseerd voor snelle demo&#39;s, het zuiveren en ook om klantenkwesties problemen op te lossen. Gebruik dit mechanisme niet voor productieplaatsingen die kiosk wijze en centraal beheer zouden vereisen.

Volg deze pagina voor informatie over het installeren van de chroomspeler als browser uitbreiding.

1. Klikken [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.

1. Pak het uit en sla het op de schijf op.

1. Open Chrome-browser en klik op het menu met drie punten en klik op **Meer gereedschappen** van **Extensies** in de rechterbovenhoek of navigeer rechtstreeks naar `chrome://extensions`.

1. Schakel de **Ontwikkelaar** vanuit de rechterbovenhoek.

1. Klikken **Niet-verpakt laden** in de linkerbovenhoek en geladen niet-gecomprimeerde Chrome Player.

1. Controleer de AEM Screens Chrome Player-insteekmodule als deze beschikbaar is in de lijst met extensies.

1. Open een nieuw tabblad en klik in de linkerbovenhoek op het pictogram Apps of navigeer rechtstreeks naar `chrome://apps`.

1. Klikken **AEM Screens-insteekmodule** zodat u Chrome Player kunt starten.

   >[!NOTE]
   >
   > Standaard wordt de speler gestart in de modus Volledig scherm. Druk **Esc** om de modus Volledig scherm af te sluiten.


## Geavanceerde tips voor foutopsporing {#advanced-debugging-tips}

1. Wanneer de speler inhoud lokaal heeft gedownload, kunt u naar lokaal gedownloade inhoud bladeren `http://localhost:24502`.

   >[!NOTE]
   >
   > Als de bovenstaande URL niet werkt, betekent dit dat aan de speler geen weergave is toegewezen of dat de inhoud niet is gedownload. Controleer het netwerklusje voor speler config JSON om te zien of worden de correcte details verkregen door de speler en voor om het even welke netwerkkwesties in download.

1. Klik met de rechtermuisknop en inspecteer drie lagen van de chroomspeler.
   **Fouten opsporen in inhoud**: Klik met de rechtermuisknop en controleer de inhoud om fouten op te sporen in de actieve inhoud (er moet één item met de naam &quot;Inspect&quot; zijn in het contextmenu)

   **Fouten opsporen in firmware**: Breng omhoog admin UI en klik dan met de rechtermuisknop aan en inspecteer om de ingebouwde programmatuur (speler) code te zuiveren. (U kunt de achtergrondpagina controleren en inspecteren en het opnieuw opstarten van de browser simuleren.)

   **Achtergrondpagina voor foutopsporing**: De interface voor beheerders weergeven en vervolgens met de rechtermuisknop klikken en de achtergrondpagina inspecteren (voor achtergrondservices zoals http-server).

## De Player-extensie bijwerken {#upgrading-player}

Voer de onderstaande stappen uit om de Player-extensie bij te werken als er een nieuwe versie van de speler wordt uitgebracht. U kunt ook de onderstaande instructies volgen om upgradescenario&#39;s te testen:

1. Alle actieve chroom- en spelerinstanties sluiten
1. De naam van de oude map wijzigen met spelerbestanden
1. Het nieuwe ritje extraheren op dezelfde locatie als de oude map
1. Chrome starten en naar `chrome://extensions`
1. Controleer het spelerpictogram en klik op de knop Vernieuwen of Opnieuw laden
