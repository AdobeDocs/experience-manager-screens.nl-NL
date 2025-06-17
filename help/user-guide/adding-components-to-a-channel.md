---
title: Componenten toevoegen aan een kanaal
description: Meer informatie over het toevoegen van componenten aan kanalen in een AEM Screens-project.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 56dbe098-05db-4fc3-977f-e50a0a312d64
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 0%

---

# Componenten toevoegen aan een kanaal{#adding-components-to-a-channel}

Componenten zijn de basiselementen van de AEM (Adobe Experience Manager)-ervaring. U kunt verschillende componenten gebruiken en deze aan uw kanaal toevoegen in een AEM Screens-project.

## Componenten in AEM Screens {#components-in-aem-screens}

AEM Screens biedt verschillende AEM-componenten die in een Screens-project kunnen worden gebruikt.

### AEM Screens-componenten weergeven {#viewing-aem-screens-components}

Wanneer u een project van AEM Screens creeert, ziet u een lijst van standaardcomponenten die aan het project kunnen worden toegevoegd.

Voer de volgende stappen uit om de standaardcomponenten voor uw Screens-project weer te geven:

1. Klik op het kanaal. Bijvoorbeeld, **`We.Retail In Store`** > **Kanalen** > **Niet-actief Kanaal**.

1. Klik **uitgeven** van de actiebar.
1. Klik in de AEM Editor op het pictogram **+** op de zijbalk.
1. Alle componenten die door gebrek in een het projectvertoningen van AEM Screens inbegrepen zijn, zoals aangetoond in het hieronder cijfer.

![ screen_shot_2017-12-18at21350pm ](assets/screen_shot_2017-12-18at21350pm.png)

### Een nieuwe component toevoegen {#adding-a-new-component}

AEM biedt verschillende andere componenten. U kunt altijd andere componenten (die niet standaard zijn opgenomen) aan uw project toevoegen, omdat deze componenten compatibel zijn met AEM Screens.

In het volgende voorbeeld wordt de toevoeging van een component Livefyre aan een AEM Screens-project getoond:

1. Klik op het kanaal waaraan u een component wilt toevoegen. Bijvoorbeeld, **`We.Retail In Store`** > **Kanalen** > **Niet-actief Kanaal**.

1. Klik **uitgeven** van de actiebar.
1. Klik **wijze van het Ontwerp 0} {.**
1. Klik de volledige ontwerpredacteur op het recht en klik het montagessymbool zodat kunt u het **Parsys de dialoogvakje van het Ontwerp** openen.
1. U kunt op de componenten klikken die u in uw AEM Screens-project wilt importeren. Het volgende voorbeeld toont de toevoeging van de **Livefyre** component aan een project van AEM Screens.

![ adding_components ](assets/adding_components.gif)

>[!NOTE]
>
>Op dezelfde manier kunt u om het even welk aantal andere nieuwe componenten toevoegen die met AEM Screens aan uw project compatibel zijn.

## AEM-schermcomponenten begrijpen {#understanding-aem-screen-components}

In de volgende sectie worden de AEM Screens-componenten uitgelegd die u in uw project kunt gebruiken.

>[!NOTE]
>
>Als u de eigenschappen van een component wilt weergeven, klikt u op de component en klikt u op het hamerpictogram om eigenschappen te openen/weergeven.

### Toepassing {#application}

De **component van de Toepassing** laat u een toepassing aan uw kanaal toevoegen.

De toepassingscomponent heeft de volgende eigenschappen:

| **Bezit** | **Beschrijving** |
|---|---|
| ***Pad van de Toepassing*** | Klik op het absolute pad waar de toepassing bestaat. |
| ***Duur (milliseconden)*** | Klik op de duur van de toepassing. Standaard is de duur ingesteld op -1, wat betekent dat het element voorgoed wordt uitgevoerd (dat wil zeggen, één paginatoepassing). Wanneer u de waarde voor de duur > 0 instelt, wordt het element voor de opgegeven duur weergegeven en gaat u vervolgens naar de volgende waarde. |

In het volgende voorbeeld wordt getoond hoe u een toepassingscomponent insluit samen met de voorvertoning van de eigenschappen ervan:

![ adding_componentsapplication ](assets/adding_componentsapplication.gif)

>[!NOTE]
>
>Zie het bovenstaande voorbeeld om de eigenschappen van elk van de onderstaande componenten weer te geven.

### Kanaal {#channel}

De **component van het Kanaal** laat u een volledig kanaal aan uw project toevoegen.

De component Channel heeft de volgende eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong><em>Kanaalpad</em></strong></td>
   <td>Selecteer dit absolute pad waar de toepassing bestaat.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duur (milliseconden)</em></strong></td>
   <td>Selecteer de volledige duur van het kanaal. Wanneer u de duur instelt op -1, wordt de volledige lengte van het ingesloten kanaal in een bepaald kanaal uitgevoerd.</td>
  </tr>
 </tbody>
</table>

### Ingesloten pagina {#embedded-page}

Een **Ingebedde Pagina** laat u een ingebedde pagina aan uw project toevoegen. Het kan bijvoorbeeld een webtoepassing of een productcatalogus zijn.

De ingesloten pagina heeft de volgende eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong><em>Pad naar pagina<br /> </em></strong></td>
   <td>Selecteer dit absolute pad waar het kanaal bestaat.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duur (milliseconden)</em></strong></td>
   <td>Selecteer de volledige duur van het kanaal. Wanneer u de duur instelt op -1, wordt de volledige lengte van het ingesloten kanaal in een bepaald kanaal uitgevoerd.</td>
  </tr>
 </tbody>
</table>

### Ingesloten reeks {#embedded-sequence}

>[!NOTE]
>
>Om in detail over ingebedde opeenvolgingen te leren, zie [ Ingesloten Reeksen ](embedded-sequences.md) onder de Authoring sectie van Screens.

Met een ingesloten reeks kunt u een ingesloten volgnummer toevoegen aan het bestaande kanaal (met andere elementen).

De ingesloten reeks heeft de volgende pagina-eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td>Kanaalpad</td>
   <td>Selecteer de absolute weg van de opeenvolging die u in uw kanaal wilt omvatten.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duur (milliseconden)</em></strong></td>
   <td>Selecteer de volledige duur van het kanaal. Wanneer u de duur instelt op -1, wordt de volledige lengte van het ingesloten kanaal in een bepaald kanaal uitgevoerd.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Plaats het aan <strong> origineel </strong> of <strong> enig </strong>. Het plaatsen van de waarde aan <strong> origineel </strong> betekent dat de verdere looppas volledig op elke cyclus van de ouderopeenvolging. De andere mogelijke waarde is <strong> enig </strong>. Bij een dergelijke waarde wordt slechts één item van de volgende reeks op elke reeks weergegeven. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.</td>
  </tr>
 </tbody>
</table>

### Dynamische ingesloten reeks {#dynamic-embedded-sequence}

Met een dynamische ingesloten reeks kunt u een reeks toevoegen die vergelijkbaar is met de bovenstaande reeks, behalve met de rol van het kanaal.

Meer over ingebedde opeenvolgingen leren, zie [ Ingesloten Reeksen ](embedded-sequences.md) onder de Authoring sectie van Screens.

De dynamische ingesloten reeks heeft de volgende eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong><em> Rol van de Toewijzing van het Kanaal </em></strong><br /> </td>
   <td>Ga de kanaalrol in.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duur (milliseconden)</em></strong></td>
   <td>Selecteer de volledige duur van het kanaal. Wanneer u de duur instelt op -1, wordt de volledige lengte van het ingesloten kanaal in een bepaald kanaal uitgevoerd.</td>
  </tr>
  <tr>
   <td><strong><em>Strategie</em></strong></td>
   <td>Plaats het aan <strong> origineel </strong> of <strong> enig </strong>. Het plaatsen van de waarde aan <strong> origineel </strong> betekent dat de verdere looppas volledig op elke cyclus van de ouderopeenvolging. De andere mogelijke waarde is <strong> enig </strong>. Een dergelijke waarde zou slechts één item van de volgende waarde op elke run weergeven. Bijvoorbeeld het eerste item op de eerste lus en het tweede item op de tweede lus.</td>
  </tr>
 </tbody>
</table>

### Ervaar fragment {#experience-fragment}

Met een ervaringsfragment kunt u een Experience-fragment (een groep van een of meer componenten, waaronder inhoud en lay-out, waarnaar op pagina&#39;s kan worden verwezen) toevoegen aan uw AEM Screens-kanaal. Sleep de component naar de AEM Editor en klik op het fragment Ervaring.

Meer over leren hoe te om een Fragment van de Ervaring tot stand te brengen en het op een project van AEM Screens toe te passen, zie [ Gebruikend de Fragmenten van de Ervaring ](experience-fragments-in-screens.md).

![ exp ](assets/exp.gif)

| **Bezit** | **Beschrijving** |
|---|---|
| **Fragment van de Ervaring** |
| ***Fragment van de Ervaring*** | Selecteer het fragment van de Ervaring. |
| ***Duur*** | Selecteer de volledige duur van het ervaringsfragment dat in het kanaal wordt afgespeeld. |
| **Offline Config** |
| ***Cliënt-zijBibliotheken*** | JavaScript- en CSS-bestanden. |
| ***Statische Dossiers*** | Statische bestanden die u als offlineconfiguraties kunt toevoegen aan het ervaringsfragment. |

>[!NOTE]
>
>De **cliënt-zijBibliotheken** en **Statische Dossiers** die u van deze component toevoegt zijn naast reeds gevormde **cliënt-zijBibliotheken** en de Statische Dossiers die van de 6} Eigenschappen van het Fragment van de Ervaring **worden toegevoegd.**

### Afbeelding {#image}

Met een afbeelding kunt u een afbeelding aan het kanaal toevoegen.

De beeldactiva heeft drie lusjes namelijk **Beeld**, **Toegankelijkheid**, en **Opeenvolging**:

| **Bezit** | **Beschrijving** |
|---|---|
| **Beeld** |
| ***Activa van het Beeld*** | Klik op het afbeeldingselement. |
| ***Titel*** | Titel van de afbeelding. |
| ***Verbinding aan*** | Voeg een koppeling toe aan de afbeelding. |
| ***Beschrijving*** | Korte beschrijving voor de afbeelding. |
| ***Grootte*** | Grootte van de afbeelding. |
| **Toegankelijkheid** |
| ***Alternatieve Tekst*** | Alternatieve tekst voor de afbeelding. |
| **Opeenvolging** |
| ***Duur*** | Door gebrek wordt de duur geplaatst aan *8000 milliseconden*. Als u de playbackduur van het beeld wilt veranderen, werk het **gebied van de Duur** bij. |

### Overgang {#transition}

Met de component Overgang kunt u een overgang toevoegen aan uw Screens-project.

In de volgende afbeelding ziet u de overgangscomponent (die wordt toegevoegd door slepen en neerzetten) in de editor.

![ screen_shot_2019-07-25at104237am ](assets/screen_shot_2019-07-25at104237am.png)

Klik het overgangspictogram en klik **vormen** (moersleutelpictogram) om het **de dialoogvakje van de Overgang** te openen. Dit dialoogvenster bevat drie tabbladen:

* **Overgang**
* **Opeenvolging**
* **Activering**

>[!NOTE]
>
>Standaard wordt de reeks ingesteld op 600 milliseconden. U kunt de overgangsopeenvolging aan andere waarden bijwerken gebruikend de **Opeenvolging** tabel.

![ overgang ](assets/transition.gif)

De overgangscomponent heeft de volgende eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><strong>Overgang</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Type</em></strong></td>
   <td><p>Het type overgang tussen het element voor en na. Het overgangstype <strong> Type </strong> omvat de volgende opties:</p>
    <ul>
     <li><strong>Normaal</strong></li>
     <li><strong>Vervagen</strong></li>
     <li><strong>Inschuiven vanaf rechterkant</strong></li>
     <li><strong>Inschuiven vanaf linkerkant</strong></li>
     <li><strong>Inschuiven vanaf bovenkant</strong></li>
     <li><strong>Inschuiven vanaf onderkant</strong></li>
    </ul> </td>
  </tr>
  <tr>
   <td><strong>Reeks</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Duur</em></strong></td>
   <td>Selecteer de volledige duur van de overgang. De standaardwaarde is 600 milliseconden.</td>
  </tr>
  <tr>
   <td><strong>Activering</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Actief van</em></strong></td>
   <td>Tijdstempel dat beschrijft wanneer de overgang actief kan zijn.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Actief tot</em></strong></td>
   <td>De tijdstempel geeft aan tot wanneer de overgang actief kan zijn.</td>
  </tr>
  <tr>
   <td><strong><em>Schema</em></strong></td>
   <td>Voeg een vooraf gedefinieerd schema toe.</td>
  </tr>
 </tbody>
</table>

### Video {#video}

Met de component Video kunt u een video toevoegen aan uw Screens-project.

De videocomponent heeft de volgende eigenschappen:

<table>
 <tbody>
  <tr>
   <td><strong>Eigenschap</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td><em><strong>Video-element</strong></em></td>
   <td>Klik op de koppeling naar de video.</td>
  </tr>
  <tr>
   <td><em><strong>Duur</strong></em></td>
   <td>Selecteer de duur van de video. Standaard is de duur ingesteld op -1, wat betekent dat het element altijd wordt uitgevoerd. Wanneer u de waarde voor de duur &gt; 0 instelt, wordt het element voor de opgegeven duur weergegeven en gaat u vervolgens naar de volgende waarde.<br /> </td>
  </tr>
  <tr>
   <td><em><strong>Renderen</strong></em></td>
   <td><p>Als de videoaspectverhouding niet het scherm past, kunt u het teruggeven aanpassen aan of <strong> </strong> of <strong> behandelen </strong> bevatten.</p> <p><em> Bevat </em> betekent dat de volledige video wordt getoond en de ontbrekende gebieden met een zwarte grens worden opgevuld.</p> <p><em> Omslag </em> betekent dat de video volledige viewport behandelt, maar sommige delen die aan de kanten overstromen zijn verborgen.</p> </td>
  </tr>
  <tr>
   <td><em><strong>Grootte</strong></em></td>
   <td>Grootte van de video.</td>
  </tr>
 </tbody>
</table>
