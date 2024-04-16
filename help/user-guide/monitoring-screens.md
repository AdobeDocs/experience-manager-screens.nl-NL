---
title: Problemen oplossen in Device Control Center
description: Leer hoe u de prestaties voor de activiteiten en het apparaat van de AEM Screens-speler kunt controleren en oplossen met het apparaatdashboard.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor de activiteiten en het apparaat van de AEM Screens-speler controleren en problemen oplossen met behulp van het apparaatdashboard. Deze pagina biedt informatie over hoe u waargenomen prestatieproblemen voor de schermspeler en de toegewezen apparaten kunt controleren en oplossen.

## Monitor en problemen oplossen vanuit Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

U kunt de activiteit controleren en zo uw speler van AEM Screens problemen oplossen, gebruikend het Dashboard van het Apparaat.

### Apparaatdashboard {#device-dashboard}

Ga als volgt te werk om naar het dashboard van het apparaat te navigeren:

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Project testen*** > ***Apparaten***.

   Klikken **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Klik op het apparaat (**NewTestDevice**) en klik op **Dashboard** in de actiebalk.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de apparaatactiviteiten en -functies kunt controleren.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

De **Activiteit** toont het laatste pingelen van uw AEM Screens speler met timestamp. Laatste pingel beantwoordt aan de laatste tijd dat het apparaat de server contacteerde.

![chlimage_1](assets/chlimage_1.png)

Klik ook op **Logbestanden verzamelen** in de rechterbovenhoek van het **Activiteit** om de logbestanden voor uw speler weer te geven.

### Apparaatdetails bijwerken {#update-device-details}

Controleer de **Apparaatdetails** zodat u de apparaat-IP, het opslaggebruik, de firmware-versie en de Player-uptime voor uw apparaat kunt bekijken.

![chlimage_1-1](assets/chlimage_1-1.png)

Klik ook op **Cache wissen** en **Bijwerken** om de cache van uw apparaat te wissen en de [firmware](screens-glossary.md) van dit deelvenster.

Klik ook op **...** in de rechterbovenhoek van het **Apparaatdetails** om de status van de speler opnieuw te starten of te vernieuwen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Apparaatgegevens bijwerken {#update-device-information}

Controleer de **APPARAATGEGEVENS** deelvenster. Hier kunt u de configuratieupdate, het apparatenmodel, apparaat OS, en shell informatie bekijken.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klik ook (**...**) in de rechterbovenhoek van het deelvenster Apparaatinformatie om eigenschappen weer te geven of het apparaat bij te werken.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klikken **Eigenschappen** zodat u de **Apparaateigenschappen** in. U kunt de apparaattitel bewerken of de optie voor configuratie-updates kiezen als **Handmatig** of **Automatisch**.

>[!NOTE]
>
>Zie de sectie voor meer informatie over de gebeurtenissen die zijn gekoppeld aan de automatische of handmatige updates van het apparaat ***Automatische versus handmatige updates van het apparaatdashboard*** in [Kanalen beheren](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt de schermafbeelding van de speler bekijken vanaf het apparaat **AFSPEELSCREENSHOT** deelvenster.

Klikken (**...**) rechtsboven in het deelvenster Schermafbeelding van speler en klik op **Schermafbeelding vernieuwen** om de opname van de actieve speler weer te geven.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

De **Voorkeuren** kan de gebruiker de voorkeuren wijzigen voor **Gebruikersinterface van beheerder**, **Kanaalswitch**, en **Foutopsporing op afstand** voor het apparaat.

>[!NOTE]
>Zie voor meer informatie over deze opties [AEM Screens Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klik ook op **Instellingen** in de rechterbovenhoek om de voorkeuren voor apparaten bij te werken. U kunt de volgende voorkeuren bijwerken:

* **Server-URL**
* **Resolutie**
* **Plan opnieuw opstarten**
* **Max. nr. van te bewaren logbestanden**
* **Logboekniveau**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>U kunt op een van de volgende logniveaus klikken:
>* **Uitschakelen**
>* **Foutopsporing**
>* **Info**
>* **Waarschuwing**
>* **Fout**

![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## OSGi-instellingen problemen oplossen {#troubleshoot-osgi-settings}

Schakel de lege referentie in zodat het apparaat gegevens naar de server kan posten. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen.

Sommige van deze functies zijn momenteel alleen beschikbaar als de *Lege filter Apache-schuifverwijzing toestaan* wordt toegelaten in de configuratie OSGi. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole**, dat wil zeggen: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Controleer de **allow.empty** -optie.
1. Klikken **Opslaan**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Recommendations {#recommendations}

In de volgende sectie wordt aanbevolen de netwerkkoppelingen, servers en spelers te controleren om de status te begrijpen en op problemen te reageren.

AEM biedt ingebouwde bewaking voor:

* *Hartslag* om de 5 seconden om aan te geven dat de AEM Screens Player wordt uitgevoerd.
* *Schermafbeelding* van de Speler die toont wat op de Speler wordt getoond.
* De *AEM Screens Player Firmware* versie geïnstalleerd op de Speler.
* *Vrije opslagruimte* op de speler.

Recommendations voor externe controle met software van derden:

* CPU-gebruik op afspeelapparatuur.
* Controleer of het AEM Screens Player-proces wordt uitgevoerd.
* Extern opnieuw opstarten/opnieuw opstarten van de Player.
* Real-time meldingen.

Het wordt aanbevolen de Player-hardware en het besturingssysteem zodanig te implementeren dat externe aanmelding problemen kan opsporen en de Player opnieuw kan starten.

#### Overige bronnen {#additional-resources}

Zie [Configuratie en probleemoplossing voor videoweergave](troubleshoot-videos.md) als u fouten wilt opsporen in video&#39;s die in uw kanaal worden afgespeeld en problemen wilt oplossen.
