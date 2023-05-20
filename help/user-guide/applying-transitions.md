---
title: Overgangen toepassen
seo-title: Applying Transitions
description: Volg deze pagina om te leren hoe u overgangen kunt toepassen op uw projecten van het Scherm.
seo-description: Follow this page to learn how to apply transitions to your Screens projects.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---

# Overgangen toepassen {#applying-transitions}

In deze sectie wordt beschreven hoe u het dialoogvenster **Overgang** tussen verschillende elementen (afbeeldingen en video&#39;s) en ingesloten reeksen in een kanaal.


>[!CAUTION]
>
>Meer informatie over de eigenschappen van de **Overgang** component, verwijzing naar [Overgangen](adding-components-to-a-channel.md#transition).

## Overgangscomponent toevoegen aan elementen in een kanaal {#adding-transition}

Voer de onderstaande stappen uit om een overgangscomponent toe te voegen aan uw AEM Screens-project:

>[!NOTE]
>
>**Vereisten**
>
>Een AEM Screens-project maken **TestProject** met een kanaal **TestTransition**. Stel bovendien een locatie en een weergave in om de uitvoer weer te geven.

1. Navigeren naar het kanaal **TestTransition** en klik op **Bewerken** in de actiebalk.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >De **TestTransition** het kanaal bevat al weinig elementen (afbeeldingen en video&#39;s). De **TestTransition** kanaal bevat drie afbeeldingen en twee video&#39;s, zoals hieronder wordt getoond:

   ![image2](assets/transitions2.png)


1. Sleep de **Overgang** aan uw redacteur.
   >[!CAUTION]
   >
   >Voordat u de overgang naar uw elementen in uw kanaal toevoegt, moet u ervoor zorgen dat u geen overgang toevoegt vóór het eerste element in het opeenvolgende kanaal. Het eerste item in uw kanaal moet een element zijn en geen overgang.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >Standaard worden de eigenschappen van de overgangscomponent, zoals **Type** is ingesteld op **Vervagen** en de **Duur** is ingesteld op *1600 ms*.  Bovendien is het niet aan te raden een overgangstijd in te stellen die langer is dan het actief waarop de overgang wordt toegepast.

1. Als u bovendien een **Ingesloten reeks** (die een opeenvolgingskanaal omvat) aan deze kanaalredacteur, kunt u een overgangscomponent aan het eind toevoegen, zodat de inhoud in orde speelt, zoals aangetoond in het hieronder cijfer:

   ![image3](assets/transitions5.png)
