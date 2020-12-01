---
title: Offlinekanalen
seo-title: Offlinekanalen
description: 'De AEM Screens-speler biedt offline ondersteuning voor kanalen door gebruik te maken van de ContentSync-technologie. Volg deze pagina voor meer informatie over updatehandlers en het inschakelen van offlineconfiguratie voor een kanaal.  '
seo-description: 'De AEM Screens-speler biedt offline ondersteuning voor kanalen door gebruik te maken van de ContentSync-technologie. Volg deze pagina voor meer informatie over updatehandlers en het inschakelen van offlineconfiguratie voor een kanaal.  '
uuid: 18b9d175-ff26-42db-86aa-5ea978909f71
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
discoiquuid: bd572743-652f-4fc5-8b75-a3c4c74536f4
docset: aem65
translation-type: tm+mt
source-git-commit: f25176be89424059b8c51296969f069687328536
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---


# Offlinekanalen {#offline-channels}

De schermspeler biedt offline ondersteuning voor de kanalen door gebruik te maken van de technologie ***ContentSync***.

De spelers gebruiken een lokale http server om de ongezipte inhoud te dienen.

Wanneer een kanaal wordt gevormd om *online* in werking te stellen, dient de speler de kanaal-middelen door tot de AEM server toegang te hebben maar wanneer het kanaal wordt gevormd om *off-line* in werking te stellen, dient de speler de kanaal-middelen van een lokale server http.

De workflow voor het proces is als volgt:

1. De gewenste pagina(&#39;s) parseren
1. Alle gerelateerde activa verzamelen
1. Alles verpakken in een ZIP-bestand
1. Het postvak downloaden en lokaal uitpakken
1. Lokale kopie van de inhoud weergeven

## Handlers {#update-handlers} bijwerken

***ContentSync*** gebruikt updatemanagers om alle noodzakelijke pagina&#39;s en activa voor een specifiek project te ontleden en te verzamelen. AEM Screens gebruikt de volgende updatehandlers:

### Algemene opties {#common-options}

* *type*: het updatehandlertype dat moet worden gebruikt
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
   <td>extensie: uitbreiding van de te verzamelen bron<br /> [pathSuffix='']: achtervoegsel toevoegen aan kanaalpad<br /> </td> 
  </tr>
  <tr>
   <td>clientlib</td> 
   <td>de opgegeven clientbibliotheek verzamelen</td> 
   <td>[extension='']: kan css of js zijn, om alleen de eerste of alleen de laatste te verzamelen</td> 
  </tr>
  <tr>
   <td>assetrendities</td> 
   <td>de rendities van het element verzamelen</td> 
   <td>[renditions=[]]: lijst met te verzamelen vertoningen. Wordt standaard ingesteld op de oorspronkelijke uitvoering</td> 
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

1. Open `https://localhost:4502/libs/cq/contentsync/content/console.html`
1. Selecteer uw config in de lijst
1. Klik op Cache wissen
1. Klik op Cache bijwerken
1. Klik op Volledige download
1. Het ZIP-bestand extraheren
1. Een lokale server starten in de uitgepakte map
1. De startpagina openen en de status van uw app controleren

## Offlineconfiguratie inschakelen voor een kanaal {#enabling-offline-config-for-a-channel}

Volg de onderstaande stappen om offline config voor een kanaal toe te laten:

1. Inspect the channel content and check if it is requested from an AEM Instance (Online).

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigeer naar het kanaaldashboard en klik op **..** in **KANAALINFORMATIE** Panel om de eigenschappen te wijzigen.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigeer naar de kanaaleigenschappen en controleer of het selectievakje is uitgeschakeld onder het tabblad **Kanaal**. Klik **Opslaan en sluiten**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Voordat inhoud correct op het apparaat wordt geïmplementeerd, klikt u op **Offlineinhoud bijwerken**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   De status **Offline** onder **EIGENSCHAPPEN** wordt ook dienovereenkomstig bijgewerkt.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Inspect de kanaalinhoud en controleer of deze wordt opgevraagd bij de lokale Player-Cache.

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>Meer over het malplaatje voor douane off-line middelmanagers en de minimumvereisten in `pom.xml` voor dat specifieke project leren, verwijs naar [Malplaatje voor de Handlers van de Douane](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Developing a Custom Component for AEM Screens**.