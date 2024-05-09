---
title: Aangepaste branding en opmaak toepassen voor tekstbedekkingen
description: Leer hoe u aangepaste branding en opmaak toepast voor tekstbedekkingen die zijn toegepast op elementen in een AEM Screens-kanaal.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 059e1b19-e9b5-48f0-8f2f-141f0c2f7842
source-git-commit: ce8340f24d116b4268a6ed15dd4e9f626bad1ef6
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Aangepaste branding en opmaak voor tekstbedekkingen {#creating-custom-branding-styling}

Leer hoe u aangepaste branding en opmaak toepast voor tekstbedekkingen die op uw middelen in een AEM Screens-kanaal zijn toegepast.

## Aangepaste branding en opmaak maken voor tekstbedekkingen {#steps-custom-branding}

Volg de onderstaande stappen om aangepaste branding en opmaak voor tekstbedekkingen te maken:

1. Maak een AEM Screens-project. In dit voorbeeld wordt de functionaliteit weergegeven door een project met de naam **`customstyle`** en een kanaal met **DemoBrand**, zoals weergegeven in onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Sleep vanuit de editor een afbeelding en zet deze neer en voeg een tekstbedekking toe aan het element.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Ga voor meer informatie over het toevoegen van een tekstbedekking aan uw element in een kanaaleditor naar [Tekstbedekking](/help/user-guide/text-overlay.md).

1. Navigeer naar CRXDE Lite via AEM > Gereedschappen > **CRXDE Lite**.

1. Een aangepast ontwerp maken in `/apps/settings/wcm/designs/<your-project>/`In dit geval navigeert u bijvoorbeeld naar `/apps/settings/wcm/designs/customstyle/`

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Een *static.css* en stelt de volgende CSS-regels in. Wordt ook weergegeven als voorbeeld in de afbeelding onder de CSS-regels.

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

1. Kopieer het pad naar uw project, in dit geval is het pad `/apps/settings/wcm/designs/customstyle`.

1. Navigeren naar het kanaal met de naam **DemoBrand** (gemaakt in stap (1)) en klik op **Eigenschappen** in de actiebalk nadat u het kanaal hebt geselecteerd.

1. Ga naar de **Geavanceerd** en controleer de **Ontwerp** veld.
   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Standaard zijn de **Ontwerp** in het veld wordt het pad weergegeven dat naar ontwerpen verwijst in de map libs.

1. Werk de **Ontwerp** veld met het pad naar de projectmap. In dit geval is het `/apps/settings/wcm/designs/customstyle`.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klikken **Opslaan en sluiten** om het ontwerppad bij te werken.

   >[!IMPORTANT]
   >U kunt desgewenst de bestaande sjablonen voor schermen bedekken om uw eigen ontwerpen standaard te injecteren of uw eigen sjabloon geheel maken. Zie de onderstaande stappen voor meer informatie.

1. Als u de bestaande sjablonen voor schermen wilt bedekken om uw eigen ontwerpen standaard te injecteren:

   1. Bedekking `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel`.
   1. Wijzig de *`cq:designPath`* eigenschap in `/apps/screens/core/templates/sequencechannel/jcr:content` zodat het naar het nieuwe ontwerp verwijst.

1. Uw eigen sjabloon maken:
   1. Kopiëren `/libs/screens/core/templates/sequencechannel` tot `/apps/customstyle/templates/styled-sequencechannel`.
   1. Wijzig de *`cq:designPath`* eigenschap in `/apps/customstyle/templates/styled-sequencechannel/jcr:content` zodat het naar het nieuwe ontwerp verwijst.


### ACLs bijwerken {#updating-acls}

Werk ACLs voor deze ontwerpen bij zodat kan de speler hen downloaden.

1. Navigeer naar gebruikersbeheerder en kies de optie `screens-<project>-devices group` en geeft deze leesmachtigingen aan het aangepaste ontwerppad.

1. Verlenen `screens-<project>-administrators` machtigingen voor het lezen en wijzigen van dit pad groeperen.

## Het resultaat weergeven {#viewing-the-result}

Wanneer u de voorgaande stappen hebt uitgevoerd, kunt u uw *stats.css* bestand van **CRXDE Lite** en bekijk daarom de update van uw tekstbedekking die al aan het element is toegevoegd.

Voer de onderstaande stappen uit om het bijgewerkte ontwerp voor tekstbedekking weer te geven:

1. Ga naar uw AEM Screens-project met de naam **`customstyle`** > **Kanalen** > **DemoBrand**. Klik op het kanaal en klik **Bewerken** in de actiebalk.

1. Aangezien u het ontwerp nu aan uw **Ontwerpen** , zoals hierboven vermeld, klikt u op **Voorvertoning** Hiermee geeft u de huidige opmaak op de afbeelding weer met tekstbedekking.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Ga naar uw *static.css* bestand in CRXDE Lite en voeg het lettertype toe, zoals `font-family: "Lucida Console", Courier, monospace;` naar dit bestand, zoals hieronder wordt weergegeven.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Wanneer u de wijzigingen opslaat en de voorvertoning opnieuw laadt, wordt het lettertype voor tekstbedekking bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Bovendien kunt u de laatste twee codeblokken verwijderen uit de *static.css* bestand om de opmaakcode van de vakken rond de tekstbedekking te verwijderen.

![afbeelding](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. Bekijk de bijgewerkte wijziging in de voorvertoning waar de tekstbedekking aan de afbeelding is toegevoegd.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand11.png)

   Nu kunt u uw merk en aangepaste opmaak bijwerken voor tekstbedekkingen die aan uw elementen zijn toegevoegd.
