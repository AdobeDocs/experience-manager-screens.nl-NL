---
title: Een AEM-rastercomponent uitbreiden
seo-title: Een AEM-rastercomponent uitbreiden
description: In de volgende zelfstudie worden de stappen en aanbevolen procedures doorlopen voor het uitbreiden uit de box AEM Screens-componenten. De component Image wordt uitgebreid om een aanwendbare tekstbedekking toe te voegen.
seo-description: In de volgende zelfstudie worden de stappen en aanbevolen procedures doorlopen voor het uitbreiden uit de box AEM Screens-componenten. De component Image wordt uitgebreid om een aanwendbare tekstbedekking toe te voegen.
uuid: 38ee3a2b-a51a-4c35-b93a-89a0e5fc3837
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
discoiquuid: 46bdc191-5056-41a4-9804-8f7c4a035abf
targetaudience: target-audience new
translation-type: tm+mt
source-git-commit: ec8324ead3789a6cd5dde35a932c89e916709f70

---


# Een AEM-rastercomponent uitbreiden {#extending-an-aem-screens-component}

In de volgende zelfstudie worden de stappen en aanbevolen procedures doorlopen voor het uitbreiden uit de box AEM Screens-componenten. De component Image wordt uitgebreid om een aanwendbare tekstbedekking toe te voegen.

## Overzicht {#overview}

Deze zelfstudie is bedoeld voor ontwikkelaars die geen ervaring hebben met AEM-schermen. In deze zelfstudie wordt de component Schermafbeelding uitgebreid om een postercomponent te maken. Boven op een afbeelding worden een titel, beschrijving en logo geplaatst om een aantrekkelijke ervaring te creëren in een sequentiekanaal.

>[!NOTE]
>
>Voordat u met deze zelfstudie begint, wordt u aangeraden de zelfstudie te voltooien: Een aangepaste component [ontwikkelen voor AEM-schermen](developing-custom-component-tutorial-develop.md).

![Aangepaste postercomponent](assets/2018-05-07_at_4_09pm.png)

De component van de Poster van de douane wordt gecreeerd door de component van het Beeld uit te breiden.

## Vereisten {#prerequisites}

Voor het voltooien van deze zelfstudie is het volgende nodig:

1. [AEM 6.4](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/release-notes.html) of [AEM 6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes.html) + Latest Screen Feature Pack
1. [AEM-schermspeler](/help/user-guide/aem-screens-introduction.md)
1. Lokale ontwikkelomgeving

De lesstappen en schermafbeeldingen worden uitgevoerd met behulp van CRXDE-Lite. [Eclipse](https://docs.adobe.com/content/help/en/experience-manager-64/developing/devtools/aem-eclipse.html) of [IntelliJ](https://docs.adobe.com/content/help/en/experience-manager-64/developing/devtools/ht-intellij.html) IDEs kan ook worden gebruikt om het leerprogramma te voltooien. Hier [vindt u meer informatie over het gebruik van een IDE voor](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/project-setup.html#eclipse-ide)ontwikkeling met AEM.

## Projectinstelling {#project-setup}

De broncode van een project van het Scherm wordt typisch geleid als multi-module Maven project. Om de zelfstudie te versnellen, werd een project pre-geproduceerd gebruikend het Archetype 13 van het Project van [AEM](https://github.com/adobe/aem-project-archetype). Meer informatie over het [maken van een project met Maven AEM Project Archetype vindt u hier](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/project-setup.html#maven-multimodule).

1. De volgende pakketten downloaden en installeren met behulp van **CRX-pakketbeheer**`http://localhost:4502/crx/packmgr/index.jsp)r:`

   [Bestand ophalen](assets/start-poster-screens-weretail-runuiapps-001-snapshot.zip)

   [Bestand ophalen](assets/start-poster-screens-weretail-runuicontent-001-snapshot.zip)
   **Als u met Eclipse of een andere IDE werkt,** kunt u het onderstaande bronpakket downloaden. Implementeer het project in een lokale AEM-instantie met de opdracht Maven:

   **`mvn -PautoInstallPackage clean install`**

   Start SRC schermen Web.Retail Run Project

   [Bestand ophalen](assets/start-poster-screens-weretail-run.zip)

1. In **CRX Package Manager** worden `http://localhost:4502/crx/packmgr/index.jsp` de volgende twee pakketten geïnstalleerd:

   1. **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip**
   1. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip**
   ![Schermen die wij.Retail Run UI.Apps en Ui.Content pakketten installeren via CRX Package Manager](assets/crx-packages.png)

   Schermen die wij.Retail Run UI.Apps en Ui.Content pakketten installeren via CRX Package Manager

## De postercomponent maken {#poster-cmp}

De component Poster breidt de afbeelding uit van het vak met rasters. Een mechanisme van het Sling, `sling:resourceSuperType`, wordt gebruikt om de kernfunctionaliteit van de component van het Beeld te erven zonder het moeten kopiëren en kleven. Meer informatie over de basisbeginselen van de verwerking van [verkoopaanvragen vindt u hier.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/the-basics.html#SlingRequestProcessing)

De postercomponent wordt op volledig scherm weergegeven in de modus Voorvertoning/Productie. In de bewerkingsmodus is het belangrijk dat de component anders wordt gerenderd om het ontwerpen van het sequentiekanaal te vergemakkelijken.

1. In **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (of winde van keus) onderaan om een nieuwe `/apps/weretail-run/components/content`genoemde `cq:Component` tot stand te brengen `poster`.

   Voeg de volgende eigenschappen toe aan de `poster` component:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Poster"
       sling:resourceSuperType="screens/core/components/content/image"
       componentGroup="We.Retail Run - Content"/>
   ```

   ![Eigenschappen voor /apps/weretail-run/components/content/poster](assets/poster.png)

   Eigenschappen voor /apps/weretail-run/components/content/poster

   Wanneer u de `sling:resourceSuperType`eigenschap gelijk aan `screens/core/components/content/image` de postercomponent instelt, wordt alle functionaliteit van de afbeeldingscomponent overgeërfd. Onder de `screens/core/components/content/image` component gevonden gelijkwaardige knooppunten en bestanden `poster` kunnen worden toegevoegd om de functionaliteit te overschrijven en uit te breiden.

1. Kopieer het `cq:editConfig` knooppunt onder `/libs/screens/core/components/content/image.`Plakken `cq:editConfig` onder de `/apps/weretail-run/components/content/poster` component.

   Op het `cq:editConfig/cq:dropTargets/image/parameters` knooppunt werkt u de `sling:resourceType` eigenschap op hetzelfde bij `weretail-run/components/content/poster`.

   ![bewerken-config](assets/edit-config.png)

   XML-representatie van de cq:editConfig hieronder weergegeven:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
       jcr:primaryType="cq:EditConfig">
       <cq:dropTargets jcr:primaryType="nt:unstructured">
           <image
               jcr:primaryType="cq:DropTargetConfig"
               accept="[image/.*]"
               groups="[media]"
               propertyName="./fileReference">
               <parameters
                   jcr:primaryType="nt:unstructured"
                   sling:resourceType="weretail-run/components/content/poster"
                   imageCrop=""
                   imageMap=""
                   imageRotate=""/>
           </image>
       </cq:dropTargets>
   </jcr:root>
   ```

1. Het `image` dialoogvenster WCM Foundation kopiëren dat voor de `poster` component moet worden gebruikt.

   Het is het gemakkelijkst om van een bestaande dialoog te beginnen en dan wijzigingen te maken.

   1. Het dialoogvenster kopiëren van: `/libs/wcm/foundation/components/image/cq:dialog`
   1. Het dialoogvenster onder plakken `/apps/weretail-run/components/content/poster`
   ![Gekopieerd dialoogvenster van /libs/wcm/foundation/components/image/cq:dialoogvenster naar /apps/weretail-run/components/content/poster](assets/2018-05-03_at_4_13pm.png)

   Gekopieerd dialoogvenster van /libs/wcm/foundation/components/image/cq:dialoogvenster naar /apps/weretail-run/components/content/poster

   De `image` component van het Scherm wordt gesupertypeerd aan de `image` component van de Stichting WCM. Daarom erft de `poster` component functionaliteit van beide. De dialoog voor de postercomponent bestaat uit een combinatie van de dialoogvensters Schermen en Stichting. Functies van de **Sling Resource Merger** worden gebruikt om irrelevante dialoogvelden en tabbladen te verbergen die zijn overgeërfd van de componenten met supertype.

1. Werk de cq:dialog hieronder bij `/apps/weretail-run/components/content/poster` met de volgende wijzigingen in XML:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
       jcr:primaryType="nt:unstructured"
       jcr:title="Poster"
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content
           jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/foundation/container">
           <layout
               jcr:primaryType="nt:unstructured"
               sling:resourceType="granite/ui/components/foundation/layouts/tabs"
               type="nav"/>
           <items jcr:primaryType="nt:unstructured">
               <image
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Elements"
                   sling:resourceType="granite/ui/components/foundation/section">
                   <layout
                       jcr:primaryType="nt:unstructured"
                       sling:resourceType="granite/ui/components/foundation/layouts/fixedcolumns"
                       margin="{Boolean}false"/>
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/foundation/container">
                           <items
                               jcr:primaryType="nt:unstructured"
                               sling:hideChildren="[linkURL,size]">
                               <file
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="cq/gui/components/authoring/dialog/fileupload"
                                   autoStart="{Boolean}false"
                                   class="cq-droptarget"
                                   fieldLabel="Image asset"
                                   fileNameParameter="./fileName"
                                   fileReferenceParameter="./fileReference"
                                   mimeTypes="[image]"
                                   multiple="{Boolean}false"
                                   name="./file"
                                   title="Upload Image Asset"
                                   uploadUrl="${suffix.path}"
                                   useHTML5="{Boolean}true"/>
                               <title
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/foundation/form/textfield"
                                   fieldLabel="Title"
                                   name="./jcr:title"/>
                               <description
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/foundation/form/textarea"
                                   fieldLabel="Description"
                                   name="./jcr:description"/>
                               <position
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/select"
                                   fieldLabel="Text Position"
                                   name="./textPosition">
                                   <items jcr:primaryType="nt:unstructured">
                                       <left
                                           jcr:primaryType="nt:unstructured"
                                           text="Left"
                                           value="left"/>
                                       <center
                                           jcr:primaryType="nt:unstructured"
                                           text="Center"
                                           value="center"/>
                                       <right
                                           jcr:primaryType="nt:unstructured"
                                           text="Right"
                                           value="right"/>
                                   </items>
                               </position>
                               <color
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/select"
                                   fieldLabel="Text Color"
                                   name="./textColor">
                                   <items jcr:primaryType="nt:unstructured">
                                       <light
                                           jcr:primaryType="nt:unstructured"
                                           text="Light"
                                           value="light"/>
                                       <dark
                                           jcr:primaryType="nt:unstructured"
                                           text="Dark"
                                           value="dark"/>
                                   </items>
                               </color>
                           </items>
                       </column>
                   </items>
               </image>
               <accessibility
                   jcr:primaryType="nt:unstructured"
                   sling:hideResource="{Boolean}true"/>
           </items>
       </content>
   </jcr:root>
   ```

   De eigenschap `sling:hideChildren`= `"[linkURL,size]`&quot; wordt gebruikt op het `items` knooppunt om ervoor te zorgen dat de velden **linkURL** en **size** worden verborgen in het dialoogvenster. Het is niet voldoende deze knooppunten uit het posterdialoogvenster te verwijderen. De eigenschap `sling:hideResource="{Boolean}true"` op het tabblad Toegankelijkheid wordt gebruikt om het hele tabblad te verbergen.

   Er worden twee geselecteerde velden toegevoegd aan het dialoogvenster, zodat auteurs de tekstpositie en -kleur van de titel en beschrijving kunnen bepalen.

   ![Poster - Definitieve dialoogstructuur](assets/2018-05-03_at_4_49pm.png)

   Poster - Definitieve dialoogstructuur

   Op dit punt kan een geval van de `poster` component aan de **Onactieve pagina van het Kanaal** in het Web.Retail project van de Looppas worden toegevoegd: `http://localhost:4502/editor.html/content/screens/we-retail-run/channels/idle-channel.edit.html`.

   ![Dialoogvensters Poster](assets/poster-dialog-full.png)

   Dialoogvensters Poster

1. Een bestand maken onder de `/apps/weretail-run/components/content/poster` naam `production.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
   
       /apps/weretail-run/components/content/poster/production.html
   
   */-->
   <div data-sly-use.image="image.js"
        data-duration="${properties.duration}"
        class="cmp-poster"
        style="background-image: url(${request.contextPath @ context='uri'}${image.src @ context='uri'});">
       <div class="cmp-poster__text
                   cmp-poster__text--${properties.textPosition @ context='attribute'}
                   cmp-poster__text--${properties.textColor @ context='attribute'}">
           <h1 class="cmp-poster__title">${properties.jcr:title}</h1>
            <h2 class="cmp-poster__description">${properties.jcr:description}</h2>
       </div>
    <img class="cmp-poster__logo" src="/content/dam/we-retail-run/logos/we-retail-run_dark.png" alt="we-retail-logo" />
   </div>
   ```

   Hierboven ziet u de productiemarkering voor de postercomponent. Het HTML-script overschrijft `screens/core/components/content/image/production.html`. Het `image.js` is een serverscript dat een POJO-achtig afbeeldingsobject maakt. Het voorwerp van het Beeld kan dan worden geroepen om het `src` als gealigneerde stijl achtergrond-beeld terug te geven.

   `The h1` en h2-tags worden toegevoegd, geven de titel en beschrijving weer op basis van de componenteigenschappen: `${properties.jcr:title}` en `${properties.jcr:description}`.

   Omringend de `h1` en `h2` tags is een div-wrapper met drie CSS-klassen met variaties van &quot; `cmp-poster__text`&quot;. De waarde voor de eigenschappen `textPosition` en `textColor` worden gebruikt om de CSS-klasse te wijzigen die wordt gerenderd op basis van de dialoogselectie van de auteur. In de volgende sectie worden CSS uit clientbibliotheken geschreven om deze wijzigingen in de weergave in te schakelen.

   Een logo wordt ook als een bedekking opgenomen in de component. In dit voorbeeld is het pad naar het logo We.Retail hard-coded in de DAM. Afhankelijk van het gebruiksgeval kan het meer zin hebben om een nieuw dialoogveld te maken om van het logopad een dynamisch gevulde waarde te maken.

   Merk ook op dat BEM-notatie (Block Element Modifier) wordt gebruikt met de component. BEM is een CSS-coderingsconventie die het gemakkelijker maakt om herbruikbare componenten te maken. BEM is de notatie die wordt gebruikt door [AEM&#39;s Core Components](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/wiki/CSS-coding-conventions). Meer informatie is te vinden op: [https://getbem.com/](https://getbem.com/)

1. Een bestand maken onder de `/apps/weretail-run/components/content/poster` naam `edit.html.`

   Vul het bestand met het volgende:

   ```xml
   <!--/*
   
       /apps/weretail-run/components/content/poster/edit.html
   
   */-->
   
   <div class="aem-Screens-editWrapper ${image.cssClass} cmp-poster" data-sly-use.image="image.js" data-emptytext="${'Poster' @ i18n, locale=request.locale}">
       <img class="cmp-poster__image" src="${request.contextPath}${image.src @ context='uri'}" width="100%" />
       <div class="cmp-poster__text
              cmp-poster__text--${properties.textPosition @ context='attribute'}
          cmp-poster__text--${properties.textColor @ context='attribute'}">
         <p class="cmp-poster__title">${properties.jcr:title}</p>
         <p class="cmp-poster__description">${properties.jcr:description}</p>
       </div>
   </div>
   ```

   Hierboven ziet u de **bewerkingsmarkeringen** voor de Postercomponent. Het HTML-script overschrijft `/libs/screens/core/components/content/image/edit.html`. De markering is vergelijkbaar met de `production.html` markering en geeft de titel en beschrijving boven op de afbeelding weer.

   Het `aem-Screens-editWrapper`wordt toegevoegd zodat de component het volledige scherm in de redacteur niet zal teruggeven. Het `data-emptytext` kenmerk zorgt ervoor dat de plaatsaanduiding wordt weergegeven wanneer er geen afbeelding of inhoud is ingevuld.

## Client-Side bibliotheken maken {#clientlibs}

Client-Side Libraries bieden een mechanisme voor het organiseren en beheren van CSS- en JavaScript-bestanden die nodig zijn voor een AEM-implementatie. Hier vindt u meer informatie over het gebruik van bibliotheken aan de [clientzijde.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

AEM-rastercomponenten worden anders weergegeven in de bewerkingsmodus dan in de modus Voorbeeld/productie. Er worden twee sets met clientbibliotheken gemaakt: een voor de bewerkingsmodus en een tweede voor Voorvertoning/Productie.

1. Maak een map voor client-side bibliotheken voor de postercomponent.

   Hieronder `/apps/weretail-run/components/content/poster,`maakt u een nieuwe map met de naam `clientlibs`.

   ![2018-05-03_1008pm](assets/2018-05-03_at_1008pm.png)

1. Onder de `clientlibs` map maakt u een nieuw knooppunt met de naam `shared` van het type `cq:ClientLibraryFolder.`

   ![2018-05-03_10:00](assets/2018-05-03_at_1011pm.png)

1. Voeg de volgende eigenschappen toe aan de gedeelde clientbibliotheek:

   * `allowProxy` | Boolean | `true`
   * `categories` | String[] | `cq.screens.components`
   ![Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/shared](assets/2018-05-03_at_1026pm-1.png)

   Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/shared

   De `categories` eigenschap is een tekenreeks die de clientbibliotheek identificeert. De `cq.screens.components` categorie wordt gebruikt in zowel de modus Bewerken als de modus Voorbeeld/productie. Daarom wordt elke CSS/JS die in de `shared` clientlib is gedefinieerd, in alle modi geladen.

   Het is aan te raden geen paden in een productieomgeving rechtstreeks toegankelijk te maken voor /apps. De `allowProxy` eigenschap zorgt ervoor dat naar de CSS- en JS-clientbibliotheek wordt verwezen via een voorvoegsel van `/etc.clientlibs`. Meer informatie over de eigenschap [allowProxy vindt u hier.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html#main-pars_title_8ced)

1. Maak een bestand met de naam `css.txt` onder de gedeelde map.

   Vul het bestand met het volgende:

   ```
   #base=css
   
   styles.less
   ```

1. Maak een map met de naam `css` onder de `shared` map. Voeg een bestand toe met de naam `style.less` onder de `css` map. De structuur van de clientbibliotheken moet er nu als volgt uitzien:

   ![2018-05-03_1057pm](assets/2018-05-03_at_1057pm.png)

   In plaats van CSS rechtstreeks te schrijven, gebruikt deze zelfstudie LESS. [LESS](https://lesscss.org/) is een populaire voorcompiler van CSS die CSS variabelen, mixins, en functies steunt. AEM-clientbibliotheken bieden native ondersteuning voor LESS-compilatie. De klasse of andere pre-compilers kunnen worden gebruikt maar moeten buiten AEM worden samengesteld.

1. Vul `/apps/weretail-run/components/content/poster/clientlibs/shared/css/styles.less` met het volgende:

   ```css
   /*
    /apps/weretail-run/components/content/poster/clientlibs/shared/css/styles.less
    Poster Component - Shared Style
   */
   
   @import url('https://fonts.googleapis.com/css?family=Fjalla+One|Open+Sans:400i');
   
   @text-light-color: #fff;
   @text-dark-color: #000;
   @title-font-family: 'Fjalla One', sans-serif;
   @description-font-family: 'Open Sans', sans-serif;
   
   .cmp-poster {
   
         &__text {
         position: absolute;
         color: @text-light-color;
         top: 0;
         text-align:center;
         width: 100%;
   
         &--left {
          text-align: left;
                margin-left: 1em;
         }
   
         &--right {
          text-align: right;
                margin-right: 1em;
         }
   
         &--dark {
          color: @text-dark-color;
         }
       }
   
       &__title {
         font-weight: bold;
            font-family: @title-font-family;
            font-size: 1.2em;
       }
   
       &__description {
     font-style: italic;
           font-family: @description-font-family;
    }
   
   }
   ```

   >[!NOTE]
   >
   >Google-weblettertypen worden gebruikt voor de lettertypefamilies. Weblettertypen vereisen internetverbinding en niet alle schermimplementaties bieden een betrouwbare verbinding. Planning voor off-line wijze is een belangrijke overweging voor de plaatsingen van het Scherm.

1. Kopieer de `shared` clientbibliotheekmap. Plak de naam op hetzelfde niveau en wijzig de naam in `production`.

   ![2018-05-03_114pm](assets/2018-05-03_at_1114pm.png)

1. Werk het `categories` bezit van de productieklantenbibliotheek bij die moet worden `cq.screens.components.production.`

   De `cq.screens.components.production` categorie zorgt ervoor dat de stijlen alleen worden geladen in de modus Voorbeeld/productie.

   ![Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/production](assets/2018-04-30_at_5_04pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/production

1. Vul `/apps/weretail-run/components/content/poster/clientlibs/production/css/styles.less` met het volgende:

   ```css
   /*
    /apps/weretail-run/components/content/poster/clientlibs/production/css/styles.less
    Poster Component - Production Style
   */
   
   .cmp-poster {
   
       background-size: cover;
    height: 100%;
    width: 100%;
    position:absolute;
   
        &__text {
   
           top: 2em;
   
           &--left {
               width: 40%;
               top: 5em;
           }
   
           &--right {
               width: 40%;
               right: 1em;
           }
       }
   
       &__title {
     font-size: 5rem;
     font-weight: 900;
     margin: 0.1rem;
    }
   
    &__description {
     font-size: 2rem;
     margin: 0.1rem;
     font-weight: 400;
   
    }
   
       &__logo {
     position: absolute;
     max-width: 200px;
     top: 1em;
     left: 0;
    }
   
   }
   ```

   De bovenstaande stijlen geven de titel en beschrijving weer op een absolute positie op het scherm. De titel wordt aanzienlijk groter weergegeven dan de beschrijving. Met de BEM-notatie van de component kunt u de stijlen in de klasse cmp-poster heel eenvoudig nauwkeurig indelen.

Een derde categorie clientbibliotheek: U `cq.screens.components.edit` kunt bijvoorbeeld alleen specifieke stijlen voor Bewerken aan de component toevoegen.

| Clientlib-categorie | Gebruik |
|---|---|
| `cq.screens.components` | Stijlen en scripts die worden gedeeld tussen de bewerkings- en de productiemodus |
| `cq.screens.components.edit` | Stijlen en scripts die alleen worden gebruikt in de bewerkingsmodus |
| `cq.screens.components.production` | Stijlen en scripts die alleen in de productiemodus worden gebruikt |

## Postercomponent toevoegen aan een volgend kanaal {#add-sequence-channel}

De postercomponent is bedoeld voor gebruik op een Kanaal van de Opeenvolging. Het startpakket voor deze zelfstudie bevat een inactief kanaal. Het onactieve kanaal is vooraf geconfigureerd om componenten van de groep **We.Retail Run - Content** toe te staan. De groep van de component Poster wordt ingesteld op `We.Retail Run - Content` en is beschikbaar om aan het kanaal te worden toegevoegd.

1. Open het Onactieve Kanaal van het Web.Retail project van de Looppas: **`http://localhost:4502/editor.html/content/screens/we-retail-run/channels/idle-channel.edit.html`**
1. Sleep en zet een nieuwe instantie van de component **Poster** neer van de zijbalk op de pagina.

   ![2018-05-07_23:00](assets/2018-05-07_at_3_23pm.png)

1. Bewerk het dialoogvenster van de postercomponent om een afbeelding, titel en beschrijving toe te voegen. Gebruik de opties Tekstpositie en Tekstkleur om ervoor te zorgen dat de titel/beschrijving op de afbeelding kan worden gelezen.

   ![2018-05-07_11_25](assets/2018-05-07_at_3_25pm.png)

1. Herhaal bovenstaande stappen om enkele postercomponenten toe te voegen. Voeg overgangen toe tussen de componenten.

   ![2018-05-07_28pm](assets/2018-05-07_at_3_28pm.png)

## Alles samenvoegen {#putting-it-all-together}

In de onderstaande video ziet u de voltooide component en de manier waarop deze aan een volgnummer kan worden toegevoegd. Het kanaal wordt vervolgens toegevoegd aan de weergave Locatie en uiteindelijk toegewezen aan een schermspeler.

>[!VIDEO](https://video.tv.adobe.com/v/22414?quaity=9)

## Voltooide code {#finished-code}

Hieronder ziet u de voltooide code uit de zelfstudie. De gecompileerde AEM-pakketten zijn **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** en **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** . **SRC-screens-weretail-looppas-0.0.1.zip **is de uncompiled broncode die kan worden opgesteld gebruikend Maven.

[Bestand ophalen](assets/final-poster-screens-weretail-runuiapps-001-snapshot.zip)

[Bestand ophalen](assets/final-poster-screens-weretail-runuicontent-001-snapshot.zip)

SRC Final Screens We.Retail Run Project

[Bestand ophalen](assets/src-screens-weretail-run-001.zip)
