---
title: Inhoud bijwerken met Schermen starten
description: Leer hoe u een toekomstige versie van de kanalen kunt maken, ook wel Launch genoemd, en hoe u een actieve datum voor de lancering instelt om inhoud live te maken op apparaten of spelers.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 0%

---

# Inhoud bijwerken met Schermen starten {#launches}

Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken, ook wel **Schermen starten** en stelt u de live datum voor deze start vast. Hierdoor kan de inhoud live worden weergegeven op apparaten of spelers op de opgegeven live datum.

Met de hulp van ***Schermen starten*** auteurs kunnen dan elk kanaal voorvertonen tijdens het starten en een verzoek om revisie starten. De groep van fiatteurs krijgt bericht en kan het verzoek goedkeuren of verwerpen. Wanneer de actieve datum is bereikt, wordt de inhoud op de apparaten afgespeeld.

Bijvoorbeeld, als de auteur toekomstige versies van c1, c2 (kanalen) wil tot stand brengen, wordt een lancering gecreeerd en een levende datum wordt geplaatst (bijvoorbeeld, 10 8:00 A.M.). Alle updates in de inhoud worden ter controle verzonden.

Na goedkeuring en op levende datum (10 November, 8:00 a.m.), speelt deze lancering de inhoud op de apparaten of de spelers.

## Vereisten {#requirements}

Voordat u begint met *Schermen starten* in een AEM Screens-project, zorg ervoor dat u het concept van Grace Period en zijn relevantie begrijpt.

Als u een ervaring uitvoert op de live-datum instellen op de speler, gaat u als volgt te werk:

* De bevordering van het lanceren (typisch neemt een paar seconden).

* Het publiceren van de bronnen voor het publiceren van instanties (neemt doorgaans een paar minuten in beslag, afhankelijk van de grootte van de kanalen of middelen die moeten worden gepubliceerd).

* De tijd die de update offline nodig heeft om te voltooien (duurt meestal een paar minuten).

* De tijd die de spelers nodig hebben om de inhoud van de publicatie-instantie te downloaden (neemt meestal minuten in beslag, afhankelijk van de bandbreedte en de grootte van de elementen die moeten worden gedownload).

* Verschillen tussen de server en de speler.

### Respijtperiode begrijpen {#understanding-grace-period}

Als u wilt dat de speler de inhoud kan beginnen af te spelen op de live-datum van de set, start u de voorgaande activiteiten vóór de live-datum.

Als de live datum *24 november, 9:00* en de respijtperiode *24 uur* Dan zal de bovenstaande opeenvolging van acties beginnen bij (levende datum - respijtperiode), namelijk 23 November, 9:00 tijd van de server A.M. Dit geeft 24 uur om alle bovengenoemde acties voor de inhoud te voltooien om de spelers te bereiken. De spelers begrijpen dat dit een lanceringsinhoud is. Als zodanig wordt de inhoud niet direct afgespeeld, maar spelers kunnen deze inhoud opslaan als een toekomstige versie en deze precies laten afspelen op de ingestelde live datum in de tijdzone van de speler.

De server bevindt zich bijvoorbeeld in PST en de apparaten in EST. Het maximale tijdsverschil is drie uur in dit geval en er wordt van uitgegaan dat de promotie 1 minuut in beslag neemt en dat het publiceren van de auteur 10 minuten in beslag neemt. De speler kan de bronnen doorgaans in 10-15 minuten downloaden. Vervolgens wordt de respijtperiode = tijdsverschil (drie uur):

* Plus tijd om de lancering te bevorderen (1 minuut)
* Plus tijd om de start te publiceren (10 minuten)
* Plus tijd om te downloaden bij speler (10-15 minuten)
* Plus-buffer (30 minuten)

Is gelijk aan 3 uur 56 minuten (14160 seconden).

Dus als je live start, begint de promotie vroeg met deze offset. In de bovenstaande vergelijking nemen de meeste items niet veel tijd in beslag. U kunt een fatsoenlijke gok voor deze compensatie gebruiken wanneer het maximumtijdverschil tussen de server en om het even welke speler kent.

>[!NOTE]
>
>De respijtperiode voor het starten van schermen is ingesteld op 24 uur. Dit betekent dat wanneer u een live datum instelt voor elke introductie van de bronnen onder */content/screens*, begint de promotie met deze compensatie.

### Respijtperiode buiten de box bijwerken {#updating-out-of-the-box-grace-period}

In deze sectie wordt uitgelegd hoe u een uitstelperiode kunt bijwerken naar 10 minuten.

1. Navigeer naar CRXDE Lite en vervolgens naar `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
1. Klik met de rechtermuisknop en kopieer het bestand.
1. Navigeren naar `/apps/system/config` en klik met de rechtermuisknop en plak deze.
1. Dubbelklikken `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` zodat kunt u het bestand in de editor openen in CRXDE Lite. De respijtperiode voor het pad moet worden vermeld */content/screens/* als **86400**. Wijzig die waarde in **600**.

De inhoud in het tekstbestand moet er nu ongeveer als volgt uitzien:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Omdat u de Periode van de Aflossing aan 10 minuten in het voorafgaande voorbeeld had geplaatst, wanneer u levende datum voor om het even welke lancering voor de middelen onder plaatst */content/screens*, begint de promotie met deze compensatie.

Als de live datum bijvoorbeeld is ingesteld op 24 november, 9:00 uur en de respijtperiode op 600 seconden, begint de promotietaak op 24 november om 8:50 uur.

## Starten van schermen gebruiken {#using-launches}

In deze sectie ziet u hoe u de functie Schermen starten in uw AEM Screens-project implementeert.

### Schermen starten {#creating-a-launch}

Voer de onderstaande stappen uit om de functie Schermen starten te implementeren voor uw AEM Screens-project:

1. Een volgnummer maken in bijvoorbeeld uw AEM Screens-project **LaunchesDemo** > **Kanalen** > **FutureLaunch**, zoals hieronder weergegeven.

   >[!CAUTION]
   >
   >Maak een lancering van een reeds bestaand kanaal in uw AEM Screens-project.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-11.png)

1. Klik op het kanaal **FutureLaunch** en klik op **Starten maken** in de actiebalk.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-12.png)

1. De **Starten maken** wizard wordt geopend. U kunt op het kanaal klikken dat al zichtbaar is in de wizard of op **+ Kanalen toevoegen** om het kanaal toe te voegen waarvoor u de lancering wilt tot stand brengen.

1. Klikken **Volgende** van de **Starten maken** wizard. De **Subpagina&#39;s opnemen** is standaard geselecteerd.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >U kunt **+ Kanalen toevoegen** om een ander kanaal toe te voegen waarvoor u de lancering wilt creëren.

   Te gebruiken **Kanalen toevoegen** navigeer naar het kanaal waarvoor u de opstart wilt maken en klik op **Selecteren**.

   De **Selecteren** is uitgeschakeld als u op meerdere kanalen of een map probeert te klikken om de opstart toe te voegen.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-14.png)

   Nadat u op het kanaal of de kanalen klikt, klikt u op **Volgende**.


1. Voer de **Titel starten** als **SummerPromotions** en u hoeft de **Opstartdatum**, zoals weergegeven in onderstaande afbeelding. Klikken **Maken**.

   >[!NOTE]
   >
   >*Inschakelen of controleren* de optie **Live-gegevens van bronpagina overnemen** Hiermee kunnen de kanalen als live kopieën worden gemaakt tijdens de lancering. Als er wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen automatisch toegepast op de startkanalen.
   >
   >
   >*Uitschakelen of uitschakelen* **Live-gegevens van bronpagina overnemen** Hiermee kunnen de kanalen worden gekopieerd zonder live relatie tijdens het starten. Als er dus wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen niet toegepast op de startkanalen.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >U kunt de live startdatum in deze stap instellen of u kunt deze later instellen tijdens het bewerken van de eigenschappen van de start nadat deze al is gemaakt.

   **Promotiebereik starten**

   * **Volledige introductie bevorderen** - Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   * **Gewijzigde pagina&#39;s promoten** - Alleen aangepaste startbronnen worden bevorderd. Gebruik deze optie als de startrevisie niet is vereist.
   * **Goedgekeurde pagina&#39;s promoten** - Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.

     >[!CAUTION]
     >
     >Bij het starten van de live datum wordt de tijdzone van de speler/het apparaat gevolgd en niet die van de server.

1. U ziet dat de opstart is gemaakt. U kunt op **Openen** om de pagina&#39;s in de editor weer te geven of klik op **Gereed** om terug naar uw project te navigeren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Selecteren **Gereed** laat u terug naar uw **FutureLaunch** kanaal.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-16.png)


### De eigenschappen voor starten bewerken om de actieve datum en het actieve bereik in te stellen {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nadat de lancering wordt gecreeerd, kunt u de eigenschappen zoals levende datum, lanceringstitel, en promotiewerkingsgebied bijwerken door te gebruiken **Starteigenschappen**.

* **Opstartdatum** - De live datum, dat wil zeggen de datum of tijd waarop de inhoud in de schermspeler wordt afgespeeld volgens de tijdzone van de speler.
* **Gereed voor productie** - Hiermee kunnen de kanalen worden gepubliceerd nadat deze zijn gepromoveerd, zodat dit niet meer nodig is.
* **Toepassingsgebied** - besluit welke kanalen worden bevorderd tijdens de promotieactiviteiten.

Voer de onderstaande stappen uit om de eigenschappen van de startpagina te bewerken:

1. Naar het kanaal navigeren **FutureLaunch** *(de volgende introductie)* en klik op het kanaal zoals in de onderstaande afbeelding wordt weergegeven.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-17.png)

1. Klikken **Dashboard** in de actiebalk en u ziet de **AFGELOPEN LAUNCHES** van het kanaaldashboard.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-18.png)

1. Klik op Starten en klik op **Starteigenschappen** van de **AFGELOPEN LAUNCHES** deelvenster.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-19.png)

### Het uitgeven van de Lancering van de Schermen om Kanalen toe te voegen of te verwijderen  {#editing-the-screens-launch-to-add-or-remove-channels}

Nadat u de opstart hebt gemaakt, kunt u kanalen toevoegen aan of verwijderen uit de bestaande opstart met **Starten bewerken** -optie.

Als u klaar bent, klikt u op **Opslaan** om terug te navigeren naar **FutureLaunch** kanaal.

### Schermen handmatig starten bevorderen{#promote-the-screens-launch-manually}

U kunt de lancering manueel bevorderen gebruikend **`Promote Launch`** van de **AFGELOPEN LAUNCHES** deelvenster.

U kunt de bronnen die u wilt promoten, kiezen in het kader van deze handmatige promotie in het dialoogvenster **Wizard Aanbieding starten**.

![afbeelding](/help/user-guide/assets/launches-images/launches-e.png)

1. U kunt de optie voor het verwijderen van de opstart na de productie in- of uitschakelen.
1. U kunt de **Toepassingsgebied** van de lancering met de volgende opties:
   * **Volledige introductie bevorderen** - Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   * **Gewijzigde pagina&#39;s promoten** - Alleen aangepaste startbronnen worden bevorderd. Gebruik deze optie als de startrevisie niet is vereist.
   * **Goedgekeurde pagina&#39;s promoten** - Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.
   * **Huidige pagina promoten** - Voor deze optie is de goedkeuringsworkflow alleen voor de huidige pagina vereist.
1. Klikken **Volgende** in de **Starten bevorderen** wizard.
1. Klikken **Bevorderen** de lancering te bevorderen.

### De functie Schermen starten verwijderen

U kunt het starten verwijderen met **Starten verwijderen** van de **AFGELOPEN LAUNCHES** deelvenster.

>[!CAUTION]
>
>Met deze handeling verwijdert u ook alle afstammingen (geneste startblokken).
