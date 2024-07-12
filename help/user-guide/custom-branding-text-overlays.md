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

1. Maak een AEM Screens-project. Dit voorbeeld toont de functionaliteit door een project te creëren genoemd **`customstyle`** en een kanaal genoemd **DemoBrand**, zoals aangetoond in het hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. Sleep vanuit de editor een afbeelding en zet deze neer en voeg een tekstbedekking toe aan het element.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand2.png)

   >[!NOTE]
   >Leren hoe te om een tekstbedekking aan uw activa in een kanaalredacteur toe te voegen, zie [ Bedekking van de Tekst ](/help/user-guide/text-overlay.md).

1. Navigeer aan CRXDE Lite van uw AEM instantie > hulpmiddelen > **CRXDE Lite**.

1. Een aangepast ontwerp maken in `/apps/settings/wcm/designs/<your-project>/` , navigeer in dit geval naar `/apps/settings/wcm/designs/customstyle/`

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Creeer a *static.css* dossier en plaats de volgende css regels. Wordt ook weergegeven als voorbeeld in de afbeelding onder de CSS-regels.

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

1. Kopieer het pad naar uw project, in dit geval is het pad `/apps/settings/wcm/designs/customstyle` .

1. Navigeer aan het kanaal dat als **wordt genoemd DemoBrand** (in stap (1) wordt gecreeerd) en klik **Eigenschappen** van de actiebar na het selecteren van het kanaal.

1. Navigeer aan het **Geavanceerde** lusje en controleer het **3} gebied van het Ontwerp {.**
   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Ben gebrek, toont het **1} gebied van het Ontwerp {de weg die aan ontwerpen in de bibliotheekomslag richt.**

1. Werk het **gebied van het Ontwerp** met de weg aan uw projectomslag bij. In dit geval is dit `/apps/settings/wcm/designs/customstyle` .

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Klik **sparen &amp; dicht** om de ontwerppad bij te werken.

   >[!IMPORTANT]
   >U kunt desgewenst de bestaande Screens-sjablonen bedekken om uw eigen ontwerpen standaard te injecteren of uw eigen sjabloon geheel maken. Zie de onderstaande stappen voor meer informatie.

1. Als u de bestaande Screens-sjablonen wilt bedekken om uw eigen ontwerpen standaard te injecteren:

   1. Bedekking `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel` .
   1. Wijzig de eigenschap *`cq:designPath`* in `/apps/screens/core/templates/sequencechannel/jcr:content` zodat deze naar het nieuwe ontwerp wijst.

1. Uw eigen sjabloon maken:
   1. Kopieer `/libs/screens/core/templates/sequencechannel` naar `/apps/customstyle/templates/styled-sequencechannel` .
   1. Wijzig de eigenschap *`cq:designPath`* in `/apps/customstyle/templates/styled-sequencechannel/jcr:content` zodat deze naar het nieuwe ontwerp wijst.


### ACLs bijwerken {#updating-acls}

Werk ACLs voor deze ontwerpen bij zodat kan de speler hen downloaden.

1. Navigeer naar gebruikersbeheerder en kies `screens-<project>-devices group` en geef deze leesmachtigingen voor het aangepaste ontwerppad.

1. Geef `screens-<project>-administrators` machtigingen voor het lezen en wijzigen van dit pad op.

## Het resultaat weergeven {#viewing-the-result}

Wanneer u de voorafgaande stappen hebt voltooid, kunt u uw {*dossier 0} stats.css van **CRXDE Lite**bijwerken en daarom de update aan uw tekstbedekking bekijken die reeds aan de activa wordt toegevoegd.*

Voer de onderstaande stappen uit om het bijgewerkte ontwerp voor tekstbedekking weer te geven:

1. Navigeer aan uw project van AEM Screens dat als **`customstyle`** wordt genoemd > **Kanalen** > **DemoBrand**. Klik het kanaal en klik **uitgeven** van de actiebar.

1. Aangezien u nu het ontwerp aan uw **Ontwerpen** gebied, zoals hierboven vermeld hebt toegevoegd, klik **Voorproef** om het huidige stileren op het beeld met tekstbedekking te bekijken.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigeer aan uw *static.css* dossier in CRXDE Lite, en voeg de doopvont zoals, `font-family: "Lucida Console", Courier, monospace;` aan dit dossier toe, zoals hieronder getoond.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Wanneer u de wijzigingen opslaat en de voorvertoning opnieuw laadt, wordt het lettertype voor tekstbedekking bijgewerkt, zoals in de onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Ook, kunt u de laatste twee blokken van code uit het {*dossier verwijderen 0} static.css om het in dozen vervaardigde stileren rond de tekstbedekking te verwijderen.*

![afbeelding](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. Bekijk de bijgewerkte wijziging in de voorvertoning waar de tekstbedekking aan de afbeelding is toegevoegd.

   ![afbeelding](/help/user-guide/assets/custom-brand/custom-brand11.png)

   Nu kunt u uw merk en aangepaste opmaak bijwerken voor tekstbedekkingen die aan uw elementen zijn toegevoegd.
