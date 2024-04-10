---
title: Offlinekanalen
seo-title: Offline Channels
description: De AEM Screens-speler biedt offline ondersteuning voor kanalen door gebruik te maken van de ContentSync-technologie. Volg deze pagina voor meer informatie over updatehandlers en het inschakelen van offlineconfiguratie voor een kanaal.
seo-description: The AEM Screens player provides offline support for channels by leveraging the ContentSync technology. Follow this page to learn more about update handlers and enabling offline configuration for a channel.
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: bd572743-652f-4fc5-8b75-a3c4c74536f4
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Offlinekanalen {#offline-channels}

De schermspeler biedt offline ondersteuning voor de kanalen door de ***ContentSync*** -technologie.

De spelers gebruiken een lokale http server om de ongezipte inhoud te dienen.

Wanneer een kanaal wordt gevormd om in werking te stellen *online*, dient de speler de kanaal-middelen door tot de AEM server toegang te hebben maar wanneer het kanaal wordt gevormd om in werking te stellen *offline*, dient de speler de kanaal-middelen van een lokale server http.

De workflow voor het proces is als volgt:

1. De gewenste pagina(&#39;s) parseren
1. Alle gerelateerde activa verzamelen
1. Alles verpakken in een ZIP-bestand
1. Het postvak downloaden en lokaal uitpakken
1. Lokale kopie van de inhoud weergeven

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
   <td>kanalen</td> 
   <td>verzamelt een kanaal</td> 
   <td>uitbreiding : uitbreiding van de te verzamelen bron<br /> [pathSuffix='']: achtervoegsel om aan het kanaalpad toe te voegen<br /> </td> 
  </tr>
  <tr>
   <td>clientlib</td> 
   <td>de opgegeven clientbibliotheek verzamelen</td> 
   <td>[extension='']: kan css of js zijn, alleen de eerste, of alleen de laatste</td> 
  </tr>
  <tr>
   <td>assetrendities</td> 
   <td>de rendities van het element verzamelen</td> 
   <td>[renditions=[]]: lijst met vertoningen die moeten worden verzameld. Wordt standaard ingesteld op de oorspronkelijke uitvoering</td> 
  </tr>
  <tr>
   <td>kopiëren</td> 
   <td>de opgegeven structuur kopiëren vanuit het pad</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Configuratie van ContentSync testen {#testing-contentsync-configuration}

Voer de onderstaande stappen uit om de ContentSync-configuratie te testen:

1. Openen `https://localhost:4502/libs/cq/contentsync/content/console.html`
1. Selecteer uw config in de lijst
1. Klik op Cache wissen
1. Klik op Cache bijwerken
1. Klik op Volledige download
1. Het ZIP-bestand extraheren
1. Een lokale server starten in de uitgepakte map
1. De startpagina openen en de status van uw app controleren

## Offlineconfig voor een kanaal inschakelen {#enabling-offline-config-for-a-channel}

Volg de onderstaande stappen om offline config voor een kanaal toe te laten:

1. Inspect the channel content and check if it is requested from an AEM Instance (Online).

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigeer naar het kanaaldashboard en klik **...** in de **KANAALINFORMATIE** Deelvenster om de eigenschappen te wijzigen.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigeer naar de kanaaleigenschappen en controleer of het selectievakje is uitgeschakeld onder het dialoogvenster **Kanaal** tab. Klikken **Opslaan en sluiten**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Voordat de inhoud correct op het apparaat wordt geïmplementeerd, klikt u op de knop **Offline inhoud bijwerken**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   De **Off line** status onder **EIGENSCHAPPEN** ook dienovereenkomstig bijgewerkt.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Inspect de kanaalinhoud en controleer of deze wordt opgevraagd bij de lokale Player-Cache.

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>Meer informatie over het malplaatje voor douane off-line middelmanagers en de minimumvereisten in `pom.xml` voor dat specifieke project , zie [Sjabloon voor aangepaste handlers](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Een aangepaste component voor AEM Screens ontwikkelen**.
