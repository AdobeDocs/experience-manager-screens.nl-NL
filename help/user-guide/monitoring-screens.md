---
title: Problemen oplossen in Device Control Center
seo-title: Controleschermen
description: Volg deze pagina om de prestaties voor de activiteit en het apparaat van de Schermspeler te controleren en problemen op te lossen gebruikend het dashboard van het Apparaat.
seo-description: Volg deze pagina om de prestaties voor de activiteit en het apparaat van de Schermspeler te controleren en problemen op te lossen gebruikend het dashboard van het Apparaat.
uuid: b6895d5d-c743-4e10-a166-de573e122335
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
discoiquuid: 3f130808-71e8-4710-8181-021d953660f8
docset: aem65
translation-type: tm+mt
source-git-commit: 2a3bbdd283f983cbdb5f21b606f508603385e041
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---


# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor de activiteit en het apparaat van de Schermspeler controleren en problemen oplossen gebruikend het dashboard van het Apparaat. Deze pagina verstrekt informatie over hoe te om waargenomen prestatiesproblemen voor de speler van het Scherm en de toegewezen apparaten te controleren en problemen op te lossen.

## Monitor en problemen oplossen vanuit Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

U kunt de activiteit controleren en zo uw speler van het Scherm problemen oplossen, gebruikend het Dashboard van het Apparaat.

### Apparaatdashboard {#device-dashboard}

Ga als volgt te werk om naar het dashboard van het apparaat te navigeren:

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Test Project*** —> ***Apparaten***.

   Selecteer **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Selecteer het apparaat (**NewTestDevice**) en klik op **Dashboard** op de actiebalk.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de activiteiten en functies van het apparaat kunt controleren.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

In het deelvenster **Activiteiten** wordt voor het laatst een tijdstempel van de schermspeler weergegeven. Laatste pingel beantwoordt aan de laatste tijd het apparaat met de server contacteerde.

![chlimage_1](assets/chlimage_1.png)

Klik bovendien in de rechterbovenhoek van het deelvenster **Activiteit** op Logboeken **** verzamelen om de logbestanden voor uw speler weer te geven.

### Apparaatdetails bijwerken {#update-device-details}

Controleer het deelvenster **Apparaatdetails** om de IP van het apparaat, het opslaggebruik, de firmware-versie en de uptime van de speler voor het apparaat weer te geven.

![chlimage_1-1](assets/chlimage_1-1.png)

Daarnaast klikt u op **Cache** wissen en **Bijwerken** om de cache van uw apparaat te wissen en de [firmware](screens-glossary.md) -versie in dit deelvenster bij te werken.

Klik ook op de knop **...** in de rechterbovenhoek van het deelvenster **Apparaatdetails** om de status van uw speler opnieuw te starten of te vernieuwen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Apparaatgegevens bijwerken {#update-device-information}

Controleer het deelvenster **APPARAATINFORMATIE** om de configuratieupdate, het apparaatmodel, het apparaatbesturingssysteem en de shell-informatie weer te geven.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klik bovendien in de rechterbovenhoek van het deelvenster Apparaatinformatie op de knop (**...**) om eigenschappen weer te geven of het apparaat bij te werken.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klik op **Eigenschappen** om het dialoogvenster **Apparaateigenschappen** weer te geven. U kunt de apparaattitel bewerken of de optie voor configuratie-updates kiezen als **Handmatig** of **Automatisch**.

>[!NOTE]
>
>Voor meer informatie over de gebeurtenissen verbonden aan de automatische of handupdates van het apparaat, zie de sectie ***Automatische versus Handmatige Updates van het Dashboard*** van het Apparaat in het [Leiden Kanalen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt de schermafbeelding van de speler weergeven vanaf het apparaat vanuit het deelvenster **PLAYER SCREENSHOT** .

Klik (**...**) op de hoogste juiste hoek van het paneel van het Schermafbeelding van de Speler en selecteer **vernieuwen Screenshot** om de momentopname van de lopende speler te bekijken.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

In het deelvenster **VOORKEUREN** kan de gebruiker voorkeuren wijzigen voor **Admin UI**, **Channel Switcher** en **Foutopsporing** op afstand voor het apparaat.

>[!NOTE]
>Zie [AEM Screens Player](working-with-screens-player.md)voor meer informatie over deze optie.

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klik bovendien in de rechterbovenhoek op **Instellingen** om de voorkeuren van het apparaat bij te werken. U kunt de volgende voorkeuren bijwerken:

* **Server-URL**
* **Resolutie**
* **Plan opnieuw opstarten**
* **Max. nr. van te bewaren logbestanden**
* **Logboekniveau**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>U kunt elk van de volgende logbestandniveaus selecteren:
>* **Uitschakelen**
>* **Foutopsporing**
>* **Info**
>* **Waarschuwing**
>* **Fout**


![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## OSGi-instellingen problemen oplossen {#troubleshoot-osgi-settings}

U moet de lege referentie inschakelen zodat het apparaat gegevens op de server kan plaatsen. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen.

Sommige van deze functies zijn momenteel alleen beschikbaar als het filter *Apache Sling Reference Allow Empty* is ingeschakeld in de OSGi-configuratie. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeer naar **Adobe Experience Manager Web Console Configuration**, dat wil zeggen, `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Schakel de optie **allow.empty** in.
1. Click **Save**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Recommendations {#recommendations}

In de volgende sectie wordt aangeraden de netwerkkoppelingen, de server en de spelers te controleren om de status te begrijpen en op problemen te reageren.

AEM biedt ingebouwde bewaking voor:

* *De hartslag* om de 5 seconden geeft aan dat de AEM Screens Player wordt uitgevoerd.
* *Screenshot* van de Player die toont wat momenteel wordt weergegeven op de Player.
* De versie *AEM Screens Player Firmware* die op de speler is geïnstalleerd.
* *Vrije opslagruimte* op de speler.

Recommendations voor externe controle met software van derden:

* CPU-gebruik op afspeelapparatuur.
* Controleer of het AEM Screens Player-proces wordt uitgevoerd.
* Extern opnieuw opstarten/opnieuw opstarten van de Player.
* Real-time meldingen.

Het wordt aanbevolen de Player-hardware en het besturingssysteem zodanig te implementeren dat externe aanmelding problemen kan opsporen en de Player opnieuw kan starten.

#### Aanvullende bronnen {#additional-resources}

Zie Configuratie en het Oplossen van problemen bij het afspelen van [video](troubleshoot-videos.md) om fouten op te sporen in video&#39;s die in uw kanaal worden afgespeeld en problemen op te lossen.
