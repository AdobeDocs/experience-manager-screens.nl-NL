---
title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
seo-title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
seo-description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: f91faa23c7c5c4f0f705c77251554b64efaf2611

---


# Aangepaste branding en opmaak voor tekstbedekkingen {#creating-custom-branding-styling}

Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.

## Aangepaste branding en opmaak maken voor tekstbedekkingen {#steps-custom-branding}

Volg de onderstaande stappen om aangepaste branding en opmaak voor tekstbedekkingen te maken:

1. Maak een AEM-schermproject met de naam **customstyle** en een kanaal met de naam **DemoBrand**, zoals in de onderstaande afbeelding wordt getoond.

   ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Sleep vanuit de editor een afbeelding en zet deze neer en voeg tekstbedekking toe aan het element.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Zie [Tekstbedekking](/help/user-guide/text-overlay.md)voor meer informatie over het toevoegen van een tekstbedekking aan uw element in een kanaaleditor.

1. Navigeer naar CRXDE Lite van uw AEM instantie —> Hulpmiddelen —> **CRXDE Lite**.

1. In dit geval moet u een aangepast ontwerp maken `/apps/settings/wcm/designs/<your-project>/`in

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Navigeer naar het bestand static.css en stel de volgende CSS-regels in. Ook weergegeven in onderstaande afbeelding.

   ```shell
    //global styles
    .cq-Screens-textOverlay
    { … }
    //authoring overrides
    .aem-AuthorLayer-Edit .cq-Screens-textOverlay { … }
    // light text variant
    .cq-Screens-textOverlay-color--light
    { … }
     // dark text variant
    .cq-Screens-textOverlay-color--dark { … }
   ```
   ![image](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Kopieer het pad naar uw project. In dit geval wordt het pad `/apps/settings/wcm/designs/customstyle`gewijzigd.

1. Navigeer naar het kanaal met de naam **DemoBrand** (gemaakt in stap 1) en klik op **Eigenschappen** in de actiebalk nadat u het kanaal hebt geselecteerd.

1. Navigeer naar het tabblad **Geavanceerd** en controleer het veld **Ontwerpen** .
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standaard wordt in het veld **Ontwerpen** het pad weergegeven dat naar ontwerpen verwijst in de map libs.

1. Werk het veld **Ontwerpen** bij met het pad naar de projectmap. In dit geval zal het zo zijn, `/apps/settings/wcm/designs/customstyle`.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klik op **Opslaan en sluiten** om het ontwerppad bij te werken.


## Het resultaat weergeven {#viewing-the-result}

Nadat u de voorgaande stappen hebt uitgevoerd, kunt u het bestand *stats.css* bijwerken vanuit **CRXDE Lite** en als gevolg daarvan de update bekijken van de tekstlay-out die aan het element is toegevoegd.

Voer de onderstaande stappen uit om het bijgewerkte ontwerp te bekijken als tekstlay-out:

1. Navigeer naar het AEM-schermproject met de naam **customstyle** en een kanaal met de naam **DemoBrand** en klik op **Bewerken** op de actiebalk om de editor te openen.

1. Aangezien u het ontwerp nu hebt toegevoegd aan het veld **Ontwerpen** , zoals hierboven vermeld, klikt u op **Voorvertoning** om de huidige opmaak van de afbeelding met tekstbedekking weer te geven.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigeer naar het bestand static.css in CRXDE Lite en voeg bijvoorbeeld het lettertype toe.
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Nadat u de wijzigingen hebt opgeslagen en de voorvertoning opnieuw hebt geladen, wordt het lettertype voor de tekstbedekking bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Bovendien kunt u de laatste twee codeblokken uit het bestand static.css verwijderen om de in vakken geplaatste opmaak rond de tekstbedekking te verwijderen.
   ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. U ziet de bijgewerkte wijziging in de voorvertoning waar de tekstbedekking aan de afbeelding wordt toegevoegd, zoals hieronder wordt weergegeven.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

Op deze manier kunt u na de stappen in de voorgaande secties uw merk en aangepaste opmaak bijwerken voor tekstbedekkingen die aan uw elementen zijn toegevoegd.









