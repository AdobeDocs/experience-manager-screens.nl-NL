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
feature: Digitale handtekening, inhoud, spelers
role: Developer
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---


# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor de activiteit en het apparaat van de Schermspeler controleren en problemen oplossen gebruikend het dashboard van het Apparaat. Deze pagina biedt informatie over hoe u waargenomen prestatieproblemen voor de schermspeler en de toegewezen apparaten kunt controleren en oplossen.

## Monitor en problemen oplossen vanuit Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

U kunt de activiteit controleren en zo uw speler van het Scherm problemen oplossen, gebruikend het Dashboard van het Apparaat.

### Apparaatdashboard {#device-dashboard}

Ga als volgt te werk om naar het dashboard van het apparaat te navigeren:

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Project testen*** —> ***Apparaten***.

   Selecteer **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Selecteer het apparaat (**NewTestDevice**) en klik **Dashboard** van de actiebar.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de activiteiten en functies van het apparaat kunt controleren.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

In het deelvenster **Activiteit** wordt het laatste pingelen van de schermspeler met het tijdstempel weergegeven. Laatste pingel beantwoordt aan de laatste tijd het apparaat met de server contacteerde.

![chlimage_1](assets/chlimage_1.png)

Klik bovendien op **Logbestanden verzamelen** in de rechterbovenhoek van het deelvenster **Activiteit** om de logbestanden voor uw speler weer te geven.

### Apparaatdetails {#update-device-details} bijwerken

Controleer het **deelvenster Apparaatdetails** om de apparaat-IP, het opslaggebruik, de firmware-versie en de Player-uptime voor uw apparaat weer te geven.

![chlimage_1-1](assets/chlimage_1-1.png)

Daarnaast klikt u op **Cache wissen** en **Bijwerken** om de cache van uw apparaat te wissen en de [firmware](screens-glossary.md)-versie in dit deelvenster bij te werken.

Klik ook op **..** in de rechterbovenhoek van het deelvenster **Apparaatdetails** om de status van uw speler opnieuw te starten of te vernieuwen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Apparaatinformatie {#update-device-information} bijwerken

Controleer het **deelvenster APPARAATINFORMATIE** om de configuratieupdate, het apparaatmodel, het apparaatbesturingssysteem en de shell-informatie weer te geven.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klik bovendien op de knop (**..**) in de rechterbovenhoek van het deelvenster Apparaatinformatie om eigenschappen weer te geven of het apparaat bij te werken.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klik op **Eigenschappen** om het dialoogvenster **Apparaateigenschappen** weer te geven. U kunt de apparaattitel bewerken of de optie voor configuratie-updates kiezen als **Handmatig** of **Automatisch**.

>[!NOTE]
>
>Voor meer informatie over de gebeurtenissen verbonden aan de automatische of handupdates van het apparaat, zie de sectie ***Automatische versus Handmatige Updates van het Dashboard van het Apparaat*** in [Managing Kanalen](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt de schermafbeelding van de speler weergeven vanaf het apparaat in het deelvenster **PLAYER SCREENSHOT**.

Klik (**..**) in de rechterbovenhoek van het deelvenster Schermafbeelding van speler en selecteer **Schermafbeelding vernieuwen** om de opname van de actieve speler weer te geven.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

In het venster **PREFERENCES** kan de gebruiker voorkeuren wijzigen voor **Admin UI**, **Kanaalswitch** en **Foutopsporing op afstand** voor het apparaat.

>[!NOTE]
>Zie [AEM Screens Player](working-with-screens-player.md) voor meer informatie over deze optie.

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klik bovendien op **Instellingen** in de rechterbovenhoek om de voorkeuren van het apparaat bij te werken. U kunt de volgende voorkeuren bijwerken:

* **Server-URL**
* **Resolutie**
* **Plan opnieuw opstarten**
* **Max. nr. van logbestanden om te behouden**
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

## OSGi-instellingen {#troubleshoot-osgi-settings} oplossen

U moet de lege referentie inschakelen zodat het apparaat gegevens op de server kan plaatsen. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen.

Momenteel zijn enkele van deze functies alleen beschikbaar als het filter *Apache Sling Reference Allow Empty* is ingeschakeld in de OSGi-configuratie. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeer naar **Adobe Experience Manager Web Console Configuration**, dat wil zeggen `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Schakel de optie **allow.empty** in.
1. Klik **Opslaan**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Recommendations {#recommendations}

In de volgende sectie wordt aangeraden de netwerkkoppelingen, de server en de spelers te controleren om de status te begrijpen en op problemen te reageren.

AEM biedt ingebouwde bewaking voor:

* ** Heartbeatter 5 seconden om aan te geven dat de AEM Screens Player wordt uitgevoerd.
* *Screenshot* van de Player die toont wat momenteel op de Speler wordt getoond.
* De *AEM Screens Player Firmware*-versie geïnstalleerd op de Player.
* *Vrije opslagruimte* op de speler.

Recommendations voor externe controle met software van derden:

* CPU-gebruik op afspeelapparatuur.
* Controleer of het AEM Screens Player-proces wordt uitgevoerd.
* Extern opnieuw opstarten/opnieuw opstarten van de Player.
* Real-time meldingen.

Het wordt aanbevolen de Player-hardware en het besturingssysteem zodanig te implementeren dat externe aanmelding problemen kan opsporen en de Player opnieuw kan starten.

#### Aanvullende bronnen {#additional-resources}

Zie [Configuratie en probleemoplossing voor videoafspelen](troubleshoot-videos.md) om fouten op te sporen in video&#39;s die in uw kanaal worden afgespeeld en problemen op te lossen.
