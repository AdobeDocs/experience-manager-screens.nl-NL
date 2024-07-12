---
title: Aangepaste sjablonen maken in MultiZone-lay-outs
description: Meer informatie over het maken van aangepaste sjablonen in MultiZone-lay-outs voor AEM Screens.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 3f4813f8-0438-4ce0-9046-84025de0ddd1
source-git-commit: df41a8794683e241b6f12b58d39c01e069187435
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 1%

---

# Aangepaste sjablonen maken voor MultiZone-layouts {#creating-custom-templates-multizone}

Op deze pagina ziet u hoe u een aangepaste sjabloon voor een lay-out met meerdere zones kunt maken.

## Belangrijke overwegingen {#considerations}

Er zijn twee belangrijke overwegingen dat u zich van bewust moet zijn alvorens een douanemalplaatje in een multi-zonelay-out tot stand te brengen:

1. **Vaste Grootte of Percentages van het Pixel**:

   Bepaal of u de vaste pixelgrootte voor verschillende zones wilt gebruiken voor uw aangepaste layout of dat u een aangepaste indeling wilt maken met percentages.

   >[!NOTE]
   >Het voordeel van het gebruiken van percentage om streken voor uw douanelay-out te plaatsen laat u het malplaatje op diverse het schermgrootte opnieuw gebruiken.

1. **noemend Overeenkomst**:

   Het helpt om te begrijpen hoe te om douane multi-zone malplaatjes tot stand te brengen in een project van AEM Screens te gebruiken. Maar eerst moet u het gemiddelde begrijpen van de sjablonen die u wilt maken.

   | **Naam van de Lay-out** | **Beschrijving** |
   |---|---|
   | `Left20-LandscapeHD3Zone` | Een landschaplay-out met drie zones waarmee u drie zones kunt maken:<br>* Zone 1 als 20% van het horizontale en verticale scherm vanaf links <br>* Zone 2 als 80% van het horizontale scherm en 20% van het verticale scherm rechts uitgevuld <br>* Zone 3 als 100% van het horizontale en 80% van het verticale scherm. De verhouding is 16:9 |
   | `Upper20-PortraitHD2Zone` | Een staande sjabloon met twee zones die 20% van het scherm vanaf de bovenkant bedekt, met een hoogte-breedteverhouding van 16:9 |
   | `Right20-LandscapeSD3Zone` | Een sjabloon met drie zones die vanaf rechts 20% van het scherm bedekt, met een hoogte-breedteverhouding van 4:3 |

   >[!IMPORTANT]
   >De zones die zijn gedefinieerd in de aangepaste indeling komen mogelijk niet overeen met de algemene hoogte-breedteverhouding van de volledige layout. In de naamgevingsconventie die in dit document wordt gevolgd, wordt de hoogte-breedteverhouding van de aangepaste layout als geheel opgegeven.

## Voorbeeld: hoofdlettergebruik `Left20-LandscapeHD3Zone` layout {#custom-template-one}

Volg de onderstaande sectie om een aangepaste sjabloon *`Left20-LandscapeHD3Zone`* te maken met de volgende configuratie:

* **`Left20`** - De bovenste zone aan de linkerkant die 20% van de horizontale en verticale schermgrootte bedekt.
* **`Landscape`** - De schermstand.
* **`HD`** - De hoogte-breedteverhouding is 16:9.
* **`3Zone`** - Drie zones van het scherm.

## Visuele representatie van MultiZone Layout {#multi-layout-visual-one}

Met de `Left20-LandscapeHD3Zone` -lay-out kunt u de volgende lay-out met meerdere zones maken in uw project:

![afbeelding](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Een `Left20-LandscapeHD3Zone` lay-out maken {#landscape-layout-one}

Voer de onderstaande stappen uit om een `Left20-LandscapeHD3Zone` lay-out voor een AEM Screens-project te maken.

1. Maak een AEM Screens-project met de naam **`customtemplate`** .

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigeer aan **CRXDE Lite** van uw AEM instantie > Hulpmiddelen > **CRXDE Lite**.

1. Creeer een omslag onder **apps** genoemd als **`customtemplate`**. Op dezelfde manier creeer een andere omslag die als **malplaatje** onder **`customtemplate`** wordt genoemd, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >Klik **sparen allen** van de actiebar in CRXDE Lite telkens als u creeert, geef, of kopieer inhoud aan om het even welke knopen uit. Anders kunt u de updates niet vastleggen.

1. Kopieer de sjabloon linksboven van `/libs/screens/core/templates/splitscreenchannel/lbar-left` naar `/apps/customtemplate/template` .

1. Verander de gekopieerde **bar-verlaten** (`/apps/customtemplate/template`) aan **my-custom-lay-out**.
   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigeer naar `/apps/customtemplate/template/my-custom-layout` en werk de eigenschappen **`jcr:description`** aan *Sjabloon voor`Left20-LandscapeHD3Zone`* en **`jcr:title`** aan *`Left20-LandscapeHD3Zone`* bij.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigeer naar het knooppunt **`offline-config`** van `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` en werk de lus **`jcr:title`** to *`Left20-LandscapeHD3Zone`* bij.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigeer aan het *`jcr:content`* bezit van **my-custom-malplaatje** van `/apps/customtemplate/template/my-custom-layout/jcr:content` en werk het **`cq:cssClass`** bezit bij zodat kunt u **aem-Lay-out my-custom-lay-out** gebruiken.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Verwijzend naar stap 4 waarin u de bar-linkermalplaatje kopieerde, kunt u drie ontvankelijke netten onder `my-custom-layout/jcr:content` bekijken. Voeg douanecss klasse aan elk van het ontvankelijke net in het *`cq:cssClass`* bezit, bijvoorbeeld, *toe my-custom-layout-top-left* voor *r1c1* knoop.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Op dezelfde manier voeg *my-custom-layout-top-right* voor *r1c2* en *toe my-custom-layout-bottom* voor *r2c1* knoop.

   >[!NOTE]
   >Deze aangepaste klassen worden in de CSS gebruikt om de breedte/hoogte voor deze responsieve rasters in te stellen.

   >[!NOTE]
   >U kunt de responsieve rasters toevoegen of verwijderen op basis van het aantal totale rasters dat u wilt. In dit voorbeeld worden twee rasters in de eerste rij en één raster in de tweede rij weergegeven. Er zijn dus in totaal drie responsieve rasters (r1c1, r1c2, r2c1).

1. Het exemplaar `/libs/settings/wcm/designs/screens` aan `/apps/settings/wcm/designs/` en noemt het gekopieerde ontwerp anders als **douane-malplaatje-ontwerpen**.

1. Navigeer aan `/apps/settings/wcm/designs/custom-template-designs` en werk het bezit *`jcr:title`* van **douane-malplaatje-ontwerpen** aan **aangepast malplaatje-ontwerp** bij.

1. Navigeer naar `/apps/settings/wcm/designs/custom-template-designs` en maak een bestand static.css.

1. Kopieer de inhoud naar het `static.css` -bestand:

   ```shell
       /*my-custom-layout styles*/
      .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-left {
       width:20%;
       height: 36%;
      float: left !important;
      }
     .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-right {
      width:80%;
      height: 36%;
     float: left !important;
     }
     .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--bottom {
     width:100%;
     height: 64%;
     }
   ```

   >[!NOTE]
   >U kunt de percentages bijwerken zodat deze overeenkomen met de vereisten voor uw aangepaste sjabloon.

1. Navigeer naar `/apps/<project>/templates/my-custom-layout/jcr:content` en werk de eigenschap *`cq:designPath`* to `/apps/settings/wcm/designs/customtemplate-designs` bij, zodat u de stijlen kunt laden die in static.css zijn geconfigureerd.

   >[!NOTE]
   >Typ alle stijlen in plaats van te kopiëren of te plakken. Hierdoor kunnen witte ruimten ontstaan die resulteren in problemen met CSS-stijlen.

## Het resultaat weergeven {#viewing-result}

Voer de onderstaande stappen uit om de bovenstaande aangepaste sjabloon te gebruiken in uw AEM Screens-project:

1. Navigeer aan uw project van Screens dat u in stap (1) creeerde en klik de **omslag van Kanalen**.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klik **creëren** van de actiebar en klik het malplaatje **`Left20-LandscapeHD3Zone`** van **creëren** tovenaar.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nadat u een kanaal met het aangepaste malplaatje hebt gecreeerd, kunt u activa aan uw kanaal van de redacteur toevoegen. In het volgende voorbeeld worden de afbeeldingen in een aangepaste sjabloon weergegeven.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Een afbeelding invoegen als achtergrondlaag {#inserting-image}

U kunt een afbeelding als achtergrondlaag invoegen in de layout:

U kunt de CSS regel aanpassen om &quot;gegeven-uri&quot;te gebruiken en direct het beeld (`Base64` gecodeerd) in het CSS dossier te inline dat u binnen creeerde (stap 13), *static.css*.

Deze regeling is als volgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

U kunt ook de onderstaande stappen volgen:

1. Zorg ervoor dat de afbeelding op een of andere manier is opgenomen in de offlineconfiguratie voor het kanaal.
1. Gebruik een directe koppeling naar de afbeelding in de bovenstaande CSS in plaats van de &quot;data-uri&quot;-variant.


## Achtergrondkleur bijwerken {#updating-color}

Om de achtergrondkleur te veranderen, voeg de volgende code aan het xml- dossier (stap 13) toe, *static.css*.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`
