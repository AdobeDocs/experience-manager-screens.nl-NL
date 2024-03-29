---
title: Chrome Player gebruiken als extensie
seo-title: Using Chrome Player as an Extension
description: Volg deze pagina voor meer informatie over het installeren van de chroomspeler als een browserextensie.
seo-description: null
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---

# Chrome Player gebruiken als extensie {#using-chrome-player}

De ChromeOS-speler kan als Chrome Browser-insteekmodule worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een daadwerkelijk chrome speler-apparaat nodig is.

>[!CAUTION]
>
> Het gebruik van de Speler van Chrome als uitbreiding voor het oplossen van problemen wordt geadviseerd voor snelle demo&#39;s, het zuiveren en ook om klantenkwesties problemen op te lossen. Dit mechanisme mag niet worden gebruikt voor productieimplementaties waarvoor de kiosk-modus en het centrale beheer vereist zijn.

Volg deze pagina voor meer informatie over het installeren van de chroomspeler als een browserextensie.

1. Klikken [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.

1. Pak het uit en sla het op de schijf op.

1. Open Chrome-browser en klik op het menu met drie punten en selecteer **Meer gereedschappen** van **Extensies** bevindt zich in de rechterbovenhoek of navigeert rechtstreeks naar `chrome://extensions`.

1. Schakel de **Ontwikkelaar** vanuit de rechterbovenhoek.

1. Klikken op **Niet-verpakt laden** in de linkerbovenhoek en geladen niet-gecomprimeerde Chrome Player.

1. Controleer de AEM Screens Chrome Player-insteekmodule als deze beschikbaar is in de lijst met extensies.

1. Open een nieuw tabblad en klik in de linkerbovenhoek op het pictogram Apps of navigeer rechtstreeks naar `chrome://apps`.

1. Klikken op **AEM Screens-insteekmodule** om Chrome Player te starten.
   >[!NOTE]
   >
   > Standaard wordt de speler gestart in de modus Volledig scherm. Druk **esc** om de modus Volledig scherm af te sluiten.


## Geavanceerde tips voor foutopsporing {#advanced-debugging-tips}

1. Wanneer de speler inhoud lokaal heeft gedownload, kunt u naar lokaal gedownloade inhoud bladeren door naar `http://localhost:24502`.

   >[!NOTE]
   >
   > Als de bovenstaande URL niet werkt, betekent dit dat aan de speler geen weergave is toegewezen of dat de inhoud niet is gedownload. Controleer het netwerklusje voor speler config JSON om te zien of worden de correcte details verkregen door de speler en voor om het even welke netwerkkwesties in download.

1. U kunt met de rechtermuisknop op drie lagen van de chroomspeler klikken en deze inspecteren
   **Fouten opsporen in inhoud**: Klik met de rechtermuisknop en controleer de inhoud om fouten op te sporen in de actieve inhoud (er moet één item met de naam &quot;Inspect&quot; zijn in het contextmenu)

   **Fouten opsporen in firmware**: Breng omhoog admin UI en klik en inspecteer dan met de rechtermuisknop aan om de ingebouwde programmatuur (speler) code (Er zou een optie moeten zijn om achtergrondpagina te inspecteren en te inspecteren en browser nieuw begin te simuleren)

   **Achtergrondpagina voor foutopsporing**: De interface voor beheerders weergeven en vervolgens met de rechtermuisknop op de achtergrondpagina klikken en deze inspecteren (voor achtergrondservices zoals http-server)

## De Player-extensie bijwerken {#upgrading-player}

Voer de onderstaande stappen uit om de Player-extensie bij te werken als er een nieuwe versie van de speler wordt uitgebracht. U kunt ook de onderstaande instructies volgen om upgradescenario&#39;s te testen:

1. Alle actieve chroom- en spelerinstanties sluiten
1. De naam van de oude map wijzigen met spelerbestanden
1. Het nieuwe ritje extraheren op dezelfde locatie als de oude map
1. Chrome starten en naar `chrome://extensions`
1. Controleer het spelerpictogram en klik op de knop Vernieuwen of Opnieuw laden
