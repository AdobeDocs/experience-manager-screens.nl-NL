---
title: Kanaaltoewijzing - Laatste FP
seo-title: Kanaaltoewijzing - Laatste FP
description: Volg deze pagina voor meer informatie over Kanaaltoewijzing en Dagverdeling.
translation-type: tm+mt
source-git-commit: 1c6a7342288a5d78dbea91d29ff8e5d6c8fec486
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 1%

---


# Kanaaltoewijzing {#channel-assignment}

>[!IMPORTANT]
>In deze sectie worden de kanaaltoewijzing en de planning van kanalen voor AEM 6.5.5-beeldschermfuncties (Functiepakket) en hoger gemarkeerd.

Nadat u een weergave hebt ingesteld, moet u een kanaal aan een weergave toewijzen om de inhoud weer te geven.

Op deze pagina ziet u hoe u een kanaal toewijst aan uw scherm.

>[!NOTE]
>U kunt meerdere kanalen aan een weergave toewijzen.


## Een kanaal toewijzen {#assign-a-channel-new-release}

Volg de onderstaande secties om een AEM Screens-project te maken en een kanaal toe te wijzen aan een weergave.

### AEM Screens-project en -kanalen maken {#creating-project}

Voer de onderstaande stappen uit om een project en een kanaal in te stellen:

1. Maak een AEM Screens-project met de naam **DemoScreens**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Raadpleeg [Projecten](creating-a-screens-project.md) maken en beheren voor meer informatie over het maken van een AEM Screens-project.

1. Maak een volgnummer met de naam **Cafeteria** in de map **Kanalen** .

1. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om inhoud aan het kanaal toe te voegen.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   Het kanaal **Cafeteria** geeft bijvoorbeeld nu de volgende afbeeldingen weer:

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Maak een locatie met de naam **SanJose** en een weergave als **Lobby**.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Kanaal toewijzen aan een weergave {#assigning-channel-to-display}

Nadat u de projectinstelling hebt voltooid, moet u het kanaal toewijzen aan een weergave om de inhoud weer te geven.

1. Navigeer naar de vereiste weergave, bijvoorbeeld **DemoScreens** —> **Locations** —> **SanJose** —> **Lobby**.

1. Tik/klik op Kanaal **** toewijzen op de actiebalk.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Of

   Tik/klik op **dashboard** en klik op **+Kanaal** toewijzen in het deelvenster **TOEGEWEZEN KANALEN EN SCHADUWEN** .

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. Het dialoogvenster **Kanaaltoewijzing** wordt geopend.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. Met de optie **Instellingen** kunt u het kanaal kiezen op pad of op naam, de kanaalrol, prioriteit, ondersteunde gebeurtenissen en onderbreekmethoden invoeren. Bovendien kunt u de optie voor het aantrekken van knopinfo vanuit dit dialoogvenster inschakelen.

   ![afbeelding](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Raadpleeg de sectie [Kanaaleigenschappen](#channel-properties) voor meer informatie over kanaaleigenschappen.

1. Selecteer bij **Planningen** de optie Tijdzone **** referentie, Venster **** activering en **Herhalingsschema**.

1. Klik op **Opslaan** als u de voorkeuren hebt geconfigureerd.

### De inhoud weergeven in Chrome Player {#viewing-content-output}

### Kanaaleigenschappen van kanaaltoewijzing {#channel-properties}

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