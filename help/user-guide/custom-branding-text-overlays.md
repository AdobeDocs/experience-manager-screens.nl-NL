---
title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
seo-title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
seo-description: Volg deze pagina om te leren hoe u aangepaste branding en opmaak voor tekstbedekkingen kunt toepassen.
contentOwner: Jyotika Syal
translation-type: tm+mt
source-git-commit: fdbe57b2cd927c112e9faa4888e3565626712c7a

---


# Aangepaste branding en opmaak voor tekstbedekkingen {#creating-custom-branding-styling}

Volg deze pagina om te leren hoe u aangepaste branding en opmaak kunt toepassen op tekstbedekkingen die op uw elementen in een rasterkanaal zijn toegepast.

## Aangepaste branding en opmaak maken voor tekstbedekkingen {#steps-custom-branding}

Volg de onderstaande stappen om aangepaste branding en opmaak voor tekstbedekkingen te maken:

1. Maak een AEM-schermproject. In dit voorbeeld wordt de functionaliteit weergegeven door een project met de naam **customstyle** en een kanaal met de naam **DemoBrand** te maken, zoals in de onderstaande afbeelding wordt getoond.

   ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Sleep vanuit de editor een afbeelding en zet deze neer en voeg tekstbedekking toe aan het element.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Zie [Tekstbedekking](/help/user-guide/text-overlay.md)voor meer informatie over het toevoegen van een tekstbedekking aan uw element in een kanaaleditor.

1. Navigeer naar CRXDE Lite van uw AEM instantie —> Hulpmiddelen —> **CRXDE Lite**.

1. U moet een aangepast ontwerp maken in `/apps/settings/wcm/designs/<your-project>/`, bijvoorbeeld, navigeer naar `/apps/settings/wcm/designs/customstyle/`

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Navigeer naar het bestand *static.css* en stel de volgende CSS-regels in. Wordt ook weergegeven als voorbeeld in de afbeelding onder de CSS-regels.

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

### ACLs bijwerken {#updating-acls}

U moet ACLs voor deze ontwerpen bijwerken zodat zij door de speler kunnen worden gedownload.

1. Navigeer naar gebruikersbeheer en kies de map `screens-<project>-devices group` en geef deze leesmachtigingen aan het aangepaste ontwerppad.

1. Geef machtigingen voor het lezen en wijzigen van `screens-<project>-administrators` groepen op voor dit pad.

## Het resultaat weergeven {#viewing-the-result}

Nadat u de voorgaande stappen hebt uitgevoerd, kunt u het bestand *stats.css* bijwerken vanuit **CRXDE Lite** en als gevolg daarvan de update bekijken van de tekstbedekking die al aan het element is toegevoegd.

Voer de onderstaande stappen uit om het bijgewerkte ontwerp voor tekstbedekking weer te geven:

1. Navigeer naar het AEM-schermproject met de naam **customstyle** —> **Channels** —> **DemoBrand**. Selecteer het kanaal en klik op **Bewerken** op de actiebalk om de editor te openen.

1. Aangezien u het ontwerp nu hebt toegevoegd aan het veld **Ontwerpen** , zoals hierboven vermeld, klikt u op **Voorvertoning** om de huidige opmaak van de afbeelding met tekstbedekking weer te geven.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigeer naar het bestand *static.css* in CRXDE Lite en voeg het lettertype, zoals, toe `font-family: "Lucida Console", Courier, monospace;` aan dit bestand, zoals hieronder wordt weergegeven.
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Nadat u de wijzigingen hebt opgeslagen en de voorvertoning opnieuw hebt geladen, wordt het lettertype voor tekstbedekking bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Bovendien kunt u de laatste twee codeblokken verwijderen uit het bestand *static.css* om de in het vak geplaatste stijl rond de tekstbedekking te verwijderen.
   ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. U ziet de bijgewerkte wijziging in de voorvertoning waar de tekstbedekking aan de afbeelding is toegevoegd.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

In de zelfstudie kunt u nu uw merk en aangepaste opmaak bijwerken voor tekstbedekkingen die aan uw elementen zijn toegevoegd.









