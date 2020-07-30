---
title: Aangepaste sjablonen maken in MultiZone-lay-outs
seo-title: Aangepaste sjablonen maken in MultiZone-lay-outs
description: Volg deze pagina voor meer informatie over het maken van aangepaste sjablonen in MultiZone-lay-outs.
seo-description: Volg deze pagina voor meer informatie over het maken van aangepaste sjablonen in MultiZone-lay-outs.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: 8492bdd071ae029a68ec4a4983c79ce326cac38b
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 1%

---


# Aangepaste sjablonen maken voor MultiZone-layouts {#creating-custom-templates-multizone}

Op deze pagina ziet u hoe u een aangepaste sjabloon voor een lay-out met meerdere zones kunt maken.

## Belangrijke overwegingen {#considerations}

Er zijn twee belangrijke overwegingen dat u zich moet bewust zijn alvorens tot douanemalplaatje in multi-zonelay-out te leiden:

1. **Vaste pixelgrootte of percentages**:

   U moet bepalen of u de vaste pixelgrootte voor verschillende zones wilt gebruiken voor uw aangepaste layout of dat u een aangepaste indeling wilt maken met percentages.

   >[!NOTE]
   >Het voordeel van het gebruiken van percentage om streken voor uw douanelay-out te plaatsen staat u toe om het malplaatje op een verscheidenheid van het schermgrootte opnieuw te gebruiken.

1. **Naamgevingsconventie**:

   Alvorens u begrijpt hoe te om douane multi-zone malplaatjes tot stand te brengen om in een project van AEM Screens te gebruiken, wordt het geadviseerd om het overzicht van de malplaatjes te begrijpen u zou willen tot stand brengen.

   | **Lay-outnaam** | **Beschrijving** |
   |---|---|
   | Left20-LandscapeHD3Zone | Verwijst naar een 3-zone liggende lay-out, waarmee u 3 zones kunt maken met zone 1 als 20% van het horizontale en verticale scherm van links, zone 2 als 80 % van het horizontale scherm en 20 % van het verticale scherm rechts uitgevuld, zone 3 als 100 % van het horizontale en 80 % van het verticale scherm met een hoogte-breedteverhouding van 16:9 |
   | Upper20-PortraitHD2Zone | Verwijst naar een 2-zone Staand malplaatje dat 20% van het scherm van de bovenkant bedekt, met aspectverhouding van 16:9 |
   | Right20-LandscapeSD3Zone | Verwijst naar een 3-zone sjabloon die 20% van het scherm van rechts bedekt, met een hoogte-breedteverhouding van 4:3 |

   >[!IMPORTANT]
   >De zones die zijn gedefinieerd in de aangepaste indeling komen mogelijk niet overeen met de algemene hoogte-breedteverhouding van de volledige layout. In de naamgevingsconventie die in dit document wordt gevolgd, wordt de hoogte-breedteverhouding van de aangepaste layout als geheel opgegeven.

## Voorbeeld Lay-out hoofdletters gebruiken: Left20-LandscapeHD3Zone {#custom-template-one}

Volg de sectie hieronder om een douanemalplaatje *Left20-LandscapeHD3Zone* met de volgende configuratie tot stand te brengen:

* **Left20** verwijst naar de naar de hoogste streek op de linkerzijde die 20% van horizontale en verticale schermgrootte bedekt.
* **Liggend** verwijst naar de schermstand
* **In HD** wordt de hoogte-breedteverhouding 16:9 genoemd
* **3Zone** verwijst naar drie zones van de weergave

## Visuele representatie van MultiZone Layout {#multi-layout-visual-one}

Met de Left20-LandscapeHD3Zone-indeling kunt u de volgende lay-out met meerdere zones maken in uw project:

![afbeelding](/help/user-guide/assets/custom-multizone/landscape-3-zone-new.png)

## Een Left20-LandscapeHD3Zone-lay-out maken {#landscape-layout-one}

Voer de onderstaande stappen uit om een Left20-LandscapeHD3Zone-lay-out te maken voor een AEM Screens-project:

1. Maak een AEM Screens-project met de naam **customtemplate**.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template2.png)

1. Navigeer naar **CRXDE Lite** vanaf uw AEM-exemplaar —> Gereedschappen —> **CRXDE Lite**.

1. Maak een map onder **apps** met de naam **customtemplate**. Maak op dezelfde manier een andere map met de naam **template** onder **aangepaste sjabloon**, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template1.png)

   >[!NOTE]
   >U wordt aangeraden op Alles **** opslaan in de actiebalk in CRXDE Lite te klikken wanneer u inhoud maakt, bewerkt of kopieert naar een van de knooppunten. Als u dit niet doet, kunt u de updates niet doorvoeren.

1. Kopieer de sjabloon linksboven van `/libs/screens/core/templates/splitscreenchannel/lbar-left` naar `/apps/customtemplate/template`.

1. Wijzig de naam van de gekopieerde **lbar-left** (`/apps/customtemplate/template`) in **my-custom-layout**.
   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigeer naar de eigenschappen `/apps/customtemplate/template/my-custom-layout` jcr:description **en werk deze bij naar** Sjabloon voor Left20-LandscapeHD3Zone *en* jcr:title **naar** Left20-LandscapeHD3Zone **.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigeer naar de **offline-config** knoop van `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` en werk **jcr:title** aan *Left20-LandscapeHD3Zone* bij.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigeer naar de eigenschap *jcr:content* van **my-custom-template** van `/apps/customtemplate/template/my-custom-layout/jcr:content` en werk de eigenschap **cq:cssClass** bij naar **aem-Layout my-custom-layout**.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Verwijzend naar stap 4, waarin, u het bar-linkermalplaatje kopieerde, zult u 3 ontvankelijke netten onder bekijken `my-custom-layout/jcr:content`. Voeg aangepaste CSS-klasse toe aan elk responsief raster in de eigenschap *cq:cssClass* , bijvoorbeeld *my-custom-layout—top-left* voor de *r1c1* -node.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Op dezelfde manier voeg *mijn-douane-lay-out-top-right* voor *r1c2* en, *mijn-douane-lay-out-bodem* voor *r2c1* knoop toe.

   >[!NOTE]
   >Deze aangepaste klassen worden in de CSS gebruikt om de breedte/hoogte voor deze responsieve rasters in te stellen.

   >[!NOTE]
   >U kunt de responsieve rasters toevoegen of verwijderen op basis van het aantal totale rasters dat u wilt. In dit voorbeeld tonen we twee rasters in de eerste rij en één raster in de tweede rij. Er zijn dus in totaal drie responsieve rasters (r1c1, r1c2, r2c1).

1. Kopieer `/libs/settings/wcm/designs/screens` naar `/apps/settings/wcm/designs/` en wijzig de naam van het gekopieerde ontwerp in **aangepaste sjabloonontwerpen**.

1. Navigeer naar `/apps/settings/wcm/designs/custom-template-designs` en werk de eigenschap *jcr:title* van **custom-template-designs** bij naar **aangepast sjabloon-ontwerp**.

1. Navigeer naar een bestand static.css `/apps/settings/wcm/designs/custom-template-designs` en maak dit.

1. Kopieer de inhoud naar het bestand static.css:

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

1. Navigeer naar de eigenschap `/apps/<project>/templates/my-custom-layout/jcr:content` cq:designPath ** `/apps/settings/wcm/designs/customtemplate-designs` en werk deze bij om de stijlen te laden die in static.css zijn geconfigureerd

   >[!NOTE]
   >U wordt aangeraden alle stijlen te typen in plaats van deze te kopiëren of te plakken. Hierdoor kunnen witte ruimten problemen met CSS-stijlen veroorzaken.

## Het resultaat weergeven {#viewing-result}

Voer de onderstaande stappen uit om de bovenstaande aangepaste sjabloon te gebruiken in uw AEM Screens-project:

1. Navigeer naar uw project van het Scherm dat u in stap (1) creeerde en selecteer de omslag van **Kanalen** .

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Klik op **Maken** op de actiebalk en selecteer de sjabloon **Left20-LandscapeHD3Zone** in de wizard **Maken** .

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template9.png)

1. Nadat u een kanaal met de aangepaste sjabloon hebt gemaakt, kunt u elementen uit de editor toevoegen aan uw kanaal. In het volgende voorbeeld worden de afbeeldingen in een aangepaste sjabloon weergegeven.

   ![afbeelding](/help/user-guide/assets/custom-multizone/custom-template10.png)

## Een afbeelding invoegen als achtergrondlaag  {#inserting-image}

U kunt een afbeelding als achtergrondlaag invoegen in de layout:

U kunt de CSS-regel aanpassen om te gebruiken wat &quot;data-uri&quot; wordt genoemd en de afbeelding (Base64-gecodeerd) direct inline in het CSS-bestand plaatsen, die u hebt gemaakt in (stap 13), *static.css*.

Dit gebeurt als volgt:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`

U kunt ook de onderstaande stappen volgen:

1. Zorg ervoor dat de afbeelding op de een of andere manier is opgenomen in de offlineconfiguratie voor het kanaal
1. Gebruik een directe koppeling naar de afbeelding in de bovenstaande CSS in plaats van de &quot;data-uri&quot;-variant


## Achtergrondkleur bijwerken {#updating-color}

Als u de achtergrondkleur wilt wijzigen, voegt u de volgende code toe aan het XML-bestand (stap 13), *static.css*.

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`



