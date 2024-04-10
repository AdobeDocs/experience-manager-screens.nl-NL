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
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor de activiteiten en het apparaat van de AEM Screens-speler controleren en problemen oplossen met behulp van het apparaatdashboard. Deze pagina biedt informatie over hoe u waargenomen prestatieproblemen voor de schermspeler en de toegewezen apparaten kunt controleren en oplossen.

## Monitor en problemen oplossen via het beheercentrum van het apparaat {#monitor-and-troubleshoot-from-device-control-center}

Via hetDevice Dashboard kunt u de activiteiten bijhouden en problemen met uw AEM Screens-speler oplossen.

### Apparaatdashboard {#device-dashboard}

Volg de onderstaande stappen om naar het apparaatdashboard te navigeren:

1. Navigeer vanuit uw project naar het apparaatdashboard, bijvoorbeeld ***Project*** testen > ***apparaten***.

   Selecteer **Apparaten** en **Apparaatbeheer op** de actiebalk.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Selecteer het apparaat (**NewTestDevice**) en klik op **Dashboard** in de actiebalk.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de apparaatactiviteiten en -functies kunt controleren.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

De **Activiteit** toont het laatste pingelen van uw AEM Screens speler met timestamp. Laatste pingel beantwoordt aan de laatste tijd dat het apparaat de server contacteerde.

![chlimage_1](assets/chlimage_1.png)

Selecteer **ook Logbestanden** verzamelen in de rechterbovenhoek van het **deelvenster Activiteit** om de logbestanden voor uw speler weer te geven.

### Apparaatdetails bijwerken {#update-device-details}

Controleer de **Apparaatdetails** zodat u de apparaat-IP, het opslaggebruik, de firmware-versie en de Player-uptime voor uw apparaat kunt bekijken.

![chlimage_1-1](assets/chlimage_1-1.png)

Selecteer ook **Cache wissen** en **Bijwerken** om de cache van uw apparaat te wissen en de [firmware](screens-glossary.md) van dit deelvenster.

Selecteer ook **...** in de rechterbovenhoek van het **Apparaatdetails** om de status van de speler opnieuw te starten of te vernieuwen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Apparaatgegevens bijwerken {#update-device-information}

Schakel het **deelvenster DEVICE INFORMATION (APPARAATINFORMATIE)** in. Hier kunt u de configuratie-update, het apparaatmodel, het apparaat besturingssysteem en de shell-informatie bekijken.

![screen_shot_2019-09-05-13853](assets/screen_shot_2019-09-05at13853pm.png)

Selecteer ook (**...**) in de rechterbovenhoek van het deelvenster Apparaatinformatie om eigenschappen weer te geven of het apparaat bij te werken.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Selecteren **Eigenschappen** zodat u de **Apparaateigenschappen** in. U kunt de apparaattitel bewerken of de optie voor configuratie-updates kiezen als **Handmatig** of **Automatisch**.

>[!NOTE]
>
>Zie de sectie voor meer informatie over de gebeurtenissen die zijn gekoppeld aan de automatische of handmatige updates van het apparaat ***Automatische versus handmatige updates van het apparaatdashboard*** in [Kanalen beheren](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt de schermafbeelding van de speler bekijken vanaf het apparaat **AFSPEELSCREENSHOT** deelvenster.

Klikken (**...**) in de rechterbovenhoek van het deelvenster Schermafbeelding van speler en selecteer **Schermafbeelding vernieuwen** om de opname van de actieve speler weer te geven.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

De **Voorkeuren** kan de gebruiker de voorkeuren wijzigen voor **Gebruikersinterface van beheerder**, **Kanaalswitch**, en **Foutopsporing op afstand** voor het apparaat.

>[!NOTE]
>Zie [AEM Screens Player](working-with-screens-player.md) voor meer informatie over deze opties.

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Selecteer ook **Instellingen** in de rechterbovenhoek om de voorkeuren voor apparaten bij te werken. U kunt de volgende voorkeuren bijwerken:

* **Server-URL**
* **Resolutie**
* **Schema opnieuw opstarten**
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

## Problemen met OSGi-instellingen oplossen {#troubleshoot-osgi-settings}

Schakel de lege verwijzer in om het apparaat toe te staan gegevens naar de server te plaatsen. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen.

Sommige van deze functies zijn momenteel alleen beschikbaar als de *Lege filter Apache-schuifverwijzing toestaan* wordt toegelaten in de configuratie OSGi. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeer naar **de webconsoleconfiguratie** van Adobe Experience Manager, dat wil gezegd `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Schakel de **optie allow.empty in** .
1. Klik op **Opslaan**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Aanbevelingen {#recommendations}

In de volgende sectie wordt aangeraden om de netwerkkoppelingen, servers en players te controleren om de gezondheid te begrijpen en op problemen te reageren.

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

Zie [Configuratie voor afspelen en problemen oplossen](troubleshoot-videos.md) voor video&#39;s die in je kanaal worden afgespeeld en problemen wilt oplossen.
