---
title: Problemen oplossen in Device Control Center
seo-title: Monitoring Screens
description: Volg deze pagina om de prestaties voor de activiteit en het apparaat van de Schermspeler te controleren en problemen op te lossen gebruikend het dashboard van het Apparaat.
seo-description: Follow this page to monitor and troubleshoot performance for your Screens player activity and device usingtheDevice dashboard.
uuid: b6895d5d-c743-4e10-a166-de573e122335
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
discoiquuid: 3f130808-71e8-4710-8181-021d953660f8
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: 707833ddd8ab2573abcac4e9a77ec88778624435
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 0%

---

# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor de activiteit en het apparaat van de Schermspeler controleren en problemen oplossen gebruikend het dashboard van het Apparaat. Deze pagina verstrekt informatie over hoe te om waargenomen prestatiesproblemen voor de speler van het Scherm en de toegewezen apparaten te controleren en problemen op te lossen.

## Monitor en problemen oplossen vanuit Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

U kunt de activiteit controleren en zo uw speler van het Scherm problemen oplossen, gebruikend het Dashboard van het Apparaat.

### Apparaatdashboard {#device-dashboard}

Ga als volgt te werk om naar het dashboard van het apparaat te navigeren:

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Project testen*** —> ***Apparaten***.

   Selecteren **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Selecteer het apparaat (**NewTestDevice**) en klik op **Dashboard** in de actiebalk.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de activiteiten en functies van het apparaat kunt controleren.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

De **Activiteit** toont laatste pingelt van uw het schermspeler met timestamp. Laatste pingel beantwoordt aan de laatste tijd het apparaat met de server contacteerde.

![chlimage_1](assets/chlimage_1.png)

Klik bovendien op **Logbestanden verzamelen** vanaf de rechterbovenhoek van het **Activiteit** om de logbestanden voor uw speler weer te geven.

### Apparaatdetails bijwerken {#update-device-details}

Controleer de **Apparaatdetails** om de IP van het apparaat, het gebruik van de Opslag, ingebouwde programmatuurversie en de speler uptime voor uw apparaat te bekijken.

![chlimage_1-1](assets/chlimage_1-1.png)

Klik bovendien op **Cache wissen** en **Bijwerken** om de cache van uw apparaat te wissen en de [firmware](screens-glossary.md) van dit deelvenster.

Klik ook op de knop **...** in de rechterbovenhoek van het dialoogvenster **Apparaatdetails** om de status van de speler opnieuw te starten of te vernieuwen.

![chlimage_1-2](assets/chlimage_1-2.png)

### Apparaatgegevens bijwerken {#update-device-information}

Controleer de **APPARAATINFORMATIE** om de configuratieupdate, het apparaatmodel, het apparaatbesturingssysteem en de shell-informatie weer te geven.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Klik bovendien op de knop (**...**) in de rechterbovenhoek van het deelvenster Apparaatinformatie om eigenschappen weer te geven of het apparaat bij te werken.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Klikken **Eigenschappen** om de **Apparaateigenschappen** in. U kunt de apparaattitel bewerken of de optie voor configuratie-updates kiezen als **Handmatig** of **Automatisch**.

>[!NOTE]
>
>Zie de sectie voor meer informatie over de gebeurtenissen die zijn gekoppeld aan de automatische of handmatige updates van het apparaat ***Automatische versus handmatige updates van het apparaatdashboard*** in [Kanalen beheren](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt de schermafbeelding van de speler bekijken vanaf het apparaat **AFSPEELSCREENSHOT** deelvenster.

Klikken (**...**) in de rechterbovenhoek van het deelvenster Schermafbeelding van speler en selecteer **Schermafbeelding vernieuwen** om de opname van de actieve speler weer te geven.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

De **VOORKEUREN** kan de gebruiker de voorkeuren wijzigen voor **Gebruikersinterface van beheerder**, **Kanaalswitch**, en **Foutopsporing op afstand** voor het apparaat.

>[!NOTE]
>Zie voor meer informatie over deze optie [AEM Screens Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Klik bovendien op **Instellingen** in de rechterbovenhoek om de voorkeuren voor apparaten bij te werken. U kunt de volgende voorkeuren bijwerken:

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

Sommige van deze functies zijn momenteel alleen beschikbaar als de *Lege filter Apache-schuifverwijzing toestaan* wordt toegelaten in de configuratie OSGi. Op het dashboard kan een waarschuwing worden weergegeven dat sommige van deze functies mogelijk niet kunnen worden gebruikt vanwege beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeren naar **Configuratie Adobe Experience Manager-webconsole**, dat wil zeggen: `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Controleer de **allow.empty** optie.
1. Klikken **Opslaan**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Recommendations {#recommendations}

In de volgende sectie wordt aangeraden de netwerkkoppelingen, de server en de spelers te controleren om de status te begrijpen en op problemen te reageren.

AEM biedt ingebouwde bewaking voor:

* *Hartslag* elke 5 seconden om aan te geven dat de AEM Screens Player wordt uitgevoerd.
* *Schermafbeelding* van de Speler die toont wat momenteel op de Speler wordt getoond.
* De *AEM Screens Player Firmware* versie geïnstalleerd op de Speler.
* *Vrije opslagruimte* op de speler.

Recommendations voor externe controle met software van derden:

* CPU-gebruik op afspeelapparatuur.
* Controleer of het AEM Screens Player-proces wordt uitgevoerd.
* Extern opnieuw opstarten/opnieuw opstarten van de Player.
* Real-time meldingen.

Het wordt aanbevolen de Player-hardware en het besturingssysteem zodanig te implementeren dat externe aanmelding problemen kan opsporen en de Player opnieuw kan starten.

#### Aanvullende bronnen {#additional-resources}

Zie [Configuratie en probleemoplossing voor het afspelen van video](troubleshoot-videos.md) om fouten op te sporen in video&#39;s die in uw kanaal worden afgespeeld en om problemen op te lossen.
