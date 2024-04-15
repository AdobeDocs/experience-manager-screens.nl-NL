---
title: Repliceer gegevenstriggers naar publicatieservers
description: Leer hoe u gegevenstriggers kunt repliceren naar de publicatieserver voor AEM Screens.
feature: Administering Screens, Data Trigger
role: Developer
level: Intermediate
exl-id: 6f90b864-eaa0-4b74-a47e-b0967a550552
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Gegevenstriggers repliceren naar publicatieservers {#replicating-data-triggers}

Wanneer het gebruiken van ContextHub en AEM het richten Motor om inhoud aan te passen die op gegevenstrekkers in een auteur/publiceer opstelling wordt gebaseerd, worden alle aan ContextHub en Personalisatie verwante configuraties niet automatisch herhaald met de kanalen wanneer zij worden gepubliceerd.

Op deze pagina kunt u leren welke handmatige stappen zijn vereist om deze configuraties afzonderlijk te publiceren.

Dit komt eigenlijk neer op handmatig publiceren:

1. Configuraties van de modules ContextHub Store en UI
1. Personalisatiepubliek
1. Personeelsactiviteiten

## Stappen voor het repliceren van gegevenstriggers naar publicatieserver {#replicating-data-triggers-publish}

Voer de onderstaande stappen uit om de gegevenstriggers voor het publiceren van de server te repliceren.

### Stap 1: het herhalen van Configuraties ContextHub {#replicating-contexthub-configurations}

1. Navigeren naar **Gereedschappen** > **Implementatie** > **Distributie** > **Publish Agent** en selecteert u de publicatieagent, zodat u uw instellingen kunt configureren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >U kunt ook de opdracht `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` om rechtstreeks naar het scherm te navigeren om de verbinding te configureren en te testen.

1. Selecteren **Verbinding testen** vanuit de actiebalk, zodat u de communicatie van de auteur met de instantie Publishing kunt valideren, zoals in het volgende voorbeeld wordt getoond:

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >Als de test ontbreekt, bevestig de configuratie van de replicatieagent tussen de Auteur en het Publiceren instantie. Zie [Problemen met testverbinding oplossen](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) voor meer informatie .

1. Selecteren **Toevoegen** van de **Distribution Agent** de het schermboom en selecteert de configuratiepad voor uw project, bijvoorbeeld `/conf/screens/settings/cloudsettings/configuration`.

1. Selecteren **Verzenden**.

### Het publiek repliceren {#replicating-audiences}

1. Ga naar uw AEM-instantie > **Personalisatie** > **Soorten publiek** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` om rechtstreeks te navigeren.

1. Ga bijvoorbeeld naar de projectmap, `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Selecteer alle soorten publiek en segmenten in de gebruikersinterface.

1. Selecteren **Publicatie beheren** in de actiebalk.

1. Selecteren **Volgende** en **Publiceren**.

### Herhaling van de activiteiten  {#replicating-activities}

1. Ga naar uw AEM-instantie > **Personalisatie** > **Activiteiten** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` om rechtstreeks te navigeren.

1. Ga naar de projectmap, dat wil zeggen: `/content/campaigns/screens/…`.

1. Selecteer alle activiteiten in de gebruikersinterface.

1. Selecteren **Publicatie beheren** in de actiebalk.

1. Selecteren **Volgende** en **Publiceren**.

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

1. Ga naar Gereedschappen > **Implementatie** > **Distributie** > **Publish Agent**.

1. Selecteren **Bewerken** van de actiebalk en zorg ervoor dat het eindpunt-URL in **Eindpunten importeren** Het veld verwijst ook naar de URL van de publicatieserver in Distribution Agent.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Als u niet de standaardadmin geloofsbrieven gebruikt, dan moet u de distributiegagent met een verschillende gebruikersbenaming en een wachtwoord vormen.

   Voer de onderstaande stappen uit:

   1. Ga naar Gereedschappen > **Bewerkingen** > **Webconsole** `http://localhost:4502/system/console/configMgr`zodat u de **Adobe Experience Manager Web Console-scherm**.
   1. Zoeken naar **Apache Sling Distribution Transport Credentials - Gebruikersreferenties gebaseerd DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Een configuratie maken door deze te vullen **Naam**, **Gebruikersnaam**, en **password**, bijvoorbeeld *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Selecteren **Opslaan**
   1. Gebruiken `Cmd +F` om naar **Apache Sling Distribution Agent - Forward Agents Factory** om de configuraties te openen en naar **Vervoersgeheim provider**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Werk de `(name=default)` with `(name=slingTransportSecretProvider)`.
   1. Selecteren **Opslaan** en voer de testverbinding opnieuw uit vanaf de **Distribution Agent** opnieuw vanaf uw AEM-instantie.
