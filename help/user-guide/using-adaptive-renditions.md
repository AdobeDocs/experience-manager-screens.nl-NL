---
title: Adaptieve uitvoeringen gebruiken in AEM Screens
description: Op deze pagina wordt beschreven hoe u Adaptieve uitvoeringen in AEM Screens kunt gebruiken.
source-git-commit: 68e7a47d7a9b10d1d3fecb7a7f7d96bbbde1c48a
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Adaptieve uitvoeringen gebruiken in AEM Screens {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *main* slechts te concentreren ervaring.

## Doelstelling {#objective}

Als AEM Screens Content Author kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudsvariaties hoeft te maken.
Als een ontwikkelaar de eigenschappen en regels voor de renditie-toewijzing heeft toegevoegd, kunt u de renditie-toewijzing nu toepassen op elementen en vervolgens de elementen in een AEM Screens-kanaal opnemen.

>[!IMPORTANT]
>Voordat u Adaptieve uitvoeringen gaat gebruiken, wordt u aangeraden om in een AEM Screens-kanaal te leren over het architecturale overzicht en de architecturale configuratie van deze functie. Zie [Aangepaste uitvoeringen: Overzicht van architectuur en configuraties](/help/user-guide/adaptive-renditions.md) voor meer informatie.

## Adaptieve uitvoeringen gebruiken in kanalen {#using-adaptive-renditions}

>[!NOTE]
>Nadat u [eigenschap voor vertoningstoewijzing voor uitvoering hebt toegevoegd aan het Schermproject](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) en [regels voor vertoningstoewijzing voor uitvoering](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules), bent u nu klaar om de uitvoeringen toe te passen op uw elementen.

### Vertoningen toepassen op elementen {#apply-renditions-assets}

Voer de onderstaande stappen uit om vertoningen toe te passen op de elementen die u wilt gebruiken in het kanaal voor touroperrasters:

1. Navigeer naar de map **Assets** in uw AEM.

1. Maak een versie van het element die beter geschikt is voor de signaalweergave, bijvoorbeeld `seahorse.jpg`.

1. Kies bijvoorbeeld het weergavematroon,`landscape`, vergelijkbaar met wat is gedefinieerd in **pattern**-eigenschap in **CRXDE Lite**. Raadpleeg [Regels voor vertoningstoewijzing toevoegen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) voor meer informatie.

1. Wijzig de naam van het elementbestand zodat het het patroon bevat (gedefinieerd in stap 3), bijvoorbeeld `seahorse-landscape.png`.

1. Klik op **Vertoning toevoegen** om de vertoning te uploaden, zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-rendition.png)

1. Nadat u het element hebt toegevoegd, selecteert u het element en klikt u op **Publicatie beheren** op de actiebalk om het element te publiceren.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Raadpleeg [On-Demand Content Update](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content.html?lang=en) voor meer informatie over het beheren van Publicatie en het leveren van inhoudsupdates van Auteur voor Publiceren op apparaat.


## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken, adviseert men dat de migratie geleidelijk wordt gedaan om de risico&#39;s te verlichten aangezien de eigenschap veranderingen in manifest en dossieropslagformaat zal introduceren. Als u `sling:configRef` toevoegt aan het hele project, moeten alle spelers zijn bijgewerkt naar Feature Pack 6.5.9. Als u een aantal spelers hebt bijgewerkt, hoeft u `sling:configRef` alleen toe te voegen aan die weergaven, locaties of kanaalmappen waarin alle spelers zijn bijgewerkt naar Feature Pack 6.5.9.

Het volgende diagram toont de migratiestrategie voor grote netwerken:

![afbeelding](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Om de eigenschap toe te laten, voeg minstens één toewijzingsregel toe en zorg ervoor de configuratie van de vertoningstoewijzing in de context van vertoningen en kanalen oplosbaar is. Voer de volgende stappen uit om te migreren:

1. Voeg [Regels voor vertoningstoewijzing](/help/user-guide/adaptive-renditions.md) toe.
1. Maak een map voor nieuwe kanalen en voeg een verwijzing toe die naar de configuratie van de vertoningstoewijzing wijst.
1. Maak nieuwe kanalen die de oude vervangen en upload uitvoeringen.
1. Wijs vertoningen aan de nieuwe kanalen opnieuw toe.
1. Voeg een verwijzing naar de gemigreerde vertoningen of plaatsen toe die bij de configuratie van de vertoningstoewijzing richten.
1. Herhaal stap 3, 4 en 5 voor alle resterende kanalen en beeldschermen.

   >[!NOTE]
   >Na de voltooiing van de migratie, zorg ervoor om alle configuratieverwijzingen uit kanalen, vertoningen, en plaatsen te verwijderen en één aan de knoop van de projectinhoud toe te voegen.

