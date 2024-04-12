---
title: Adaptieve uitvoeringen gebruiken in AEM Screens
description: Leer hoe u Adaptieve uitvoeringen kunt gebruiken in AEM Screens.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
source-git-commit: ba5327077e4a2d30cc7b77f02123da5a240c67ae
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---

# Adaptieve uitvoeringen gebruiken in AEM Screens {#adaptive-renditions}

## Inleiding {#introduction}

De adaptieve Vertoningen staan de apparaten toe om automatisch de beste vertoning voor een apparaat te selecteren dat op klant-bepaalde regels wordt gebaseerd. De apparaten downloaden en spelen automatisch de meest aangewezen vertoning van activa die op deze regels wordt gebaseerd die klanten toestaan om zich bij het ontwerpen van *hoofd* ervaring.

## Doelstelling {#objective}

Als AEM Screens Content Author kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudsvariaties hoeft te maken.
Nadat een ontwikkelaar de eigenschappen en regels voor het toewijzen van vertoningen heeft toegevoegd, kunt u de vertoningstoewijzing op elementen toepassen en vervolgens de elementen in een AEM Screens-kanaal opnemen.

>[!IMPORTANT]
>Voordat u begint met het gebruik van Adaptieve uitvoeringen in een AEM Screens-kanaal, raadt de Adobe u aan kennis te nemen van het architecturale overzicht en de architectuurconfiguratie van deze functie. Zie [Adaptieve uitvoeringen: Overzicht van architectuur en configuraties](/help/user-guide/adaptive-renditions.md).

## Adaptieve uitvoeringen gebruiken in kanalen {#using-adaptive-renditions}

>[!NOTE]
>Zodra u hebt toegevoegd [rendition-mapping, eigenschap voor het schermproject](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) en [regels voor het toewijzen van vertoningen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules)Als inhoudsauteur kunt u nu de uitvoeringen toepassen op uw elementen.

### Vertoningen toepassen op elementen {#apply-renditions-assets}

Ga als volgt te werk om vertoningen toe te passen op elementen die u wilt gebruiken in het kanaal Rondleiding.

1. Ga naar de **Activa** in uw AEM-exemplaar.
1. Maak een versie van het element die beter geschikt is voor de bewegingsweergave, bijvoorbeeld `seahorse.jpg`.
1. Kies bijvoorbeeld het naamgevingspatroon van de vertoning.`landscape`, vergelijkbaar met de definitie in **patroon** eigenschap in **CRXDE Lite**. Zie [Regels voor renderingstoewijzing toevoegen](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) voor meer informatie .
1. Klikken **Vertoning toevoegen** om de vertoning te uploaden, zoals in onderstaande afbeelding wordt getoond.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Selecteer de naam van het elementbestand. De vertoning die u toevoegt, moet het patroon bevatten (gedefinieerd in stap 3), bijvoorbeeld `seahorse-landscape.png`.
1. Selecteer het element en klik op **Publicatie beheren** op de actiebalk om het element te publiceren.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Zie [Update voor on-demand inhoud](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content) voor meer informatie over het beheren van Publicatie en het leveren van inhoudsupdates van Auteur aan Publish aan apparaat.

## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken beveelt de Adobe aan de migratie geleidelijk te laten plaatsvinden om de risico&#39;s te beperken. De reden hiervoor is dat de functie wijzigingen kan aanbrengen in de indeling voor manifest en bestandsopslag. De `sling:configRef` voor het hele project moeten alle spelers worden bijgewerkt naar Feature Pack 6.5.9. Als u een aantal spelers hebt bijgewerkt, voegt u de opdracht `sling:configRef` alleen naar die weergaven, locaties of kanaalmappen waarin alle spelers zijn bijgewerkt naar Feature Pack 6.5.9.

Het volgende diagram toont de migratiestrategie voor grote netwerken:

![afbeelding](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Om de eigenschap toe te laten, voeg minstens één toewijzingsregel toe en zorg ervoor dat de vertoning-afbeelding configuratie in de context van vertoningen en kanalen oplosbaar is. Voer de volgende stappen uit om te migreren:

1. Toevoegen [Regels voor renderingstoewijzing](/help/user-guide/adaptive-renditions.md).
1. Maak een map voor nieuwe kanalen en voeg een verwijzing toe naar de configuratie voor de renditie-toewijzing.
1. Maak kanalen die de oude vervangen en upload uitvoeringen.
1. Wijs vertoningen aan de nieuwe kanalen opnieuw toe.
1. Voeg een verwijzing naar de gemigreerde vertoningen of plaatsen toe die bij de vertoning-afbeelding configuratie richten.
1. Herhaal stap 3, 4 en 5 voor alle resterende kanalen en beeldschermen.

   >[!NOTE]
   >Na de voltooiing van de migratie, zorg ervoor om alle configuratieverwijzingen uit kanalen, vertoningen, en plaatsen te verwijderen en één aan de knoop van de projectinhoud toe te voegen.
