---
title: Cloud Player implementeren
seo-title: Implementing Cloud Player
description: Volg deze pagina voor meer informatie over de implementatie van Cloud Player.
seo-description: Follow  this page to learn about the implementation of the Cloud Player.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 184168f5-6070-4c33-a2c5-5429061dac75
source-git-commit: 214da80530b472b67a30b575eb8ab11486d44692
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---

# Cloud Player implementeren  {#implementing-cloud-player}

AEM Screens heeft traditioneel verschillende native spelertoepassingen aangeboden voor verschillende platforms, waaronder ChromeOS, Windows, Android &amp; Tizen. In reactie op de veranderende behoeften van onze gebruikers hebben we echter een innovatieve oplossing geïntroduceerd, de AEM Screens Cloud Player.
De Cloud Player is een belangrijke afwijking van onze eerdere native toepassingen. Het is een Progressieve Web App (PWA), die op een server wordt ontvangen. Deze transformatieve aanpak stelt onze klanten in staat een platformonafhankelijke speler te kiezen die rechtstreeks in een webbrowser wordt uitgevoerd.
Toegang tot de Cloud Player is net zo eenvoudig als het bezoeken van https://player.adobescreens.com. Gebruikers kunnen de software op hun apparaat installeren, ongeacht het platform, en genieten van een naadloze digitale handtekening. De compatibiliteit van de Cloud Player hangt af van de aanwezigheid van een moderne browser met ondersteuning voor PWA, waardoor consistente prestaties op verschillende apparaten worden gegarandeerd. Neem afscheid van handmatige updates en hallo tegenover een speler die automatisch oplossingen en functies levert, zodat u altijd de nieuwste mogelijkheden binnen handbereik hebt. Deze verschuiving naar een op PWA gebaseerde Cloud Player markeert een opwindende evolutie in ons aanbod voor digitale handtekeningen, waardoor het toegankelijker, veelzijdiger en gebruiksvriendelijker wordt dan ooit tevoren.
In deze sectie wordt beschreven hoe u de Cloud Player implementeert.


>[!NOTE]
>
>De compatibiliteit van Cloud Player vereist een moderne browser met ondersteuning voor PWA om consistente prestaties op verschillende apparaten te garanderen.

## Cloud Player installeren {#installing-cloud-player}

De installatie van Cloud Player kan op verschillende platforms verschillen. In het algemeen kan elk platform met een moderne browser de toepassing van de cloudspeler uitvoeren door de volgende stappen uit te voeren:

1. Open browser en ga in [URL van cloudspeler](https://player.adobescreens.com) in de adresbalk.
1. De browser controleert of de cloudspeler kan worden geïnstalleerd en geeft vervolgens een installatiepictogram weer op de adresbalk.

   ![afbeelding](/help/user-guide/assets/cloud-player-install.png)

1. Klik op het installatiepictogram en de installatieknop in het bevestigingsdialoogvenster. Cloud Player wordt als zelfstandige toepassing op uw apparaat geïnstalleerd en kan met een pictogram worden gestart.

>[!NOTE]
>
>### Installatieoptie voor Cloud Player {#cloud-player-install-option}
>
1. De installatieoptie voor een PWA wordt ook wel &quot;Toevoegen aan beginscherm&quot; of &quot;A2HS&quot; genoemd.  Ondersteuning voor het installeren van PWA vanaf het web varieert per browser en per platform.
1. Elke browser heeft verschillende criteria om te controleren of de PWA-app kan worden geïnstalleerd of niet. Doorgaans controleert de browser het volgende (hier meer informatie):
* Als de toepassing een manifest-jsdossier met minimale vereiste sleutels voor het installeren van app op het platform heeft, d.w.z., naam, pictogrammen, start_url, vertoning
* Als de toepassing een dossier van de de dienstarbeider met een haal gebeurtenisluisteraar heeft.
* App moet via https worden verzonden.
1. De installatieoptie is mogelijk op verschillende locaties zichtbaar in verschillende browsers en apparaattypen. Het installatiepictogram wordt mogelijk verborgen in de optiebalk.

## Cloud Player voor bulkprovisioning {#bulk-provisioning}

Een bulkprovisioning van de cloudspeler uitvoeren op meerdere apparaten:

1. Kies een oplossing MDM die het runnen van browser met een URL op de wijze van Kiosk steunt.
1. U kunt dezelfde configuraties op alle apparaten toepassen door de volgende stappen uit te voeren:
   1. Host config.json op een server die toegankelijk is, zoals: https://&lt;config_server_host>/config.json
   1. Gebruik de URL van de cloudspeler zoals: https://player.adobescreens.com?playerConfigAddress=https:// als u de cloudspeler wilt installeren en de gehoste configuraties wilt toepassen&lt;config_server_host>
   1. De toepassing van de Speler van de Wolk zoekt config.json bij de wortel van &lt;config_server_host>, ontleedt config.json om de douaneconfiguraties te krijgen en die configuraties toe te passen.
   1. Deze configuraties worden toegepast bij elke nieuwe laadbewerking van de speler.

## Bulkprovisioning op Chrome OS {#bulk-provisioning-chrome}

Raadpleeg voor meer informatie over bulkprovisioning op Chrome OS: [Cloud Player installeren op Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.page/updates/cloud-player/guides/chromeos-install-cloud-player).

## Configuratie vereist op AEM instanties {#bulk-provisioning-config-aem}

Selecteer op basis van het type van de AEM-instantie een van de volgende hulplijnen om CORS b/w AEM &amp; cloudspeler in te schakelen:
* [AEM op locatie/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams)
* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs)

>[!NOTE]
>
>## Veroudering van Chrome-toepassingen door Google
>1. Chrome Apps on Chrome OS Hardware: 
>Google heeft Chrome Apps actief vervangen door PWA apps, met een geplande migratie tot januari 2025. Daarom werkt de AEM Screens Player-app op Chrome OS niet meer op basis van de gedeelde tijdlijn. We roepen onze klanten die momenteel Chrome Player in productie gebruiken op om te plannen voor de overgang naar de Screens Cloud Player.
>2. Chrome Extension Player op Mac, Windows en Linux: 
>vanwege Google-veroudering, vanaf Google Chrome versie 114, wordt de Screens Chrome Extension Player niet meer ondersteund. We raden u ten zeerste aan over te stappen op onze schermcloudspeler voor al uw ontwikkelings- en testvereisten.

## Offlineondersteuning voor externe inhoud ophalen {#offline-support}

In verschillende gebruiksscenario&#39;s kunnen kanalen vereisen dat inhoud wordt opgehaald uit een externe bron (bijvoorbeeld weerswidgets of toepassingen voor één pagina van de Handel) die niet van nature offline ondersteuning kunnen bieden. Om offline functionaliteit voor deze specifieke gebruiksgevallen in te schakelen, biedt Cloud Player ondersteuning voor aangepaste kopteksten.
Cloud Player past een Network First-cachemethode toe, wat betekent dat het probeert inhoud van het netwerk op te halen (en de cache vervolgens met de nieuwste versie bij), en dat het terugvalt op cacheinhoud indien beschikbaar. Als u offline ondersteuning voor het ophalen van dergelijke inhoud wilt implementeren, moet de aangepaste header in de aanvraag worden opgenomen. Vervolgens wordt de aanvraag met de aangepaste header in de cache van de speler geplaatst, zodat de offline toegang tot de inhoud wordt vergemakkelijkt terwijl de cachemethode Netwerkeerste behouden blijft.

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

We waarderen je feedback! Kindly deelt uw gedachten hierover met ons [formulier](https://forms.office.com/r/MQXX9JsuEd).
