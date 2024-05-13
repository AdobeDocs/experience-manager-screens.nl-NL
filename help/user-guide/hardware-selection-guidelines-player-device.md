---
title: Richtlijnen voor hardwareselectie voor afspeelapparaten
description: Lees meer over de richtlijnen voor hardwareselectie voor AEM Screens Player-apparaten.
source-git-commit: f7653d8b386c02f510eb7a770cf3cdc22c41a5fb
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# Richtlijnen voor hardwareselectie voor afspeelapparaat {#hardware-selection}

In de volgende sectie vindt u de richtlijnen voor het selecteren van hardware voor een AEM Screens Player.

## Belangrijke overwegingen {#important-considerations}

* Altijd bron ***Commercieel*** of ***Industrieel*** Graducomponenten voor zowel de speler van PC als het Comité van de Vertoning of Projector.

* Neem altijd contact op met leveranciers die de markt voor digitale handtekeningen bedienen.
* Houd altijd rekening met omgevingsfactoren zoals omgevingstemperatuur en relatieve vochtigheid.
* Controleer altijd de stroomvereisten en de conditionering van het energieverbruik.
* Controleer zorgvuldig de prestatiebehoeften en I/O-poorten die vereist zijn voor de toepassing.

## Hardwareconfiguraties {#hardware-configurations}

De volgende tabel geeft een overzicht van de hardwareconfiguraties met standaardgebruiksscenario&#39;s voor een AEM Screens-project:

<table>
 <tbody>
  <tr>
   <tr>
   <td><strong>Configuratie van speler</strong></td>
   <td><strong>Processor</strong></td>
   <td><strong>Geheugen</strong></td>
   <td><strong>OpslagSSD</strong></td>
   <td><strong>GPU</strong></td>
   <td><strong>Weergave</strong></td>
   <td><strong>I/O</strong></td>
   <td><strong>Gebruiksscenario's</strong></td>
  </tr>
  <tr>
   <td>Basis</td>
   <td>Dual Core, i3 of quad core Intel® Atom processor op instapniveau</td>
   <td><p>4 GB geheugen</p> <p>2 MB cache</p> </td>
   <td><p>*ChromeOS 32 GB</p> <p>*Windows 128 GB</p> </td>
   <td>onBoard</td>
   <td>1920 x 1080</td>
   <td>DVI<br /> Ethernet/Wireless,<br /> 2x USB</td>
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
   <td>3840x2160 (<code>4K</code>)</td>
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
   <td>3840x2160 (<code>4K</code>)</td>
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
