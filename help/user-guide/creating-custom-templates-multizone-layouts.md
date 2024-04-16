---
title: Aangepaste sjablonen maken in MultiZone-lay-outs
description: Meer informatie over het maken van aangepaste sjablonen in MultiZone-lay-outs voor AEM Screens.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 3f4813f8-0438-4ce0-9046-84025de0ddd1
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 1%

---

# Aangepaste sjablonen maken voor MultiZone-layouts {#creating-custom-templates-multizone}

Op deze pagina ziet u hoe u een aangepaste sjabloon voor een lay-out met meerdere zones kunt maken.

## Belangrijke overwegingen {#considerations}

Er zijn twee belangrijke overwegingen dat u zich moet bewust zijn alvorens tot douanemalplaatje in multi-zonelay-out te leiden:

1. **Vaste pixelgrootte of percentages**:

   Bepaal of u de vaste pixelgrootte voor verschillende zones wilt gebruiken voor uw aangepaste layout of dat u een aangepaste indeling wilt maken met percentages.

   >[!NOTE]
   >Het voordeel van het gebruiken van percentage om streken voor uw douanelay-out te plaatsen laat u het malplaatje op diverse het schermgrootte opnieuw gebruiken.

1. **Naamgevingsconventie**:

   Voordat u begrijpt hoe u aangepaste multi-zone sjablonen kunt maken voor gebruik in een AEM Screens-project, moet u weten hoe de sjablonen die u wilt maken, zijn verdeeld.

   | **Lay-outnaam** | **Beschrijving** |
   |---|---|
   | `Left20-LandscapeHD3Zone` | Een liggende lay-out met drie zones waarmee u drie zones kunt maken:<br>* Zone 1 als 20% van het horizontale en verticale scherm vanaf links<br>* Zone 2 als 80 % van het horizontale scherm en 20 % van het verticale scherm rechts uitgevuld<br>* Zone 3 als 100 % van het horizontale en verticale scherm met een hoogte-breedteverhouding van 16:9 |
   | `Upper20-PortraitHD2Zone` | Een staande sjabloon met twee zones die 20% van het scherm vanaf de bovenkant bedekt, met een hoogte-breedteverhouding van 16:9 |
   | `Right20-LandscapeSD3Zone` | Een sjabloon met drie zones die vanaf rechts 20% van het scherm bedekt, met een hoogte-breedteverhouding van 4:3 |

   >[!IMPORTANT]
   >De zones die zijn gedefinieerd in de aangepaste indeling komen mogelijk niet overeen met de algemene hoogte-breedteverhouding van de volledige layout. In de naamgevingsconventie die in dit document wordt gevolgd, wordt de hoogte-breedteverhouding van de aangepaste layout als geheel opgegeven.

## Voorbeeld: hoofdletter gebruiken `Left20-LandscapeHD3Zone` Layout {#custom-template-one}

Volg de onderstaande sectie om een aangepaste sjabloon te maken *`Left20-LandscapeHD3Zone`* met de volgende configuratie:

* **`Left20`** - De bovenste zone aan de linkerkant die 20% van de horizontale en verticale schermgrootte bedekt.
* **`Landscape`** - De schermstand.
* **`HD`** - De verhouding is 16:9.
* **`3Zone`** - Drie zones van het scherm.

## Visuele representatie van MultiZone Layout {#multi-layout-visual-one}

De `Left20-LandscapeHD3Zone` Met Layout kunt u de volgende lay-out met meerdere zones maken in uw project:

![afbeelding](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Een `Left20-LandscapeHD3Zone` Layout {#landscape-layout-one}

Volg onderstaande stappen om een `Left20-LandscapeHD3Zone` Layout voor een AEM Screens-project.

1. Een AEM Screens-project maken met de naam **`customtemplate`**.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigeren naar **CRXDE Lite** van uw AEM instantie > Gereedschappen > **CRXDE Lite**.

1. Een map maken onder **apps** getiteld als **`customtemplate`**. Maak ook een andere map met de naam **template** krachtens **`customtemplate`**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >Klikken **Alles opslaan** van de actiebar in CRXDE Lite telkens als u creeert, uitgeeft, of inhoud kopieert aan om het even welke knopen. Anders kunt u de updates niet vastleggen.

1. De linker-balksjabloon kopiëren vanuit `/libs/screens/core/templates/splitscreenchannel/lbar-left` tot `/apps/customtemplate/template`.

1. De naam van de gekopieerde gegevens wijzigen **lbar-left** (`/apps/customtemplate/template`) naar **my-custom-layout**.
   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigeren naar `/apps/customtemplate/template/my-custom-layout` en de eigenschappen bijwerken **`jcr:description`** tot *Template voor`Left20-LandscapeHD3Zone`* en **`jcr:title`** tot *`Left20-LandscapeHD3Zone`*.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Ga naar de **`offline-config`** knooppunt van `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` en de **`jcr:title`** tot *`Left20-LandscapeHD3Zone`*.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Ga naar de *`jcr:content`* eigenschap van **my-custom-template** van `/apps/customtemplate/template/my-custom-layout/jcr:content` en de **`cq:cssClass`** eigenschap zodat u kunt gebruiken **aem-Layout my-custom-layout**.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Verwijzend naar stap (4) waarin u het bar-linkermalplaatje kopieerde, kunt u drie ontvankelijke netten onder bekijken `my-custom-layout/jcr:content`. Aangepaste CSS-klasse toevoegen aan elk responsief raster in het dialoogvenster *`cq:cssClass`* eigenschap, bijvoorbeeld *my-custom-layout—top-left* for *r1c1* knooppunt.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Op dezelfde manier toevoegen *my-custom-layout-top-right* for *r1c2*  en *my-custom-layout—bottom* for *r2c1* knooppunt.

   >[!NOTE]
   >Deze aangepaste klassen worden in de CSS gebruikt om de breedte/hoogte voor deze responsieve rasters in te stellen.

   >[!NOTE]
   >U kunt de responsieve rasters toevoegen of verwijderen op basis van het aantal totale rasters dat u wilt. In dit voorbeeld worden twee rasters in de eerste rij en één raster in de tweede rij weergegeven. Er zijn dus in totaal drie responsieve rasters (r1c1, r1c2, r2c1).

1. Kopiëren `/libs/settings/wcm/designs/screens` tot `/apps/settings/wcm/designs/` en wijzig de naam van het gekopieerde ontwerp **custom-template-ontwerpen**.

1. Navigeren naar `/apps/settings/wcm/designs/custom-template-designs` en werk de eigenschap bij *`jcr:title`* van **custom-template-ontwerpen** tot **customtemplate-design**.

1. Navigeren naar `/apps/settings/wcm/designs/custom-template-designs` en maak een bestand static.css.

1. Inhoud kopiëren naar `static.css` bestand:

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

1. Navigeren naar `/apps/<project>/templates/my-custom-layout/jcr:content` en werk de eigenschap bij *`cq:designPath`* tot `/apps/settings/wcm/designs/customtemplate-designs` zodat kunt u de stijlen laden die in static.css worden gevormd.

   >[!NOTE]
   >Typ alle stijlen in plaats van kopiëren of plakken. Hierdoor kunnen er witruimten ontstaan die resulteren in problemen met CSS-stijlen.

## Het resultaat weergeven {#viewing-result}

Voer de onderstaande stappen uit om de bovenstaande aangepaste sjabloon te gebruiken in uw AEM Screens-project:

1. Navigeer naar uw project van het Scherm dat u in stap 1 creeerde en klik **Kanalen** map.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klikken **Maken** op de actiebalk en klik op de sjabloon **`Left20-LandscapeHD3Zone`** van de **Maken** wizard.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nadat u een kanaal met het aangepaste malplaatje hebt gecreeerd, kunt u activa aan uw kanaal van de redacteur toevoegen. In het volgende voorbeeld worden de afbeeldingen in een aangepaste sjabloon weergegeven.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Een afbeelding invoegen als achtergrondlaag  {#inserting-image}

U kunt een afbeelding als achtergrondlaag invoegen in de layout:

U kunt de CSS-regel aanpassen om &quot;data-uri&quot; te gebruiken en de afbeelding direct in te line (`Base64` gecodeerd) in het CSS-bestand waarin u hebt gemaakt (stap 13), *static.css*.

Dit gebeurt als volgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

U kunt ook de onderstaande stappen volgen:

1. Zorg ervoor dat de afbeelding op een of andere manier is opgenomen in de offlineconfiguratie voor het kanaal.
1. Gebruik een directe koppeling naar de afbeelding in de bovenstaande CSS in plaats van de &quot;data-uri&quot;-variant.


## Achtergrondkleur bijwerken {#updating-color}

Als u de achtergrondkleur wilt wijzigen, voegt u de volgende code toe aan het XML-bestand (stap 13). *static.css*.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`
