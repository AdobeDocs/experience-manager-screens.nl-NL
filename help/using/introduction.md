---
title: Inleiding tot [!UICONTROL AEM Screens]
seo-title: Best Practices Guide for [!UICONTROL AEM Screens] projects
description: Deze pagina is een inleidende sectie voor AEM Screens
seo-description: Deze pagina biedt een inleiding op AEM Screens
translation-type: tm+mt
source-git-commit: 54c5a2f2f3f755e4da4028d54042f4bd8f2df369
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 9%

---


# Inleiding tot AEM Screens {#introduction}

**AEM (Adobe Experience Manager)** Screensis a Digital Signage Solution waarmee u dynamische en interactieve digitale ervaringen kunt ontwerpen, publiceren en afspelen met verschillende typen in-venue weergaveschermen, in overleg met een alomvattende strategie voor digitale marketing in het universeel kanaal.

Met AEM Screens kunt u:

* **speciale digitale menuborden**
* **productadviseurs**
* **achtergrondafbeelding van levensstijl**

Bovendien, verstrekken de Schermen vele unieke toepassingen voor klanten en werknemers die op het domein worden gebaseerd waar deze, zoals worden opgesteld:

* **interactieve weergaven**
* **wegwerken**
* **brandmerken**
* **het toevoegen van ambitie aan uw milieu**

Het maken en beheren van een digitaal signalisatienetwerk met behulp van AEM Screens is eenvoudig en intuïtief. Een spelerappicatie host contentkanalen die voor de AEM Screens door klanten of implementatiepartners zijn gebouwd. *Locaties* beheren een vooraf gedefinieerde locatiehiërarchie en bevatten weergaven. Elke *weergave* heeft een dashboard waarop verschillende gekoppelde apparaten en schermen worden weergegeven. Content voor AEM Screens wordt beheerd in *kanalen*. *Speler voor AEM Screens* rendert de content die aanwezig is in kanalen op displays.



>[!NOTE]
>
>Raadpleeg **[AEM Screens User Guide](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html)** voor meer informatie over de verschillende functies in een AEM Screens-projectontwikkeling en -beheer.

## AEM Sites versus AEM Screens {#aem-sites-screens}

>[!NOTE]
>
>Als uw implementatieteam ervaring heeft met het werken met AEM Sites-toepassingen, is het belangrijk dat u het verschil begrijpt tussen AEM Sites en AEM Screens.

AEM Screens biedt een geïntegreerd platform voor ontwerpen/afspelen voor het implementeren van inhoud naar digitale signaalapparaten in openbare ruimten. Hoewel de auteur van de ervaring moet streven naar consistentie op het web en in-venue kanalen, zijn er enkele verschillen die moeten worden opgemerkt.

* **Weltijd**: Webpagina&#39;s zijn doorgaans ontworpen om een schat aan informatie te bieden die over een relatief langere periode kan worden gebruikt. In-locatiegebonden digitale ervaringen moeten daarentegen anticiperen op de behoeften van de kijker en duidelijke en beknopte aanwijzingen bieden voor de manier waarop en waarom de gebruiker zich moet engageren. Dit leidt tot meer gerichte, gekromde en contextuele ervaringen.

* **Kijkafstand**: De weergaveafstand is over het algemeen langer of verder verwijderd dan de weergaveafstand die gebruikers doorgaans afleggen op een website. Daarom moet de tekstgrootte normaal gesproken groter zijn en moet de afstand tussen tekst, afbeeldingen en andere aanvullende inhoud worden getest op basis van de verwachte schermgrootte en plaatsing in de fysieke ruimte.

* **Persistentie**: De verbonden staat van het spelerapparaat zou nooit moeten worden toegestaan om te beïnvloeden of digitale ervaringen aan de gebruiker worden geleverd of niet. De speler moet zodanig zijn ontworpen dat een of meer ervaringen altijd aanhouden en kunnen worden geleverd, ongeacht de verbindingsstatus van het spelerapparaat.

* **Segmentatie** medialijn: Wanneer u elk spelerapparaat configureert voor een eigen lussegment, weet u zeker dat gelokaliseerde inhoud eenvoudig kan worden gemaakt, gepubliceerd en afgespeeld binnen de algemene digitale ervaring. Media-elementen die zich in ingesloten reekskanalen bevinden, worden toegevoegd aan het vorige lussegment en bieden de mogelijkheid een medialusegment voor elke locatiegroep als doel in te stellen.

* **Interactieve ervaringen**: Een toepassing met aanraakbediening kan worden ontworpen en geleverd in een rasterkanaal met AEM en de SPA-editor. Het is aan te raden om consistente eigenschappen van het universeel ontwerp toe te passen, een inactiviteitstimer om de ervaring opnieuw in te stellen en een duidelijke aanroep van actie te maken voor welke taken de toepassing kan uitvoeren. De landingspagina moet bestaan uit belangrijke digitale elementen die zijn ontworpen om waarde over te brengen, de gebruiker op het scherm aan te trekken en de gebruiker ertoe aan te zetten zich aan te sluiten.

AEM Screens biedt een framework om inhoud te implementeren op fysieke apparaten. Inhoud wordt toegewezen aan kanalen in schermen, die media-inhoud of toepassingen op aanraakschermen kunnen bevatten. Binnen dit framework kan een AEM Sites-toepassing als inhoud worden geleverd via een kanaal.

Voordat een AEM Sites in een Kanaal in rasters wordt neergezet, moet deze zijn opgemaakt voor gebruik met de afmetingen van het weergaveapparaat waarvoor het bestemd is.

>[!NOTE]
>Veel AEM Sites-componenten zijn niet compatibel met AEM Screens. AEM Screens wordt geleverd met veel van zijn eigen kant-en-klare componenten waarmee u digitale ervaringen kunt opbouwen zonder aanpassingen. Als projectvereisten dit toestaan, kunt u waar mogelijk ingebouwde AEM Screens-functionaliteit gebruiken.
