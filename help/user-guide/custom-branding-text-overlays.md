---
title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
seo-title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
seo-description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
contentOwner: Jyotika Syal
feature: Schermen ontwikkelen
role: Developer
level: Intermediate
source-git-commit: 4611dd40153ccd09d3a0796093157cd09a8e5b80
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 1%

---


# Aangepaste branding en opmaak voor tekstbedekkingen {#creating-custom-branding-styling}

Volg deze pagina om te leren hoe u aangepaste branding en opmaak kunt toepassen op tekstbedekkingen die op uw elementen in een AEM Screens-kanaal zijn toegepast.

## Aangepaste branding en opmaak maken voor tekstbedekkingen {#steps-custom-branding}

Volg de onderstaande stappen om aangepaste branding en opmaak voor tekstbedekkingen te maken:

1. Maak een AEM Screens-project. In dit voorbeeld wordt de functionaliteit weergegeven door een project met de naam **customstyle** te maken en een kanaal met de naam **DemoBrand**, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Sleep vanuit de editor een afbeelding en zet deze neer en voeg tekstbedekking toe aan het element.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Zie [Tekstbedekking](/help/user-guide/text-overlay.md) voor meer informatie over het toevoegen van een tekstbedekking aan uw element in een kanaaleditor.

1. Navigeer naar CRXDE Lite van uw AEM-instantie —> -gereedschappen —> **CRXDE Lite**.

1. U moet een aangepast ontwerp maken in `/apps/settings/wcm/designs/<your-project>/`, in dit geval navigeert u bijvoorbeeld naar `/apps/settings/wcm/designs/customstyle/`

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Maak *static.css* bestand en stel de volgende css-regels in. Wordt ook weergegeven als voorbeeld in de afbeelding onder de CSS-regels.

   ```shell
    //global styles
    cq-Screens-textOverlay {
    padding: 1em;
    font-size: 3rem;
    line-height: 1em;
     }
    //authoring overrides
   .aem-AuthorLayer-Edit .cq-Screens-textOverlay {
    display: none;
    padding: 0;
    font-size: 1rem;
    }
     // light text variant
    .cq-Screens-textOverlay-color--light {
     background-color: rgba(0, 0, 0, .6);
     }
     // dark text variant
     .cq-Screens-textOverlay-color--dark {
      background-color: rgba(255, 255, 255, .6);
    }
   ```

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Kopieer het pad naar uw project. In dit geval is het pad `/apps/settings/wcm/designs/customstyle`.

1. Navigeer naar het kanaal met de naam **DemoBrand** (gemaakt in stap(1)) en klik op **Eigenschappen** op de actiebalk nadat u het kanaal hebt geselecteerd.

1. Navigeer naar het tabblad **Geavanceerd** en controleer het veld **Design**.
   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standaard wordt in het veld **Design** het pad weergegeven dat naar ontwerpen verwijst in de map libs.

1. Werk het **Ontwerp** gebied met de weg aan uw projectomslag bij. In dit geval is dit `/apps/settings/wcm/designs/customstyle`.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klik **Opslaan en sluiten** om het ontwerppad bij te werken.

   >[!IMPORTANT]
   >U kunt de bestaande sjablonen voor schermen bedekken door standaard uw eigen ontwerpen te injecteren of uw eigen sjabloon te maken. Raadpleeg de onderstaande stappen voor meer informatie.

1. Als u de bestaande sjablonen voor schermen wilt bedekken om uw eigen ontwerpen standaard te injecteren:

   1. Bedekking `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel`.
   1. Wijzig *cq:designPath* bezit in `/apps/screens/core/templates/sequencechannel/jcr:content` om aan het nieuwe ontwerp te richten.

1. Uw eigen sjabloon maken:
   1. Kopieer `/libs/screens/core/templates/sequencechannel` naar `/apps/customstyle/templates/styled-sequencechannel`.
   1. Wijzig *cq:designPath* bezit in `/apps/customstyle/templates/styled-sequencechannel/jcr:content` om aan het nieuwe ontwerp te richten.


### ACLs {#updating-acls} bijwerken

U moet ACLs voor deze ontwerpen bijwerken zodat zij door de speler kunnen worden gedownload.

1. Navigeer naar gebruikersbeheerder en kies `screens-<project>-devices group` en geef deze leesmachtigingen aan het aangepaste ontwerppad.

1. Geef `screens-<project>-administrators` groep lees- en wijzigingsmachtigingen op voor dit pad.

## Resultaat {#viewing-the-result} weergeven

Nadat u de voorgaande stappen hebt uitgevoerd, kunt u het bestand *stats.css* uit **CRXDE Lite** bijwerken en als gevolg daarvan de update bekijken van de tekstbedekking die al aan het element is toegevoegd.

Voer de onderstaande stappen uit om het bijgewerkte ontwerp voor tekstbedekking weer te geven:

1. Navigeer naar uw AEM Screens-project met de naam **customstyle** —> **Channels** —> **DemoBrand**. Selecteer het kanaal en klik **Bewerken** van de actiebar om de redacteur te openen.

1. Aangezien u het ontwerp nu hebt toegevoegd aan het veld **Ontwerpen**, zoals hierboven vermeld, klikt u op **Voorvertoning** om de huidige opmaak van de afbeelding met tekstbedekking weer te geven.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigeer naar het bestand *static.css* in CRXDE Lite en voeg het lettertype `font-family: "Lucida Console", Courier, monospace;` toe aan dit bestand, zoals hieronder wordt weergegeven.
   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Nadat u de wijzigingen hebt opgeslagen en de voorvertoning opnieuw hebt geladen, wordt het lettertype voor tekstbedekking bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Bovendien kunt u de laatste twee codeblokken verwijderen uit het bestand *static.css* om de in vakken geplaatste opmaak rond de tekstbedekking te verwijderen.
   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. U ziet de bijgewerkte wijziging in de voorvertoning waar de tekstbedekking aan de afbeelding is toegevoegd.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand11.png)

   Nu kunt u uw merk en aangepaste opmaak bijwerken voor tekstbedekkingen die aan uw elementen zijn toegevoegd.









