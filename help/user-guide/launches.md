---
title: Inhoud bijwerken met Schermen starten
seo-title: Inhoud bijwerken met Schermen starten
description: Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken, ook wel Launch genoemd, en als u de actieve datum voor deze lancering verder instelt, kan inhoud live worden weergegeven op apparaten of spelers.
seo-description: Inhoudsauteurs kunnen een toekomstige versie van de kanalen maken, ook wel Launch genoemd, en als u de actieve datum voor deze lancering verder instelt, kan inhoud live worden weergegeven op apparaten of spelers.
uuid: fb13117c-b99b-48bd-adb6-040dbd13af16
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 9cd8892b-fe5d-4ad3-9b10-10ff068adba6
docset: aem65
feature: Ontwerpschermen, starten
role: Beheerder, ontwikkelaar
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 0%

---


# Inhoud bijwerken met gebruik van Startpagina {#launches} voor schermen

Inhoudsauteurs kunnen een toekomstige versie van het kanaal of de kanalen maken, ook wel **Starten van schermen** genoemd, en de live datum voor deze lancering verder instellen. Hierdoor kan de inhoud live worden weergegeven in apparaten of spelers op de opgegeven live datum.

Met behulp van ***Screens Launch***, kunnen de auteurs elk kanaal in de lancering voorproef en een verzoek tot overzicht in werking stellen. De groep van fiatteurs zal bericht krijgen en kan het verzoek goedkeuren of verwerpen. Wanneer de actieve datum is bereikt, wordt de inhoud op de apparaten afgespeeld.

Als de auteur bijvoorbeeld toekomstige versies van c1, c2 (kanalen) wil maken, wordt een introductie gemaakt en wordt een live datum ingesteld (bijvoorbeeld 10e 8:00 AM nov). Eventuele verdere updates in de inhoud worden ter controle verzonden.

Na goedkeuring en op live datum (10 november, 8:00 uur) speelt deze lancering de inhoud op de apparaten of spelers af.

## Vereisten {#requirements}

Voordat u de functie *Screens Launch* in een AEM Screens-project gaat gebruiken, moet u controleren of u het concept Respijtperiode en de relevantie ervan begrijpt.

Als u een ervaring uitvoert op de live-datum instellen op de speler, gaat u als volgt te werk:

* het promoten van de opstart (duurt meestal een paar seconden)

* het publiceren van de bronnen voor het publiceren van instanties (neemt doorgaans een paar minuten in beslag, afhankelijk van de grootte van de kanalen of middelen die moeten worden gepubliceerd)

* de tijd die de update offline nodig heeft om te voltooien (neemt doorgaans een paar minuten in beslag)

* de tijd die de spelers nodig hebben om de inhoud van de publicatie-instantie te downloaden (neemt meestal minuten in beslag, afhankelijk van de bandbreedte en de grootte van de elementen die moeten worden gedownload)

* eventuele tijdverschillen tussen de server en de speler

### Respijtperiode {#understanding-grace-period}

Als u wilt dat de speler de inhoud kan afspelen op de actieve datum van de set, moeten de voorgaande activiteiten worden gestart vóór de live datum.

Als de live datum *24 nov., 9:00 AM* is en de respijtperiode *24 uur* is, dan zal de bovenstaande reeks acties beginnen bij (levende datum - respijtperiode), namelijk 23 nov, 9:00 AM servertijd. Dit geeft 24 uur de tijd om alle bovengenoemde acties te voltooien en de inhoud zal de spelers bereiken. De spelers zullen begrijpen dat dit een lanceringsinhoud is, zodat zal de inhoud niet onmiddellijk spelen, maar de spelers zullen deze inhoud als toekomstige versie opslaan en zullen beginnen precies op de vastgestelde levende datum op de tijdzone van de speler te spelen.

Bijvoorbeeld, is de server in PST en de apparaten in EST zijn, is het maximumtijdverschil 3 uren in dit geval en veronderstelt dat de bevordering 1 min zal vergen en het publiceren van auteur 10 min neemt en de speler kan de middelen typisch in 10-15 min downloaden. De respijtperiode = tijdsverschil (3 uur) + tijd om de start te bevorderen (1 min) + tijd om de start te publiceren (10 min) + tijd om te downloaden bij speler (10-15 min) + buffer (om veilig te zijn, bijvoorbeeld 30 min) = 3 uur 56 min = 14160 seconden.

Dus als we live gaan, zal de promotie vroeg beginnen bij deze offset. In de bovenstaande vergelijking, nemen de meeste punten niet veel tijd, kunnen wij een behoorlijk gok voor deze compensatie gebruiken zodra wij het maximumtijdverschil tussen de server en om het even welke speler kennen.

>[!NOTE]
>
>De evaluatieperiode voor het starten van schermen is ingesteld op 24 uur. Dit betekent dat wanneer we de live-datum instellen voor het opstarten van bronnen onder */content/screens*, de promotie begint met deze verschuiving.

### Respijtperiode {#updating-out-of-the-box-grace-period} bijwerken

In deze sectie wordt uitgelegd hoe u een uitstelperiode kunt bijwerken naar 10 minuten.

1. Navigeer naar CRXDE Lite en vervolgens naar `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
2. Klik met de rechtermuisknop en kopieer het bestand.
3. Navigeer naar `/apps/system/config` en klik met de rechtermuisknop en plak.
4. Dubbelklik op `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` om het bestand in de editor in CRXDE Lite te openen. De respijtperiode voor het pad */content/screens/* moet worden weergegeven als **86400**. Wijzig die waarde in **600**.

De inhoud in het tekstbestand moet er nu ongeveer als volgt uitzien:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Aangezien u de Periode van de Aflossing aan 10 minuten in het voorafgaande voorbeeld hebt geplaatst, wanneer u levende datum voor om het even welke lancering voor de middelen onder */content/screens* plaatst, zal de bevordering met deze compensatie beginnen.

Als de live datum bijvoorbeeld is ingesteld op 24 november, 9:00 uur en de respijtperiode op 600 seconden, begint de promotietaak op 24 november om 8:50 uur.

## Starten van schermen {#using-launches} gebruiken

In deze sectie ziet u hoe u de functie Schermen starten in uw AEM Screens-project implementeert.

### Starten van schermen {#creating-a-launch} maken

Voer de onderstaande stappen uit om de functie Schermen starten te implementeren voor uw AEM Screens-project:

1. Creeer een opeenvolgingskanaal in uw AEM Screens project, bijvoorbeeld **LaunchesDemo** —> **Kanalen** —> **FutureLaunch**, zoals hieronder getoond.

   >[!CAUTION]
   >
   >U moet een lancering van een reeds bestaand kanaal in uw AEM Screens project tot stand brengen.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-11.png)

1. Selecteer het kanaal **FutureLaunch** en klik **Create Launch** van de actiebar.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-12.png)

1. De wizard **Starten maken** wordt geopend. Of u kunt het kanaal selecteren dat reeds zichtbaar in de tovenaar is of **+ klikt toevoegt Kanalen** om het kanaal toe te voegen waarvoor u de lancering wilt tot stand brengen.

1. Klik **Volgende** van **Create Launch** tovenaar. De optie **Inclusief subpagina&#39;s** is standaard geselecteerd.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >Met de optie **+ Kanalen toevoegen** kunt u een ander kanaal toevoegen waarvoor u de opstart wilt maken.

   Als u de optie **Kanalen toevoegen** wilt gebruiken, navigeert u naar het kanaal waarvoor u de opstart wilt maken en klikt u op **Selecteren**.

   De optie **Select** wordt uitgeschakeld als u meerdere kanalen of een map probeert te selecteren om de opstart toe te voegen.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-14.png)

   Nadat u het kanaal of de kanalen hebt geselecteerd, klikt u op **Volgende**.


1. Voer **Titel starten** in als **SummerPromotions** en u hoeft de **Launch Date** niet in te stellen, zoals in de onderstaande afbeelding wordt getoond. Klik **Maken**.

   >[!NOTE]
   >
   >*Als u de optie* Live  **gegevens van bronpagina overnemen inschakelt of** inschakelt, kunnen de kanalen tijdens de lancering als live kopieën worden gemaakt. Als er wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen automatisch toegepast op de startkanalen.
   >
   >
   >*Als u de actieve* **gegevens van de bronpagina voor** overnemen uitschakelt of ongedaan maakt, kunnen de kanalen worden gekopieerd zonder live relatie tijdens het opstarten. Als er dus wijzigingen worden aangebracht in het oorspronkelijke kanaal, worden deze wijzigingen niet toegepast op de startkanalen.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >U kunt de live startdatum in deze stap instellen of u kunt deze later instellen tijdens het bewerken van de eigenschappen van de start nadat deze al is gemaakt.

   **Promotiebereik starten**

   * **Volledige introductie** bevorderen: Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   * **Gewijzigde pagina**&#39;s promoten: Alleen aangepaste startbronnen worden bevorderd. U wordt aangeraden deze optie te gebruiken als de startrevisie niet vereist is.
   * **Goedgekeurde pagina**&#39;s promoten: Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.

      >[!CAUTION]
      >
      >Bij het starten van de live datum wordt de tijdzone van de speler/het apparaat gevolgd en niet die van de server.

1. U ziet dat de opstart is gemaakt. U kunt of **Open** klikken om de pagina&#39;s in de redacteur te bekijken of **Done** klikken om terug naar uw project te navigeren.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Als u op **Done** klikt, kunt u terugnavigeren naar uw **FutureLaunch**-kanaal.

   ![Afbeelding](/help/user-guide/assets/launches-images/launches-16.png)


### De eigenschappen voor starten bewerken om de actieve datum en het actieve bereik in te stellen {#editing-the-launch-properties-to-set-the-live-date-and-scope}

Nadat de lancering wordt gecreeerd, kunt u de eigenschappen zoals levende datum, lanceringstitel en promotiewerkingsgebied bijwerken door **Eigenschappen van de Lancering** te gebruiken.

* **Begindatum** verwijst naar de live datum, dat wil zeggen de datum of tijd waarop de inhoud in de schermspeler wordt afgespeeld volgens de tijdzone van de speler.
* **Productie Klaar**, staat de kanalen toe om na het bevorderen van deze, uit-van-de-doos worden gepubliceerd dit wordt toegelaten, zodat te hoeven om dit niet te veranderen.
* **Bereik**, bepaalt welke kanalen tijdens de lanceringsbevordering zullen worden bevorderd.


Voer de onderstaande stappen uit om de eigenschappen van de startpagina te bewerken:

1. Navigeer naar het kanaal **FutureLaunch**, *(dat is de volgende lancering)* en selecteer het kanaal, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-17.png)

1. Klik op **Dashboard** van de actiebar en u ziet **PENDING LAUNCHES** paneel van het kanaaldashboard.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-18.png)

1. Selecteer de lancering en klik **Eigenschappen van de Lancering** van **PENDING LAUNCHES** paneel.

   ![afbeelding](/help/user-guide/assets/launches-images/launches-19.png)

### Het uitgeven van de Lancering van de Schermen om Kanalen {#editing-the-screens-launch-to-add-or-remove-channels} toe te voegen of te verwijderen

Nadat u de lancering hebt gecreeerd, kunt u kanalen aan de bestaande lancering toevoegen of verwijderen gebruikend **de optie van de Lanceer van de Edit**.

Als u klaar bent, klikt u op **Opslaan** om terug te navigeren naar **FutureLaunch** kanaal.

### Schermen handmatig starten bevorderen{#promote-the-screens-launch-manually}

U kunt de lancering manueel bevorderen gebruikend **Bevorderen Starten** optie van **PENDING LAUNCHES** paneel.

U kunt de middelen kiezen u als deel van deze handbevordering in **de Tovenaar van de Bevordering van de Lancering** wilt bevorderen.

![afbeelding](/help/user-guide/assets/launches-images/launches-e.png)

1. U kunt de optie voor het verwijderen van de opstart na de productie in- of uitschakelen.
1. U kunt **Scope** van de lancering, met de volgende opties plaatsen:
   1. **Volledige introductie** bevorderen: Alle kanalen van de lancering worden bevorderd op de vastgestelde levende datum.
   1. **Gewijzigde pagina**&#39;s promoten: Alleen aangepaste startbronnen worden bevorderd. U wordt aangeraden deze optie te gebruiken als de startrevisie niet vereist is.
   1. **Goedgekeurde pagina**&#39;s promoten: Voor deze optie moet de goedkeuringsworkflow voor het starten worden uitgevoerd op de startkanalen. Alleen goedgekeurde pagina&#39;s worden gepromoveerd op de ingestelde live datum.
   1. **Huidige pagina** promoten: Voor deze optie moet de goedkeuringsworkflow alleen voor de huidige pagina worden uitgevoerd.
1. Klik **Next** in **Promote Launch** tovenaar.
1. Klik **Promote** om de lancering te bevorderen.

### Starten van schermen {#deleting-the-screens-launch} verwijderen

U kunt de lancering schrappen gebruikend **Schrap Lancering** optie van **PENDING LAUNCHES** paneel.

>[!CAUTION]
>
>Met deze actie verwijdert u ook alle onderliggende elementen (geneste lanceringen).

