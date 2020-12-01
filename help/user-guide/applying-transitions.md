---
title: Overgangen toepassen
seo-title: Overgangen toepassen
description: Volg deze pagina om te leren hoe u overgangen kunt toepassen op uw projecten van het Scherm.
seo-description: Volg deze pagina om te leren hoe u overgangen kunt toepassen op uw projecten van het Scherm.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
translation-type: tm+mt
source-git-commit: 9b54b153676852742859b704ac9aedf908fceecf
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 1%

---


# Overgangen {#applying-transitions} toepassen

In deze sectie wordt beschreven hoe u de component **Overgang** kunt toepassen tussen verschillende elementen (afbeeldingen en video&#39;s) en ingesloten reeksen in een kanaal.


>[!CAUTION]
>
>Raadpleeg [Overgangen](adding-components-to-a-channel.md#transition) voor meer informatie over de eigenschappen van de component **Overgang**.

## Overgangscomponent toevoegen aan elementen in een kanaal {#adding-transition}

Voer de onderstaande stappen uit om een overgangscomponent toe te voegen aan uw AEM Screens-project:

>[!NOTE]
>
>**Vereisten**
>
>Maak een AEM Screens-project **TestProject** met een kanaal **TestTransition**. Stel bovendien een locatie en een weergave in om de uitvoer weer te geven.

1. Navigeer naar het kanaal **TestTransition** en klik **Edit** van de actiebar.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >Het kanaal **TestTransition** bevat al weinig elementen (afbeeldingen en video&#39;s). Het kanaal **TestTransition** bevat bijvoorbeeld drie afbeeldingen en twee video&#39;s, zoals hieronder wordt getoond:

   ![image2](assets/transitions2.png)


1. Sleep de component **Transition** naar de editor.
   >[!CAUTION]
   >
   >Voordat u de overgang naar uw elementen in uw kanaal toevoegt, moet u ervoor zorgen dat u geen overgang toevoegt vóór het eerste element in het opeenvolgende kanaal. Het eerste item in uw kanaal moet een element zijn en geen overgang.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >Standaard worden de eigenschappen van de overgangscomponent, zoals **Type**, ingesteld op **Vervagen** en **Duur** op *1600 ms*.  Bovendien is het niet aan te raden een overgangstijd in te stellen die langer is dan het actief waarop de overgang wordt toegepast.

1. Als u bovendien een **Ingesloten reeks** component (die een opeenvolgingskanaal omvat) aan deze kanaalredacteur toevoegt, kunt u een overgangscomponent aan het eind toevoegen, zodat de inhoud in orde speelt, zoals aangetoond in het hieronder cijfer:

   ![image3](assets/transitions5.png)

