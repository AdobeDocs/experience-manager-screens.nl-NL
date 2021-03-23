---
title: Repliceer gegevenstriggers om servers te publiceren
seo-title: Repliceer gegevenstriggers om de server te publiceren
description: Volg deze pagina om te leren hoe u gegevenstriggers kunt repliceren om de server te publiceren.
seo-description: Repliceer gegevenstriggers naar publicatieserver.
feature: Schermen beheren, Data Trigger
role: Developer
level: Intermediair
translation-type: tm+mt
source-git-commit: 89c70e64ce1409888800af7c7edfbf92ab4b2c68
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 2%

---


# Gegevenstriggers repliceren naar publicatieservers {#replicating-data-triggers}

Wanneer het gebruiken van ContextHub en AEM het richten Motor om inhoud aan te passen die op gegevenstrekkers in een auteur/publiceer opstelling wordt gebaseerd, worden alle aan ContextHub en Personalisatie verwante configuraties niet automatisch herhaald met de kanalen wanneer zij worden gepubliceerd.

Volg deze pagina om de stappen te leren die de handboeken worden vereist om deze configuraties afzonderlijk te publiceren.

Dit komt in feite neer op handmatig publiceren:

1. Configuraties van de modules ContextHub Store en UI
1. Personalisatiepubliek
1. Personeelsactiviteiten

## Stappen voor het repliceren van gegevenstriggers naar publicatieserver {#replicating-data-triggers-publish}

Voer de onderstaande stappen uit om de gegevenstriggers voor het publiceren van de server te repliceren.

### Stap 1: Replicating ContextHub Configurations {#replicating-contexthub-configurations}

1. Navigeer naar **Tools** > **Implementatie** > **Distributie** > **Publish Agent** en klik op de publicatieagent om uw instellingen te configureren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >U kunt ook `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` gebruiken om rechtstreeks naar het scherm te navigeren om de verbinding te configureren en te testen.

1. Klik **Verbinding van de Test** van de actiebar om de mededeling van de auteur met te bevestigen publiceert instantie, zoals aangetoond in het hieronder cijfer.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Als de test ontbreekt, moet u de configuratie van de replicatieagent tussen de auteur bevestigen en instantie publiceren. Raadpleeg [Verbinding voor het oplossen van problemen](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) voor meer informatie.

1. Selecteer **Add** van **Distribution Agent** het schermboom en selecteer de configuratiepad voor uw project, bijvoorbeeld `/conf/screens/settings/cloudsettings/configuration`.

1. Klik **Verzenden**.

### De doelgroepen {#replicating-audiences} repliceren

1. Navigeer naar uw AEM-instantie > **Personalisatie** > **Soorten publiek** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` om rechtstreeks te navigeren.

1. Boor neer in uw projectomslag, bijvoorbeeld, `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Selecteer alle soorten publiek en segmenten in de gebruikersinterface.

1. Klik **Publicatie beheren** van de actiebar.

1. Klik **Volgende** en **Publiceren**.

### Repliceren van de activiteiten {#replicating-activities}

1. Navigeer naar uw AEM-instantie > **Personalisatie** > **Activiteiten** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` om rechtstreeks te navigeren.

1. Boor neer in uw projectomslag, namelijk `/content/campaigns/screens/…`.

1. Selecteer alle activiteiten in de gebruikersinterface.

1. Klik **Publicatie beheren** van de actiebar.

1. Klik **Volgende** en **Publiceren**.

>[!IMPORTANT]
>
>Het repliceren van configuraties ContextHub en het publiek wordt gedaan tijdens de projectopstelling, terwijl het herhalen van activiteiten en zal worden vereist telkens als het richten binnen een kanaal wordt veranderd.

#### Resultaat {#result}

Als de replicatie succesvol is, zou u de volgende structuur op publiceren instantie (of gelijkaardig voor uw project) moeten bekijken:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Problemen met testverbinding {#troubleshoot-test} oplossen

Als de testverbinding terwijl het herhalen van de configuraties ContextHub ontbreekt, volg de sectie hieronder voor het oplossen van problemen de kwestie:

1. Navigeer naar Extra > **Implementatie** > **Distributie** > **Publish Agent**.

1. Klik **geef** van de actiebar uit en zorg ervoor het eindpunt URL in **de Eindpunten van de Importer** gebied ook aan publicatieserver URL in de Agent van de Distributie richt.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Als u niet de standaardadmin geloofsbrieven gebruikt, dan moet u de distributieagent met een verschillende gebruikersbenaming en een wachtwoord vormen.

   Voer de onderstaande stappen uit:

   1. Navigeer naar Extra > **Bewerkingen** > **Webconsole** `http://localhost:4502/system/console/configMgr`om het **Adobe Experience Manager-webconsolescherm** te openen.
   1. Zoeken naar **Apache Sling Distribution Transport Credentials - Gebruikersreferenties gebaseerd DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Maak een configuratie door **Naam**, **Gebruikersnaam** en **wachtwoord** te vullen, bijvoorbeeld *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Klik **Opslaan**
   1. Gebruik `Cmd +F` om naar **Apache Sling Distribution Agent - Forward Agents Factory** te zoeken om de configuraties te openen en naar **Transport Secret Provider** te zoeken.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Werk `(name=default)` met `(name=slingTransportSecretProvider)` bij.
   1. Klik **sparen** en stel opnieuw de testverbinding van het **scherm van de Agent van de Distributie** van uw AEM instantie in werking.
