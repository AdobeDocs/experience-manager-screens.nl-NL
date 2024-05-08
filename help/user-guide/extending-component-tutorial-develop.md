---
title: Een AEM Screens-component uitbreiden
description: Leer in deze zelfstudie de stappen en beste praktijken voor het uitbreiden uit de doosAEM Screens componenten. De component Image wordt uitgebreid om een aanwendbare tekstbedekking toe te voegen.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
targetaudience: target-audience new
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: e316614f-2d40-4b62-a1e5-f30817def742
source-git-commit: ef74265eadf5972eae7451b7725946d8b014c198
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 0%

---

# Een AEM Screens-component uitbreiden

De volgende zelfstudie doorloopt de stappen en aanbevolen procedures voor het uitbreiden uit de doos AEM Screens-componenten. De component Image wordt uitgebreid om een aanwendbare tekstbedekking toe te voegen.

## Overzicht {#overview}

Deze zelfstudie is bedoeld voor nieuwe ontwikkelaars van AEM Screens. In deze zelfstudie wordt de component Schermafbeelding uitgebreid om een postercomponent te maken. Boven op een afbeelding worden een titel, beschrijving en logo geplaatst om een aantrekkelijke ervaring te creëren in een sequentiekanaal.

>[!NOTE]
>
>Voordat u met deze zelfstudie begint, wordt u aangeraden de zelfstudie te voltooien: [Een aangepaste component voor AEM Screens ontwikkelen](developing-custom-component-tutorial-develop.md).

![Aangepaste postercomponent](assets/2018-05-07_at_4_09pm.png)

De component van de Poster van de douane wordt gecreeerd door de component van het Beeld uit te breiden.

## Vereisten {#prerequisites}

U hebt het volgende nodig om deze zelfstudie te voltooien:

1. AEM 6.5 + het nieuwste pakket met schermfuncties
1. [AEM Screens Player](/help/user-guide/aem-screens-introduction.md)
1. Lokale ontwikkelomgeving

De stappen en schermafbeeldingen van de zelfstudie worden uitgevoerd gebruikend CRXDE-Lite. [Eclipse](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/devtools/aem-eclipse) of [IntelliJ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/devtools/ht-intellij) IDEs kan ook worden gebruikt om het leerprogramma te voltooien. Meer informatie over het gebruiken van winde aan [ontwikkelen met AEM kunt u hier vinden](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup).

## Projectinstelling {#project-setup}

De broncode van een project van het Scherm wordt typisch geleid als multi-module Maven project. Om de zelfstudie te versnellen, werd een project vooraf gegenereerd met de [Projectarchetype AEM 13](https://github.com/adobe/aem-project-archetype). Meer informatie over [een project maken met Maven AEM Project Archetype:](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup).

1. De volgende pakketten downloaden en installeren met **CRX-pakketbeheer** `http://localhost:4502/crx/packmgr/index.jsp)r:`

[Bestand ophalen](assets/start-poster-screens-weretail-runuiapps-001-snapshot.zip)

   [Bestand ophalen](assets/start-poster-screens-weretail-runuicontent-001-snapshot.zip)
   **Optioneel** Als u werkt met Eclipse of een andere IDE, downloadt u het onderstaande bronpakket. Stel het project aan een lokale AEM instantie op door het Maven bevel te gebruiken:

   **`mvn -PautoInstallPackage clean install`**

   Startschermen SRC `We.Retail` Project uitvoeren

[Bestand ophalen](assets/start-poster-screens-weretail-run.zip)

1. In **CRX Package Manager** `http://localhost:4502/crx/packmgr/index.jsp` de volgende twee pakketten zijn geïnstalleerd :

   1. **`screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip`**
   1. **`screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip`**

   ![Screens Web.Retail Run Ui.Apps en Ui.Content pakketten geïnstalleerd via CRX Package Manager](assets/crx-packages.png)

   AEM Screens `We.Retail Run Ui.Apps` en `Ui.Content` pakketten geïnstalleerd via CRX Package Manager

## De postercomponent maken {#poster-cmp}

De postercomponent breidt de uit-van-de-doos AEM Screens-afbeeldingscomponent uit. een Sling-mechanisme, `sling:resourceSuperType`, wordt gebruikt om de kernfunctionaliteit van de component Image over te nemen zonder dat u deze hoeft te kopiëren en plakken. Meer informatie over de basisbeginselen van [Hier vindt u een verwerking van de verkoopaanvraag.](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/the-basics)

De postercomponent wordt op volledig scherm weergegeven in de modus Voorvertoning/Productie. In de bewerkingsmodus is het belangrijk dat de component anders wordt gerenderd om het ontwerpen van het sequentiekanaal te vergemakkelijken.

1. In **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (of IDE van keus) onderaan `/apps/weretail-run/components/content`een `cq:Component` benoemd `poster`.

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

   Door het `sling:resourceSuperType`eigenschap gelijk aan `screens/core/components/content/image`overerft de component Poster in feite alle functionaliteit van de component Image. Equivalente knooppunten en bestanden aangetroffen onder `screens/core/components/content/image` kan onder de `poster` om de functionaliteit te overschrijven en uit te breiden.

1. De `cq:editConfig` knooppunt onder `/libs/screens/core/components/content/image`. Plak de `cq:editConfig` onder de `/apps/weretail-run/components/content/poster` component.

   Op de `cq:editConfig/cq:dropTargets/image/parameters` knooppunt, update de `sling:resourceType` eigenschap gelijk aan `weretail-run/components/content/poster`.

   ![bewerken-config](assets/edit-config.png)

   XML-representatie van de `cq:editConfig` hieronder weergegeven:

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

1. WCM Foundation kopiëren `image` wordt gebruikt voor de `poster` component.

   Het is het gemakkelijkst om van een bestaande dialoog te beginnen en dan wijzigingen te maken.

   1. Het dialoogvenster kopiëren van: `/libs/wcm/foundation/components/image/cq:dialog`
   1. Het dialoogvenster onder plakken `/apps/weretail-run/components/content/poster`

   ![Gekopieerd dialoogvenster van /libs/wcm/foundation/components/image/cq:dialoogvenster naar /apps/weretail-run/components/content/poster](assets/2018-05-03_at_4_13pm.png)

   Gekopieerd dialoogvenster van `/libs/wcm/foundation/components/image/cq:dialog` tot `/apps/weretail-run/components/content/poster`

   De AEM Screens `image` de component wordt supertypt aan de Stichting WCM `image` component. Daarom `poster` -component overerft functionaliteit van beide. De dialoog voor de postercomponent bestaat uit een combinatie van de dialoogvensters Schermen en Stichting. Functies van de **Samenvoeging van verkoopbronnen** worden gebruikt om irrelevante dialooggebieden en lusjes te verbergen die van supertyped componenten worden geërft.

1. Werk de `cq:dialog` beneide `/apps/weretail-run/components/content/poster` waarbij de volgende wijzigingen in XML worden vertegenwoordigd:

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
                                   sling:resourceType="granite/ui/components/coral/foundation/form/click"
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
                                   sling:resourceType="granite/ui/components/coral/foundation/form/click"
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

   De eigenschap `sling:hideChildren`= `"[linkURL,size]`&quot; wordt gebruikt op de `items` knoop om ervoor te zorgen dat **linkURL** en **size** velden worden verborgen in het dialoogvenster. Het is niet voldoende deze knooppunten uit het posterdialoogvenster te verwijderen. De eigenschap `sling:hideResource="{Boolean}true"` op het tabblad Toegankelijkheid wordt gebruikt om het hele tabblad te verbergen.

   Er worden twee klikvelden toegevoegd aan het dialoogvenster om auteurs de tekstpositie en -kleur van de titel en beschrijving te geven.

   ![Poster - Definitieve structuur van dialoogvenster](assets/2018-05-03_at_4_49pm.png)

   Poster - Definitieve structuur van dialoogvenster

   Op dit punt, een geval van `poster` kan worden toegevoegd aan de **Niet-actief kanaal** pagina in de`We.Retail` Project uitvoeren: `http://localhost:4502/editor.html/content/screens/we-retail-run/channels/idle-channel.edit.html`.

   ![Dialoogvensters Poster](assets/poster-dialog-full.png)

   Dialoogvensters Poster

1. Een bestand maken onder `/apps/weretail-run/components/content/poster` benoemd `production.html.`

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

   De productiemarkering voor de Postercomponent wordt direct hierboven weergegeven. Het HTML-script overschrijft `screens/core/components/content/image/production.html`. De `image.js` is een serverscript dat een POJO-achtig afbeeldingsobject maakt. Het voorwerp van het Beeld kan dan worden geroepen om `src` als een inline-stijlachtergrondafbeelding.

   `The h1` en h2-tags worden toegevoegd, geven de titel en beschrijving weer op basis van de componenteigenschappen: `${properties.jcr:title}` en `${properties.jcr:description}`.

   Omringend de `h1` en `h2` -tags is een div-wrapper met drie CSS-klassen met variaties van &quot; `cmp-poster__text`&quot;. De waarde voor de `textPosition` en `textColor` eigenschappen worden gebruikt om de CSS-klasse te wijzigen die wordt gerenderd op basis van de dialoogselectie van de auteur. In de volgende sectie worden CSS uit clientbibliotheken geschreven om deze wijzigingen in de weergave in te schakelen.

   Een logo wordt ook als een bedekking opgenomen in de component. In dit voorbeeld wordt het pad naar het` We.Retail` logo is hard-gecodeerd in de DAM. Afhankelijk van het geval van het gebruik, zou het nuttiger kunnen zijn om een dialoogvakje tot stand te brengen om van de logoweg een dynamisch bevolkte waarde te maken.

   Merk ook op dat BEM-notatie (Block Element Modifier) wordt gebruikt met de component. BEM is een CSS-coderingsconventie die het gemakkelijker maakt om herbruikbare componenten te maken. BEM is de notatie die wordt gebruikt door [AEM kerncomponenten](https://github.com/adobe/aem-core-wcm-components/wiki/CSS-coding-conventions). <!-- DEAD LINK More info can be found at: [https://getbem.com/](https://getbem.com/) -->

1. Een bestand maken onder `/apps/weretail-run/components/content/poster` benoemd `edit.html.`

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

   De **bewerken** Opmaak voor de Postercomponent wordt direct boven weergegeven. Het HTML-script overschrijft `/libs/screens/core/components/content/image/edit.html`. De markering is vergelijkbaar met de `production.html` en geeft de titel en beschrijving boven op de afbeelding weer.

   De `aem-Screens-editWrapper`wordt toegevoegd zodat de component niet volledig-scherm in de redacteur wordt teruggegeven. De `data-emptytext` zorgt ervoor dat een plaatsaanduiding wordt weergegeven wanneer er geen afbeelding of inhoud is gevuld.

## Client-Side bibliotheken maken {#clientlibs}

Client-Side Libraries bieden een mechanisme voor het organiseren en beheren van CSS- en JavaScript-bestanden die nodig zijn voor een AEM-implementatie. Meer informatie over het gebruik [Hier vindt u bibliotheken aan de clientzijde.](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/clientlibs)

AEM Screens-componenten worden in de bewerkingsmodus anders weergegeven dan in de modus Voorbeeld/productie. Er worden twee sets met clientbibliotheken gemaakt: een voor de bewerkingsmodus en een tweede voor Voorvertoning/Productie.

1. Maak een map voor client-side bibliotheken voor de postercomponent.

   Beneath `/apps/weretail-run/components/content/poster`, maakt u een map met de naam `clientlibs`.

   ![2018-05-03_1008pm](assets/2018-05-03_at_1008pm.png)

1. Onder de `clientlibs` map, een knooppunt maken met de naam `shared` van het type `cq:ClientLibraryFolder.`

   ![2018-05-03_10:00](assets/2018-05-03_at_1011pm.png)

1. Voeg de volgende eigenschappen toe aan de gedeelde clientbibliotheek:

   * `allowProxy` | Boolean | `true`
   * `categories` | String[] | `cq.screens.components`

   ![Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/shared](assets/2018-05-03_at_1026pm-1.png)

   Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/shared

   De `categories` eigenschap is een tekenreeks die de clientbibliotheek identificeert. De `cq.screens.components` Deze categorie wordt gebruikt in zowel de modus Bewerken als de modus Voorbeeld/productie. Daarom zijn er CSS/JS-definities in de `shared` clientlib wordt in alle modi geladen.

   Het is aan te raden geen paden in een productieomgeving rechtstreeks toegankelijk te maken voor /apps. De `allowProxy` zorgt ervoor dat in de clientbibliotheek naar de CSS- en JS-indeling wordt verwezen door een voorvoegsel van `/etc.clientlibs`. Meer informatie over de [allowProxy eigenschap is hier te vinden.](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/clientlibs)

1. Bestandsnaam maken `css.txt` onder de gedeelde map.

   Vul het bestand met het volgende:

   ```
   #base=css
   
   styles.less
   ```

1. Een map maken met de naam `css` onder de `shared` map. Een bestand met de naam toevoegen `style.less` onder de `css` map. De structuur van de clientbibliotheken moet er nu als volgt uitzien:

   ![2018-05-03_1057pm](assets/2018-05-03_at_1057pm.png)

   In plaats van CSS rechtstreeks te schrijven, gebruikt deze zelfstudie LESS. [MINDER](https://lesscss.org/) is een populaire CSS-voorcompiler die CSS-variabelen, -mixins en -functies ondersteunt. AEM clientbibliotheken ondersteunen native LESS-compilatie. De klasse of andere pre-compilers kunnen worden gebruikt maar moeten buiten AEM worden gecompileerd.

1. Vullen `/apps/weretail-run/components/content/poster/clientlibs/shared/css/styles.less` met het volgende:

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
   >Google-Webben Fonts worden gebruikt voor de lettertypefamilies. Webben Fonts vereisen internetverbinding en niet alle AEM Screens-implementaties beschikken over een betrouwbare verbinding. Planning voor off-line wijze is een belangrijke overweging voor de plaatsingen van AEM Screens.

1. De `shared` clientbibliotheekmap. Plak het op hetzelfde niveau en wijzig de naam in `production`.

   ![2018-05-03_114pm](assets/2018-05-03_at_1114pm.png)

1. Werk de `categories` eigenschap van de productiecliënt die moet worden `cq.screens.components.production.`

   De `cq.screens.components.production` zorgt ervoor dat de stijlen alleen worden geladen in de modus Voorbeeld/productie.

   ![Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/production](assets/2018-04-30_at_5_04pm.png)

   Eigenschappen voor /apps/weretail-run/components/content/poster/clientlibs/production

1. Vullen `/apps/weretail-run/components/content/poster/clientlibs/production/css/styles.less` met het volgende:

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

   De bovenstaande stijlen geven de titel en beschrijving weer op een absolute positie op het scherm. De titel wordt groter weergegeven dan de beschrijving. Met de BEM-notatie van de component kunt u de stijlen in de klasse cmp-poster heel eenvoudig nauwkeurig indelen.

Een derde categorie voor clientbibliotheken: `cq.screens.components.edit` kan worden gebruikt om alleen specifieke stijlen aan de component toe te voegen.

| Clientlib-categorie | Gebruik |
|---|---|
| `cq.screens.components` | Stijlen en scripts die worden gedeeld tussen de bewerkings- en de productiemodus |
| `cq.screens.components.edit` | Stijlen en scripts die alleen worden gebruikt in de bewerkingsmodus |
| `cq.screens.components.production` | Stijlen en scripts die alleen in de productiemodus worden gebruikt |

## Postercomponent toevoegen aan een volgend kanaal {#add-sequence-channel}

De component Poster wordt gebruikt op een Kanaal van de Opeenvolging. Het startpakket voor deze zelfstudie bevatte een onactief kanaal. Het onactieve kanaal is vooraf geconfigureerd om componenten van de groep toe te staan **`We.Retail Run - Content`**. De groep van de component Poster wordt ingesteld op `We.Retail Run - Content` en is beschikbaar om aan het kanaal te worden toegevoegd.

1. Open het onactieve kanaal via het `We.Retail` Project uitvoeren: **`http://localhost:4502/editor.html/content/screens/we-retail-run/channels/idle-channel.edit.html`**
1. Sleep + zet een nieuwe instantie van het gereedschap **Poster** van de zijbalk op de pagina.

   ![2018-05-07_23:00](assets/2018-05-07_at_3_23pm.png)

1. Bewerk het dialoogvenster van de postercomponent zodat u een afbeelding, titel, beschrijving kunt toevoegen. Gebruik de opties Tekstpositie en Tekstkleur om ervoor te zorgen dat de titel/beschrijving op de afbeelding kan worden gelezen.

   ![2018-05-07_11_25](assets/2018-05-07_at_3_25pm.png)

1. Herhaal de bovenstaande stappen om enkele postercomponenten toe te voegen. Voeg overgangen toe tussen de componenten.

   ![2018-05-07_28pm](assets/2018-05-07_at_3_28pm.png)

## Alles samenvoegen {#putting-it-all-together}

In de onderstaande video ziet u de voltooide component en de manier waarop deze aan een volgnummer kan worden toegevoegd. Het kanaal wordt vervolgens toegevoegd aan de weergave Locatie en uiteindelijk toegewezen aan een schermspeler.

>[!VIDEO](https://video.tv.adobe.com/v/22414?quaity=9)

## Voltooide code {#finished-code}

Hieronder ziet u de voltooide code uit de zelfstudie. De **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** en **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** Dit zijn de gecompileerde AEM pakketten. De **SRC-screens-weretail-run-0.0.1.zip** is de uncompiled broncode die kan worden opgesteld gebruikend Maven.

[Bestand ophalen](assets/final-poster-screens-weretail-runuiapps-001-snapshot.zip)

[Bestand ophalen](assets/final-poster-screens-weretail-runuicontent-001-snapshot.zip)

SRC Final AEM Screens `We.Retail` Project uitvoeren

[Bestand ophalen](assets/src-screens-weretail-run-001.zip)
