---
title: Overzicht van auteur- en publicatiearchitectuur
description: AEM Screens-architectuur lijkt op een traditionele AEM Sites-architectuur. De inhoud wordt ontworpen op een AEM auteursinstantie en dan voorwaarts-herhaald aan veelvoudige publiceer instanties.
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: ba23eb8e-bbde-4a6e-8cfb-ae98176ed890
source-git-commit: 6643f4162c8f0ee7bcdb0fd3305d3978234f5cfd
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 0%

---

# Overzicht van auteur- en publicatiearchitectuur {#author-and-publish-architectural-overview}

Deze pagina benadrukt de volgende onderwerpen:

* **Inleiding tot publicatieservers**
* **Overzicht van architectuur**
* **Registratieproces**

## Vereisten {#prerequisites}

Voordat u begint met auteurservers en publicatieservers, moet u op de hoogte zijn van:

* **AEM**
* **AEM Screens-project maken en beheren**
* **Registratieproces van apparaat**

>[!NOTE]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.4 Screens Feature Pack 2 hebt geïnstalleerd. Neem contact op met de Adobe voor ondersteuning en vraag toegang tot dit functiepakket. Nadat u toestemming hebt, download het van het Aandeel van het Pakket.

## Inleiding {#introduction}

AEM Screens-architectuur lijkt op een traditionele AEM Sites-architectuur. De inhoud wordt ontworpen op een AEM auteursinstantie en dan voorwaarts-herhaald aan veelvoudige publiceer instanties. Apparaten op AEM Screens kunnen nu verbinding maken met een AEM publicatiefarm via een taakverdelingsmechanisme. De veelvoudige AEM publiceer instanties kunnen worden toegevoegd om te blijven het publicatielandbouwbedrijf schrapen.

*Bijvoorbeeld*, geeft een AEM Screens Content Author een opdracht uit op het ontwerpsysteem voor een bepaald apparaat. Dat apparaat wordt gevormd om met te communiceren publiceer landbouwbedrijf of een Inhoudsauteur van AEM Screens die informatie over apparaten verkrijgt die worden gevormd om met te communiceren publiceert landbouwbedrijven.

Het volgende diagram illustreert zowel de auteursomgeving als het het publiceren milieu.

![screen_shot_2019-03-04at30236pm](assets/screen_shot_2019-03-04at30236pm.png)

## Architecturaal ontwerp {#architectural-design}

Er zijn vijf architecturale componenten die deze oplossing vergemakkelijken:

* ***Inhoud repliceren*** van auteur naar publicatie voor weergave op apparaten

* ***Omkeren*** het repliceren van binaire inhoud van het het publiceren milieu (die van apparaten wordt ontvangen) aan het auteursmilieu.
* ***Verzenden*** opdrachten van de auteur om te publiceren via specifieke REST API&#39;s.
* ***Berichten*** tussen publicatie-instanties om updates en opdrachten voor apparaatinformatie te synchroniseren.
* ***Opiniepeiling*** door de auteur van publicatie-instanties om apparaatinformatie via specifieke REST API&#39;s te verkrijgen.

### Replicatie (vooruit) van inhoud en configuraties  {#replication-forward-of-content-and-configurations}

De standaard replicatieagenten worden gebruikt om de inhoud van het AEM Screens-kanaal, locatieconfiguraties, en apparatenconfiguraties te herhalen. Op deze manier kunnen auteurs de inhoud van een kanaal bijwerken en desgewenst een goedkeuringswerkstroom doorlopen voordat ze kanaalupdates publiceren. Een replicatieagent moet voor elk worden gecreeerd publiceer instantie in publiceer landbouwbedrijf.

Het volgende diagram illustreert het replicatieproces:

![screen_shot_2019-03-04at33935pm](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>Een replicatieagent moet voor elk worden gecreeerd publiceer instantie in publiceer landbouwbedrijf.

### Screens Replication Agents and Commands  {#screens-replication-agents-and-commands}

Er worden aangepaste schermspecifieke replicatiemiddelen gemaakt om opdrachten van de instantie Auteur naar het AEM Screens-apparaat te verzenden. De AEM publiceer instanties dienen als tussenpersoon om deze bevelen aan het apparaat door te sturen.

Hierdoor kunnen auteurs het apparaat blijven beheren, zoals apparaatupdates verzenden en screenshots nemen van de auteursomgeving. De de replicatieagenten van AEM Screens hebben een configuratie van het douanevervoer, als standaardreplicatieagenten.

### Berichten tussen publicatie-instanties  {#messaging-between-publish-instances}

Vaak is een opdracht slechts bedoeld om één keer naar een apparaat te worden verzonden. In een publicatiearchitectuur met taakverdeling is het echter onbekend met welke instantie het apparaat verbinding maakt.

Daarom verzendt de auteurinstantie het bericht naar alle Publish instanties. Nochtans zou slechts één enkel bericht dan aan het apparaat moeten worden afgelost. Voor een correct bericht moet er communicatie plaatsvinden tussen de publicatie-instanties. Dit wordt bereikt met *Apache ActiveMQ Artemis*. Elke publicatieinstantie wordt geplaatst in een losjes gekoppelde Topologie gebruikend de Eak-Gebaseerde de ontdekkingsdienst van de Verkenning en ActiveMQ wordt gevormd zodat elke publicatieinstantie één enkele berichtrij kan communiceren en creëren. Het apparaat van AEM Screens pollt AEM publiceer landbouwbedrijf als taakverdelingsmechanisme en neemt het bevel van de bovenkant van de rij op.

### Replicatie omkeren {#reverse-replication}

Vaak wordt na een opdracht een reactie van het apparaat Screens verwacht die naar de instantie Auteur wordt doorgestuurd. Om dit AEM te bereiken ***Replicatie omkeren*** wordt gebruikt.

* Creeer een omgekeerde replicatieagent voor elke publiceer instantie, zoals aan de standaardreplicatieagenten en de replicatieagenten van AEM Screens.
* Een configuratie van de werkschemaopstarter luistert naar knopen die op AEM worden gewijzigd publiceert instantie en teweegbrengt beurtelings een werkschema om de reactie van het Apparaat in AEM outbox van de publicatieinstantie te plaatsen.
* Een omgekeerde replicatie in deze context wordt slechts gebruikt voor binaire gegevens (zoals, logboekdossiers en screenshots) die door de apparaten worden verstrekt. Niet-binaire gegevens worden opgehaald door polling.
* De omgekeerde replicatieopiniepeiling van de AEM auteursinstantie wint de reactie en bewaart het aan de auteursinstantie.

### Opiniepeiling van publicatie-instanties  {#polling-of-publish-instances}

De auteurinstantie moet de apparaten kunnen opiniepeilen om een hartslag te krijgen en de gezondheidsstatus van een aangesloten apparaat te kennen.

Apparaten pingelen het taakverdelingsmechanisme en worden gerouteerd naar een publicatie-instantie. De status van het apparaat wordt vervolgens vrijgegeven door de AEM-publicatie-instantie via een API voor publiceren die @ **api/screens-dcc/devices/static** voor alle actieve apparaten en **api/screens-dcc/devices/&lt;device_id>/status.json** voor één apparaat.

De instantie van de auteur opiniepeilt alle publicatieinstanties en voegt de reacties van de apparatenstatus in één enkele status samen. De geplande taak die wordt opiniepeild bij de auteur is `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` en kan worden geconfigureerd op basis van een uitsnijduitdrukking.

## Registratie {#registration}

Registratie begint nog steeds bij de AEM auteur. AEM Screens Device wordt verwezen naar de auteurinstantie en de registratie is voltooid.

Nadat een apparaat op het AEM auteursmilieu wordt geregistreerd, worden de apparatenconfiguratie en kanaal/planningtoewijzingen herhaald aan de AEM publicatieinstanties. De configuratie van het Apparaat van AEM Screens wordt dan bijgewerkt om aan de Balancer van de Lading vóór AEM te richten publiceert landbouwbedrijf. Dit is bedoeld als een eenmalige installatie. Nadat het Apparaat van de Schermen met succes met het publicatiemilieu wordt verbonden, kan het bevelen uit het auteursmilieu blijven ontvangen. Het is niet nodig om het AEM Screens-apparaat rechtstreeks aan te sluiten op de AEM auteur-omgeving.

![screen_shot_2019-02-25at15218pm](assets/screen_shot_2019-02-25at15218pm.png)

### De volgende stappen {#the-next-steps}

Wanneer u het architecturale ontwerp van auteur en publiceer opstelling in AEM Screens begrijpt, zie [Auteur en publicatie configureren voor AEM Screens](author-and-publish.md) voor meer informatie .
