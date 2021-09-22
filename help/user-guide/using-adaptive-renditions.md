---
title: Adaptieve uitvoeringen gebruiken in AEM Screens
description: Op deze pagina wordt beschreven hoe u Adaptieve uitvoeringen in AEM Screens kunt gebruiken.
index: false
source-git-commit: 97354c05f3b01dd76b6b8d4bdaf45c9be3ce4db2
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Adaptieve uitvoeringen gebruiken in AEM Screens {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten zullen automatisch de meest aangewezen vertoning van activa downloaden en spelen die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *main* slechts te concentreren ervaring.

## Doelstelling {#objective}

Als AEM Screens Content Author kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudsvariaties hoeft te maken.

Als u dus een aantal verschillende apparaten hebt geïmplementeerd, kan het apparaat met deze functie automatisch de meest geschikte uitvoering van een element downloaden en afspelen op basis van de regels.

>[!IMPORTANT]
>Voordat u Adaptieve uitvoeringen gaat gebruiken, wordt u aangeraden om in een AEM Screens-kanaal te leren over het architecturale overzicht en de architecturale configuratie van deze functie. Zie Adaptieve uitvoeringen: Overzicht van architectuur en configuraties voor meer informatie.

## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken, adviseert men dat de migratie geleidelijk wordt gedaan om de risico&#39;s te verlichten aangezien de eigenschap veranderingen in manifest en dossieropslagformaat zal introduceren.

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


## Uitvoeringen uploaden en Adaptieve uitvoeringen gebruiken in een AEM Screens Channel {#upload-renditions}

1. Maak een versie van het element die beter geschikt is voor de signaalweergave, bijvoorbeeld `portrait orientation`.

1. Kies het naamgevingspatroon van de vertoning, bijvoorbeeld `portrait`.

1. Wijzig de naam van het elementbestand zodat het het patroon bevat, bijvoorbeeld `my_asset_portrait.png`.

1. Klik op **Vertoning toevoegen** om de vertoning te uploaden, zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/add-rendition.png)