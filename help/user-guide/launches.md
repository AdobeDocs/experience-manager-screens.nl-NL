---
title: Inhoud bijwerken met Screens Launch
description: Leer hoe u een toekomstige versie van de kanalen kunt maken, ook wel Launch genoemd, en hoe u een live-datum voor de introductie instelt om inhoud live te laten gaan op apparaten of spelers.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
source-git-commit: e82cfee5ecc6b639b7b2b65553d1635943b356ea
workflow-type: tm+mt
source-wordcount: '1567'
ht-degree: 0%

---

# Inhoud bijwerken met Screens Launch {#launches}

Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken en de live datum voor deze introductie verder instellen. Hierdoor kan de inhoud live worden weergegeven op apparaten of spelers op de opgegeven live datum.

Met hulp van ***de Lancering van Screens***, kunnen de auteurs voorproef elk kanaal in de lancering en een verzoek om overzicht in werking stellen. De groep van fiatteurs krijgt bericht en kan het verzoek goedkeuren of verwerpen. Wanneer de actieve datum is bereikt, wordt de inhoud op de apparaten afgespeeld.

Bijvoorbeeld, als de auteur toekomstige versies van c1, c2 (kanalen) wil tot stand brengen, wordt een lancering gecreeerd en een levende datum wordt geplaatst (bijvoorbeeld, 10 8:00 A.M.). Alle updates in de inhoud worden ter controle verzonden.

Na goedkeuring en op de live datum (10 november, 18:00 om 00 uur) speelt deze lancering de inhoud op de apparaten of spelers.

## Vereisten {#requirements}

Alvorens u *de Lancering van Screens* in een project van AEM Screens begint te gebruiken, zorg ervoor u het concept respijtperiode en zijn relevantie begrijpt.

Als u een ervaring uitvoert op de live-datum instellen op de speler, gaat u als volgt te werk:

* De bevordering van het lanceren (typisch neemt een paar seconden).

* Het publiceren van de bronnen voor het publiceren van instanties (neemt doorgaans een paar minuten in beslag, afhankelijk van de grootte van de kanalen of middelen die moeten worden gepubliceerd).

* De tijd die nodig is om de update offline-inhoud te voltooien (duurt meestal een paar minuten).

* De tijd die de spelers nodig hebben om de inhoud van de publicatie-instantie te downloaden (neemt meestal minuten in beslag, afhankelijk van de bandbreedte en de grootte van de elementen die moeten worden gedownload).

* Verschillen tussen de server en de speler.

### Respijtperiode begrijpen {#understanding-grace-period}

Als u wilt dat de speler de inhoud kan beginnen af te spelen op de live-datum van de set, start u de voorgaande activiteiten vóór de live-datum.

Als de levende datum *November 24, 9:00 A.M.* en *24 uren* is de respijtperiode, dan begint de bovengenoemde opeenvolging van acties bij (levende datum - respijtperiode), namelijk 23 November, 9:00 A.M. servertijd. Deze instelling geeft 24 uur de tijd om alle hierboven vermelde handelingen uit te voeren zodat de inhoud de spelers kan bereiken. De spelers begrijpen dat deze periode een lanceringsinhoud is. Als zodanig wordt de inhoud niet direct afgespeeld, maar spelers kunnen deze inhoud opslaan als een toekomstige versie en deze precies laten afspelen op de ingestelde live datum in de tijdzone van de speler.

De server bevindt zich bijvoorbeeld in PST en de apparaten in EST. Het maximale tijdsverschil is drie uur. Hierbij wordt ervan uitgegaan dat de promotie 1 minuut in beslag neemt en dat het publiceren van de auteur 10 minuten in beslag neemt en dat de speler de bronnen doorgaans in 10-15 minuten kan downloaden. Vervolgens wordt de respijtperiode = tijdsverschil (drie uur):

* Plus tijd om de lancering te bevorderen (1 minuut)
* Plus tijd om de start te publiceren (10 minuten)
* Plus tijd om te downloaden bij speler (10-15 minuten)
* Plus-buffer (30 minuten)

Daarom 3 uur 56 minuten (14160 seconden).

Dus als je live start, begint de promotie vroeg met het in aanmerking nemen van deze offset. In de bovenstaande vergelijking nemen de meeste items niet veel tijd in beslag. U kunt een fatsoenlijke gok voor deze compensatie gebruiken wanneer het maximumtijdverschil tussen de server en om het even welke speler kent.

>[!NOTE]
>
>De respijtperiode voor Screens Launch is ingesteld op 24 uur. Dit betekent dat wanneer u een live datum instelt voor elke opstart voor de bronnen onder */content/screens* , de promotie begint met deze verschuiving.

### Een respijtperiode buiten de box bijwerken {#updating-out-of-the-box-grace-period}

In deze sectie wordt uitgelegd hoe u een respijtperiode buiten de box kunt bijwerken naar 10 minuten.

1. Navigeer naar CRXDE Lite en vervolgens naar `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` .
1. Klik met de rechtermuisknop en kopieer het bestand.
1. Navigeer naar `/apps/system/config` en klik met de rechtermuisknop en plak.
1. Dubbelklik op `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` zodat u het bestand in de editor in CRXDE Lite kunt openen. Het moet de respijtperiode voor weg */content/screens/* als **86400** tonen. Verandering die waarde in **600**.

De inhoud in het tekstbestand moet er nu ongeveer als volgt uitzien:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

In het vorige voorbeeld stelt u de respijtperiode in op 10 minuten. Daarom wanneer u een levende datum voor om het even welke lancering voor de middelen onder */content/screens* plaatst, begint de bevordering met deze compensatie.

Bijvoorbeeld, als de levende datum wordt geplaatst als 24 November, 9:00 A.M. en de respijtperiode 600 seconden is, begint de bevorderingsbaan 24 om 8:50 A.M.

## Screens Launch gebruiken {#using-launches}

In deze sectie ziet u hoe u Screens Launch kunt implementeren in uw AEM Screens-project.

### Screens Launch maken {#creating-a-launch}

Voer de volgende stappen uit om de Screens-startfunctionaliteit te implementeren voor uw AEM Screens-project:

1. Creeer een opeenvolgingskanaal in uw project van AEM Screens, bijvoorbeeld **LaunchesDemo** > **Kanalen** > **FutureLaunch**, zoals hieronder getoond.

   >[!CAUTION]
   >
   >Maak een lancering van een reeds bestaand kanaal in uw AEM Screens-project.

   ![ Beeld ](/help/user-guide/assets/launches-images/launches-11.png)

1. Klik het kanaal **FutureLaunch** en klik **creeer Lancering** van de actiebar.

   ![ Beeld ](/help/user-guide/assets/launches-images/launches-12.png)

1. **creeer de 1} tovenaar van de Lancering {opent.** U kunt op het kanaal klikken dat al zichtbaar is in de wizard of op **+ Kanalen toevoegen** klikken om het kanaal toe te voegen waarvoor u de opstart wilt maken.

1. Klik **daarna** van **creeer de 3} tovenaar van de Lancering {.** **omvat subpages** optie wordt geselecteerd door gebrek.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Met de optie **+ Kanalen toevoegen** kunt u een ander kanaal toevoegen waarvoor u de opstart wilt maken.

   Om **te gebruiken voeg de optie van Kanalen** toe, navigeer aan het kanaal waarvoor u de lancering wilt tot stand brengen en **Uitgezocht** klikken.

   De **Uitgezochte** optie is gehandicapt als u probeert om veelvoudige kanalen of een omslag voor het toevoegen van de lancering te klikken.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-14.png)

   Nadat u het kanaal/de kanalen klikt, klik **daarna**.


1. Ga de **Titel van de Lancering** als **SummerPromotions** in en u te hoeven niet om de **Datum van de Lancering** te plaatsen, zoals aangetoond in hieronder cijfer. Klik **creëren**.

   >[!NOTE]
   >
   >*toelatend of controlerend* de optie **erven bron paginageeft levende gegevens** laat de kanalen toe om als levende exemplaren in de lancering worden gecreeerd. Als er wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen automatisch toegepast op de startkanalen.
   >
   >
   >*onbruikbaar makend of unchecking* **erven bron paginageeft levende gegevens** laat de kanalen toe om zonder enige levende verhouding in de lancering worden gekopieerd. Als er dus wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen niet toegepast op de startkanalen.

   ![ Beeld ](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >U kunt de live startdatum in deze stap instellen of u kunt deze later instellen tijdens het bewerken van de eigenschappen van de start nadat deze al is gemaakt.

   **Begrijpend het Toepassingsgebied van de Bevordering van de Lancering**

   * **bevordert volledige lancering** - Alle kanalen van de lancering worden bevorderd bij de vastgestelde levende datum.
   * **bevordert gewijzigde pagina&#39;s** - slechts worden de gewijzigde lanceringsmiddelen bevorderd. Gebruik deze optie als de startrevisie niet is vereist.
   * **bevordert goedgekeurde pagina&#39;s** - deze optie vereist het werkschema van de lanceringsgoedkeuring om op de lanceringskanalen te lopen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.

     >[!CAUTION]
     >
     >Bij het starten van de live datum wordt de tijdzone van de speler/het apparaat in plaats van de servers gerespecteerd.

1. U ziet dat de opstart is gemaakt. U kunt of **Open** klikken om de pagina&#39;s in de redacteur te bekijken of **Gedaan** klikken om terug naar uw project te navigeren.

   ![ screen_shot_2019-06-25at20355pm ](assets/screen_shot_2019-06-25at20355pm.png)

   Het selecteren **Gedaan** laat u terug naar uw **FutureLaunch** kanaal navigeren.

   ![ Beeld ](/help/user-guide/assets/launches-images/launches-16.png)


### De eigenschappen voor starten bewerken om de actieve datum en het actieve bereik in te stellen {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nadat de lancering wordt gecreeerd, kunt u de eigenschappen zoals levende datum, lanceringstitel, en promotiewerkingsgebied bijwerken door **Eigenschappen van de Lancering** te gebruiken.

* **Datum van de Lancering** - de levende datum, namelijk de datum of de tijd de inhoud in de speler van Screens volgens timezone van de speler speelt.
* **Klaar Productie** - na bevordering, staat het de kanalen toe om worden gepubliceerd, en uit-van-de-doos wordt toegelaten, zodat te hoeven om het te veranderen.
* **Reikwijdte** - besluit welke kanalen tijdens de lanceringsbevordering worden bevorderd.

Voer de onderstaande stappen uit om de eigenschappen van de startpagina te bewerken:

1. Navigeer aan het kanaal **FutureLaunch** *(de hangende lancering)*, en klik het kanaal zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-17.png)

1. Klik **Dashboard** van de actiebar en u ziet het **PENDING LAUNCHES** paneel van het kanaaldashboard.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-18.png)

1. Klik de lancering en klik **Eigenschappen van de Lancering** van het **PENDING LAUNCHES** paneel.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-19.png)

### Screens starten bewerken om kanalen toe te voegen of te verwijderen {#editing-the-screens-launch-to-add-or-remove-channels}

Nadat u de lancering hebt gecreeerd, kunt u kanalen aan de bestaande lancering toevoegen of verwijderen gebruikend **uitgeeft de optie van de Lancering**.

Wanneer u wordt gedaan, klik **sparen** om terug naar het **FutureLaunch** kanaal te navigeren.

### Screens handmatig starten bevorderen{#promote-the-screens-launch-manually}

U kunt de lancering manueel bevorderen gebruikend de **`Promote Launch`** optie van het **PENDING LAUNCHES** paneel.

U kunt de middelen kiezen u als deel van deze handbevordering in de **Tovenaar van de Bevordering van de Lancering** wilt bevorderen.

![afbeelding](/help/user-guide/assets/launches-images/launches-e.png)

1. U kunt de optie voor het verwijderen van de opstart na de productie in- of uitschakelen.
1. U kunt het **Reikwijdte** van de lancering met de volgende opties plaatsen:
   * **bevordert volledige lancering** - Alle kanalen van de lancering worden bevorderd bij de vastgestelde levende datum.
   * **bevordert gewijzigde pagina&#39;s** - slechts worden de gewijzigde lanceringsmiddelen bevorderd. Gebruik deze optie als de startrevisie niet is vereist.
   * **bevordert goedgekeurde pagina&#39;s** - deze optie vereist het werkschema van de lanceringsgoedkeuring om op de lanceringskanalen te lopen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.
   * **bevordert huidige pagina** - deze optie vereist het werkschema van de lanceringsgoedkeuring om slechts voor de huidige pagina in werking te stellen.
1. Klik **daarna** in **bevorderen de tovenaar van de Lancering**.
1. Klik **bevorderen** om de lancering te bevorderen.

### Screens Launch verwijderen

U kunt de lancering schrappen gebruikend de **Optie van de Lancering van de Schrapping** van **HET PENNEN START** paneel.

>[!CAUTION]
>
>Met deze handeling verwijdert u ook alle afstammingen (geneste startblokken).
