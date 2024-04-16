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
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 0%

---

# Een aangepaste component voor AEM Screens ontwikkelen {#developing-a-custom-component-for-aem-screens}

De volgende zelfstudie doorloopt de stappen om een aangepaste component voor AEM Screens te maken. AEM Screens gebruikt veel bestaande ontwerppatronen en technologieën van andere AEM. In de zelfstudie worden verschillen en speciale overwegingen benadrukt bij het ontwikkelen voor AEM Screens.

## Overzicht {#overview}

Deze zelfstudie is bedoeld voor nieuwe ontwikkelaars van AEM Screens. In deze zelfstudie wordt een eenvoudige component &quot;Hello World&quot; gemaakt voor een volgnummer in AEM Screens. In een dialoogvenster kunnen auteurs de weergegeven tekst bijwerken.

![overzien](assets/overviewhellow.png)

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [AEM 6,5](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes) plus het nieuwste pakket met schermfuncties.

1. [AEM Screens Player](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction)
1. Lokale ontwikkelomgeving

De stappen en schermafbeeldingen van de zelfstudie worden uitgevoerd met **CRXDE-Lite**. IDEs kan ook worden gebruikt om het leerprogramma te voltooien. Meer informatie over het gebruiken van winde om te ontwikkelen [met AEM kunt u hier vinden.](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup)


## Projectinstelling {#project-setup}

De broncode van een project van het Scherm wordt typisch geleid als multi-module Maven project. Om de zelfstudie te versnellen, werd een project vooraf gegenereerd met de [Projectarchetype AEM 13](https://github.com/adobe/aem-project-archetype). Meer informatie over [een project maken met Maven AEM Project Archetype:](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup).

1. De volgende pakketten downloaden en installeren met [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp):

[Bestand ophalen](assets/base-screens-weretail-runuiapps-001-snapshot.zip)

   [Bestand ophalen](assets/base-screens-weretail-runuicontent-001-snapshot.zip)
   **Optioneel** als het werken met Eclipse of een andere winde het hieronder bronpakket downloadt. Stel het project aan een lokale AEM instantie op door het Maven bevel te gebruiken:

   **`mvn -PautoInstallPackage clean install`**

   HelloWorld SRC-schermen starten `We.Retail` Project uitvoeren.

[Bestand ophalen](assets/src-screens-weretail-run.zip)

1. In [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp)controleert u of de volgende twee pakketten zijn geïnstalleerd:

   1. **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip**
   1. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip**

   ![Schermen die wij.Retail Run UI.Apps en Ui.Content pakketten installeren via CRX Package Manager](assets/crx-packages.png)

   Schermen `We.Retail` Uitvoeren `Ui.Apps` en `Ui.Content` pakketten geïnstalleerd via CRX Package Manager.

1. De **screens-weretail-run.ui.apps** pakket installeert code onder `/apps/weretail-run`.

   Dit pakket bevat de code die verantwoordelijk is voor het renderen van aangepaste componenten voor het project. Dit pakket bevat componentcode en eventuele benodigde JavaScript- of CSS-code. Dit pakket sluit ook in **screens-weretail-run.core-0.0.1-SNAPSHOT.jar** die Java™-code bevat die nodig is voor het project.

   >[!NOTE]
   >
   >In deze zelfstudie wordt geen Java™-code geschreven. Als complexere bedrijfslogica nodig is, kan back-end Java™ worden gemaakt en geïmplementeerd met de Core Java™-bundel.

   ![Weergave van de code ui.apps in CRXDE Lite](assets/uipps-contents.png)

   Weergave van de code ui.apps in CRXDE Lite

   De **Hallo wereld** is slechts een plaatsaanduiding. Tijdens de zelfstudie wordt functionaliteit toegevoegd waarmee een auteur het bericht kan bijwerken dat door de component wordt weergegeven.

1. De **screens-weretail-run.ui.content** pakket installeert code onder:

   * `/conf/we-retail-run`
   * `/content/dam/we-retail-run`
   * `/content/screens/we-retail-run`

   Dit pakket bevat de eerste inhoud en configuratiestructuur die nodig zijn voor het project. **`/conf/we-retail-run`** bevat alle configuraties voor de `We.Retail` Project uitvoeren. **`/content/dam/we-retail-run`** omvat het starten van digitale elementen voor het project. **`/content/screens/we-retail-run`** bevat de structuur van de inhoud van het Scherm. De inhoud onder al deze paden wordt voornamelijk in AEM bijgewerkt. Om de consistentie tussen omgevingen (lokaal, Ontwikkelen, Stage, Prod) te bevorderen, wordt vaak een basisinhoudsstructuur opgeslagen in bronbeheer.

1. **Ga naar de AEM Screens > `We.Retail` Project uitvoeren:**

   Klik in het menu AEM Start op het pictogram Schermen. Controleer de `We.Retail` Project uitvoeren wordt gezien.

   ![wij-kleinhandelaarster](assets/we-retaiul-run-starter.png)

## De Hello World-component maken {#hello-world-cmp}

De component Hello World is een eenvoudige component waarmee een gebruiker een bericht kan invoeren dat op het scherm moet worden weergegeven. De component is gebaseerd op de [AEM Screens-componentsjabloon: https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template).

AEM Screens heeft sommige interessante beperkingen die niet noodzakelijk waar voor traditionele componenten van Plaatsen WCM zijn.

* De meeste componenten van het Scherm moeten in volledig scherm op de doeldigitale signaalapparaten lopen
* De meeste componenten van het Scherm moeten in de opeenvolgingskanalen inbedbaar zijn om diapresentaties te produceren
* Authoring moet het mogelijk maken afzonderlijke componenten te bewerken in een reekskanaal, zodat het volledig scherm niet meer nodig is

1. In **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (of IDE van keus) navigeer aan `/apps/weretail-run/components/content/helloworld.`

   Voeg de volgende eigenschappen toe aan de `helloworld` component:

   ```
       jcr:title="Hello World"
       sling:resourceSuperType="foundation/components/parbase"
       componentGroup="We.Retail Run - Content"
   ```

   ![Eigenschappen voor /apps/weretail-run/components/content/helloworld](assets/2018-04-28_at_4_23pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/helloworld

   De **Hallo wereld** component breidt de **stichting/componenten/parbase** zodat deze op de juiste manier binnen een volgnummer kan worden gebruikt.

1. Een bestand maken onder `/apps/weretail-run/components/content/helloworld` benoemd `helloworld.html.`

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

   Schermcomponenten vereisen twee verschillende weergaven afhankelijk van welke [ontwerpmodus](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/authoring/author-environment-tools) wordt gebruikt:

   1. **Productie**: Modus Voorvertoning of Publiceren (wcmmode=disabled)
   1. **Bewerken**: wordt gebruikt voor alle andere ontwerpmodi, zoals bewerken, ontwerpen, basisstructuur, ontwikkelaar...

   `helloworld.html`handelt als schakelaar, die welke auteurswijze controleert en aan een ander manuscript van HTML opnieuw richt. Een algemene regel die door rasteronderdelen wordt gebruikt, is het hebben van een `edit.html` script voor de bewerkingsmodus en een `production.html` script voor de productiemodus.

1. Een bestand maken onder `/apps/weretail-run/components/content/helloworld` benoemd `production.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
    /apps/weretail-run/components/content/helloworld/production.html
   
   */-->
   
   <div data-duration="${properties.duration}" class="cmp-hello-world">
    <h1 class="cmp-hello-world__message">${properties.message}</h1>
   </div>
   ```

   Het bovenstaande is de productiemarkering voor de Hello World-component. A `data-duration` wordt opgenomen aangezien de component op een kanaal van de Opeenvolging wordt gebruikt. De `data-duration` wordt gebruikt door het opeenvolgingskanaal om te weten hoe lang een opeenvolgingspunt moet worden getoond.

   De component rendert een `div` en `h1` -tag met tekst. `${properties.message}` is een deel van het manuscript van HTML dat de inhoud van een bezit JCR uitvoert dat wordt genoemd `message`. Later wordt een dialoogvenster gemaakt waarin een gebruiker een waarde voor het dialoogvenster `message` eigenschapstekst.

   Merk ook op dat BEM-notatie (Block Element Modifier) wordt gebruikt met de component. BEM is een CSS-coderingsconventie die het gemakkelijker maakt om herbruikbare componenten te maken. BEM is de notatie die wordt gebruikt door [AEM kerncomponenten](https://github.com/adobe/aem-core-wcm-components/wiki/CSS-coding-conventions). <!-- DEAD LINK More info can be found at: [https://getbem.com/](https://getbem.com/) -->

1. Een bestand maken onder `/apps/weretail-run/components/content/helloworld` benoemd `edit.html.`

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

   Het bovenstaande is de bewerkte markering voor de Hello World-component. In het eerste blok wordt een bewerkte versie van de component weergegeven als het dialoogvenster is gevuld.

   Het tweede blok wordt teruggegeven als geen dialoogdoos is ingegaan. De `cq-placeholder` en `data-emptytext` het label renderen ***Hallo wereld*** als plaatsaanduiding in dat geval. De tekenreeks voor het label kan met i18n worden geïnternationaliseerd ter ondersteuning van ontwerpen in meerdere landinstellingen.

1. **Het dialoogvenster Schermafbeelding kopiëren dat moet worden gebruikt voor de component Hello World.**

   Het is het gemakkelijkst om van een bestaande dialoog te beginnen en dan wijzigingen te maken.

   1. Het dialoogvenster kopiëren van: `/libs/screens/core/components/content/image/cq:dialog`
   1. Het dialoogvenster onder plakken `/apps/weretail-run/components/content/helloworld`

   ![copy-image-dialog](assets/copy-image-dialog.gif)

1. **Werk het dialoogvenster Hello World bij en voeg een tabblad voor het bericht toe.**

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

   Het tekstveld voor het bericht wordt opgeslagen naar een eigenschap met de naam `message` en dat het nummerveld voor de Duur wordt opgeslagen naar een eigenschap met de naam `duration`. Naar deze twee eigenschappen wordt in `/apps/weretail-run/components/content/helloworld/production.html` door HTL als `${properties.message}` en `${properties.duration}`.

   ![Hello World - dialoogvenster voltooid](assets/2018-04-29_at_5_21pm.png)

   Hello World - dialoogvenster voltooid

## Client-Side bibliotheken maken {#clientlibs}

Client-Side Libraries bieden een mechanisme voor het organiseren en beheren van CSS- en JavaScript-bestanden die nodig zijn voor een AEM-implementatie.

AEM Screens-componenten worden in de bewerkingsmodus anders weergegeven dan in de modus Voorbeeld/productie. Er worden twee clientbibliotheken gemaakt: een voor de bewerkingsmodus en een voor Voorvertoning/Productie.

1. Maak een map voor client-side bibliotheken voor de component Hello World.

   Beneath `/apps/weretail-run/components/content/helloworld`, maakt u een map met de naam `clientlibs`.

   ![2018-04-30_at_1046am](assets/2018-04-30_at_1046am.png)

1. Onder de `clientlibs` map, een knooppunt maken met de naam `shared` van het type `cq:ClientLibraryFolder`.

   ![2018-04-30_at_1115am](assets/2018-04-30_at_1115am.png)

1. Voeg de volgende eigenschappen toe aan de gedeelde clientbibliotheek:

   * `allowProxy` | Boolean | `true`

   * `categories`| String[] | `cq.screens.components`

   ![Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/shared](assets/2018-05-03_at_1026pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/shared

   De eigenschap category is een tekenreeks die de clientbibliotheek identificeert. De categorie cq.screens.component wordt gebruikt in zowel de modus Bewerken als de modus Voorbeeld/productie. Daarom wordt elke CSS/JS die in de sharedclientLib is gedefinieerd, in alle modi geladen.

   Het is aan te raden geen paden in een productieomgeving rechtstreeks toegankelijk te maken voor /apps. De eigenschap allowProxy zorgt ervoor dat naar de CSS- en JS-clientbibliotheek wordt verwezen via het voorvoegsel of/etc.clientlibs.

1. Bestandsnaam maken `css.txt` onder de gedeelde map.

   Vul het bestand met het volgende:

   ```
   #base=css
   
   styles.less
   ```

1. Een map maken met de naam `css` onder de `shared` map. Een bestand met de naam toevoegen `style.less` onder de `css` map. De structuur van de clientbibliotheken moet er nu als volgt uitzien:

   ![2018-04-30_11:00](assets/2018-04-30_at_3_11pm.png)

   In plaats van CSS rechtstreeks te schrijven, gebruikt deze zelfstudie LESS. [MINDER](https://lesscss.org/) is een populaire CSS-voorcompiler die CSS-variabelen, -mixins en -functies ondersteunt. AEM clientbibliotheken ondersteunen native LESS-compilatie. De klasse of andere pre-compilers kunnen worden gebruikt maar moeten buiten AEM worden gecompileerd.

1. Vullen `/apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less` met het volgende:

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

1. Kopieer en plak de `shared` clientbibliotheekmap om een clientbibliotheek te maken met de naam `production`.

   ![Kopieer de gedeelde clientbibliotheek om een nieuwe productieclientbibliotheek te maken](assets/copy-clientlib.gif)

   Kopieer de gedeelde clientbibliotheek om een productieclientbibliotheek te maken.

1. Werk de `categories` eigenschap van de productiecliënt die moet worden `cq.screens.components.production.`

   Dit zorgt ervoor dat de stijlen alleen worden geladen in de modus Voorbeeld/productie.

   ![Eigenschappen voor /apps/weretail-run/components/content/helloworld/clientlibs/production](assets/2018-04-30_at_5_04pm.png)

   Eigenschappen voor `/apps/weretail-run/components/content/helloworld/clientlibs/production`.

1. Vullen `/apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less` met het volgende:

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

Een derde categorie voor clientbibliotheken: `cq.screens.components.edit` kan worden gebruikt om alleen-bewerken specifieke stijlen toe te voegen aan de component.

| Clientlib-categorie | Gebruik |
|---|---|
| `cq.screens.components` | Stijlen en scripts die worden gedeeld tussen de bewerkings- en de productiemodus |
| `cq.screens.components.edit` | Stijlen en scripts die alleen worden gebruikt in de bewerkingsmodus |
| `cq.screens.components.production` | Stijlen en scripts die alleen in de productiemodus worden gebruikt |

## Een ontwerppagina maken {#design-page}

AEM Screens gebruikt [statische paginasjablonen](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/templates/page-templates-static) en [Ontwerpconfiguraties](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/siteandpage/default-components-designmode) voor algemene wijzigingen. De configuraties van het ontwerp worden vaak gebruikt om toegestane componenten voor Parsys op een kanaal te vormen. U kunt deze configuraties het beste op een toepassingsspecifieke manier opslaan.

Onder een `We.Retail` De pagina van het Ontwerp van de looppas wordt gecreeerd die alle configuraties specifiek voor `We.Retail` Project uitvoeren.

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs`, navigeer naar `/apps/settings/wcm/designs`.
1. Maak een knooppunt onder de map designs met de naam `we-retail-run` met een type `cq:Page`.
1. Onder de `we-retail-run` pagina, een ander knooppunt toevoegen met de naam `jcr:content` van het type `nt:unstructured`. Voeg de volgende eigenschappen toe aan de `jcr:content` knooppunt:

   | Naam | Type | Waarde |
   |---|---|---|
   | `jcr:title` | String | `We.Retail` Uitvoeren |
   | `sling:resourceType` | String | wcm/core/components/ontwerper |
   | `cq:doctype` | String | html_5 |

   ![Ontwerppagina op /apps/settings/wcm/designs/we-Retail-run](assets/2018-05-07_at_1219pm.png)

   Ontwerppagina bij `/apps/settings/wcm/designs/we-retail-run`.

## Een volgend kanaal maken {#create-sequence-channel}

De Hello World-component is bedoeld voor gebruik op een Volgekanaal. Om de component te testen, wordt een nieuw Kanaal van de Opeenvolging gecreeerd.

1. Navigeer in het menu AEM Start naar **Schermen** > **`We.Retail`Uitvoeren** > en klik op **Kanalen**.

1. Klik op de knop **Maken** knop

   1. Kies **Entiteit maken**

   ![2018-04-30_17_05](assets/2018-04-30_at_5_18pm.png)

1. In de wizard Maken:

1. Sjabloonstap - kies **Volgekanaal**

   1. Eigenschappenstap

   * Basistabblad > Titel = **Niet-actief kanaal**
   * Tabblad Kanaal > Controleren **Kanaal online maken**

   ![niet-kanaals](assets/idle-channel.gif)

1. Open de pagina-eigenschappen voor het onactieve kanaal.
1. Het veld Ontwerp bijwerken, zodat het naar `/apps/settings/wcm/designs/we-retail-run`, de ontwerppagina die in de vorige sectie is gemaakt.

   ![Ontwerpconfig /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1240pm.png)

   Ontwerpconfiguratie die wijst naar /apps/settings/wcm/designs/we-retail-run

1. Bewerk het nieuwe inactieve kanaal zodat u het kunt openen.

1. De paginamodus wijzigen in **Ontwerp** Modus.

   1. Klik op de knop **moersleutel** Pictogram in Parsys zodat kunt u de toegestane componenten vormen.

   1. Klik op de knop **Schermen** en de **`We.Retail`Uitvoeren - Inhoud** groep.

   ![2018-04-30_om_5_43:00](assets/2018-04-30_at_5_43pm.png)

1. De paginamodus wijzigen in **Bewerken**. De component Hello World kan nu aan de pagina worden toegevoegd en met andere componenten van het opeenvolgingskanaal worden gecombineerd.

   ![2018-04-30_10_07](assets/2018-04-30_at_5_53pm.png)

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs/we-retail-run/jcr%3Acontent/sequencechannel/par`, navigeer naar `/apps/settings/wcm/designs/we-retail-run/jcr:content/sequencechannel/par`. Let op: `components` eigenschap bevat nu `group:Screens`, `group:We.Retail Run - Content`.

   ![Ontwerpconfiguratie onder /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1_14pm.png)

   Ontwerpconfiguratie onder /apps/settings/wcm/designs/we-retail-run

## Sjabloon voor aangepaste handlers {#custom-handlers}

Als uw aangepaste component externe bronnen gebruikt, zoals elementen (afbeeldingen, video&#39;s, lettertypen en pictogrammen), specifieke elementuitvoeringen of clientbibliotheken (css en js), worden deze niet automatisch toegevoegd aan de offlineconfiguratie. De reden is dat alleen de markering HTML standaard is gebundeld.

Om u te laten aanpassen en de nauwkeurige activa optimaliseren die aan de speler worden gedownload, biedt de Adobe een uitbreidingsmechanisme voor douanecomponenten aan om hun gebiedsdelen aan de off-line caching logica in AEM Screens bloot te stellen.

In de onderstaande sectie ziet u de sjabloon voor aangepaste offline bronhandlers en de minimumvereisten in de `pom.xml` voor dat specifieke project.

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

De volgende code bevat de minimumvereisten in het `pom.xml` voor dat specifieke project:

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

## Alles samenvoegen {#putting-it-all-together}

In de onderstaande video ziet u de voltooide component en de manier waarop deze aan een volgnummer kan worden toegevoegd. Het kanaal wordt vervolgens toegevoegd aan de weergave Locatie en uiteindelijk toegewezen aan een schermspeler.

>[!VIDEO](https://video.tv.adobe.com/v/22385?quaity=9)

## Andere overwegingen voor aangepaste componenten die andere pagina&#39;s of fragmenten insluiten {#additional-considerations}

Houd rekening met de volgende twee beperkingen als uw aangepaste component andere pagina&#39;s of ervaringsfragmenten moet bevatten en u wilt dat wijzigingen in de ingesloten inhoud automatisch door de speler worden opgepakt (zonder het kanaal opnieuw te publiceren):

1. In plaats van rechtstreeks uit te breiden `foundation/components/parbase`, moet u beide `screens/core/components/content/page` of `screens/core/components/content/experiencefragment`
2. De naam van de eigenschap die u gebruikt om naar de ingesloten inhoud te verwijzen, moet `pagePath`.

Het gebruik van deze twee kerncomponenten van het Scherm wordt ook geleverd met het extra voordeel dat zij kunnen zorgen voor het bundelen van sommige gebiedsdelen u nodig hebt (cliënt-zijbibliotheken, doopvonten, etc.). Zij doen dit door hun off-line configuratieopties in de doos van de componentendialoog, die dan de verantwoordelijkheid van om het even welke douane off-line manager vermindert u voor dit zou moeten gebruiken. Het kan soms zelfs de noodzaak om er een te gebruiken helemaal uit verwijderen.

## Voltooide code {#finished-code}

Hieronder ziet u de voltooide code uit de zelfstudie. De **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** en **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** Dit zijn de gecompileerde AEM pakketten. **SRC-screens-weretail-looppas-0.0.1.zip **is de uncompiled broncode die kan worden opgesteld gebruikend Maven.

[Bestand ophalen](assets/screens-weretail-runuiapps-001-snapshot.zip)

[Bestand ophalen](assets/screens-weretail-runuicontent-001-snapshot.zip)

[Bestand ophalen](assets/screens-weretail-run.zip)
