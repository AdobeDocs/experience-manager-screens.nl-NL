---
title: Problemen oplossen in Device Control Center
description: Leer hoe u de prestaties voor uw AEM Screens Player-activiteit en -apparaat kunt controleren en oplossen met het apparaatdashboard.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---

# Problemen oplossen in Device Control Center {#troubleshooting-device-control-center}

U kunt de prestaties voor uw AEM Screens Player-activiteit en -apparaat bewaken en problemen oplossen met behulp van het apparaatdashboard. Deze pagina biedt informatie over het bewaken en oplossen van waargenomen prestatieproblemen voor Screens Player en de toegewezen apparaten.

## Monitor en problemen oplossen vanuit Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

U kunt de activiteit controleren en zo uw Speler van AEM Screens problemen oplossen, gebruikend het Dashboard van het Apparaat.

### Apparaatdashboard {#device-dashboard}

Ga als volgt te werk om naar het dashboard van het apparaat te navigeren:

1. Navigeer aan het apparatendashboard van uw project, bijvoorbeeld, ***Project van de Test*** > ***Apparaten***.

   Klik **Apparaten** en **Manager van het Apparaat** van de actiebar.

   ![&#x200B; screen_shot_2019-09-03at13823pm &#x200B;](assets/screen_shot_2019-09-03at13823pm.png)

1. De lijst toont de toegewezen en niet toegewezen apparaten, zoals aangetoond in het hieronder cijfer.

   ![&#x200B; screen_shot_2019-09-05at12823pm &#x200B;](assets/screen_shot_2019-09-05at12823pm.png)

1. Klik het apparaat (**NewTestDevice**) en klik **Dashboard** van de actiebar.

   ![&#x200B; screen_shot_2019-09-05at13341pm &#x200B;](assets/screen_shot_2019-09-05at13341pm.png)

1. De pagina bevat de apparaatinformatie, de activiteit en de apparaatdetails waarmee u de apparaatactiviteiten en -functies kunt controleren.

   ![&#x200B; screen_shot_2019-09-05at13700pm &#x200B;](assets/screen_shot_2019-09-05at13700pm.png)

### Apparaatactiviteit controleren {#monitor-device-activity}

Het **paneel van de Activiteit** toont laatste pingelen van uw Speler van AEM Screens met timestamp. Laatste pingel beantwoordt aan de laatste tijd dat het apparaat de server contacteerde.

![&#x200B; chlimage_1 &#x200B;](assets/chlimage_1.png)

Ook, klik **verzamelen Logboeken** van de top-juiste hoek van het **paneel van de Activiteit** om de logboeken voor uw speler te bekijken.

### Apparaatdetails bijwerken {#update-device-details}

Controleer het **paneel van de Details van het Apparaat** zodat kunt u het apparaatIP, het gebruik van de Opslag, ingebouwde programmatuurversie, en speler uptime voor uw apparaat bekijken.

![&#x200B; chlimage_1-1 &#x200B;](assets/chlimage_1-1.png)

Ook, klik **Duidelijk Geheime voorgeheugen** en **Update** om het geheime voorgeheugen van uw apparaat te ontruimen en de [&#x200B; ingebouwde programmatuur &#x200B;](screens-glossary.md) versie respectievelijk van dit paneel bij te werken.

Ook, klik **...** van de hoger-juiste hoek van het **paneel van de Details van het Apparaat** om het statuut van uw speler opnieuw te beginnen of te verfrissen.

![&#x200B; chlimage_1-2 &#x200B;](assets/chlimage_1-2.png)

### Apparaatgegevens bijwerken {#update-device-information}

Controleer het **paneel van de INFORMATIE VAN HET APPARAAT**. Hier kunt u de configuratieupdate, het apparatenmodel, apparaat OS, en shell informatie bekijken.

![&#x200B; screen_shot_2019-09-05at13853pm &#x200B;](assets/screen_shot_2019-09-05at13853pm.png)

Klik ook (**...**) van de hoger-juiste hoek van het paneel van de Informatie van het Apparaat om eigenschappen te bekijken of het apparaat bij te werken.

![&#x200B; screen_shot_2019-09-05at14017pm &#x200B;](assets/screen_shot_2019-09-05at14017pm.png)

Klik **Eigenschappen** zodat kunt u het **de dialoogvakje van de Eigenschappen van het Apparaat** bekijken. U kunt de apparatentitel uitgeven of de optie voor configuratieupdates als **Handboek** kiezen of **Automatisch**.

>[!NOTE]
>
>Om meer over de gebeurtenissen te leren verbonden aan de automatische of handupdates van het apparaat, zie de sectie ***Automatisch tegenover Handmatige Updates van het Dashboard van het Apparaat*** in [&#x200B; het Leiden Kanalen &#x200B;](managing-channels.md).

![&#x200B; screen_shot_2019-09-05at14112pm &#x200B;](assets/screen_shot_2019-09-05at14112pm.png)

### Schermafbeelding van speler weergeven {#view-player-screenshot}

U kunt het spelerscherm bekijken van het apparaat van **SPELER SCREENSHOT** paneel.

Klik (**..**) op de hoogste juiste hoek van het paneel van het Schermafbeelding van de Speler en klik **verfrissen Screenshot** om de momentopname van de lopende speler te bekijken.

![&#x200B; screen_shot_2019-09-05at14205pm &#x200B;](assets/screen_shot_2019-09-05at14205pm.png)

### Voorkeuren beheren {#manage-preferences}

Het **paneel van VOORKEUREN** staat de gebruiker toe om voorkeur voor **Admin UI**, **Schakelaar van het Kanaal** te veranderen, en **Verre het Zuiveren** voor het apparaat.

>[!NOTE]
>Meer over deze opties leren, zie [&#x200B; Speler van AEM Screens &#x200B;](working-with-screens-player.md).

![&#x200B; screen_shot_2019-09-05at14250pm &#x200B;](assets/screen_shot_2019-09-05at14250pm.png)

Ook, klik **Montages** van de top-juiste hoek om apparatenvoorkeur bij te werken. U kunt de volgende voorkeuren bijwerken:

* **Server URL**
* **Resolutie**
* **Reboot Programma**
* **Max nr. van logboekdossiers om te houden**
* **Niveau van het Logboek**

![&#x200B; screen_shot_2019-09-05at14511pm &#x200B;](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>U kunt op een van de volgende logniveaus klikken:
>
>* **onbruikbaar maken**
>* **zuivert**
>* **Info**
>* **Waarschuwing**
>* **Fout**

![&#x200B; screen_shot_2019-09-05at15645pm &#x200B;](assets/screen_shot_2019-09-05at15645pm.png)

## OSGi-instellingen problemen oplossen {#troubleshoot-osgi-settings}

Schakel de lege referentie in zodat het apparaat gegevens naar de server kan posten. Als de lege referentie-eigenschap bijvoorbeeld is uitgeschakeld, kan het apparaat geen schermafbeelding terugplaatsen.

Sommige van deze functies zijn momenteel alleen beschikbaar als de *`Apache Sling Referrer Filter Allow Empty`* is ingeschakeld in de OSGi-configuratie. Op het dashboard kan een waarschuwing worden weergegeven dat bepaalde functies mogelijk niet kunnen worden gebruikt door beveiligingsinstellingen.

Voer de onderstaande stappen uit om het filter Leeg toestaan van Apache-verwijzing in te schakelen

1. Navigeer aan **Configuratie van de Console van het Web van Adobe Experience Manager**, namelijk `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Controleer **allow.empty** optie.
1. Klik **sparen**.

![&#x200B; chlimage_1-3 &#x200B;](assets/chlimage_1-3.png)

### Aanbevelingen {#recommendations}

In de volgende sectie wordt aanbevolen de netwerkkoppelingen, servers en spelers te controleren om de status te begrijpen en op problemen te reageren.

AEM biedt ingebouwde bewaking voor:

* *Hartslag* om de 5 seconden om erop te wijzen dat de Speler van AEM Screens in verrichting is.
* *Schermafbeelding* van de Speler die toont wat op de Speler wordt getoond.
* De *versie van de Ingebouwde programmatuur van de Speler van AEM Screens* is geïnstalleerd op de Speler.
* *Vrije opslagruimte* op de Speler.

Aanbevelingen voor externe controle met software van derden:

* CPU-gebruik in afspeelapparatuur.
* Controleer of het AEM Screens Player-proces wordt uitgevoerd.
* Extern opnieuw opstarten/opnieuw opstarten van de Player.
* Real-time meldingen.

Het wordt aanbevolen de Player-hardware en het besturingssysteem zodanig te implementeren dat externe aanmelding problemen kan opsporen en de Player opnieuw kan starten.

#### Overige bronnen {#additional-resources}

Zie [&#x200B; VideoPlayback Configuratie en het Oplossen van problemen &#x200B;](troubleshoot-videos.md) als u video&#39;s wilt zuiveren en problemen oplossen die in uw kanaal spelen.
