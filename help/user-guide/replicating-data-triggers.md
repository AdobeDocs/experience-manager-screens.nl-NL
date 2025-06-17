---
title: Repliceer gegevenstriggers naar publicatieservers
description: Leer hoe u gegevenstriggers kunt repliceren naar de publicatieserver voor AEM Screens.
feature: Administering Screens, Data Trigger
role: Developer
level: Intermediate
exl-id: 6f90b864-eaa0-4b74-a47e-b0967a550552
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---

# Gegevenstriggers repliceren naar publicatieservers {#replicating-data-triggers}

Wanneer het gebruiken van ContextHub en AEM die Motor richten om inhoud aan te passen die op gegevenstrekkers in een auteur/publiceer opstelling wordt gebaseerd, worden alle aan ContextHub en Personalization verwante configuraties niet automatisch herhaald met de kanalen wanneer gepubliceerd.

Op deze pagina kunt u leren welke handmatige stappen zijn vereist om deze configuraties afzonderlijk te publiceren.

Dit proces komt neer op het manueel publiceren van het volgende:

1. Configuraties van de modules ContextHub Store en UI
1. Personalization-publiek
1. Personalization-activiteiten

## Stappen voor het repliceren van gegevenstriggers naar publicatieserver {#replicating-data-triggers-publish}

Voer de onderstaande stappen uit om de gegevenstriggers voor het publiceren van de server te repliceren.

### Stap 1: het herhalen van Configuraties ContextHub {#replicating-contexthub-configurations}

1. Navigeer aan **Hulpmiddelen** > **Plaatsing** > **Distributie** > **publiceer Agent** en klik de het publiceren agent zodat kunt u uw montages vormen.

   ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >U kunt `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` ook gebruiken om rechtstreeks naar het scherm te navigeren om de verbinding te configureren en te testen.

1. Klik **Verbinding van de Test** van de actiebar zodat kunt u de mededeling van de Auteur met de het Publiceren instantie bevestigen, zoals aangetoond in het volgende:

   ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Als de test ontbreekt, bevestig de configuratie van de replicatieagent tussen de Auteur en het Publiceren instantie. Zie [ Verbinding van de Test van het Oplossen van problemen ](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) voor meer details.

1. Klik **toevoegen** van de **het schermboom van de Agent van de Distributie** en klik de configuratiepad voor uw project, bijvoorbeeld, `/conf/screens/settings/cloudsettings/configuration`.

1. Klik **voorleggen**.

### Het publiek repliceren {#replicating-audiences}

1. Navigeer aan uw instantie van AEM > **Personalization** > **Soorten publiek** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` om direct te navigeren.

1. Ga bijvoorbeeld naar de projectmap `/conf/screens/` .

   ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Klik op alle soorten publiek en segmenten in de gebruikersinterface.

1. Klik **leiden Publicatie** van de actiebar.

1. Klik **daarna** en **publiceren**.

### Herhaling van de activiteiten {#replicating-activities}

1. Navigeer aan uw instantie van AEM > **Personalization** > **Activiteiten** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` om direct te navigeren.

1. Bouw neer in uw projectomslag, namelijk `/content/campaigns/screens/…`.

1. Klik op alle activiteiten in de gebruikersinterface.

1. Klik **leiden Publicatie** van de actiebar.

1. Klik **daarna** en **publiceren**.

>[!IMPORTANT]
>
>Het repliceren van configuraties ContextHub en het publiek wordt gedaan tijdens de projectopstelling terwijl het herhalen van activiteiten en wordt vereist telkens het richten binnen een kanaal veranderd.

#### Resultaat {#result}

Als de replicatie succesvol is, zou u de volgende structuur op publiceren instantie (of gelijkaardig voor uw project) moeten bekijken:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Problemen met testverbinding oplossen {#troubleshoot-test}

Als de testverbinding terwijl het herhalen van de configuraties ContextHub ontbreekt, volg de sectie hieronder voor het oplossen van problemen de kwestie:

1. Navigeer aan **Hulpmiddelen** > **Plaatsing** > **Distributie** > **publiceer Agent**.

1. Klik **uitgeven** van de actiebar en zorg ervoor dat het eindpunt URL in het **Eindpunten van de Importeur** gebied ook aan de het publiceren server URL in de Agent van de Distributie richt.
   ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Als u niet de standaardadmin geloofsbrieven gebruikt, dan moet u de Agent van de Distributie met een verschillende gebruikersbenaming en een wachtwoord vormen.

   Voer de onderstaande stappen uit:

   1. Navigeer aan Hulpmiddelen > **Verrichtingen** > **Console van het Web** `http://localhost:4502/system/console/configMgr` zodat kunt u het **scherm van de Console van het Web van Adobe Experience Manager** openen.
   1. Zoeken naar **`Apache Sling Distribution Transport Credentials - User Credentials based DistributionTransportSecretProvider`**

      ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Creeer een configuratie, door **Naam** te bevolken, **Naam van de Gebruiker**, en **wachtwoord**, bijvoorbeeld, *slingTransportSecretProvider*.

      ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Klik **sparen**
   1. Gebruik `Cmd +F` om naar **Apache het Schipen van de Agent van de Distributie te zoeken - de Voorwaartse Fabriek van Agenten** om de configuraties te openen en naar **Geheime Leverancier van het Vervoer** te zoeken.

      ![ image1 ](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Werk `(name=default)` bij met `(name=slingTransportSecretProvider)` .
   1. Klik **sparen** en stel opnieuw de testverbinding van het **scherm van de Agent van de Distributie** van uw instantie van AEM in werking.
