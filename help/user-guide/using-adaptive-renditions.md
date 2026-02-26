---
title: Adaptieve uitvoeringen gebruiken in AEM Screens
description: Leer hoe u Adaptieve uitvoeringen kunt gebruiken in AEM Screens.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
source-git-commit: f1ddcf5e5ee9691e436e139ce0084f2c39f9c9dd
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Adaptieve uitvoeringen gebruiken in AEM Screens {#adaptive-renditions}

## Inleiding {#introduction}

>[!CAUTION]
>Deze functie wordt alleen ondersteund op AEM on-premise (AEM 6.x). Deze functie wordt niet ondersteund op AEM as a Cloud Service.

Met adaptieve uitvoeringen kunnen de apparaten automatisch op de beste uitvoering voor een apparaat klikken op basis van door de klant gedefinieerde regels. De apparaten downloaden automatisch de meest geschikte uitvoering van een middel en spelen deze die op deze regels wordt gebaseerd. Het laat klanten zich bij het ontwerpen van de *belangrijkste* ervaring concentreren.

## Doelstelling {#objective}

Als AEM Screens Content Author kunt u nu apparaatspecifieke elementuitvoeringen configureren die automatisch moeten worden gedownload en afgespeeld zonder dat u handmatig alle inhoudsvariaties hoeft te maken.
Nadat een ontwikkelaar de eigenschappen en regels voor het toewijzen van vertoningen heeft toegevoegd, kunt u de vertoningstoewijzing toepassen op elementen en deze vervolgens opnemen in een AEM Screens-kanaal.

>[!IMPORTANT]
>Voordat u de Adaptieve uitvoeringen gaat gebruiken in een AEM Screens-kanaal, raadt Adobe u aan kennis te nemen van het architecturaal overzicht en de architecturale configuratie van deze functie. Zie [ Aangepaste Vertoningen: Het Overzicht van de architectuur en Configuraties ](/help/user-guide/adaptive-renditions.md).

## Adaptieve uitvoeringen gebruiken in kanalen {#using-adaptive-renditions}

>[!NOTE]
>Nadat u het [ vertoning-afbeelding bezit aan het Project van Screens ](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) en [ vertoning-afbeelding regels ](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) hebt toegevoegd, als Inhoudsauteur bent u nu klaar om de vertoningen op uw activa toe te passen.

### Uitvoeringen toepassen op Assets {#apply-renditions-assets}

Ga als volgt te werk om vertoningen toe te passen op elementen die u wilt gebruiken in het Screens-kanaal Rondleiding.

1. Navigeer aan de **omslag van Assets** in uw instantie van AEM.
1. Maak een versie van het element die beter geschikt is voor de bewegingsweergave, bijvoorbeeld `seahorse.jpg` .
1. Kies de vertoning noemend patroon, bijvoorbeeld, `landscape`, gelijkend op wat in **patroon** bezit in **CRXDE Lite** werd bepaald. Zie [ Toevoegend de Regels van de Afbeelding van de Vertoning ](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) voor meer details.
1. Klik **Vertoning** toevoegen om de vertoning, zoals aangetoond in het hieronder cijfer te uploaden.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Klik op de naam van het elementbestand. De vertoning die u toevoegt, moet het patroon bevatten (gedefinieerd in stap 3), bijvoorbeeld `seahorse-landscape.png`.
1. Wanneer u de activa hebt toegevoegd, klik de activa en klik **leiden Publicatie** van de actiebar om de activa te publiceren.

   ![afbeelding](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Zie [ Update van de Inhoud op bestelling ](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content) om meer te leren over het beheren van Publicatie en het leveren van inhoudsupdates van Auteur aan Publish aan apparaat.

## Migratiestrategie {#migration-strategy}

>[!IMPORTANT]
>Voor grote netwerken beveelt Adobe aan dat de migratie geleidelijk plaatsvindt om de risico&#39;s te beperken. De reden hiervoor is dat de functie wijzigingen kan aanbrengen in de indeling voor manifest en bestandsopslag. Wanneer u `sling:configRef` toevoegt aan het gehele project, moeten alle spelers zijn bijgewerkt naar Feature Pack 6.5.9. Als u een aantal spelers hebt bijgewerkt, voegt u de `sling:configRef` alleen toe aan de weergaven, locaties of kanaalmappen waarin alle spelers zijn bijgewerkt naar Feature Pack 6.5.9.

Het volgende diagram toont de migratiestrategie voor grote netwerken:

![afbeelding](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

Om de eigenschap toe te laten, voeg minstens één toewijzingsregel toe en zorg ervoor dat de vertoning-afbeelding configuratie in de context van vertoningen en kanalen oplosbaar is. Voer de volgende stappen uit om te migreren:

1. Voeg [ Regels van de Toewijzing van de Vertoning ](/help/user-guide/adaptive-renditions.md) toe.
1. Maak een map voor nieuwe kanalen en voeg een verwijzing toe naar de configuratie voor de renditie-toewijzing.
1. Maak kanalen die de oude vervangen en upload uitvoeringen.
1. Wijs vertoningen aan de nieuwe kanalen opnieuw toe.
1. Voeg een verwijzing naar de gemigreerde vertoningen of plaatsen toe die bij de vertoning-afbeelding configuratie richten.
1. Herhaal stap 3, 4 en 5 voor alle resterende kanalen en beeldschermen.

   >[!NOTE]
   >Na de voltooiing van de migratie, zorg ervoor om alle configuratieverwijzingen uit kanalen, vertoningen, en plaatsen te verwijderen en één aan de knoop van de projectinhoud toe te voegen.
