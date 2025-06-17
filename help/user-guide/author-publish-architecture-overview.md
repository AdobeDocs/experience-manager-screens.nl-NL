---
title: Overzicht van auteur- en publicatiearchitectuur
description: AEM Screens-architectuur lijkt op traditionele AEM Sites-architectuur. Inhoud wordt gemaakt op een AEM-auteurinstantie en wordt vervolgens doorgestuurd naar meerdere publicatie-instanties.
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: ba23eb8e-bbde-4a6e-8cfb-ae98176ed890
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 0%

---

# Overzicht van auteur- en publicatiearchitectuur {#author-and-publish-architectural-overview}

Deze pagina benadrukt de volgende onderwerpen:

* **Inleiding om Servers** te publiceren
* **Architecturaal Overzicht**
* **Proces van de Registratie**

## Vereisten {#prerequisites}

Voordat u begint met auteurservers en publicatieservers, moet u op de hoogte zijn van:

* **de Topologie van AEM**
* **Creërend en het Leiden het Project van AEM Screens**
* **Proces van de Registratie van het Apparaat**

>[!NOTE]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.4 Screens Feature Pack 2 hebt geïnstalleerd. Neem contact op met Adobe Support en vraag om toegang tot dit functiepakket. Nadat u toestemming hebt, download het van het Aandeel van het Pakket.

## Inleiding {#introduction}

AEM Screens-architectuur lijkt op traditionele AEM Sites-architectuur. Inhoud wordt gemaakt op een AEM-auteurinstantie en wordt vervolgens doorgestuurd naar meerdere publicatie-instanties. Apparaten op AEM Screens kunnen nu via een taakverdelingsmechanisme verbinding maken met een AEM-publicatiefarm. Meerdere AEM-publicatie-instanties kunnen worden toegevoegd om door te gaan met het schalen van de publicatiecapaciteit.

*bijvoorbeeld*, geeft een Auteur van de Inhoud van AEM Screens een bevel op het auteurssysteem voor een bepaald apparaat uit. Dat apparaat wordt gevormd om met te communiceren publiceer landbouwbedrijf. Of communiceer met een AEM Screens Content Author die informatie verkrijgt over apparaten die zijn geconfigureerd om te communiceren met publicatieboerderijen.

Het volgende diagram illustreert zowel de auteursomgeving als het het publiceren milieu.

![ screen_shot_2019-03-04at30236pm ](assets/screen_shot_2019-03-04at30236pm.png)

## Architecturaal ontwerp {#architectural-design}

Er zijn vijf architecturale componenten die deze oplossing vergemakkelijken:

* ***het Repliceren inhoud*** van auteur voor vertoning door apparaten te publiceren

* ***omgekeerd*** het herhalen binaire inhoud van het het publiceren milieu (die van apparaten wordt ontvangen) aan het auteursmilieu.
* ***verzendt*** bevelen van de auteur om als specifieke REST APIs te publiceren.
* ***Overseinen*** tussen publiceer instanties om de updates en de bevelen van de apparateninformatie te synchroniseren.
* ***Opiniepeiling*** door de auteur van publiceer instanties om apparateninformatie als specifieke REST APIs te verkrijgen.

### Replicatie (vooruit) van inhoud en configuraties {#replication-forward-of-content-and-configurations}

De standaard replicatieagenten worden gebruikt om de inhoud van het AEM Screens-kanaal, locatieconfiguraties, en apparatenconfiguraties te herhalen. Met deze functionaliteit kunnen auteurs de inhoud van een kanaal bijwerken en eventueel een goedkeuringswerkstroom doorlopen voordat ze kanaalupdates publiceren. Een replicatieagent moet voor elk worden gecreeerd publiceer instantie in publiceer landbouwbedrijf.

Het volgende diagram illustreert het replicatieproces:

![ screen_shot_2019-03-04at33935pm ](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>Een replicatieagent moet voor elk worden gecreeerd publiceer instantie in publiceer landbouwbedrijf.

### Screens Replication Agents and Commands {#screens-replication-agents-and-commands}

Aangepaste Screens-specifieke replicatiemiddelen worden gemaakt om opdrachten van de Author-instantie naar het AEM Screens-apparaat te verzenden. De AEM-publicatie-instanties fungeren als tussenpersoon om deze opdrachten naar het apparaat door te sturen.

Met deze workflow kunnen auteurs het apparaat blijven beheren, zoals apparaatupdates verzenden en screenshots maken van de auteuromgeving. De de replicatieagenten van AEM Screens hebben een configuratie van het douanevervoer, als standaardreplicatieagenten.

### Berichten tussen publicatie-instanties {#messaging-between-publish-instances}

Vaak is een opdracht slechts bedoeld om één keer naar een apparaat te worden verzonden. In een publicatiearchitectuur met taakverdeling is de publicatieinstantie waarmee het apparaat verbinding maakt echter onbekend.

Daarom verzendt de auteurinstantie het bericht naar alle Publish instanties. Nochtans, zou slechts één enkel bericht dan aan het apparaat moeten worden afgelost. Voor een correct bericht moet er communicatie plaatsvinden tussen de publicatie-instanties. Deze mededeling wordt bereikt gebruikend *Apache ActiveMQ Artemis*. Elke publicatie-instantie wordt in een los gekoppelde Topologie geplaatst met behulp van de op Oak gebaseerde Sling Discovery-service. ActiveMQ wordt gevormd zodat elke publicatieinstantie één enkele berichtrij kan communiceren en creëren. Het AEM Screens-apparaat pollt de AEM-publicatiecapaciteit via het taakverdelingsmechanisme en haalt de opdracht boven aan de wachtrij op.

### Replicatie omkeren {#reverse-replication}

Vaak wordt na een opdracht een soort reactie van het Screens-apparaat verwacht dat deze naar de instantie Auteur wordt doorgestuurd. Om deze AEM ***omgekeerde replicatie*** te bereiken wordt gebruikt.

* Creeer een omgekeerde replicatieagent voor elke publiceer instantie, zoals aan de standaardreplicatieagenten en de replicatieagenten van AEM Screens.
* Een workflowstartconfiguratie luistert naar knooppunten die zijn gewijzigd op de AEM-publicatie-instantie en activeert op zijn beurt een workflow om de reactie van het apparaat in de outbox van de AEM-publicatie-instantie te plaatsen.
* Een omgekeerde replicatie in deze context wordt slechts gebruikt voor binaire gegevens (zoals logboekdossiers en screenshots) die door de apparaten worden verstrekt. Opiniepeiling van niet-binaire gegevens wordt opgehaald.
* De omgekeerde replicatieopiniepeiling van de de auteursinstantie van AEM wint het antwoord terug en bewaart het aan de auteursinstantie.

### Opiniepeiling van publicatie-instanties {#polling-of-publish-instances}

De auteur instanties moeten de apparaten kunnen opiniepeilen om een hartslag te krijgen en de gezondheidsstatus van een aangesloten apparaat te kennen.

Apparaten pingelen het taakverdelingsmechanisme en worden gerouteerd naar een publicatie-instantie. Het statuut van het apparaat wordt dan blootgesteld door AEM publiceert instantie door Publish API gediend @ **api/screens-dcc/devices/static** voor alle actieve apparaten en **api/screens-dcc/devices/&lt;device_id>/status.json** voor één enkel apparaat.

De instantie van de auteur opiniepeilt alle publicatieinstanties en voegt de reacties van de apparatenstatus in één enkele status samen. De geplande taak die opiniepeilt bij de auteur is `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` en kan worden geconfigureerd op basis van een uitsnijdexpressie.

## Registratie {#registration}

Registratie begint nog steeds bij de auteur-instantie van AEM. Het AEM Screens-apparaat wordt naar de instantie van de auteur verwezen en de registratie wordt voltooid.

Nadat een apparaat is geregistreerd in de AEM-auteursomgeving, worden de apparaatconfiguratie en kanaal-/planningtoewijzingen gerepliceerd naar de AEM-publicatie-instanties. De configuratie van het Apparaat van AEM Screens wordt dan bijgewerkt om aan het taakverdelingsmechanisme vóór AEM te richten publiceert landbouwbedrijf. Deze opstelling is bedoeld om eenmalig te zijn. Nadat het Screens-apparaat is aangesloten op de publicatieomgeving, kan het opdrachten blijven ontvangen die afkomstig zijn van de auteursomgeving. U hoeft het AEM Screens-apparaat niet rechtstreeks aan te sluiten op de AEM-auteursomgeving.

![ screen_shot_2019-02-25at15218pm ](assets/screen_shot_2019-02-25at15218pm.png)

### De volgende stappen {#the-next-steps}

Wanneer u het architecturale ontwerp van auteur begrijpt en opstelling in AEM Screens publiceert, zie [ het Vormen Auteur en publiceert voor AEM Screens ](author-and-publish.md) voor meer details.
