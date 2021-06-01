---
title: REST API's
seo-title: REST API
description: AEM Screens biedt een eenvoudige RESTful-API die voldoet aan de Sirenespecificatie. Volg deze pagina om te leren hoe u door de inhoudsstructuur kunt navigeren en opdrachten naar apparaten in de omgeving kunt verzenden.
seo-description: AEM Screens biedt een eenvoudige RESTful-API die voldoet aan de Sirenespecificatie. Volg deze pagina om te leren hoe u door de inhoudsstructuur kunt navigeren en opdrachten naar apparaten in de omgeving kunt verzenden.
uuid: 5988fdcb-cda5-4d3e-a2ab-f9ee4179e568
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: c07b6e4f-c0a4-4151-a543-76dabd6d5146
feature: Schermen ontwikkelen
role: Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# REST API&#39;s{#rest-apis}

AEM Screens biedt een eenvoudige RESTful-API die voldoet aan de [Siren](https://github.com/kevinswiber/siren)-specificatie. Het staat toe om de inhoudsstructuur te navigeren en bevelen naar apparaten in het milieu te verzenden.

De API is toegankelijk op [*http://localhost:4502/api/screens.json*](http://localhost:4502/api/screens.json).

## Navigeren door inhoudsstructuur {#navigating-content-structure}

De JSON die door de API-aanroepen wordt geretourneerd, vermeldt de entiteiten met betrekking tot de huidige bron. Na de vermelde zelfverbinding, is elk van deze entiteiten opnieuw toegankelijk als middel REST.

Als u bijvoorbeeld toegang wilt krijgen tot de weergaven in onze vlaggenschiplocatie voor demo, kunt u het volgende oproepen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship.json HTTP/1.1
Host: http://localhost:4502
```

Of met krullen:

```xml
curl -u admin:admin http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship.json
```

Het resultaat zou er als volgt uitzien:

```xml
{
  "class": [
    "aem-io/screens/location"
  ],
  "links": [
    {
      "rel": [
        "self"
      ],
      "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship.json"
    },
    {
      "rel": [
        "parent"
      ],
      "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo.json"
    }
  ],
  "properties": {…},
  "entities": [
    {
      "class": [
        "aem-io/screens/display"
      ],
      "links": [
        {
          "rel": [
            "self"
          ],
          "href": "http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json"
        }
      ],
      "rel": [
        "child"
      ],
      "properties": {
        "title": "Single Screen Display",
        "height": 1440,
        "description": "Demo location of a single screen display.",
        "name": "single",
        "width": 2560,
        "idletimeout": 300,
        "layoutrows": 1,
        "layoutcols": 1
      }
    },
    …
  ]
}
```

En dan om tot de Enige Vertoning van het Scherm toegang te hebben, kunt u roepen:

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

## Handelingen uitvoeren op de bron {#executing-actions-on-the-resource}

JSON die door de API vraag is teruggekeerd kan een lijst van acties bevatten die op het middel beschikbaar zijn.

De vertoning, bijvoorbeeld, maakt een lijst van een *uitzending-bevel* actie die toestaat om een bevel naar alle apparaten te verzenden die aan die vertoning worden toegewezen.

```xml
GET /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502
```

Of met krullen:

```xml
curl -u admin:admin http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```

***Resultaat:***

```xml
{
  "class": [
    "aem-io/screens/display"
  ],
  "links": […],
  "properties": {…},
  "entities": […],
  "actions": [
    {
      "title": "",
      "name": "broadcast-command",
      "method": "POST",
      "href": "/api/screens/content/screens/we-retail/locations/demo/flagship/single",
      "fields": [
        {
          "name": ":operation",
          "value": "broadcast-command",
          "type": "hidden"
        },
        {
          "name": "msg",
          "type": "text"
        }
      ]
    }
  ]
}
```

Om deze actie teweeg te brengen zou men roepen:

```xml
POST /api/screens/content/screens/we-retail/locations/demo/flagship/single.json HTTP/1.1
Host: http://localhost:4502

:operation=broadcast-command&msg=reboot
```

Of met krullen:

```xml
curl -u admin:admin -X POST -d ':operation=broadcast-command&msg=reboot' http://localhost:4502/api/screens/content/screens/we-retail/locations/demo/flagship/single.json
```

