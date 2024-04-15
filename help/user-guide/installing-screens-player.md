---
title: Schermspeler installeren
description: Leer hoe u een AEM Screens Player correct installeert.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---

# AEM Screens Player installeren {#installing-player}

In deze pagina wordt beschreven hoe u AEM Screens Player kunt installeren.

## Beschikbare schermspeler {#available-players}

De AEM Screens-speler is beschikbaar voor Android™, Chrome OS en Windows.

Downloaden **AEM Screens Player**, bezoek de [AEM 6.5 Player-downloads](https://download.macromedia.com/screens/) pagina.

>[!NOTE]
>
>Nadat u de nieuwste speler (*.exe*), voert u de stappen op de speler uit, zodat u de ad-hocinstallatie kunt voltooien:
>
>1. Druk op de linkerbovenhoek om het beheerpaneel te openen.
>1. Navigeren naar **Configuratie** in het linkeractiemenu en voer het locatieadres van de AEM in **Server** en selecteert u **Opslaan**.
>1. Selecteren **Registratie** Klik op de koppeling in het menu met de linkeractie en voer de onderstaande stappen uit om het registratieproces voor apparaten te voltooien.

## Standaardafspeelcontrole {#playback-monitoring}

De speler rapporteert verschillende afspeelmetriek voor elke speler `ping` dat is standaard 30 seconden. Op basis van deze maatstaven kan het verschillende randgevallen detecteren, zoals geplakte ervaring, een leeg scherm en planningsproblemen. Dit laat ons kwesties op het apparaat begrijpen en problemen oplossen, en bespoedigt zo een onderzoek en correctieve maatregelen met u.

Met de standaardafspeelcontrole in een AEM Screens-speler kunt u het volgende doen:

* Op afstand controleren of een speler de inhoud correct afspeelt.

* Verbeter reactiviteit aan lege schermen of gebroken ervaringen op het gebied.

* Vermindert het risico om een gebroken ervaring aan het eind - gebruiker te tonen.

### Eigenschappen {#understand-properties}

De volgende eigenschappen worden in elk `ping`:

| Eigenschap | Beschrijving |
|---|---|
| id {string} | de speler-id |
| activeChannel {string} | momenteel het kanaalpad afspelen, of null als er niets is gepland |
| activeElements {string} | door komma&#39;s gescheiden tekenreeksen, die momenteel zichtbare elementen zijn in alle kanalen van de afspeelvolgorde (meerdere lagen hebben een lay-out met meerdere zones) |
| isDefaultContent {boolean} | true als het afspeelkanaal wordt beschouwd als een standaard- of fallback-kanaal (heeft dus prioriteit 1 en geen planning) |
| hasContentChanged {boolean} | true als de inhoud in de laatste 5 minuten is gewijzigd, anders false |
| lastContentChange {string} | tijdstempel van de laatste inhoudswijziging |

>[!NOTE]
>Naar keuze, kan een geavanceerdere bezit van de spelervoorkeur (Enable Playback Controle) worden toegelaten en dat is:
>
>| Eigenschap | Beschrijving |
>|---|---|
>| isContentRendering {boolean} | true als de GPU kan bevestigen dat de werkelijke inhoud wordt afgespeeld (op basis van pixelanalyse) |

### Beperkingen {#limitations}

Hieronder worden enkele beperkingen weergegeven voor elementaire afspeelcontrole:

* De speler rapporteert zijn eigen playbackstaat aan de server, zodat vereist het een actieve verbinding.

* De `isContentRendering` eigenschap die de GPU controleert, is te hulpbronnenintensief om standaard te kunnen worden ingeschakeld en vereist expliciete opt-in bij de voorkeuren voor spelers. Adobe raadt u aan deze functie niet te gebruiken met video&#39;s in productie.

* Deze functie wordt alleen ondersteund voor reekskanalen en heeft nog geen betrekking op het gebruik van interactieve kanalen (SPA).

* De metriek worden nog niet volledig blootgesteld aan klanten, Adobe werkt aan het toelaten van dashboard-als rapporterings en alarmeringsmechanismen spoedig.

### Overige bronnen {#additional-resources}

Zie de volgende onderwerpen voor een diepgaande informatie:

* Ga voor het downloaden van Android™ Player naar **Google Play**. Ga voor meer informatie over het implementeren van Android™ Watchdog naar [Android™-speler implementeren](implementing-android-player.md).

* Als u Chrome OS Player wilt implementeren, raadpleegt u [Chrome Management Console](implementing-chrome-os-player.md) voor meer informatie .

* Voor het configureren van AEM Screens Windows Player raadpleegt u [Windows Player implementeren](implementing-windows-player.md).
