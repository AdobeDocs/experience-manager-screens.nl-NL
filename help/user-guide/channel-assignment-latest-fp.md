---
title: Kanaaltoewijzing - Laatste FP
seo-title: Kanaaltoewijzing - Laatste FP
description: Volg deze pagina voor meer informatie over Kanaaltoewijzing en Dagverdeling.
translation-type: tm+mt
source-git-commit: 963262bb4b7b26aa1e9fbf1be2362c7029818789
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 0%

---


# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>In deze sectie worden de kanaaltoewijzing en de planning van kanalen voor AEM 6.5.5-beeldschermfuncties (Functiepakket) en hoger gemarkeerd.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw scherm.

>[!NOTE]
>U kunt meerdere kanalen aan een weergave toewijzen.

## Een kanaal toewijzen {#assign-a-channel-new-release}

Voer de onderstaande stappen uit om een kanaal toe te wijzen aan een weergave:

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoProject** —> **Locaties** —> **SanJose** —> **StoreDisplay**.


1. Tik/klik op Kanaal **** toewijzen op de actiebalk

   Of

   Tik/klik op **dashboard** en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** om het dialoogvenster **Kanaaltoewijzing** te openen.

1. Met de optie Instellen kunt u het kanaal kiezen op pad of op naam, de kanaalrol, prioriteit of Ondersteunde gebeurtenissen invoeren.

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.

1. Selecteer bij **Planningen** de optie Tijdzone **** referentie, Venster **** activering en **Herhalingsschema**.

1. Klik op **Opslaan** als u de voorkeuren hebt geconfigureerd.

## Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

### Referentiekanaal {#ref-channel}

Met het referentiekanaal kunt u een verwijzing naar het gewenste kanaal opgeven, op kanaalnaam of op kanaalpad.

* **per pad**: u verstrekt een expliciete verwijzing gebruikend de absolute weg van het kanaal.

* **op naam**: U voert de naam in van het kanaal dat per context wordt omgezet in een daadwerkelijk kanaal. Met deze functie kunt u een lokale versie van een kanaal maken om locatie-specifieke inhoud dynamisch op te lossen. Een kanaal met een naam *gaat bijvoorbeeld over de dag*, waar de inhoud in feite anders zou zijn in twee steden, maar u hebt nog steeds de rol van een normaal kanaal op alle schermen.

### Kanaalrol {#role-channel}

De rol van het kanaal bepaalt de context van de vertoning. De rol wordt op verschillende acties gericht en staat los van het daadwerkelijke kanaal dat de rol vervult.

### Priority {#priority-channel}

Prioriteit wordt gebruikt om de toewijzingen te bestellen als meerdere toewijzingen voldoen aan de afspeelcriteria. Degene met de hoogste waarde heeft altijd voorrang op lagere waarden. Bijvoorbeeld, als er twee kanalen A en B zijn. A heeft een prioriteit van 1 en B heeft een prioriteit van 2, dan wordt kanaal B getoond, aangezien het een hogere prioriteit dan A heeft.

>[!NOTE]
>De prioriteit voor een kanaal wordt ingesteld als een getal (1 voor minimaal) in het dialoogvenster **Kanaaltoewijzing** , zoals hierboven vermeld. Bovendien, worden de toegewezen kanalen gesorteerd gebaseerd op dalende prioriteit.

### Ondersteunde gebeurtenissen {#supported-events-channel}

* **Oorspronkelijke belasting**: laadt het kanaal wanneer de speler wordt gestart. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Niet-actief scherm**: wordt geladen wanneer het scherm niet actief is. Het kan aan veelvoudige kanalen in combinatie met programma worden toegewezen
* **Timer**: moet worden vastgesteld wanneer een schema wordt verstrekt
* **Gebruikersinteractie**: de speler schakelt over naar het opgegeven kanaal als er een gebruikersinteractie op het scherm is (aanraking) in een niet-actief kanaal en wordt geladen wanneer het scherm wordt aangeraakt

### Onderbrekingsmethode {#interruption-method-channel}

>[!IMPORTANT]
>
> Deze optie is alleen beschikbaar bij AEM 6.4 Feature Pack 8 of AEM 6.5 Feature Pack 4.

Als auteur van inhoud moet u kunnen opgeven wanneer een kanaal wordt onderbroken, zodat u niet-kritieke inhoud kunt uitschakelen, maar belangrijke inhoud volledig kunt laten afspelen voordat u het afspelen afsluit vanwege het plannen.

Selecteer een van de volgende opties die beschikbaar zijn om de methode voor onderbreking in te stellen in het dialoogvenster **Kanaaltoewijzing** :

* **Onmiddellijk**: wanneer het programma wordt geactiveerd of een update wordt ontvangen, kunt u het afspelen uitschakelen en de nieuwe inhoud direct vernieuwen of afspelen
* **Aan het einde van het huidige item**: wanneer een nieuw programma wordt geactiveerd of een update wordt ontvangen, hebt u de optie om te wachten tot het huidige item in de reeks klaar is met afspelen en pas daarna vernieuwt of afspeelt u de nieuwe inhoud
   >[!NOTE]
   >Deze optie is standaard geselecteerd.
* **Aan het einde van de reeks**: wanneer een nieuw programma activeert of een update wordt ontvangen, hebt u de optie om op de volledige opeenvolging te wachten om zijn eind te bereiken, en net vóór de gewenste opeenvolging, kunt u terugloop naar het eerste element, u vernieuwt of de nieuwe inhoud speelt

   >[!NOTE]
   >Als u de tweede of derde optie gebruikt, kunnen de op de toewijzing gedefinieerde planningstijden enigszins worden uitgesteld omdat de speler op het einde van het item of de reeks (na de opgegeven tijd) wacht voordat het item of de reeks wordt vernieuwd. De vertraging is afhankelijk van de afspeelduur van het item.