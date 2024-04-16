---
title: Overgangen toepassen
description: Leer hoe u overgangen toepast op uw AEM Screens-projecten.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
source-git-commit: fff2df02661fc3fb3098be40e090b8bc6925bcc2
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Overgangen toepassen {#applying-transitions}

In deze sectie wordt beschreven hoe u het dialoogvenster **Overgang** tussen verschillende elementen (afbeeldingen en video&#39;s) en ingesloten reeksen in een kanaal.

>[!CAUTION]
>
>Meer informatie over de eigenschappen van de **Overgang** component, zie [Overgangen](adding-components-to-a-channel.md#transition).

## Overgangscomponent toevoegen aan elementen in een kanaal {#adding-transition}

Voer de onderstaande stappen uit om een overgangscomponent toe te voegen aan uw AEM Screens-project:

>[!NOTE]
>
>**Vereisten**
>
>Een AEM Screens-project maken **TestProject** met een kanaal **TestTransition**. Stel ook een locatie en een weergave in om de uitvoer weer te geven.

1. Navigeren naar het kanaal **TestTransition** en klik op **Bewerken** in de actiebalk.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >De **TestTransition** het kanaal bevat al weinig elementen (afbeeldingen en video&#39;s). Bijvoorbeeld de **TestTransition** kanaal bevat drie afbeeldingen en twee video&#39;s, zoals hieronder wordt getoond:

   ![image2](assets/transitions2.png)


1. Sleep de **Overgang** aan uw redacteur.

   >[!CAUTION]
   >
   >Voordat u de overgang naar uw elementen in uw kanaal toevoegt, moet u ervoor zorgen dat u geen overgang toevoegt vóór het eerste element in het opeenvolgende kanaal. Het eerste item in uw kanaal moet een element zijn en geen overgang.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >Standaard worden de eigenschappen van de overgangscomponent, zoals **Type** is ingesteld op **Vervagen** en de **Duur** is ingesteld op *1600 milliseconden*. Het is ook niet aan te raden een overgangstijd in te stellen die langer is dan het actief waarop het wordt toegepast.

1. Ook als u een **Ingesloten reeks** (met een volgnummer) aan deze kanaaleditor kunt u aan het einde een overgangscomponent toevoegen. Op deze manier wordt de inhoud in de juiste volgorde afgespeeld, zoals in de volgende afbeelding wordt getoond:

   ![image3](assets/transitions5.png)
