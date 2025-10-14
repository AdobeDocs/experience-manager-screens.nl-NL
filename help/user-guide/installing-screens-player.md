---
title: Screens Player installeren
description: Leer hoe u een AEM Screens Player correct installeert.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# AEM Screens Player installeren {#installing-player}

In deze pagina wordt beschreven hoe u AEM Screens Player kunt installeren.

## Beschikbare Screens Player {#available-players}

De AEM Screens Player is beschikbaar voor Android™, Chrome OS en Windows.

Om **Speler van AEM Screens** te downloaden, bezoek [&#x200B; AEM 6.5 de Downloads van de Speler &#x200B;](https://download.macromedia.com/screens/) pagina.

>[!NOTE]
>
>Nadat u de recentste Speler (*.exe*) downloadt, volg de stappen op de speler zodat kunt u de ad hoc installatie voltooien:
>
>1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
>1. Navigeer aan **Configuratie** van het linkeractiemenu en ga het plaatsadres van de instantie van AEM in **Server** in en klik **sparen**.
>1. Klik de **verbinding van de Registratie** van het linkeractiemenu en de stappen hieronder om het proces van de apparatenregistratie te voltooien.

## Standaardafspeelcontrole {#playback-monitoring}

De speler rapporteert verschillende afspeelmetriek bij elke `ping` die standaard 30 seconden bedraagt. Op basis van deze maatstaven kan het verschillende randgevallen detecteren, zoals geplakte ervaring, een leeg scherm en planningsproblemen. Het laat ons kwesties op het apparaat begrijpen en problemen oplossen, en bespoedigt zo een onderzoek en correctieve maatregelen voor u.

Met de standaardafspeelcontrole in een AEM Screens Player kunt u het volgende doen:

* Op afstand controleren of een speler de inhoud correct afspeelt.

* Verbeter reactiviteit aan lege schermen of gebroken ervaringen op het gebied.

* Vermindert het risico om een gebroken ervaring aan het eind - gebruiker te tonen.

### Eigenschappen {#understand-properties}

De volgende eigenschappen worden in elke `ping` opgenomen:

| Eigenschap | Beschrijving |
|---|---|
| id {string} | de speler-id |
| activeChannel {string} | momenteel het kanaalpad afspelen, of null als er niets is gepland |
| activeElements {string} | door komma&#39;s gescheiden tekenreeksen, die momenteel zichtbare elementen zijn in alle kanalen van de afspeelvolgorde (meerdere lagen hebben een lay-out met meerdere zones) |
| isDefaultContent {boolean} | true als het afspeelkanaal wordt beschouwd als een standaard- of fallback-kanaal (heeft dus prioriteit 1 en geen planning) |
| hasContentChanged {boolean} | true als de inhoud in de laatste 5 minuten is gewijzigd, anders false |
| lastContentChange {string} | tijdstempel van de laatste inhoudswijziging |

>[!NOTE]
>
>Naar keuze, kan een geavanceerdere bezit van de spelervoorkeur (Enable Playback Controle) worden toegelaten en dat is:
>
>| Eigenschap | Beschrijving |
>|---|---|
>| isContentRendering {boolean} | true als de GPU kan bevestigen dat de werkelijke inhoud wordt afgespeeld (op basis van pixelanalyse) |

### Beperkingen {#limitations}

Hieronder volgt een aantal beperkingen voor elementaire afspeelcontrole:

* De speler rapporteert zijn eigen playbackstaat aan de server, zodat vereist het een actieve verbinding.

* De eigenschap `isContentRendering` die de GPU controleert, is veel bronintensiever om standaard te kunnen worden ingeschakeld en vereist expliciete opt-in bij de voorkeuren voor spelers. Adobe raadt u aan deze functie niet te gebruiken met video&#39;s in productie.

* Deze eigenschap wordt slechts gesteund voor opeenvolgingskanalen en behandelt nog niet de interactieve kanalen (SPA) gebruiksgeval.

* De cijfers zijn nog niet volledig beschikbaar voor klanten, maar Adobe werkt aan het mogelijk maken van dashboardachtige rapportage- en waarschuwingsmechanismen.

### Overige bronnen {#additional-resources}

Zie de volgende onderwerpen voor diepgaande informatie:

* Om de Speler van Android™ te downloaden, bezoek **Google Play**. Om over het uitvoeren van Android™ Watchdog te leren, zie [&#x200B; het Uitvoeren van de speler van Android™ &#x200B;](implementing-android-player.md).

* Om de Speler van Chrome OS uit te voeren, zie [&#x200B; de Console van het Beheer van Chrome &#x200B;](implementing-chrome-os-player.md) voor meer informatie.

* Om de Speler van AEM Screens Windows te vormen, zie [&#x200B; Uitvoerend de Speler van Vensters van Vensters &#x200B;](implementing-windows-player.md).
