---
title: Chrome Player gebruiken als extensie
seo-title: Chrome Player gebruiken als extensie
description: 'null'
seo-description: 'null'
translation-type: tm+mt
source-git-commit: 1753009451e4bed75eb8241bcca887f7abe2f77b

---


# Chrome Player gebruiken als extensie {#using-chrome-player}

De ChromeOS-speler kan als Chrome Browser-insteekmodule worden geïnstalleerd in de modus voor ontwikkelaars zonder dat hiervoor een daadwerkelijk chrome speler-apparaat nodig is.

>[!CAUTION]
>
> Het gebruik van de Speler van Chrome als uitbreiding voor het oplossen van problemen wordt geadviseerd voor snelle demo&#39;s, het zuiveren en ook om klantenkwesties problemen op te lossen. Dit mechanisme mag niet worden gebruikt voor productieimplementaties waarvoor de kiosk-modus en het centrale beheer vereist zijn.

Volg deze pagina voor meer informatie over het installeren van de chroomspeler als een browserextensie.

1. Klik [hier](https://download.macromedia.com/screens/) om de nieuwste Chrome Player te downloaden.

1. Pak het uit en sla het op de schijf op.

1. Open Chrome-browser en klik op het menu met drie puntjes en selecteer **Meer gereedschappen** in **Extensies** in de rechterbovenhoek of navigeer rechtstreeks naar `chrome://extensions`.

1. Schakel de modus **Ontwikkelaar** vanuit de rechterbovenhoek in.

1. Klik op **Niet-verpakt** laden in de linkerbovenhoek en laad niet-gecomprimeerde Chrome Player.

1. Schakel AEM-scherminsteekmodule voor Chrome Player in als deze beschikbaar is in de lijst met extensies.

1. Open een nieuw tabblad en klik in de linkerbovenhoek op het pictogram Apps of navigeer rechtstreeks naar `chrome://apps`.

1. Klik op de insteekmodule **AEM-schermen** om Chrome Player te starten.
   >[!NOTE]
   >
   > Standaard wordt de speler gestart in de modus Volledig scherm. Druk op **esc** om de modus Volledig scherm af te sluiten.


## Geavanceerde tips voor foutopsporing {#advanced-debugging-tips}

1. Wanneer de speler inhoud lokaal heeft gedownload, kunt u naar lokaal gedownloade inhoud bladeren door naar `http://localhost:24502`te gaan.

   >[!NOTE]
   >
   > Als de bovenstaande URL niet werkt, betekent dit dat aan de speler geen weergave is toegewezen of dat de inhoud niet is gedownload. Controleer het netwerklusje voor speler config JSON om te zien of worden de correcte details verkregen door de speler en voor om het even welke netwerkkwesties in download.

1. U kunt met de rechtermuisknop op drie lagen van de chroomspeler klikken en deze inspecteren
   **Foutopsporingsinhoud**: Klik met de rechtermuisknop en controleer de inhoud om fouten op te sporen in de actieve inhoud (er moet één item zijn met de naam &quot;Inspect&quot; in het contextmenu)

   **Foutopsporingsfirmware**: Breng omhoog admin UI en klik en inspecteer dan met de rechtermuisknop aan om de ingebouwde programmatuur (speler) code (Er zou een optie moeten zijn om achtergrondpagina te inspecteren en te inspecteren en browser nieuw begin te simuleren)

   **Achtergrondpagina** van foutopsporing: De interface voor beheerders weergeven en vervolgens met de rechtermuisknop op de achtergrondpagina klikken en deze inspecteren (voor achtergrondservices zoals http-server)

## De Player-extensie bijwerken {#upgrading-player}

Voer de onderstaande stappen uit om de Player-extensie bij te werken als er een nieuwe versie van de speler wordt uitgebracht. U kunt ook de onderstaande instructies volgen om upgradescenario&#39;s te testen:

1. Alle actieve chroom- en spelerinstanties sluiten
1. De naam van de oude map wijzigen met spelerbestanden
1. Het nieuwe ritje extraheren op dezelfde locatie als de oude map
1. Chrome starten en naar `chrome://extensions`
1. Controleer het spelerpictogram en klik op de knop Vernieuwen of Opnieuw laden