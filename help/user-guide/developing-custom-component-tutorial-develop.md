---
title: Een aangepaste component voor AEM Screens ontwikkelen
description: Leer hoe u een aangepaste component voor AEM Screens maakt.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
targetaudience: target-audience new
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: d14f8c55-dc09-4ac9-8d75-bafffa82ccc0
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '2163'
ht-degree: 0%

---

# Een aangepaste component voor AEM Screens ontwikkelen {#developing-a-custom-component-for-aem-screens}

De volgende zelfstudie doorloopt de stappen om een aangepaste component voor AEM Screens te maken. AEM Screens gebruikt veel bestaande ontwerppatronen en technologieën van andere AEM-producten opnieuw. In de zelfstudie worden verschillen en speciale overwegingen benadrukt bij het ontwikkelen voor AEM Screens.

## Overzicht {#overview}

Deze zelfstudie is bedoeld voor nieuwe ontwikkelaars van AEM Screens. In deze zelfstudie wordt een eenvoudige component &quot;Hello World&quot; gemaakt voor een volgnummer in AEM Screens. In een dialoogvenster kunnen auteurs de weergegeven tekst bijwerken.

![ overviewhellow ](assets/overviewhellow.png)

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [ AEM 6.5 ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes) plus het Meest recente Pak van de Eigenschap van Screens.

1. [ Speler van AEM Screens ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction)
1. Lokale ontwikkelomgeving

De stappen en de schermafbeeldingen van het leerprogramma worden uitgevoerd gebruikend **CRXDE-Lite**. IDEs kan ook worden gebruikt om het leerprogramma te voltooien. Meer informatie bij het gebruiken van winde om [ met AEM te ontwikkelen kan hier worden gevonden.](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup)


## Projectinstelling {#project-setup}

De broncode van een Screens-project wordt doorgaans beheerd als een Maven-project met meerdere modules. Om het leerprogramma te versnellen, werd een project pre-geproduceerd gebruikend [ Archetype 13 van het Project van AEM ](https://github.com/adobe/aem-project-archetype). Meer details bij [ het creëren van een project met Maven het Archetype van het Project van AEM kunnen hier ](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup) worden gevonden.

1. Download en installeer de volgende pakketten gebruikend [ Manager van het Pakket van CRX ](http://localhost:4502/crx/packmgr/index.jsp):

[Bestand ophalen](assets/base-screens-weretail-runuiapps-001-snapshot.zip)

   [ krijgt Dossier ](assets/base-screens-weretail-runuicontent-001-snapshot.zip)
   **naar keuze** als het werken met Verduistering of een andere winde, download het hieronder bronpakket. Implementeer het project in een lokale AEM-instantie met de opdracht Maven:

   **`mvn -PautoInstallPackage clean install`**

   Start HelloWorld SRC Screens `We.Retail` Project uitvoeren.

[Bestand ophalen](assets/src-screens-weretail-run.zip)

1. In [ de Manager van het Pakket van CRX ](http://localhost:4502/crx/packmgr/index.jsp), verifieer dat de volgende twee pakketten geïnstalleerd zijn:

   1. **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip**
   1. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip**

   ![ Screens Wij.Retail de pakketten van de Looppas Ui.Apps en Ui.Content die door als de Manager van het Pakket van CRX worden geïnstalleerd ](assets/crx-packages.png)

   Screens `We.Retail` Run `Ui.Apps` - en `Ui.Content` -pakketten geïnstalleerd via CRX Package Manager.

1. Het **screens-weretail-run.ui.apps** pakket installeert code onder `/apps/weretail-run`.

   Dit pakket bevat de code die verantwoordelijk is voor het renderen van aangepaste componenten voor het project. Dit pakket bevat componentcode en eventueel benodigde JavaScript of CSS. Dit pakket sluit ook **schermen-weretail-run.core-0.0.1-SNAPSHOT.jar** in die om het even welke code Java™ nodig door het project bevat.

   >[!NOTE]
   >
   >In deze zelfstudie wordt geen Java™-code geschreven. Als complexere bedrijfslogica nodig is, kan back-end Java™ worden gemaakt en geïmplementeerd met de Core Java™-bundel.

   ![ Vertegenwoordiging van de code ui.apps in CRXDE Lite ](assets/uipps-contents.png)

   Weergave van de code ui.apps in CRXDE Lite

   De **World van Hello** component is enkel placeholder. Tijdens de zelfstudie wordt functionaliteit toegevoegd waarmee een auteur het bericht kan bijwerken dat door de component wordt weergegeven.

1. Het **screens-weretail-run.ui.content** pakket installeert code onder:

   * `/conf/we-retail-run`
   * `/content/dam/we-retail-run`
   * `/content/screens/we-retail-run`

   Dit pakket bevat de eerste inhoud en configuratiestructuur die nodig zijn voor het project. **`/conf/we-retail-run`** bevat alle configuraties voor het `We.Retail` -project uitvoeren. **`/content/dam/we-retail-run`** bevat startende digitale elementen voor het project. **`/content/screens/we-retail-run`** bevat de Screens-inhoudsstructuur. De inhoud van al deze paden wordt voornamelijk in AEM bijgewerkt. Om de consistentie tussen omgevingen (lokaal, Ontwikkelen, Stage, Prod) te bevorderen, wordt vaak een basisinhoudsstructuur opgeslagen in bronbeheer.

1. **navigeer aan AEM Screens > `We.Retail` project van de Looppas:**

   Klik in het menu Start van AEM op het Screens-pictogram. Controleer of het `We.Retail` Run-project wordt weergegeven.

   ![ wij-detailul-looppas-starter ](assets/we-retaiul-run-starter.png)

## De Hello World-component maken {#hello-world-cmp}

De component Hello World is een eenvoudige component waarmee een gebruiker een bericht kan invoeren dat op het scherm moet worden weergegeven. De component is gebaseerd op het [ Malplaatje van de Component van AEM Screens: https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template).

AEM Screens heeft sommige interessante beperkingen die niet noodzakelijk waar voor traditionele componenten van Plaatsen WCM zijn.

* De meeste Screens-componenten moeten op volledig scherm worden uitgevoerd op de doelapparaten voor digitale handtekeningen
* De meeste Screens-componenten moeten in de volgordekanalen kunnen worden ingesloten om presentaties te kunnen genereren
* Authoring moet het mogelijk maken afzonderlijke componenten te bewerken in een reekskanaal, zodat het volledig scherm niet meer nodig is

1. In **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (of winde van keus) navigeren aan `/apps/weretail-run/components/content/helloworld.`

   Voeg de volgende eigenschappen toe aan de component `helloworld` :

   ```
       jcr:title="Hello World"
       sling:resourceSuperType="foundation/components/parbase"
       componentGroup="We.Retail Run - Content"
   ```

   ![ Eigenschappen voor /apps/weretail-run/components/content/helloworld ](assets/2018-04-28_at_4_23pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/helloworld

   De **component van de Wereld van 0&rbrace; Hello breidt de** stichting, componenten, parbase **component uit zodat kan het behoorlijk binnen een kanaal van de Opeenvolging worden gebruikt.**

1. Een bestand maken onder de naam `/apps/weretail-run/components/content/helloworld` `helloworld.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
   
    /apps/weretail-run/components/content/helloworld/helloworld.html
   
   */-->
   
   <!--/* production: preview authoring mode + unspecified mode (i.e. on publish) */-->
   <sly data-sly-test.production="${wcmmode.preview || wcmmode.disabled}" data-sly-include="production.html" />
   
   <!--/* edit: any other authoring mode, i.e. edit, design, scaffolding, etc. */-->
   <sly data-sly-test="${!production}" data-sly-include="edit.html" />
   ```

   De componenten van Screens vereisen twee verschillende teruggaven afhankelijk van welke [ auteurswijze ](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/authoring/author-environment-tools) wordt gebruikt:

   1. **Productie**: Voorproef of publiceer wijze (wcmmode=disabled)
   1. **geeft** uit: gebruikt voor alle andere auteurswijzen, namelijk uitgeven, ontwerp, steigers, ontwikkelaar...

   `helloworld.html` doet dienst als schakelaar, die welke auteurswijze actief is en aan een ander manuscript opnieuw richt HTML controleert. Schermcomponenten worden vaak gebruikt met een `edit.html` -script voor de bewerkingsmodus en een `production.html` -script voor de productiemodus.

1. Een bestand maken onder de naam `/apps/weretail-run/components/content/helloworld` `production.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
    /apps/weretail-run/components/content/helloworld/production.html
   
   */-->
   
   <div data-duration="${properties.duration}" class="cmp-hello-world">
    <h1 class="cmp-hello-world__message">${properties.message}</h1>
   </div>
   ```

   Het bovenstaande is de productiemarkering voor de component Hello World. Een attribuut `data-duration` wordt opgenomen aangezien de component op een kanaal van de Opeenvolging wordt gebruikt. Het attribuut `data-duration` wordt gebruikt door het kanaal van de Opeenvolging om te weten hoe lang een opeenvolgingspunt moet worden getoond.

   De component rendert een `div` - en een `h1` -tag met tekst. `${properties.message}` is een deel van het HTML-script dat de inhoud van een JCR-eigenschap met de naam `message` uitvoert. Later wordt een dialoogvenster gemaakt waarin een gebruiker een waarde voor de eigenschapstekst `message` kan invoeren.

   Merk ook op dat BEM-notatie (Block Element Modifier) wordt gebruikt met de component. BEM is een CSS-coderingsconventie die het gemakkelijker maakt om herbruikbare componenten te maken. BEM is de aantekening die door [ wordt gebruikt de Componenten van de Kern van AEM ](https://github.com/adobe/aem-core-wcm-components/wiki/CSS-coding-conventions). <!-- DEAD LINK More info can be found at: [https://getbem.com/](https://getbem.com/) -->

1. Een bestand maken onder de naam `/apps/weretail-run/components/content/helloworld` `edit.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
   
    /apps/weretail-run/components/content/helloworld/edit.html
   
   */-->
   
   <!--/* if message populated */-->
   <div
    data-sly-test.message="${properties.message}"
    class="aem-Screens-editWrapper cmp-hello-world">
    <p class="cmp-hello-world__message">${message}</p>
   </div>
   
   <!--/* empty place holder */-->
   <div data-sly-test="${!message}"
        class="aem-Screens-editWrapper cq-placeholder cmp-hello-world"
        data-emptytext="${'Hello World' @ i18n, locale=request.locale}">
   </div>
   ```

   Het bovenstaande is de bewerkte markering voor de component Hello World. In het eerste blok wordt een bewerkte versie van de component weergegeven als het dialoogvenster is gevuld.

   Het tweede blok wordt teruggegeven als geen bericht van de dialoogdoos is ingegaan. `cq-placeholder` en `data-emptytext` geven de etiket ***Wereld van Hello*** als plaatsaanduiding in dat geval terug. De tekenreeks voor het label kan met i18n worden geïnternationaliseerd ter ondersteuning van ontwerpen in meerdere landinstellingen.

1. **de Dialoogvenster van het Beeld van Screens van het Exemplaar dat voor de component van de Wereld van Hello moet worden gebruikt.**

   Het is het eenvoudigst om vanuit een bestaand dialoogvenster te beginnen en vervolgens wijzigingen aan te brengen.

   1. Kopieer het dialoogvenster van: `/libs/screens/core/components/content/image/cq:dialog`
   1. Het dialoogvenster onder plakken `/apps/weretail-run/components/content/helloworld`

   ![ exemplaar-beeld-dialoog ](assets/copy-image-dialog.gif)

1. **werk het de dialoogvakje van de Wereld van Hello bij om een lusje voor bericht te omvatten.**

   Werk het dialoogvenster bij, zodat dit overeenkomt met het volgende. De JCR-knooppuntstructuur van het laatste dialoogvenster wordt hieronder in XML weergegeven:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
       jcr:primaryType="nt:unstructured"
       jcr:title="Hello World"
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content
           jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/coral/foundation/tabs"
           size="L">
           <items jcr:primaryType="nt:unstructured">
               <message
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Message"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <message
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/textfield"
                                   fieldDescription="Message for component to display"
                                   fieldLabel="Message"
                                   name="./message"/>
                           </items>
                       </column>
                   </items>
               </message>
               <sequence
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Sequence"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <duration
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/numberfield"
                                   defaultValue=""
                                   fieldDescription="Amount of time the image is shown in the sequence, in milliseconds"
                                   fieldLabel="Duration (milliseconds)"
                                   min="0"
                                   name="./duration"/>
                           </items>
                       </column>
                   </items>
               </sequence>
           </items>
       </content>
   </jcr:root>
   ```

   Het tekstveld voor het bericht wordt opgeslagen naar een eigenschap met de naam `message` en dat het nummerveld voor de duur wordt opgeslagen naar een eigenschap met de naam `duration` . In `/apps/weretail-run/components/content/helloworld/production.html` door HTML wordt naar deze twee eigenschappen verwezen als `${properties.message}` en `${properties.duration}` .

   ![ de Wereld van Hello - voltooide dialoog ](assets/2018-04-29_at_5_21pm.png)

   Hello World - dialoogvenster voltooid

## Client-Side bibliotheken maken {#clientlibs}

Client-Side Libraries bieden een mechanisme voor het organiseren en beheren van CSS- en JavaScript-bestanden die nodig zijn voor een AEM-implementatie.

AEM Screens-componenten worden in de bewerkingsmodus anders weergegeven dan in de modus Voorbeeld-productie. Er worden twee clientbibliotheken gemaakt: een voor de bewerkingsmodus en een voor Voorvertoning-Productie.

1. Maak een map voor client-side bibliotheken voor de component Hello World.

   Onder `/apps/weretail-run/components/content/helloworld` maakt u een map met de naam `clientlibs` .

   ![ 2018-04-30_at_1046am ](assets/2018-04-30_at_1046am.png)

1. Onder de map `clientlibs` maakt u een knooppunt met de naam `shared` van het type `cq:ClientLibraryFolder` .

   ![ 2018-04-30_at_1115am ](assets/2018-04-30_at_1115am.png)

1. Voeg de volgende eigenschappen toe aan de gedeelde clientbibliotheek:

   * `allowProxy` | Boolean | `true`

   * `categories`| String [] | `cq.screens.components`

   ![ Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/shared ](assets/2018-05-03_at_1026pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/shared

   De eigenschap category is een tekenreeks die de clientbibliotheek identificeert. De cq.screens.componentCategorie wordt gebruikt in zowel Edit als voorproef-Productie wijze. Daarom wordt elke CSS of JS die in de sharedclientlib is gedefinieerd, in alle modi geladen.

   Het is aan te raden paden die rechtstreeks naar `/apps` in een productieomgeving gaan, nooit te zien. De eigenschap allowProxy zorgt ervoor dat naar de CSS- en JS-client-bibliotheek wordt verwezen via een voorvoegsel `/etc.clientlibs` .

1. Maak een bestand met de naam `css.txt` onder de gedeelde map.

   Vul het bestand met het volgende:

   ```
   #base=css
   
   styles.less
   ```

1. Maak een map met de naam `css` onder de map `shared` . Voeg een bestand met de naam `style.less` toe onder de map `css` . De structuur van de clientbibliotheken moet er nu als volgt uitzien:

   ![ 2018-04-30_at_3_11pm ](assets/2018-04-30_at_3_11pm.png)

   In plaats van CSS rechtstreeks te schrijven, gebruikt deze zelfstudie LESS. [ LESS ](https://lesscss.org/) is populaire CSS pre-compiler die CSS variabelen, mixins, en functies steunt. AEM-clientbibliotheken bieden native ondersteuning voor LESS-compilatie. U kunt de Klasse of andere pre-compilers gebruiken, maar u moet hen buiten AEM compileren.

1. Vul `/apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less` met het volgende:

   ```css
   /**
       Shared Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less
   
   **/
   
   .cmp-hello-world {
       background-color: #fff;
   
    &__message {
     color: #000;
     font-family: Helvetica;
     text-align:center;
    }
   }
   ```

1. Kopieer en plak de clientbibliotheekmap van `shared` om een clientbibliotheek met de naam `production` te maken.

   ![ Kopieer de gedeelde cliëntbibliotheek om een nieuwe bibliotheek van de productiecliënt tot stand te brengen ](assets/copy-clientlib.gif)

   Kopieer de gedeelde clientbibliotheek om een productieclientbibliotheek te maken.

1. De eigenschap `categories` van de productieclientbibliotheek bijwerken naar `cq.screens.components.production.`

   Zo zorgt u ervoor dat de stijlen alleen worden geladen in de modus Voorvertoning-productie.

   ![ Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/production ](assets/2018-04-30_at_5_04pm.png)

   Eigenschappen voor `/apps/weretail-run/components/content/helloworld/clientlibs/production` .

1. Vul `/apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less` met het volgende:

   ```css
   /**
       Production Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less
   
   **/
   .cmp-hello-world {
   
       height: 100%;
       width: 100%;
       position: fixed;
   
    &__message {
   
     position: relative;
     font-size: 5rem;
     top:25%;
    }
   }
   ```

   Bij de bovenstaande stijlen wordt het bericht gecentreerd weergegeven in het midden van het scherm, maar alleen in de productiemodus.

Een derde categorie in de clientbibliotheek: `cq.screens.components.edit` kan worden gebruikt om alleen-bewerkingsstijlen toe te voegen aan de component.

| Clientlib-categorie | Gebruik |
|---|---|
| `cq.screens.components` | Stijlen en scripts die worden gedeeld tussen de bewerkings- en de productiemodus |
| `cq.screens.components.edit` | Stijlen en scripts die alleen worden gebruikt in de bewerkingsmodus |
| `cq.screens.components.production` | Stijlen en scripts die alleen in de productiemodus worden gebruikt |

## Een ontwerppagina maken {#design-page}

AEM Screens gebruikt [ statische Malplaatjes van de Pagina ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/templates/page-templates-static) en [ configuraties van het Ontwerp ](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/siteandpage/default-components-designmode) voor globale veranderingen. De configuraties van het ontwerp worden vaak gebruikt om toegestane componenten voor Parsys op een kanaal te vormen. U kunt deze configuraties het beste op een toepassingsspecifieke manier opslaan.

Onder een `We.Retail` pagina Ontwerp uitvoeren wordt gecreeerd die alle configuraties specifiek voor het `We.Retail` project van de Looppas opslaat.

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs`, navigeer aan `/apps/settings/wcm/designs`.
1. Maak een knooppunt onder de map designs met de naam `we-retail-run` met het type `cq:Page` .
1. Voeg onder de pagina `we-retail-run` een ander knooppunt met de naam `jcr:content` van het type `nt:unstructured` toe. Voeg de volgende eigenschappen toe aan het knooppunt `jcr:content` :

   | Naam | Type | Waarde |
   |---|---|---|
   | `jcr:title` | String | `We.Retail` Uitvoeren |
   | `sling:resourceType` | String | `wcm`, `core`, `components`, `designer` |
   | `cq:doctype` | String | html_5 |

   ![ Pagina van het Ontwerp bij /apps/settings/wcm/designs/wij-retail-run ](assets/2018-05-07_at_1219pm.png)

   Ontwerppagina bij `/apps/settings/wcm/designs/we-retail-run` .

## Een volgend kanaal maken {#create-sequence-channel}

De Hello World-component is bedoeld voor gebruik op een volgnummer. Om de component te testen, wordt een nieuw kanaal van de Opeenvolging gecreeerd.

1. Van het Menu van het Begin van AEM, navigeer aan **Screens** > **`We.Retail`Looppas** > en klik **Kanalen**.

1. Klik **creëren** knoop

   1. Kies **tot Entiteit** leiden

   ![ 2018-04-30_at_5_18pm ](assets/2018-04-30_at_5_18pm.png)

1. In de wizard Maken:

1. De Stap van het malplaatje - kies **Kanaal van de Reeks 0&rbrace;**

   1. Eigenschappenstap

   * Basis Lusje > Titel = **Onactief Kanaal**
   * Het Lusje van het kanaal > controle **maakt kanaal online**

   ![ nutteloos-kanaal ](assets/idle-channel.gif)

1. Open de pagina-eigenschappen voor het onactieve kanaal.
1. Werk het ontwerpveld bij, zodat het naar `/apps/settings/wcm/designs/we-retail-run` verwijst, de ontwerppagina die in de vorige sectie is gemaakt.

   ![ Ontwerp config /apps/settings/wcm/designs/wij-retail-run ](assets/2018-05-07_at_1240pm.png)

   Ontwerpconfiguratie die wijst naar /apps/settings/wcm/designs/we-retail-run

1. Bewerk het nieuwe inactieve kanaal zodat u het kunt openen.

1. Schakelaar de paginamodus aan **Wijze van het Ontwerp**.

   1. Klik het **moersleutel** Pictogram in Parsys zodat kunt u de toegestane componenten vormen.

   1. Klik de **Screens** groep en de **`We.Retail`Looppas - de groep van de Inhoud**.

   ![ 2018-04-30_at_5_43pm ](assets/2018-04-30_at_5_43pm.png)

1. Schakelaar de paginamodus aan **geeft** uit. De Hello World-component kan nu aan de pagina worden toegevoegd en met andere het kanaalcomponenten van de Opeenvolging worden gecombineerd.

   ![ 2018-04-30_at_5_53pm ](assets/2018-04-30_at_5_53pm.png)

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs/we-retail-run/jcr%3Acontent/sequencechannel/par`, navigeer aan `/apps/settings/wcm/designs/we-retail-run/jcr:content/sequencechannel/par`. De eigenschap `components` bevat nu `group:Screens` , `group:We.Retail Run - Content` .

   ![ configuratie van het ontwerp onder /apps/settings/wcm/designs/wij-retail-run ](assets/2018-05-07_at_1_14pm.png)

   Ontwerpconfiguratie onder /apps/settings/wcm/designs/we-retail-run

## Sjabloon voor aangepaste handlers {#custom-handlers}

Als uw aangepaste component externe bronnen gebruikt, zoals elementen (afbeeldingen, video&#39;s, lettertypen en pictogrammen), specifieke elementuitvoeringen of clientbibliotheken (css en js), worden deze bronnen niet automatisch toegevoegd aan de offlineconfiguratie. De reden hiervoor is dat alleen de HTML-opmaakcode standaard in een pakket wordt opgenomen.

Adobe biedt een extensiemechanisme om de exacte elementen die naar de speler worden gedownload, aan te passen en te optimaliseren. Dit mechanisme is voor douanecomponenten om hun gebiedsdelen aan de off-line caching logica in AEM Screens bloot te stellen.

In de onderstaande sectie ziet u de sjabloon voor aangepaste offline bronhandlers. Ook worden de minimale vereisten in de `pom.xml` weergegeven voor dat specifieke project.

```java
package …;

import javax.annotation.Nonnull;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Reference;
import org.apache.felix.scr.annotations.Service;
import org.apache.sling.api.resource.Resource;
import org.apache.sling.api.resource.ResourceUtil;
import org.apache.sling.api.resource.ValueMap;

import com.adobe.cq.screens.visitor.OfflineResourceHandler;

@Service(value = OfflineResourceHandler.class)
@Component(immediate = true)
public class MyCustomHandler extends AbstractResourceHandler {

 @Reference
 private …; // OSGi services injection

 /**
  * The resource types that are handled by the handler.
  * @return the handled resource types
  */
 @Nonnull
 @Override
 public String[] getSupportedResourceTypes() {
     return new String[] { … };
 }

 /**
  * Accept the provided resource, visit and traverse it as needed.
  * @param resource The resource to accept
  */
 @Override
 public void accept(@Nonnull Resource resource) {
     ValueMap properties = ResourceUtil.getValueMap(resource);
     
     /* You can directly add explicit paths for offline caching using the `visit`
        method of the visitor. */
     
     // retrieve a custom property from the component
     String myCustomRenditionUrl = properties.get("myCustomRenditionUrl", String.class);
     // adding that exact asset/rendition/path to the offline manifest
     this.visitor.visit(myCustomRenditionUrl);
     
     
     /* You can delegate handling for dependent resources so they are also added to
        the offline cache using the `accept` method of the visitor. */
     
     // retrieve a referenced dependent resource
     String referencedResourcePath = properties.get("myOtherResource", String.class);
     ResourceResolver resolver = resource.getResourceResolver();
     Resource referencedResource = resolver.getResource(referencedResourcePath);
     // let the handler for that resource handle it
     if (referencedResource != null) {
         this.visitor.accept(referencedResource);
     }
   }
}
```

De volgende code bevat de minimumvereisten in de `pom.xml` voor dat specifieke project:

```css
   <dependencies>
        …
        <!-- Felix annotations -->
        <dependency>
            <groupId>org.apache.felix</groupId>
            <artifactId>org.apache.felix.scr.annotations</artifactId>
            <version>1.9.0</version>
            <scope>provided</scope>
        </dependency>

        <!-- Screens core bundle with OfflineResourceHandler/AbstractResourceHandler -->
        <dependency>
            <groupId>com.adobe.cq.screens</groupId>
            <artifactId>com.adobe.cq.screens</artifactId>
            <version>1.5.90</version>
            <scope>provided</scope>
        </dependency>
        …
      </dependencies>
```

**NOTA**: Als er AEM as a Cloud Service is, gebruik onder gebiedsdeel in `pom.xml` voor dat specifieke project.

```css
   <dependencies>
        …
        <!-- AEM Screens SDK API with OfflineResourceHandler/AbstractResourceHandler -->
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>aem-screens-sdk-api</artifactId>
            <version>1.0.8</version>
        </dependency>
        …
      </dependencies>
```

## Alles samenvoegen {#putting-it-all-together}

In de onderstaande video ziet u de voltooide component en de manier waarop deze aan een volgnummer kan worden toegevoegd. Het kanaal wordt vervolgens toegevoegd aan de weergave Locatie en uiteindelijk toegewezen aan een Screens-speler.

>[!VIDEO](https://video.tv.adobe.com/v/22385?quaity=9)

## Andere overwegingen voor aangepaste componenten die andere pagina&#39;s of fragmenten insluiten {#additional-considerations}

Houd rekening met de volgende twee beperkingen als uw aangepaste component andere pagina&#39;s of ervaringsfragmenten moet bevatten en u wilt dat wijzigingen in de ingesloten inhoud automatisch door de speler worden opgepakt (zonder het kanaal opnieuw te publiceren):

1. In plaats van `foundation/components/parbase` rechtstreeks uit te breiden, moet u ofwel `screens/core/components/content/page` ofwel `screens/core/components/content/experiencefragment` uitbreiden
2. De naam van de eigenschap die u gebruikt om naar de ingesloten inhoud te verwijzen, moet `pagePath` zijn.

Het gebruik van deze twee Screens-kerncomponenten biedt ook het extra voordeel dat ze kunnen zorgen voor het bundelen van een aantal afhankelijkheden die u nodig hebt (bibliotheken aan de clientzijde, lettertypen, enzovoort). Deze functionaliteit wordt gedaan door middel van hun off-line configuratieopties in de de dialoogdoos van de component. Het vermindert dan de verantwoordelijkheid van om het even welke douane off-line manager die u voor het zou moeten gebruiken. Het kan soms zelfs de noodzaak om er een te gebruiken helemaal uit verwijderen.

## Voltooide code {#finished-code}

Hieronder ziet u de voltooide code uit de zelfstudie. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** en **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** zijn de gecompileerde pakketten van AEM. **SRC-screens-weretail-looppas-0.0.1.zip &#x200B;** is de uncompiled broncode die kan worden opgesteld gebruikend Maven.

[Bestand ophalen](assets/screens-weretail-runuiapps-001-snapshot.zip)

[Bestand ophalen](assets/screens-weretail-runuicontent-001-snapshot.zip)

[Bestand ophalen](assets/screens-weretail-run.zip)
