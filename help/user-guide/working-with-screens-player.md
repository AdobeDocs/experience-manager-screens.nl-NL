---
title: Werken met AEM Screens Player
description: Meer informatie over het werken met AEM Screens Player, de beheerinterface en de kanaalswitch.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4faac090-ad8a-4d7e-a502-6fb63f6b2761
source-git-commit: 1e8beb9dfaf579250138d4a41eeec88cc81f2d39
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 0%

---

# Werken met AEM Screens Player

U kunt de inhoud van het kanaal en andere instellingen in AEM Screens Player beheren.

>[!NOTE]
>
>Druk ***Ctrl+Cmd+F*** zodat u de modus Volledig scherm kunt afsluiten voor OS X AEM Screens Player.

Nadat u een kanaal aan een vertoning toewijst, toont de Speler van AEM Screens de inhoud. U kunt instellingen voor de speler configureren met de voorkeuren voor de interface voor beheerders (van het dashboard) of met de speler zelf.

## Het dashboard van het Apparaat gebruiken {#using-the-device-dashboard}

U kunt voorkeuren voor uw apparaat configureren vanaf het dashboard van het apparaat, dat toegankelijk is via de AEM ontwerpinstantie.

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Project testen*** > ***Apparaten***.

   Selecteren **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![chlimage_1-66](assets/chlimage_1-66.png)

1. Klik op het apparaat zodat u het dashboard van het apparaat kunt openen.

   ![chlimage_1-67](assets/chlimage_1-67.png)

1. Controleer de **Voorkeuren** deelvenster. U kunt de **Gebruikersinterface van beheerder** en **Kanaalswitch** voor uw speler uit deze twee opties.

   ![chlimage_1-68](assets/chlimage_1-68.png)

### De interface van Admin {#the-admin-ui}

Het inschakelen van de **Gebruikersinterface van beheerder** in het voorkeurenvenster kan de gebruiker de beheerinstellingen openen vanuit de schermspeler. Als u deze optie uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de interface voor beheer niet openen vanuit de speler.

Als u de interface voor het beheer van de schermspeler wilt weergeven, drukt u op de linkerbovenhoek om het menu Admin te openen, op de AEM Screens-speler met aanraakbediening of met een muis. De informatie wordt weergegeven nadat de registratie is voltooid en de kanalen zijn geladen.

>[!NOTE]
>
>U kunt ook de uptime van de AEM Screens Player-app weergeven om de status van de app te controleren.

![chlimage_1-3](assets/chlimage_1-3.gif)

#### Toegang tot de Opties van het Menu van de Configuratie {#configuration-options}

U kunt uw configuraties bijwerken als u **Configuratie** van het zijmenu, zoals weergegeven in onderstaande afbeelding:

![screen_shot_2018-10-15at101257am](assets/screen_shot_2018-10-15at101257am.png)

In het menu Configuratie kunt u de volgende instellingen wijzigen:

* Herstellen **Firmware**, **Voorkeuren**, of **Naar fabriek** in dit dialoogvenster.

* Geef het maximumaantal logbestanden op dat u voor een AEM Screens-speler wilt behouden in **Max. nr. van te bewaren logbestanden**.

* In- of uitschakelen **Menu Beheer**, **Kanaalswitch**, en **UI voor activiteiten** voor de Schermspeler.

  Als de **UI voor activiteiten** is ingeschakeld vanuit de **Configuratie** in de AEM Screens-speler wordt de *spelersactiviteitmeldingen* in de rechterbovenhoek van de speler, zoals in de onderstaande afbeelding wordt getoond.

  ![afbeelding](/help/user-guide/assets/activity_ui.png)

>[!NOTE]
>
>De **Firmware bijwerken** werkt alleen op de Cordova, zoals Android™-spelers.

>[!NOTE]
>
>Het wordt aanbevolen de **Gebruikersinterface van beheerder** uitgeschakeld zijn bij productieimplementaties.

#### Opties voor het menu-cachegeheugen voor inhoud openen {#content-cache-options}

U kunt cache voor kanalen en toepassingen wissen via de interface voor beheer in AEM Screens Player.

Selecteer de **Inhoudcache** van de zijspoorstaaf zodat kunt u het geheime voorgeheugen bijwerken.

![screen_shot_2018-10-15at105717am](assets/screen_shot_2018-10-15at105717am.png)

### De kanaalschakelaar {#the-channel-switcher}

Het inschakelen van de **Kanaalswitch** in het voorkeurenvenster kan de gebruiker de kanaalselectie/instellingen openen vanuit de schermspeler.

Als u deze optie uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de kanaalvoorkeuren niet besturen via de schermspeler.

U kunt instellingen voor uw kanaal wijzigen en beheren vanuit uw schermspeler.

Als u de kanaalschakelaar van de speler wilt weergeven, drukt u lang op de linkerbenedenhoek om de kanaalschakelaar te openen die het schakelen tussen kanalen en andere functies toestaat.

![chlimage_1-69](assets/chlimage_1-69.png)

>[!NOTE]
>
>U kunt ook het beheermenu en de kanaalschakelaar voor de speler in- of uitschakelen via de schermspeler.
>
>(Zie *Voorkeuren wijzigen vanuit schermspeler* zoals vermeld in de onderstaande paragraaf).

### Voorkeuren beheren vanuit AEM Screens Player

U kunt ook de instellingen voor de interface van de beheerder en de kanaalschakelaar wijzigen vanuit de speler zelf.

Voorkeuren wijzigen van uw speler:

1. Druk op de linkerbovenhoek van het inactieve kanaal lang om het beheerpaneel te openen.
1. Navigeren naar **Configuratie** in het linkeractiemenu.
1. Configuratie inschakelen/uitschakelen voor **Gebruikersinterface van beheerder** of **Kanaalswitch**.

![screen_shot_2018-10-15at101257am-1](assets/screen_shot_2018-10-15at101257am-1.png)

## Problemen met AEM Screens Player oplossen

U kunt verschillende problemen met de AEM Screens Player (hardware en software) oplossen:

| **Problemen** | **Recommendations** |
|---|---|
| Player-opslag is vol | Overbodige bestanden verwijderen |
| Speler verloren netwerk | Kat-5/kat-6 van het gebruik kabel. Voor wifi, verminder de afstand van de router aan het spelerapparaat |
| AEM Screens Player vastgelopen | Het wordt aanbevolen een waakhond-app te hebben die ervoor zorgt dat de AEM Screens Player altijd wordt uitgevoerd |
| AEM Screens Player heeft instellingen verloren | Verbinding met AEM server controleren |
| AEM Screens Player wordt niet automatisch gestart nadat de speler opnieuw is opgestart/opgestart | Start van OS-map of initialisatieprocedure controleren |
| AEM Screens Player geeft onjuiste/oude inhoud weer | Netwerkverbinding controleren |

### Updates voor AEM Screens Player

Er zijn twee typen updates voor de AEM Screens Player:

| **Methode** | **Details** | **door middel van externe** | **Automatisch** | **0 Downtime** |
|---|---|---|---|---|
| Firmware-update | Toegepast op bestaande geïnstalleerde Players door middel van ver bevel. Na de update wordt de speler automatisch opnieuw geladen met de bestaande inhoud. | Ja | Aangepast | Bijna - 1-3 seconden |
| Updates van Flash Player | Dit is een nieuw uitvoerbaar die op de Speler moet worden opgesteld. Dit vereist om nieuw binair getal op afstand op de speler te kopiëren en de huidige versie te stoppen en de nieuwe versie te starten. Hiervoor kan het nodig zijn de voorgeladen pakketten opnieuw te downloaden. | Ja (via externe shell) | Aangepast | Nee |

## Richtlijnen voor hardwareselectie voor afspeelapparaat {#hardware-selection-guidelines-for-player-device}

In de volgende sectie vindt u de richtlijnen voor hardwareselectie voor een rasterproject:

* Altijd bron ***Commercieel*** of ***Industrieel*** Graducomponenten voor zowel de speler van PC als het Comité van de Vertoning of Projector.

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
   <td><p>*ChromeOS 32 GB</p> <p>*Windows 128 GB</p> </td>
   <td>onBoard</td>
   <td>1920 x 1080</td>
   <td>DVI<br /> Ethernet/Wireless<br /> 2x USB</td>
   <td>
    <ul>
     <li>Standaardherhaling op volledig scherm<br /> </li>
     <li>Dagverdeling</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Standaard</td>
   <td>Quad Core, Intel® Core™ i5 processor</td>
   <td><p>8 GB geheugen</p> <p>4 MB cache</p> </td>
   <td>128 GB</td>
   <td>onBoard</td>
   <td>3840x2160 (4K)</td>
   <td>DVI, HDMI<br /> Ethernet/Wireless,<br /> 2x USB</td>
   <td>
    <ul>
     <li>Dynamische inhoud van één bron</li>
     <li>Eenvoudig interactief</li>
     <li>1-3 Zone-indelingen</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Geavanceerd</td>
   <td>Quad Core met hyperthreading, Intel® Core™ i7 processor</td>
   <td><p>16 GB geheugen</p> <p>8 MB cache</p> </td>
   <td>256 GB</td>
   <td>GPU voor speciale grafische kaarten</td>
   <td>3840x2160 (4K)</td>
   <td>DVI, HDMI<br /> Ethernet/Wireless,<br /> 4x USB</td>
   <td>
    <ul>
     <li>4 of meer inhoudszones, gelijktijdige videoweergave</li>
     <li>Interactief meerdere pagina's</li>
     <li>Multi-Source Data Triggers</li>
    </ul> </td>
  </tr>
 </tbody>
</table>
