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
translation-type: tm+mt
source-git-commit: 428e1dbaa1a252d2aa9bcbb02264a0076b95291b

---


# Werken met AEM Screens Player {#working-with-aem-screens-player}

U kunt de inhoud van het kanaal en andere instellingen beheren in AEM Screens Player.

>[!NOTE]
>
>Druk op ***Ctrl+Cmd+F*** om de modus Volledig scherm af te sluiten voor OS X AEM Screens Player.

Nadat u een kanaal aan een weergave hebt toegewezen, wordt de inhoud weergegeven in de AEM Screens Player. U kunt instellingen voor de speler configureren met de voorkeuren voor de interface voor beheerders (van het dashboard) of met de speler zelf.

## Het dashboard van het Apparaat gebruiken {#using-the-device-dashboard}

U kunt voorkeuren voor uw apparaat configureren vanaf het apparaatdashboard, dat toegankelijk is via de AEM-ontwerpinstantie.

1. Navigeer naar het apparaatdashboard van uw project, bijvoorbeeld ***Test Project*** —> ***Apparaten***.

   Selecteer **Apparaten** en **Apparaatbeheer** in de actiebalk.

   ![chlimage_1-66](assets/chlimage_1-66.png)

1. Klik op het apparaat om het dashboard van het apparaat te openen.

   ![chlimage_1-67](assets/chlimage_1-67.png)

1. Controleer het deelvenster **VOORKEUREN** . U kunt de **Admin UI** en de Schakelaar **van het** Kanaal voor uw speler van deze twee opties toelaten/onbruikbaar maken.

   ![chlimage_1-68](assets/chlimage_1-68.png)

### De interface van Admin {#the-admin-ui}

Als u de **beheerdersinterface** inschakelt vanuit het voorkeurenvenster, kan de gebruiker de beheerinstellingen openen vanuit de schermspeler. Bovendien, als u deze optie van het apparatendashboard onbruikbaar maakt, kan de gebruiker niet admin UI van de speler openen.

Als u de interface voor het beheer van de schermspeler wilt weergeven, drukt u op de linkerbovenhoek om het menu Admin te openen, op de AEM Screens player met aanraakbediening of met een muis. Er wordt informatie weergegeven nadat de registratie is voltooid en de kanalen zijn geladen.

>[!NOTE]
>
>Bovendien kunt u de uptime van de AEM Screens Player-app weergeven om de status van de app te controleren.

![chlimage_1-3](assets/chlimage_1-3.gif)

Als u de optie **Configuratie** in het zijmenu selecteert, kunt u **Ingebouwde programmatuur**, **Voorkeur**, of **aan Factory** van dit dialoogvakje ook terugstellen.

Bovendien kunt u het maximale aantal logbestanden opgeven dat voor een AEM-schermspeler moet worden behouden in **Max. aantal. van logbestanden die moeten worden bewaard**. Zie de onderstaande schermafbeelding voor meer informatie.

>[!NOTE]
>
>De optie Firmware **** bijwerken werkt alleen op de cordova, zoals Android-spelers.

![screen_shot_2018-10-15at101257am](assets/screen_shot_2018-10-15at101257am.png)

>[!NOTE]
>
>Aanbevolen wordt om de **Admin UI** in de Plaatsingen van de Productie onbruikbaar te maken.

U kunt de cache voor kanalen en toepassingen wissen via de interface van Admin in AEM Screens Player.

Selecteer de **inhoudscache** in de zijbalk om de cache bij te werken.

![screen_shot_2018-10-15at105717am](assets/screen_shot_2018-10-15at105717am.png)

### De kanaalschakelaar {#the-channel-switcher}

Als u de **Kanaalschakelaar** inschakelt vanuit het voorkeurenvenster, kan de gebruiker de kanaalselectie/instellingen openen vanuit de schermspeler.

Als u deze optie ook uitschakelt vanaf het dashboard van het apparaat, kan de gebruiker de kanaalvoorkeuren niet besturen via de schermspeler.

U kunt instellingen voor uw kanaal wijzigen en beheren vanuit uw schermspeler.

Om de kanaalschakelaar van de speler te bekijken, duw op de lagere linkerhoek om de kanaalschakelaar te openen die omschakelingskanalen en andere eigenschappen toestaat.

![chlimage_1-69](assets/chlimage_1-69.png)

>[!NOTE]
>
>U kunt ook het beheermenu en de kanaalschakelaar voor de speler in- of uitschakelen via de schermspeler.
>
>(Zie Voorkeuren *wijzigen van schermspeler* , zoals vermeld in de onderstaande sectie).

### Voorkeuren beheren vanuit AEM Screens Player {#managing-preferences-from-the-aem-screens-player}

U kunt ook de instellingen voor de interface van de beheerder en de kanaalschakelaar wijzigen vanuit de speler zelf.

Ga als volgt te werk om de voorkeuren van uw speler te wijzigen:

1. Druk op de linkerbovenhoek van het inactieve kanaal om het beheerpaneel te openen.
1. Navigeer aan **Configuratie** van het linkeractiemenu.
1. Configuratie voor **Admin UI** of **Kanaalswitch** in-/uitschakelen.

![screen_shot_2018-10-15at101257am-1](assets/screen_shot_2018-10-15at101257am-1.png)

## Problemen met AEM Screens Player oplossen {#troubleshooting-aem-screens-player}

U kunt verschillende problemen met AEM Screens Player (hardware en software) oplossen:

| **Problemen** | **Aanbevelingen** |
|---|---|
| Player-opslag is vol | Overbodige bestanden verwijderen |
| Speler verloren netwerk | Kat-5/kat-6 van het gebruik kabel. Voor wifi, verminder de afstand van de router aan het spelerapparaat |
| AEM Screens Player vastgelopen | Het wordt aanbevolen een waakhond-app te hebben die ervoor zorgt dat de AEM Screens Player altijd wordt uitgevoerd |
| Instellingen voor AEM-schermspeler zijn verloren | Verbinding met AEM-server controleren |
| AEM Screens Player start niet automatisch nadat Player opnieuw is opgestart/opnieuw is opgestart | Start van OS-map of initialisatieprocedure controleren |
| AEM Screenspeler toont onjuiste/oude inhoud | Netwerkverbinding controleren |

### Updates voor AEM Screens Player {#updates-for-aem-screens-player}

Er zijn twee typen updates voor de AEM Screens Player:

| **Methode** | **Details** | **via extern** | **Geautomatiseerd** | **0 Downtime** |
|---|---|---|---|---|
| Firmware-update | Toegepast op bestaande geïnstalleerde Players via verre bevel. Na de update wordt de speler automatisch opnieuw geladen met de bestaande inhoud. | Ja | Aangepast | Bijna - 1-3 seconden |
| Updates van Flash Player | Dit is een nieuw uitvoerbaar die op de Speler moet worden opgesteld. Dit vereist om nieuw binair getal op afstand op de speler te kopiëren en de huidige versie te stoppen en de nieuwe versie te starten. Hiervoor moet u mogelijk de voorgeladen pakketten opnieuw downloaden. | Ja (via externe shell) | Aangepast | Nee |

## Richtlijnen voor hardwareselectie voor afspeelapparaat {#hardware-selection-guidelines-for-player-device}

In de volgende sectie vindt u de richtlijnen voor hardwareselectie voor een rasterproject:

* Bron altijd ***commerciële*** of ***industriële*** componenten voor zowel de speler van PC als van het Comité van de Vertoning of Projector.

* Neem altijd contact op met leveranciers die de markt voor digitale handtekeningen bedienen.
* Houd altijd rekening met omgevingsfactoren zoals omgevingstemperatuur en relatieve vochtigheid.
* Controleer altijd de stroomvereisten en de conditionering van het energieverbruik.
* Controleer zorgvuldig de prestatiebehoeften en I/O-poorten die vereist zijn voor de toepassing.

De volgende tabel geeft een overzicht van de hardwareconfiguraties met standaardgebruiksscenario&#39;s voor een AEM-schermproject:

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
   <td>DVI,<br /> Ethernet/Wireless,<br /> 2 x USB</td>
   <td>
    <ul>
     <li>Standaardherhaling op volledig scherm<br /> </li>
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
   <td>DVI, HDMI<br /> Ethernet/Wireless,<br /> 2 x USB</td>
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
   <td>DVI, HDMI<br /> Ethernet/Wireless,<br /> 4x USB</td>
   <td>
    <ul>
     <li>4 of meer inhoudszones, gelijktijdig afspelen van video</li>
     <li>Interactief meerdere pagina's</li>
     <li>Multi-Source Data Triggers</li>
    </ul> </td>
  </tr>
 </tbody>
</table>