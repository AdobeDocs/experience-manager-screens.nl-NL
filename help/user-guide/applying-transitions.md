---
title: Overgangen toepassen
description: Leer hoe u overgangen toepast op uw AEM Screens-projecten.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Overgangen toepassen {#applying-transitions}

Deze sectie beschrijft hoe u de **component van de Overgang** binnen-tussen verschillende activa (beelden en video&#39;s) en ingebedde opeenvolgingen in een kanaal kunt toepassen.

>[!CAUTION]
>
>Om in detail over de eigenschappen voor de **component van de Overgang** te leren, zie [&#x200B; Overgangen &#x200B;](adding-components-to-a-channel.md#transition).

## Overgangscomponent toevoegen aan Assets in een kanaal {#adding-transition}

Voer de onderstaande stappen uit om een overgangscomponent toe te voegen aan uw AEM Screens-project:

>[!NOTE]
>
>**Eerste vereisten**
>
>Creeer een project van AEM Screens **TestProject** met een kanaal **TestTransition**. Stel ook een locatie en een weergave in om de uitvoer weer te geven.

1. Navigeer aan het Kanaal **TestTransition** en klik **uitgeven** van de actiebar.

   ![&#x200B; image1 &#x200B;](assets/transitions1.png)

   >[!NOTE]
   >
   >Het **&#x200B;**&#x200B;kanaal TestTransition heeft reeds een paar activa (beelden en video&#39;s) in het. Bijvoorbeeld, omvat het **kanaal 0&rbrace; TestTransition &lbrace;drie beelden en twee video&#39;s, zoals hieronder getoond:**

   ![&#x200B; image2 &#x200B;](assets/transitions2.png)


1. Sleep en laat vallen de **component van de Overgang** aan uw redacteur.

   >[!CAUTION]
   >
   >Voordat u de overgang naar uw elementen in uw kanaal toevoegt, moet u ervoor zorgen dat u de overgang niet toevoegt vóór het eerste element in het opeenvolgende kanaal. Het eerste item in uw kanaal moet een element zijn en geen overgang.

   ![&#x200B; image3 &#x200B;](assets/transitions3.png)

   >[!NOTE]
   >
   >Door gebrek, worden de eigenschappen van de overgangscomponent zoals **Type** geplaatst aan **langzaam verdwijnen** en de **Duur** wordt geplaatst aan *1600 milliseconden*. Het is ook niet aan te raden een overgangstijd in te stellen die langer is dan het actief waarop het wordt toegepast.

1. Ook, als u een **Ingebedde component van de Opeenvolging** (die een opeenvolgingskanaal) aan deze kanaalredacteur omvat, kunt u een overgangscomponent aan het eind toevoegen. Zo weet u zeker dat de inhoud in de juiste volgorde wordt afgespeeld, zoals in de volgende afbeelding wordt getoond:

   ![&#x200B; image3 &#x200B;](assets/transitions5.png)
