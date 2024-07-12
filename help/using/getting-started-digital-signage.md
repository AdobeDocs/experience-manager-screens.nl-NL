---
title: Basisbeginselen van digitale signalen voor [!UICONTROL AEM Screens]
description: Leer de grondbeginselen van een digitaal ondertekeningsproject.
exl-id: e3913be2-9028-4773-a034-e16924a71e04
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Basisbeginselen van een digitaal ondertekeningsproject {#basics-digital-signage}

Voordat u naar de best practices voor AEM Screens-implementatie gaat, is het belangrijk dat u het project beschouwt als een digitaal ondertekeningsproject in plaats van als een traditionele softwareontwikkeling.

In deze sectie worden aanbevelingen gegeven over belangrijke sleutelelementen die van essentieel belang zijn voor de AEM Screens-projectimplementatie.

## Belangrijkste elementen in digitale signalen {#key-elements}

De *Zeer belangrijke Elementen* in een digitaal ondertekeningsproject zijn:

![](/help/assets/Elements-Revised.png)

Het definiëren van de belangrijkste elementen is van essentieel belang voordat een digitaal ondertekeningsproject wordt uitgevoerd:

1. **Hardware**

   De hardware bepaalt welke hardwarecomponenten voor uw digitaal ondertekeningsproject ideaal zijn:
   * Beschikt het apparaat over voldoende opslagruimte om alle variaties van de ervaringen offline uit te voeren?
   * Hebt u het type en de lengte van videokabel toegestaan? En ondersteunt het apparaat zowel de gewenste resoluties (HD, FullHD, `4K` enzovoort) als video-codecs die ik wil implementeren (h.264, h.265, enzovoort)
   * Gebruik van fysiek koperdraad
   * Grootte van schermen
   * Aantal schermen
      * oriëntatie
      * hoogte-breedteverhouding
      * resolutievoorkeur

1. **Connectiviteit**

   De connectiviteit benadrukt op de volgende vragen:
   * Een netwerk (cel of wi-fi) of standalone?
      * Moet u updates van USB-inhoud toestaan?
      * Moet u het gebruik van gegevensverzameling toestaan?

1. **Installatie**

   Installatie omvat:
   * Weergave: liggend of staand
   * Hoe wordt het scherm gemonteerd?
      * Oriëntatie Staand versus oriëntatie Liggend
      * Volledige huisvesting
      * Dekplaat
   * Ondersteuning voor reparaties
   * Personeel: verantwoordelijk voor het installeren van de apparatuur en het verbinden met het netwerk
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
      * Het verzenden/Ontvangende periodieke bevelen (contactsluiting, PLC, etc.)
      * Binnenkomende gegevens worden op het scherm weergegeven (RSS) of activeren de inhoud
      * RFID/NFC/Bluetooth/iBeacon
      * Externe diensten (weer, verkeer)

1. **Milieu**

   Het milieu legt de nadruk op:
   * Locatie weergeven?
      * Binnen vs. buiten
      * Buiten bereik of rechtstreeks toegankelijk
   * Speciale tijdelijke vereiste?
   * Vandal proof?
   * Hoog omgevingslicht? Sterke contrasten?

1. **Onderhoud**

   Onderhoud legt de nadruk op:

   * Zijn installatiehulplijnen en gebruikershandleidingen vereist?
   * Configureert (programmeert) u het apparaat vóór verzending?
   * Moet u elk serienummer vastleggen voor traceringsdoeleinden?
   * Zijn er back-upstroomvereisten (ononderbroken stroomvoorziening)?
   * Hoe worden systeemupdates geïmplementeerd? En hoe worden apparaten op afstand gecontroleerd? Is een oplossing MDM vereist?
