---
title: Cloud Player implementeren
description: Leer meer over de implementatie van de Cloud Player.
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 184168f5-6070-4c33-a2c5-5429061dac75
source-git-commit: 6720e20f5254e869bde814bd167730e426d0f8fe
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---

# Cloud Player implementeren {#implementing-cloud-player}

AEM Screens heeft traditioneel verschillende native spelertoepassingen aangeboden voor verschillende platforms, waaronder ChromeOS, Windows, Android™ en `Tizen`. In reactie op de veranderende behoeften van gebruikers introduceerde Adobe echter een innovatieve oplossing, de AEM Screens Cloud Player.

De Cloud Player is een belangrijke afwijking van eerdere native toepassingen van Adobe. Het is een Progressieve Web App (PWA), die op een server wordt ontvangen. Deze transformatieve aanpak stelt klanten in staat een platformonafhankelijke speler te gebruiken die rechtstreeks in een webbrowser werkt.

Toegang tot de Cloud Player is net zo eenvoudig als bezoeken `https://player.adobescreens.com`. Gebruikers kunnen de software op hun apparaat installeren, ongeacht het platform, en genieten van een naadloze digitale handtekening. De compatibiliteit van de Cloud Player hangt af van de aanwezigheid van een moderne browser met ondersteuning voor PWA, waardoor consistente prestaties op verschillende apparaten worden gegarandeerd. Neem afscheid van handmatige updates en hallo tegenover een speler die automatisch oplossingen en functies levert, zodat u altijd de nieuwste mogelijkheden binnen handbereik hebt. Deze verschuiving naar een op PWA gebaseerde Cloud Player markeert een opwindende evolutie in het aanbod voor digitale handtekeningen van de Adobe, waardoor het toegankelijker, veelzijdiger en gebruiksvriendelijker wordt dan ooit tevoren.

In deze sectie wordt beschreven hoe u de Cloud Player implementeert.

>[!NOTE]
>
>De compatibiliteit van Cloud Player vereist een moderne browser met ondersteuning voor PWA om consistente prestaties op verschillende apparaten te garanderen.

## Cloud Player installeren {#installing-cloud-player}

De installatie van Cloud Player kan op verschillende platforms verschillen. In het algemeen kan elk platform met een moderne browser de toepassing van de cloudspeler uitvoeren door de volgende stappen uit te voeren:

1. Open browser en ga in [URL van cloudspeler](https://player.adobescreens.com/content/dam/universal-player/firmware.html) in de adresbalk.
1. De browser controleert of de Cloud Player kan worden geïnstalleerd en geeft vervolgens een installatiepictogram weer op de adresbalk.

   ![afbeelding](/help/user-guide/assets/cloud-player-install.png)

1. Klik op het installatiepictogram en de installatieknop in het bevestigingsdialoogvenster. Cloud Player wordt als zelfstandige toepassing op uw apparaat geïnstalleerd en kan met een pictogram worden gestart.

>[!NOTE]
>
>### Installatieoptie voor Cloud Player {#cloud-player-install-option}
>
1. De installatieoptie voor een PWA wordt ook wel &quot;Toevoegen aan beginscherm&quot; of &quot;A2HS&quot; genoemd. Ondersteuning voor het installeren van PWA via het web varieert per browser en per platform.
1. Elke browser heeft verschillende criteria om te controleren of de PWA-app kan worden geïnstalleerd of niet. Over het algemeen kan de browser het volgende controleren (meer details hier):
>
* Als de toepassing een manifest-jsdossier met minimale vereiste sleutels voor het installeren van app op het platform heeft, namelijk naam, pictogrammen, start_url, vertoning
* Als de toepassing een dossier van de de dienstarbeider met een haal gebeurtenisluisteraar heeft
* De app moet via https worden verzonden
>
1. De installatieoptie is mogelijk op verschillende locaties zichtbaar in verschillende browsers en apparaattypen. Sommige browsers verbergen het installatiepictogram in de optiemenubalk.

## Cloud Player voor bulkprovisioning {#bulk-provisioning}

Een bulkprovisioning van de cloudspeler uitvoeren op meerdere apparaten:

1. Kies een oplossing MDM die het runnen van browser met een URL op de wijze van Kiosk steunt.
1. U kunt dezelfde configuraties op alle apparaten toepassen door de volgende stappen uit te voeren:

   1. Host config.json op een server dusdanig dat het zoals toegankelijk is: `https://<config_server_host>/config.json`
   1. Als u de cloudspeler wilt installeren en de gehoste configuraties wilt toepassen, gebruikt u de URL van de cloudspeler, zoals: `https://player.adobescreens.com?playerConfigAddress=https://<config_server_host>`
   1. De toepassing van de Speler van de Wolk zoekt config.json bij de wortel &lt;config_server_host>, dan ontleedt config.json om de douaneconfiguraties te krijgen en die configuraties toe te passen.
   1. Deze configuraties worden toegepast bij elke herbelasting van de speler.

## Bulkprovisioning op Chrome OS {#bulk-provisioning-chrome}

Meer informatie over bulkprovisioning op Chrome OS. Zie [Cloud Player installeren op Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/chromeos-install-cloud-player). &lt;!-- `https://www.adobe.com/go/aem_screens_cloud_player_en` >

## Configuratie vereist op AEM instanties {#bulk-provisioning-config-aem}

Op basis van het type van de AEM-instantie klikt u op een van de volgende hulplijnen om CORS b/w AEM en Cloud Player in te schakelen:

* [AEM op locatie/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams) <!-- `https://www.adobe.com/go/aem_screens_cors_ams_en` -->

* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs) <!-- `https://www.adobe.com/go/aem_screens_cors_aemaacs_en` -->


>[!NOTE]
>
## Veroudering van Chrome-toepassingen door Google
>
1. Chrome-apps op Chrome OS-hardware:
>
Google heeft Chrome Apps actief afgekeurd ten gunste van PWA apps, met een geplande migratie tot januari 2025. Daarom werkt de AEM Screens Player-app op Chrome OS niet meer op basis van de gedeelde tijdlijn. Adobe dringt er bij gebruikers die momenteel Chrome Player in productie gebruiken op aan om de overgang naar de Screens Cloud Player te plannen.
>
1. Chrome Extension Player op Mac, Windows en Linux®:
>
Vanwege het afgekeuringsproces van Google, vanaf Google Chrome versie 114, wordt de Screens Chrome Extension Player niet meer ondersteund. Adobe raadt u aan over te schakelen naar de schermcloudspeler voor al uw ontwikkelings- en testvereisten.

## Offlineondersteuning voor externe inhoud ophalen {#offline-support}

In verschillende gebruiksscenario&#39;s kunnen kanalen vereisen dat inhoud wordt opgehaald uit een externe bron (bijvoorbeeld weerswidgets of Commerce geïntegreerde toepassingen voor één pagina) die niet inherent offline ondersteuning kunnen bieden. Om offline functionaliteit voor deze specifieke gebruiksgevallen in te schakelen, biedt Cloud Player ondersteuning voor aangepaste kopteksten.

Cloud Player past een Network First-cachemethode toe, wat betekent dat het probeert inhoud van het netwerk op te halen (en vervolgens de cache met de nieuwste versie bij), en dat het terugvalt op cacheinhoud indien beschikbaar. Als u offline ondersteuning voor het ophalen van dergelijke inhoud wilt implementeren, moet de aangepaste header in de aanvraag worden opgenomen. Dan, wordt het verzoek met de douanekop in het voorgeheugen ondergebracht op de speler, die off-line toegang tot de inhoud terwijl het handhaven van de het geheime voorgeheugenstrategie van het Netwerk Eerste vergemakkelijkt.

```
// Sample fetch request with the 'X-Cache-Strategy' header
fetch(externalUrl, {
  headers: {
    'X-Cache-Strategy': 'external-cache'
  }
})
  .then(response => {
    // Handle the response, which may be from the network or cache.
    // Your logic here.
  })
  .catch(error => {
    // Handle any errors that may occur during the fetch operation.
    // Your error handling logic here.
  }); 
```

## Feedback

Adobe geeft de waarde van je feedback aan. Deel je gedachten met ons via deze [formulier](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4TFE0b_GjstOj6I1uGs9vLpURVdWWklQQTZZRTFVNEhRVlBWWldMWlJXOC4u).
