---
title: Adaptieve uitvoeringen gebruiken in AEM Screens
description: Op deze pagina wordt beschreven hoe u Adaptieve uitvoeringen in AEM Screens kunt gebruiken.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
source-git-commit: cd26f77b9b41a5854aaa1f936abed3b410533684
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Adaptieve uitvoeringen gebruiken in AEM Screens {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *hoofd* ervaring.

## Doelstelling {#objective}

Als AEM Screens Content Author kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudsvariaties hoeft te maken.
Als een ontwikkelaar de eigenschappen en regels voor de renditie-toewijzing heeft toegevoegd, kunt u de renditie-toewijzing nu toepassen op elementen en vervolgens de elementen in een AEM Screens-kanaal opnemen.

>[!IMPORTANT]
>Voordat u Adaptieve uitvoeringen gaat gebruiken, wordt u aangeraden om in een AEM Screens-kanaal te leren over het architecturale overzicht en de architecturale configuratie van deze functie. Zie [Adaptieve uitvoeringen: Overzicht en configuraties van architectuur](/help/user-guide/adaptive-renditions.md) voor meer informatie .

## Adaptieve uitvoeringen gebruiken in kanalen {#using-adaptive-renditions}

>[!NOTE]
>Zodra u hebt toegevoegd [eigenschap voor het toewijzen van vertoningen aan het schermproject](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) en [toewijzingsregels voor vertoningen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules)Als inhoudsauteur kunt u nu de uitvoeringen toepassen op uw elementen.

### Vertoningen toepassen op elementen {#apply-renditions-assets}

Voer de onderstaande stappen uit om vertoningen toe te passen op de elementen die u wilt gebruiken in het kanaal voor touroperrasters:

1. Ga naar de **Activa** in uw AEM-exemplaar.

1. Maak een versie van het element die beter geschikt is voor de bewegingsweergave, bijvoorbeeld `seahorse.jpg`.

1. Kies bijvoorbeeld het naamgevingspatroon van de vertoning.`landscape`, vergelijkbaar met de definitie in **patroon** eigenschap in **CRXDE Lite**. Zie [Regels voor renderingstoewijzing toevoegen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) voor meer informatie .

1. Klikken op **Vertoning toevoegen** om de vertoning te uploaden, zoals in onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Selecteer de naam van het elementbestand. De vertoning die u toevoegt, moet het patroon bevatten (gedefinieerd in stap 3), bijvoorbeeld `seahorse-landscape.png`.

1. Nadat u het element hebt toegevoegd, selecteert u het element en klikt u op **Publicatie beheren** op de actiebalk om het element te publiceren.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Zie [Update voor on-demand inhoud](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content.html?lang=en) voor meer informatie over het beheren van Publicatie en het leveren van inhoudsupdates van Auteur aan Publish aan apparaat.


## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken, adviseert men dat de migratie geleidelijk wordt gedaan om de risico&#39;s te verlichten aangezien de eigenschap veranderingen in manifest en dossieropslagformaat zal introduceren. Het toevoegen van `sling:configRef` voor het hele project moeten alle spelers worden bijgewerkt naar Feature Pack 6.5.9. Als u een aantal spelers hebt bijgewerkt, moet u de `sling:configRef` alleen naar die weergaven, locaties of kanaalmappen waarin alle spelers zijn bijgewerkt naar Feature Pack 6.5.9.

Het volgende diagram toont de migratiestrategie voor grote netwerken:

![afbeelding](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Om de eigenschap toe te laten, voeg minstens één toewijzingsregel toe en zorg ervoor de configuratie van de vertoningstoewijzing in de context van vertoningen en kanalen oplosbaar is. Voer de volgende stappen uit om te migreren:

1. Toevoegen [Regels voor renderingstoewijzing](/help/user-guide/adaptive-renditions.md).
1. Maak een map voor nieuwe kanalen en voeg een verwijzing toe die naar de configuratie van de vertoningstoewijzing wijst.
1. Maak nieuwe kanalen die de oude vervangen en upload uitvoeringen.
1. Wijs vertoningen aan de nieuwe kanalen opnieuw toe.
1. Voeg een verwijzing naar de gemigreerde vertoningen of plaatsen toe die bij de configuratie van de vertoningstoewijzing richten.
1. Herhaal stap 3, 4 en 5 voor alle resterende kanalen en beeldschermen.

   >[!NOTE]
   >Na de voltooiing van de migratie, zorg ervoor om alle configuratieverwijzingen uit kanalen, vertoningen, en plaatsen te verwijderen en één aan de knoop van de projectinhoud toe te voegen.
