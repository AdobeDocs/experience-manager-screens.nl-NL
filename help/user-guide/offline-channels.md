---
title: Offlinekanalen
description: Meer informatie over hoe AEM Screens Player offline ondersteuning voor kanalen biedt met ContentSync-technologie.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
source-git-commit: 8dde26d36847fb496aed6d4bf9732233116b5ea6
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Offlinekanalen {#offline-channels}

De schermspeler biedt offline ondersteuning voor de kanalen via de ***ContentSync*** -technologie.

De spelers gebruiken een lokale http server om de ongezipte inhoud te dienen.

Wanneer een kanaal wordt gevormd om in werking te stellen *online*, dient de speler de kanaal-middelen door tot de AEM server toegang te hebben. Nochtans, wanneer het kanaal wordt gevormd om in werking te stellen *offline*, dient de speler de kanaal-middelen van een lokale server http.

De workflow voor het proces is als volgt:

1. Parseer de gewenste pagina&#39;s.
1. Alle gerelateerde elementen verzamelen.
1. Verpak alles in een ZIP-bestand.
1. Download het gecomprimeerde bestand en extraheer het lokaal.
1. Een lokale kopie van de inhoud weergeven.

## Handlers bijwerken {#update-handlers}

De ***ContentSync*** gebruikt updatehandlers om alle noodzakelijke pagina&#39;s en activa voor een specifiek project te ontleden en te verzamelen. AEM Screens gebruikt de volgende updatehandlers:

### Algemene opties {#common-options}

* *type*: het type update-handler dat moet worden gebruikt
* *pad*: pad naar de bron
* *[targetRootDirectory]*: doelmap in het ZIP-bestand

<table>
 <tbody>
  <tr>
   <td><strong>Type</strong></td> 
   <td><strong>Beschrijving</strong></td> 
   <td><strong>Opties</strong></td> 
  </tr>
  <tr>
   <td><code>channels</code></td> 
   <td>verzamelt een kanaal</td> 
   <td>uitbreiding : uitbreiding van de te verzamelen bron<br /> [pathSuffix='']: achtervoegsel om aan het kanaalpad toe te voegen<br /> </td> 
  </tr>
  <tr>
   <td><code>clientlib</code></td> 
   <td>de opgegeven clientbibliotheek verzamelen</td> 
   <td>[extension='']: kan css of js zijn, alleen de eerste, of alleen de laatste</td> 
  </tr>
  <tr>
   <td><code>assetrenditions</code></td> 
   <td>de rendities van het element verzamelen</td> 
   <td>[renditions=[]]: lijst met vertoningen die moeten worden verzameld. Wordt standaard ingesteld op de oorspronkelijke uitvoering</td> 
  </tr>
  <tr>
   <td><code>copy</code></td> 
   <td>de opgegeven structuur kopiëren vanuit het pad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Configuratie van ContentSync testen {#testing-contentsync-configuration}

Voer de onderstaande stappen uit om de ContentSync-configuratie te testen:

1. Open `https://localhost:4502/libs/cq/contentsync/content/console.html`.
1. Klik uw config in de lijst.
1. Klikken **Cache wissen**.
1. Klikken **Cache bijwerken**.
1. Klikken **Volledige download**.
1. Extraheer het ZIP-bestand.
1. Start een lokale server in de uitgepakte map.
1. Open de startpagina en controleer de status van uw app.

## Offlineconfig voor een kanaal inschakelen {#enabling-offline-config-for-a-channel}

Volg de onderstaande stappen om offline config voor een kanaal toe te laten:

1. Inspect the channel content and check if it is requested from an AEM Instance (Online).

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigeer naar het kanaaldashboard.
1. Klikken **...** in de **KANAALINFORMATIE** Deelvenster.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Ga naar de kanaaleigenschappen.
1. Controleer of het selectievakje is uitgeschakeld op het tabblad (Kanaal) en klik vervolgens op **Opslaan en sluiten**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Voordat de inhoud correct op het apparaat wordt geïmplementeerd, klikt u op de knop **Offline inhoud bijwerken**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   De **Off line** status onder **EIGENSCHAPPEN** ook dienovereenkomstig bijgewerkt.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Inspect de kanaalinhoud en controleer of deze wordt opgevraagd bij de lokale Player-Cache.

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>Leer over het malplaatje voor douane off-line middelmanagers. Meer informatie over de minimumvereisten in de `pom.xml` voor het project. Zie [Sjabloon voor aangepaste handlers](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Een aangepaste component voor AEM Screens ontwikkelen**.
