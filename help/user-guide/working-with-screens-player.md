---
title: Werken met AEM Screens Player
description: Meer informatie over het werken met de AEM Screens Player, de Admin-gebruikersinterface en de kanaalswitch.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4faac090-ad8a-4d7e-a502-6fb63f6b2761
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 0%

---

# Werken met AEM Screens Player

U kunt de inhoud van het kanaal en andere instellingen in AEM Screens Player beheren.

>[!NOTE]
>
>Pers ***Ctrl+Cmd+F*** zodat kunt u volledig-schermwijze voor OS X AEM Screens Player weggaan.

Nadat u een kanaal aan een vertoning toewijst, toont de Speler van AEM Screens de inhoud. U kunt instellingen voor de speler configureren met de voorkeuren voor de interface van Admin (van het dashboard) of met de speler zelf.

## Het dashboard van het Apparaat gebruiken {#using-the-device-dashboard}

U kunt voorkeuren voor uw apparaat configureren vanaf het apparaatdashboard, dat toegankelijk is via de AEM-ontwerpinstantie.

1. Navigeer aan het apparatendashboard van uw project, bijvoorbeeld, ***Project van de Test*** > ***Apparaten***.

   Klik **Apparaten** en **Manager van het Apparaat** van de actiebar.

   ![ chlimage_1-66 ](assets/chlimage_1-66.png)

1. Klik op het apparaat zodat u het dashboard van het apparaat kunt openen.

   ![ chlimage_1-67 ](assets/chlimage_1-67.png)

1. Controleer het **paneel van VOORKEUREN**. U kunt **Admin UI** en **Schakelaar van het Kanaal** voor uw speler van deze twee opties toelaten of onbruikbaar maken.

   ![ chlimage_1-68 ](assets/chlimage_1-68.png)

### De interface van Admin {#the-admin-ui}

Het toelaten van **Admin UI** van het voorkeurenpaneel staat de gebruiker toe om de adminmontages van de Speler van Screens te openen. Als u deze optie uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de interface Admin niet openen vanuit de speler.

Als u de Admin UI van de Speler van de Screens wilt bekijken, duw op de hoogste-linkerhoek om het Admin menu, op uw aanraking-toegelaten Speler van de AEM Screens te openen, of door een muis te gebruiken. De informatie wordt weergegeven nadat de registratie is voltooid en de kanalen zijn geladen.

>[!NOTE]
>
>U kunt ook de uptime van de AEM Screens Player-app weergeven om de status van de app te controleren.

![ chlimage_1-3 ](assets/chlimage_1-3.gif)

#### Toegang tot de Opties van het Menu van de Configuratie {#configuration-options}

U kunt uw configuraties bijwerken als u de **optie van de Configuratie** van het zijmenu klikt, zoals aangetoond in het hieronder cijfer:

![ screen_shot_2018-10-15at101257am ](assets/screen_shot_2018-10-15at101257am.png)

In het menu Configuratie kunt u de volgende instellingen wijzigen:

* Het terugstellen **Ingebouwde programmatuur**, **Voorkeur**, of **aan Factory** van deze dialoogdoos.

* Specificeer het aantal maximumlogboekdossiers die u voor een Speler van AEM Screens in **Max Nr wilt houden. van logboekdossiers om** te houden.

* Laat toe of maak het **Menu Admin**, **Schakelaar van het Kanaal**, en **Activiteit UI** voor de Speler van Screens onbruikbaar.

  Als de **Activiteit UI** van het **menu van de Configuratie** wordt toegelaten, toont de Speler van AEM Screens de *berichten van de speleractiviteit* in de hoogste rechterhoek van de speler, zoals aangetoond in het hieronder cijfer.

  ![afbeelding](/help/user-guide/assets/activity_ui.png)

>[!NOTE]
>
>De **optie van de Ingebouwde programmatuur van de Update** werkt slechts op Cordova, zoals spelers Android™.

>[!NOTE]
>
>Men adviseert dat **Admin UI** in de Plaatsingen van de Productie wordt onbruikbaar gemaakt.

#### Opties voor het menu-cachegeheugen voor inhoud openen {#content-cache-options}

U kunt cache voor kanalen en toepassingen wissen via de beheerinterface in AEM Screens Player.

Klik het **Geheime voorgeheugen van de Inhoud** van de zijspoorstaaf zodat kunt u het geheime voorgeheugen bijwerken.

![ screen_shot_2018-10-15at105717am ](assets/screen_shot_2018-10-15at105717am.png)

### De kanaalschakelaar {#the-channel-switcher}

Het toelaten van de **Schakelaar van het Kanaal** van het voorkeurenpaneel laat de gebruiker de montages van de kanaalselectie van de Speler van Screens openen.

Als u deze optie uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de kanaalvoorkeuren niet besturen vanuit Screens Player.

U kunt instellingen voor uw kanaal wijzigen en beheren vanuit uw Screens Player.

Als u de kanaalschakelaar van de speler wilt weergeven, drukt u lang op de linkerbenedenhoek om de kanaalschakelaar te openen die het schakelen tussen kanalen en andere functies toestaat.

![ chlimage_1-69 ](assets/chlimage_1-69.png)

>[!NOTE]
>
>U kunt het beheermenu en de kanaalschakeloptie voor de speler ook in- of uitschakelen via de Screens Player.
>
>(Zie *Voorkeur van de Verandering van de Speler van Screens* zoals vermeld in de hieronder sectie).

### Voorkeuren beheren vanuit AEM Screens Player

U kunt ook de instellingen voor de interface van Admin en de kanaalschakelaar van de speler zelf wijzigen.

Voorkeuren wijzigen van uw speler:

1. Druk op de linkerbovenhoek van het inactieve kanaal lang om het beheerpaneel te openen.
1. Navigeer aan **Configuratie** van het linkeractiemenu.
1. Laat of maak de configuratie voor **Admin UI** of **Schakelaar van het Kanaal** toe onbruikbaar.

![ screen_shot_2018-10-15at101257am-1 ](assets/screen_shot_2018-10-15at101257am-1.png)

## Problemen met AEM Screens Player oplossen

U kunt verschillende problemen met de AEM Screens Player (hardware en software) oplossen:

| **Kwesties** | **Aanbevelingen** |
|---|---|
| Player-opslag is vol | Overbodige bestanden verwijderen |
| Speler verloren netwerk | Kat-5 of kat-6 van het gebruik kabel. Voor wifi, verminder de afstand van de router aan het spelerapparaat |
| AEM Screens Player vastgelopen | Het wordt aanbevolen een waakhond-app te hebben die ervoor zorgt dat de AEM Screens Player altijd wordt uitgevoerd |
| AEM Screens Player heeft instellingen verloren | Verbinding met AEM-server controleren |
| AEM Screens Player wordt niet automatisch gestart na opnieuw opstarten of opnieuw opstarten | Start van OS-map of initialisatieprocedure controleren |
| AEM Screens Player geeft onjuiste of oude inhoud weer | Netwerkverbinding controleren |

### Updates voor AEM Screens Player

Er zijn twee typen updates voor de AEM Screens Player:

| **Methode** | **Details** | **als Verre** | **Geautomatiseerd** | **0 Downtime** |
|---|---|---|---|---|
| Firmware-update | Toegepast op bestaande geïnstalleerde Players door middel van ver bevel. Na de update wordt de speler automatisch opnieuw geladen met de bestaande inhoud. | Ja | Aangepast | Bijna - 1-3 seconden |
| Updates van Flash Player | Een nieuw uitvoerbaar die op de Speler wordt opgesteld. Deze functionaliteit vereist u om het nieuwe binaire getal op afstand op de speler te kopiëren, de huidige uitvoering te stoppen en de nieuwe versie te starten. Het kan nodig zijn de voorgeladen pakketten opnieuw te downloaden. | Ja (via externe shell) | Aangepast | Nee |

## Richtlijnen voor hardwareselectie voor afspeelapparaat {#hardware-selection-guidelines-for-player-device}

In het volgende gedeelte vindt u de richtlijnen voor hardwareselectie voor een Screens-project:

* Bron altijd ***Commerciële*** of ***Industriële*** componenten van de Grade voor zowel de speler van PC als Comité van de Vertoning of Projector.

* Neem altijd contact op met leveranciers die de markt voor digitale handtekeningen bedienen.
* Houd altijd rekening met omgevingsfactoren, zoals omgevingstemperatuur en relatieve vochtigheid.
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
   <td>DVI <br /> Ethernet / Wireless <br /> 2x USB</td>
   <td>
    <ul>
     <li>Standaard herhalen op volledig scherm <br /> </li>
     <li>Dagverdeling</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Standaard</td>
   <td>Quad Core, Intel® Core™ i5 processor</td>
   <td><p>8 GB geheugen</p> <p>4 MB cache</p> </td>
   <td>128 GB</td>
   <td>onBoard</td>
   <td>3840x2160 (<code>4K</code>)</td>
   <td>DVI, HDMI <br /> Ethernet/Wireless, <br /> 2x USB</td>
   <td>
    <ul>
     <li>Single Source Dynamic Content</li>
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
   <td>3840x2160 (<code>4K</code>)</td>
   <td>DVI, HDMI <br /> Ethernet/Wireless, <br /> 4x USB</td>
   <td>
    <ul>
     <li>4 of meer inhoudszones, gelijktijdige videoweergave</li>
     <li>Interactief meerdere pagina's</li>
     <li>Multi-Source Data Triggers</li>
    </ul> </td>
  </tr>
 </tbody>
</table>
