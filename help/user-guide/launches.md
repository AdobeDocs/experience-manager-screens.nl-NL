---
title: Inhoud bijwerken met Schermen starten
seo-title: Content Update using Screens Launch
description: Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken, ook wel Launch genoemd, en als u de actieve datum voor deze lancering verder instelt, kan inhoud live worden weergegeven op apparaten of spelers.
seo-description: Content authors can create future version of the channel(s), known as Launch and further setting live date for this launch allows content to be live in devices or players.
uuid: fb13117c-b99b-48bd-adb6-040dbd13af16
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 9cd8892b-fe5d-4ad3-9b10-10ff068adba6
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: 299018986ae58ecbdb51a30413222a9682fffc76
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 0%

---

# Inhoud bijwerken met Schermen starten {#launches}

Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken, ook wel **Schermen starten** en stelt u de live datum voor deze start vast. Hierdoor kan de inhoud live worden weergegeven op apparaten of spelers op de opgegeven live datum.

Met de hulp van ***Schermen starten*** auteurs kunnen dan elk kanaal voorvertonen tijdens het starten en een verzoek om revisie starten. De groep van fiatteurs zal bericht krijgen en kan het verzoek goedkeuren of verwerpen. Wanneer de actieve datum is bereikt, wordt de inhoud op de apparaten afgespeeld.

Als de auteur bijvoorbeeld toekomstige versies van c1, c2 (kanalen) wil maken, wordt een introductie gemaakt en wordt een live datum ingesteld (bijvoorbeeld 10e 8:00 AM nov). Eventuele verdere updates in de inhoud worden ter controle verzonden.

Na goedkeuring en op live datum (10 november, 8:00 uur) speelt deze lancering de inhoud op de apparaten of spelers af.

## Vereisten {#requirements}

Voordat u weer aan het werk gaat *Schermen starten* in een AEM Screens-project, zorg ervoor dat u het concept van Grace Period en zijn relevantie begrijpt.

Als u een ervaring uitvoert op de live-datum instellen op de speler, gaat u als volgt te werk:

* het promoten van de opstart (duurt meestal een paar seconden)

* het publiceren van de bronnen voor het publiceren van instanties (neemt doorgaans een paar minuten in beslag, afhankelijk van de grootte van de kanalen of middelen die moeten worden gepubliceerd)

* de tijd die de update offline nodig heeft om te voltooien (duurt meestal een paar minuten)

* de tijd die de spelers nodig hebben om de inhoud van de publicatie-instantie te downloaden (neemt meestal minuten in beslag, afhankelijk van de bandbreedte en de grootte van de elementen die moeten worden gedownload)

* eventuele tijdverschillen tussen de server en de speler

### Respijtperiode begrijpen {#understanding-grace-period}

Als u wilt dat de speler de inhoud kan afspelen op de actieve datum van de set, moeten de voorgaande activiteiten worden gestart vóór de live datum.

Als de live datum *24 nov., 9:00* en de respijtperiode *24 uur* Dan begint de bovenstaande reeks acties bij (live datum - respijtperiode), dat wil zeggen: 23 november, 9:00 uur servertijd. Dit geeft 24 uur de tijd om alle bovengenoemde acties te voltooien en de inhoud zal de spelers bereiken. De spelers zullen begrijpen dat dit een lanceringsinhoud is, zodat zal de inhoud niet onmiddellijk spelen, maar de spelers zullen deze inhoud als toekomstige versie opslaan en zullen beginnen precies op de vastgestelde levende datum op de tijdzone van de speler te spelen.

Bijvoorbeeld, is de server in PST en de apparaten in EST zijn, is het maximumtijdverschil 3 uren in dit geval en veronderstelt dat de bevordering 1 min zal vergen en het publiceren van auteur 10 min neemt en de speler kan de middelen typisch in 10-15 min downloaden. De respijtperiode = tijdsverschil (3 uur) + tijd om de start te bevorderen (1 min) + tijd om de start te publiceren (10 min) + tijd om te downloaden bij speler (10-15 min) + buffer (om veilig te zijn, bijvoorbeeld 30 min) = 3 uur 56 min = 14160 seconden.

Dus als we live gaan, zal de promotie vroeg beginnen bij deze offset. In de bovenstaande vergelijking, nemen de meeste punten niet veel tijd, kunnen wij een behoorlijk gok voor deze compensatie gebruiken zodra wij het maximumtijdverschil tussen de server en om het even welke speler kennen.

>[!NOTE]
>
>De respijtperiode voor het starten van de schermen is ingesteld op 24 uur. Dit betekent dat we de datum waarop we live gaan bepalen voor de middelen die onder */content/screens*, zal de promotie met deze compensatie beginnen.

### Respijtperiode buiten de box bijwerken {#updating-out-of-the-box-grace-period}

In deze sectie wordt uitgelegd hoe u een uitstelperiode kunt bijwerken naar 10 minuten.

1. Navigeer naar CRXDE Lite en vervolgens naar `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
2. Klik met de rechtermuisknop en kopieer het bestand.
3. Navigeren naar `/apps/system/config` en klik met de rechtermuisknop en plak deze.
4. Dubbelklikken op `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` om het bestand in de editor in CRXDE Lite te openen. De respijtperiode voor het pad moet worden vermeld */content/screens/* als **86400**. Wijzig die waarde in **600**.

De inhoud in het tekstbestand moet er nu ongeveer als volgt uitzien:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Aangezien u de Periode van de Aflossing aan 10 minuten in het voorafgaande voorbeeld hebt geplaatst, wanneer u levende datum voor om het even welke lancering voor de middelen onder plaatst */content/screens*, zal de promotie met deze compensatie beginnen.

Als de live datum bijvoorbeeld is ingesteld op 24 november, 9:00 uur en de respijtperiode op 600 seconden, begint de promotietaak op 24 november om 8:50 uur.

## Starten van schermen gebruiken {#using-launches}

In deze sectie ziet u hoe u de functie Schermen starten in uw AEM Screens-project implementeert.

### Schermen starten {#creating-a-launch}

Voer de onderstaande stappen uit om de functie Schermen starten te implementeren voor uw AEM Screens-project:

1. Een volgnummer maken in bijvoorbeeld uw AEM Screens-project **LaunchesDemo** > **Kanalen** > **FutureLaunch**, zoals hieronder weergegeven.

   >[!CAUTION]
   >
   >U moet een lancering van een reeds bestaand kanaal in uw AEM Screens project tot stand brengen.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-11.png)

1. Selecteer het kanaal **FutureLaunch** en klik op **Starten maken** in de actiebalk.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-12.png)

1. De **Starten maken** wizard wordt geopend. U kunt het kanaal selecteren dat al zichtbaar is in de wizard of op **+ Kanalen toevoegen** om het kanaal toe te voegen waarvoor u de lancering wilt tot stand brengen.

1. Klikken **Volgende** van de **Starten maken** wizard. De **Subpagina&#39;s opnemen** is standaard geselecteerd.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >U kunt **+ Kanalen toevoegen** om een ander kanaal toe te voegen waarvoor u de opstart wilt maken.

   Te gebruiken **Kanalen toevoegen** navigeer naar het kanaal waarvoor u de opstart wilt maken en klik op **Selecteren**.

   De **Selecteren** Deze optie wordt uitgeschakeld als u meerdere kanalen of een map probeert te selecteren om de opstart toe te voegen.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-14.png)

   Nadat u het kanaal of de kanalen hebt geselecteerd, klikt u op **Volgende**.


1. Voer de **Titel starten** als **SummerPromotions** en u hoeft de **Opstartdatum**, zoals weergegeven in onderstaande afbeelding. Klikken **Maken**.

   >[!NOTE]
   >
   >*Inschakelen of controleren* de optie **Live-gegevens van bronpagina overnemen** Hiermee kunnen de kanalen als live kopieën worden gemaakt tijdens de lancering. Als er wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen automatisch toegepast op de startkanalen.
   >
   >
   >*Uitschakelen of uitschakelen* **Live-gegevens van bronpagina overnemen** Hiermee kunnen de kanalen worden gekopieerd zonder live relatie tijdens het opstarten. Als er dus wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen niet toegepast op de startkanalen.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >U kunt de live startdatum in deze stap instellen of u kunt deze later instellen tijdens het bewerken van de eigenschappen van de start nadat deze al is gemaakt.

   **Promotiebereik starten**

   * **Volledige introductie bevorderen**: Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   * **Gewijzigde pagina&#39;s promoten**: Alleen gewijzigde startbronnen worden bevorderd. U wordt aangeraden deze optie te gebruiken als de startrevisie niet vereist is.
   * **Goedgekeurde pagina&#39;s promoten**: Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.

     >[!CAUTION]
     >
     >Bij het starten van de live datum wordt de tijdzone van de speler/het apparaat gevolgd en niet die van de server.

1. U ziet dat de opstart is gemaakt. U kunt op **Openen** om de pagina&#39;s in de editor weer te geven of klik op **Gereed** om terug naar uw project te navigeren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Klikken **Gereed** kunt u terugnavigeren naar uw **FutureLaunch** kanaal.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-16.png)


### De eigenschappen voor starten bewerken om de actieve datum en het actieve bereik in te stellen {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nadat de lancering wordt gecreeerd, kunt u de eigenschappen zoals levende datum, lanceringstitel en promotiewerkingsgebied bijwerken door te gebruiken **Starteigenschappen**.

* **Opstartdatum**, verwijst naar de live datum, dat wil zeggen de datum of tijd waarop de inhoud wordt afgespeeld in de schermspeler volgens de tijdzone van de speler.
* **Gereed voor productie** kunnen de kanalen worden gepubliceerd nadat deze zijn gepromoveerd, zodat dit mogelijk is en dit niet hoeft te worden gewijzigd.
* **Toepassingsgebied**, bepaalt welke kanalen tijdens de promotieperiode worden bevorderd.


Voer de onderstaande stappen uit om de eigenschappen van de startpagina te bewerken:

1. Naar het kanaal navigeren **FutureLaunch**, *(dat is de volgende start)* en selecteert u het kanaal, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-17.png)

1. Klikken op **Dashboard** in de actiebalk en u ziet de **AFGELOPEN LAUNCHES** van het kanaaldashboard.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-18.png)

1. Selecteer de start en klik op **Starteigenschappen** van de **AFGELOPEN LAUNCHES** deelvenster.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-19.png)

### Het uitgeven van de Lancering van de Schermen om Kanalen toe te voegen of te verwijderen  {#editing-the-screens-launch-to-add-or-remove-channels}

Nadat u de opstart hebt gemaakt, kunt u kanalen toevoegen aan of verwijderen uit de bestaande opstart met **Starten bewerken** -optie.

Als u klaar bent, klikt u **Opslaan** om terug te navigeren naar **FutureLaunch** kanaal.

### Schermen handmatig starten bevorderen{#promote-the-screens-launch-manually}

U kunt de lancering manueel bevorderen gebruikend **Starten bevorderen** van de **AFGELOPEN LAUNCHES** deelvenster.

U kunt de bronnen die u wilt promoten, kiezen in het kader van deze handmatige promotie in het dialoogvenster **Wizard Aanbieding starten**.

![afbeelding](/help/user-guide/assets/launches-images/launches-e.png)

1. U kunt de optie voor het verwijderen van de opstart na de productie in- of uitschakelen.
1. U kunt de **Toepassingsgebied** van de lancering, met de volgende opties:
   1. **Volledige introductie bevorderen**: Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   1. **Gewijzigde pagina&#39;s promoten**: Alleen gewijzigde startbronnen worden bevorderd. U wordt aangeraden deze optie te gebruiken als de startrevisie niet vereist is.
   1. **Goedgekeurde pagina&#39;s promoten**: Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.
   1. **Huidige pagina promoten**: Voor deze optie is de goedkeuringsworkflow alleen voor de huidige pagina vereist.
1. Klikken **Volgende** in de **Starten bevorderen** wizard.
1. Klikken **Bevorderen** de lancering te bevorderen.

### De functie Schermen starten verwijderen {#deleting-the-screens-launch}

U kunt het starten verwijderen met **Starten verwijderen** van de **AFGELOPEN LAUNCHES** deelvenster.

>[!CAUTION]
>
>Met deze actie verwijdert u ook alle onderliggende elementen (geneste lanceringen).
