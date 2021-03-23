---
title: Werken met AEM Screens Player
seo-title: Werken met schermspeler
description: Volg deze pagina voor meer informatie over schermspeler. Het verklaart ook Admin UI en de Schakelaar van het Kanaal.
seo-description: Volg deze pagina voor meer informatie over schermspeler. Het verklaart ook Admin UI en de Schakelaar van het Kanaal.
uuid: 93e113ea-fbef-4757-982b-b7dc52fc76a7
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 4ad51b5e-c628-4440-9f2e-41d17cb10bc3
feature: Schermen beheren
role: Beheerder
level: Intermediair
translation-type: tm+mt
source-git-commit: 9d36c0ebc985b815ab41d3f3ef44baefa22db915
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---


# Werken met AEM Screens Player {#working-with-aem-screens-player}

U kunt de inhoud van het kanaal en andere instellingen in AEM Screens Player beheren.

>[!NOTE]
>
>Druk op ***Ctrl+Cmd+F*** om de modus Volledig scherm voor OS X AEM Screens Player af te sluiten.

Nadat u een kanaal aan een weergave hebt toegewezen, geeft de AEM Screens Player de inhoud weer. U kunt instellingen voor de speler configureren met de voorkeuren voor de interface voor beheerders (van het dashboard) of met de speler zelf.

## Het dashboard van het Apparaat gebruiken {#using-the-device-dashboard}

U kunt voorkeuren voor uw apparaat configureren vanaf het dashboard van het apparaat, dat toegankelijk is via de AEM ontwerpinstantie.

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Project testen*** —> ***Apparaten***.

   Selecteer **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![chlimage_1-66](assets/chlimage_1-66.png)

1. Klik op het apparaat om het dashboard van het apparaat te openen.

   ![chlimage_1-67](assets/chlimage_1-67.png)

1. Controleer het **PREFERENCES** paneel. U kunt **Admin UI** en **Kanaalschakelaar** voor uw speler van deze twee opties toelaten/onbruikbaar maken.

   ![chlimage_1-68](assets/chlimage_1-68.png)

### De interface Admin {#the-admin-ui}

Als u de **Admin UI** vanuit het voorkeurenvenster inschakelt, kan de gebruiker de beheerinstellingen openen vanuit de Schermspeler. Bovendien, als u deze optie van het apparatendashboard onbruikbaar maakt, kan de gebruiker niet admin UI van de speler openen.

Als u de interface voor het beheer van de schermspeler wilt weergeven, drukt u op de linkerbovenhoek om het menu Admin te openen, op de AEM Screens-speler met aanraakbediening of met een muis. Er wordt informatie weergegeven nadat de registratie is voltooid en de kanalen zijn geladen.

>[!NOTE]
>
>Bovendien kunt u de AEM Screens Player-app uptime weergeven om de status van de app te controleren.

![chlimage_1-3](assets/chlimage_1-3.gif)

#### Toegang tot de Opties van het Menu van de Configuratie {#configuration-options}

U kunt uw configuraties bijwerken, als u **Configuratie** optie van het zijmenu selecteert, zoals aangetoond in het hieronder cijfer:

![screen_shot_2018-10-15at101257am](assets/screen_shot_2018-10-15at101257am.png)

In het menu Configuratie kunt u de volgende instellingen wijzigen:

* Stel **Firmware**, **Voorkeuren** of **Naar fabriek** vanuit dit dialoogvenster opnieuw in.

* Geef het aantal maximale logbestanden op dat voor een AEM Screens-speler behouden moet blijven in **Max. aantal. van logbestanden om** te houden.

* **Admin Menu**, **Channel Switcher** en **Activity UI** voor de Schermspeler in- of uitschakelen.

   Als **Activity UI** is ingeschakeld via het menu **Configuration**, geeft de AEM Screens-speler de *Player activity notifications* weer in de rechterbovenhoek van de speler, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/activity_ui.png)

>[!NOTE]
>
>De optie **Firmware bijwerken** werkt alleen op de cordova, zoals Android-spelers.

>[!NOTE]
>
>Het wordt geadviseerd om **Admin UI** in de Plaatsingen van de Productie onbruikbaar te maken.

#### Opties {#content-cache-options} voor het menu-cachegeheugen voor inhoud openen

U kunt cache voor kanalen en toepassingen wissen via de interface voor beheer in AEM Screens Player.

Selecteer de **Content Cache** van de zijspoorstaaf om de cache bij te werken.

![screen_shot_2018-10-15at105717am](assets/screen_shot_2018-10-15at105717am.png)

### De kanaalschakelaar {#the-channel-switcher}

Als u de **Kanaalswitch** vanuit het voorkeurenvenster inschakelt, kan de gebruiker de kanaalselectie/-instellingen openen vanuit de schermspeler.

Als u deze optie ook uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de kanaalvoorkeuren niet besturen via de schermspeler.

U kunt instellingen voor uw kanaal wijzigen en beheren vanuit uw schermspeler.

Om de kanaalschakelaar van de speler te bekijken, duw op de lagere linkerhoek om de kanaalschakelaar te openen die omschakelingskanalen en andere eigenschappen toestaat.

![chlimage_1-69](assets/chlimage_1-69.png)

>[!NOTE]
>
>U kunt ook het beheermenu en de kanaalschakelaar voor de speler in- of uitschakelen via de schermspeler.
>
>(Zie *Voorkeuren wijzigen van schermspeler* zoals vermeld in de onderstaande sectie).

### Voorkeuren beheren vanuit AEM Screens Player {#managing-preferences-from-the-aem-screens-player}

U kunt ook de instellingen voor de interface van de beheerder en de kanaalschakelaar wijzigen vanuit de speler zelf.

Ga als volgt te werk om de voorkeuren van uw speler te wijzigen:

1. Druk op de linkerbovenhoek van het inactieve kanaal om het beheerpaneel te openen.
1. Navigeer naar **Configuratie** van het linkeractiemenu.
1. Configuratie voor **Admin UI** of **Kanaalswitch** in-/uitschakelen.

![screen_shot_2018-10-15at101257am-1](assets/screen_shot_2018-10-15at101257am-1.png)

## Problemen met AEM Screens Player {#troubleshooting-aem-screens-player} oplossen

U kunt verschillende problemen met de AEM Screens Player (hardware en software) oplossen:

| **Problemen** | **Recommendations** |
|---|---|
| Player-opslag is vol | Overbodige bestanden verwijderen |
| Speler verloren netwerk | Kat-5/kat-6 van het gebruik kabel. Voor wifi, verminder de afstand van de router aan het spelerapparaat |
| AEM Screens Player vastgelopen | Het wordt aanbevolen een waakhond-app te hebben die ervoor zorgt dat de AEM Screens Player altijd wordt uitgevoerd |
| AEM Screens Player heeft instellingen verloren | Verbinding met AEM server controleren |
| AEM Screens Player wordt niet automatisch gestart nadat de speler opnieuw is opgestart/opgestart | Start van OS-map of initialisatieprocedure controleren |
| AEM Screens Player geeft onjuiste/oude inhoud weer | Netwerkverbinding controleren |

### Updates voor AEM Screens Player {#updates-for-aem-screens-player}

Er zijn twee typen updates voor de AEM Screens Player:

| **Methode** | **Details** | **via extern** | **Geautomatiseerd** | **0 Downtime** |
|---|---|---|---|---|
| Firmware-update | Toegepast op bestaande geïnstalleerde Players via verre bevel. Na de update wordt de speler automatisch opnieuw geladen met de bestaande inhoud. | Ja | Aangepast | Bijna - 1-3 seconden |
| Updates van Flash Player | Dit is een nieuw uitvoerbaar die op de Speler moet worden opgesteld. Dit vereist om nieuw binair getal op afstand op de speler te kopiëren en de huidige versie te stoppen en de nieuwe versie te starten. Hiervoor moet u mogelijk de voorgeladen pakketten opnieuw downloaden. | Ja (via externe shell) | Aangepast | Nee |

## Richtlijnen voor hardwareselectie voor afspeelapparaat {#hardware-selection-guidelines-for-player-device}

In de volgende sectie vindt u de richtlijnen voor hardwareselectie voor een rasterproject:

* Bron altijd ***Commerciële*** of ***Industriële*** Gradecomponenten voor zowel de speler van PC als het Comité van de Vertoning of Projector.

* Neem altijd contact op met leveranciers die de markt voor digitale handtekeningen bedienen.
* Houd altijd rekening met omgevingsfactoren zoals omgevingstemperatuur en relatieve vochtigheid.
* Controleer altijd de stroomvereisten en de conditionering van het energieverbruik.
* Controleer zorgvuldig de prestatiebehoeften en I/O-poorten die vereist zijn voor de toepassing.

De volgende tabel geeft een overzicht van de hardwareconfiguraties met standaardgebruiksscenario&#39;s voor een AEM Screens-project:

<table>
 <tbody>
  <tr>
   <td>Configuratie van speler</td>
   <td>Processor</td>
   <td>Geheugen</td>
   <td>OpslagSSD</td>
   <td>GPU</td>
   <td>Weergave</td>
   <td>I/O</td>
   <td>Gebruiksscenario's</td>
  </tr>
  <tr>
   <td>Basis</td>
   <td>Dual Core, i3 of quad core Intel® Atom processor op instapniveau</td>
   <td><p>4 GB geheugen</p> <p>2 MB cache</p> </td>
   <td><p>・ChromeOS 32 GB</p> <p>・Windows 128 GB</p> </td>
   <td>onBoard</td>
   <td>1920 x 1080</td>
   <td>DVI,<br /> Ethernet / Wireless,<br /> 2x USB</td>
   <td>
    <ul>
     <li>Standaardherhalen op volledig scherm<br /> </li>
     <li>Dagverdeling</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Standaard</td>
   <td>Quad Core, Intel® Core i5 processor</td>
   <td><p>8 GB geheugen</p> <p>4 MB cache</p> </td>
   <td>128 GBB</td>
   <td>onBoard</td>
   <td>3840x2160 (4K)</td>
   <td>DVI, HDMI<br /> Ethernet / Wireless,<br /> 2x USB</td>
   <td>
    <ul>
     <li>Dynamische inhoud van één bron</li>
     <li>Eenvoudig interactief</li>
     <li>1-3 Zone-indelingen</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Geavanceerd</td>
   <td>Quad Core met hyperthreading, Intel® Core i7 processor</td>
   <td><p>16 GB geheugen</p> <p>8 MB cache</p> </td>
   <td>256 GB</td>
   <td>GPU voor speciale grafische kaarten</td>
   <td>3840x2160 (4K)</td>
   <td>DVI, HDMI<br /> Ethernet / Wireless,<br /> 4x USB</td>
   <td>
    <ul>
     <li>4 of meer inhoudszones, gelijktijdig afspelen van video</li>
     <li>Interactief meerdere pagina's</li>
     <li>Multi-Source Data Triggers</li>
    </ul> </td>
  </tr>
 </tbody>
</table>
