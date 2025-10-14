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

De speler van Screens verleent off-line steun voor de kanalen door de **&#x200B;**&#x200B;** technologie te gebruiken ContentSync.

De spelers gebruiken een lokale http server om de ongezipte inhoud te dienen.

Wanneer een kanaal wordt gevormd om *online* in werking te stellen, dient de speler de kanaal-middelen door tot de AEM server toegang te hebben. Nochtans, wanneer het kanaal wordt gevormd om *off-line* in werking te stellen, dient de speler de kanaal-middelen van een lokale server http.

De workflow voor het proces is als volgt:

1. Parseer de gewenste pagina&#39;s.
1. Alle gerelateerde elementen verzamelen.
1. Verpak alles in een ZIP-bestand.
1. Download het gecomprimeerde bestand en extraheer het lokaal.
1. Een lokale kopie van de inhoud weergeven.

## Handlers bijwerken {#update-handlers}

***ContentSync*** gebruikt updatemanagers om alle noodzakelijke pagina&#39;s en activa voor een specifiek project te ontleden en te verzamelen. AEM Screens gebruikt de volgende updatehandlers:

### Algemene opties {#common-options}

* *type*: Het type van updatemanager aan gebruik
* *weg*: weg aan het middel
* *[targetRootDirectory]*: doelomslag in het ZIP dossier

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
   <td>uitbreiding: uitbreiding van het middel om te verzamelen <br /> [pathSuffix='']: achtervoegsel om aan de kanaalweg toe te voegen <br /> </td> 
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
1. Klik **Duidelijk Geheime voorgeheugen**.
1. Klik **Geheime voorgeheugen van de Update**.
1. Klik **Volledige Download**.
1. Extraheer het ZIP-bestand.
1. Start een lokale server in de uitgepakte map.
1. Open de startpagina en controleer de status van uw app.

## Offlineconfig voor een kanaal inschakelen {#enabling-offline-config-for-a-channel}

Volg de onderstaande stappen om offline config voor een kanaal toe te laten:

1. Inspect the channel content and check if it is requested from an AEM Instance (Online).

   ![&#x200B; chlimage_1-24 &#x200B;](assets/chlimage_1-24.png)

1. Navigeer naar het kanaaldashboard.
1. Klik **...** in het **INFORMATIE VAN HET KANAAL** Comité.

   ![&#x200B; chlimage_1-25 &#x200B;](assets/chlimage_1-25.png)

1. Ga naar de kanaaleigenschappen.
1. Onder het (Kanaal) lusje, zorg ervoor dat checkbox gehandicapt is, dan klik **sparen &amp; sluit**.

   ![&#x200B; screen_shot_2017-12-19at122422pm &#x200B;](assets/screen_shot_2017-12-19at122422pm.png)

   Alvorens de inhoud behoorlijk aan het apparaat wordt opgesteld, klik de **Offline Inhoud van de Update**.

   ![&#x200B; screen_shot_2017-12-19at122637pm &#x200B;](assets/screen_shot_2017-12-19at122637pm.png)

   De **Off-line** status onder **EIGENSCHAPPEN** werkt ook dienovereenkomstig bij.

   ![&#x200B; screen_shot_2017-12-19at124735pm &#x200B;](assets/screen_shot_2017-12-19at124735pm.png)

1. Inspect de kanaalinhoud en controleer of deze wordt opgevraagd bij de lokale Player-Cache.

   ![&#x200B; chlimage_1-26 &#x200B;](assets/chlimage_1-26.png)

>[!NOTE]
>
>Leer over het malplaatje voor douane off-line middelmanagers. Meer informatie over de minimale vereisten in de `pom.xml` voor het project. Zie [&#x200B; Malplaatje voor de Handlers van de Douane &#x200B;](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Ontwikkelend een Component van de Douane voor AEM Screens**.
