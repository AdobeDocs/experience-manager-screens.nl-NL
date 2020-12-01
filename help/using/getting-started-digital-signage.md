---
title: Basisbeginselen van digitale signalen voor [!UICONTROL AEM Screens]
seo-title: Basisbeginselen van digitale signalen voor [!UICONTROL AEM Screens]
description: In de handleiding worden de basisbeginselen van een digitaal ondertekeningsproject beschreven
seo-description: In de handleiding worden de basisbeginselen van een digitaal ondertekeningsproject beschreven
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---


# Basisbeginselen van een digitaal ondertekeningsproject {#basics-digital-signage}

Voordat u naar de best practices voor AEM Screens-implementatie gaat, is het belangrijk dat u het project beschouwt als een digitaal ondertekeningsproject in plaats van als een traditionele softwareontwikkeling.

Deze sectie bevat aanbevelingen voor belangrijke sleutelelementen die essentieel zijn voor een AEM Screens-projectimplementatie.

## Belangrijke elementen in digitale handtekening {#key-elements}

De *Belangrijke elementen* in een digitaal ondertekeningsproject zijn:

![](/help/assets/Elements-Revised.png)

Het definiëren van de belangrijkste elementen is van essentieel belang voordat een digitaal ondertekeningsproject wordt uitgevoerd:

1. **Hardware**

   De hardware bepaalt welke hardwarecomponenten voor uw digitaal ondertekeningsproject ideaal zijn:
   * Beschikt het apparaat over voldoende opslagruimte om alle variaties van de ervaringen offline uit te voeren?
   * Hebben wij voor videokabeltype en lengte toegestaan? En ondersteunt het apparaat beide gewenste resoluties (HD, FullHD, 4K, enz.) en video-codecs die ik wil implementeren (h.264, h.265, enz.)
   * Gebruik van fysiek koperdraad
   * Grootte van schermen
   * Aantal schermen
      * orientation
      * hoogte-breedteverhouding
      * resolutievoorkeur

1. **Connectiviteit**

   De connectiviteit benadrukt op de volgende vragen:
   * Een netwerk (cel of wi-fi) of standalone?
      * moeten we updates van USB-inhoud toestaan?
      * moeten we gegevensverzameling voor het gebruik toestaan ?

1. **Installatie**

   Installatie omvat:
   * Weergaven: liggend of staand
   * Hoe wordt het scherm gemonteerd?
      * Staand versus liggend
      * Volledige huisvesting
      * Dekplaat
   * Ondersteuning voor reparaties
   * Personeel: verantwoordelijk voor het installeren van het materiaal en het verbinden met het netwerk
   * Hoe ver is de energiebron van de correctie vandaan?
   * Hoe ver is het fysieke paneel van het daadwerkelijke apparaat?

1. **Inhoud**

   Inhoud omvat:
   * Eén of meerdere zones?
      * Hoeveel media-elementen bevinden zich tegelijkertijd op het scherm?
      * Hoeveel pagina&#39;s voor interactieve toepassingen?
      * De UI-lus definiëren
      * Door gegevens gestuurde inhoud?
   * Versiebeheer

1. **Interactief**

   Interactief omvat:
   * Gewenste type touchscreen?(weerstandzaam, capacitief, multi-touch)?
      * Knop drukken
      * Gesture
   * Gegevens activeren (I/O)?
      * Het verzenden/Ontvangend periodieke bevelen (contactsluiting, PLC, enz.)
      * Binnenkomende gegevens worden op het scherm weergegeven (RSS) of activeren de inhoud
      * RFID/NFC/Bluetooth/iBeacon
      * Externe diensten (weer, verkeer)

1. **Omgeving**

   Milieu benadrukt het volgende:
   * Locatie weergeven?
      * Binnen vs. buiten
      * Buiten bereik of rechtstreeks toegankelijk
   * Speciale tijdelijke vereiste?
   * Vandal proof?
   * Hoog omgevingslicht? Sterke contrasten?

1. **Onderhoud**

   Onderhoud legt de nadruk op:

   * Zijn gedetailleerde installatiehulplijnen/gebruikershandleidingen vereist?
   * Zijn wij het apparaat voorafgaand aan verzending vormen (programmeren)?
   * Moeten we elk serienummer vastleggen voor traceringsdoeleinden?
   * Zijn er back-upstroomvereisten (ononderbroken stroomvoorziening)?
   * Hoe worden systeemupdates geïmplementeerd? En hoe worden apparaten op afstand gecontroleerd? Is een oplossing MDM vereist?
