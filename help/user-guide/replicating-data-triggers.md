---
title: Repliceer gegevenstriggers om servers te publiceren
seo-title: Repliceer gegevenstriggers om de server te publiceren
description: Repliceer gegevenstriggers naar publicatieserver.
seo-description: Repliceer gegevenstriggers naar publicatieserver.
translation-type: tm+mt
source-git-commit: c9d618c4d38e8b1f74125c89cc9d25a1dcde54bb

---


# Gegevenstriggers repliceren naar publicatieservers {#replicating-data-triggers}

Wanneer het gebruiken van ContextHub en AEM die Motor richten om inhoud aan te passen die op gegevenstrekkers in een auteur/publiceer opstelling wordt gebaseerd, worden alle aan ContextHub en Personalisatie verwante configuraties niet automatisch herhaald met de kanalen wanneer zij worden gepubliceerd.

Volg deze pagina om de stappen te leren die de handboeken worden vereist om deze configuraties afzonderlijk te publiceren.

Dit komt in feite neer op handmatig publiceren:

1. Configuraties van de modules ContextHub Store en UI
1. Personalisatiepubliek
1. Personeelsactiviteiten

## Stappen voor het repliceren van gegevenstriggers naar publicatieserver {#replicating-data-triggers-publish}

Voer de onderstaande stappen uit om de gegevenstriggers voor het publiceren van de server te repliceren.

### Stap 1: Replicatie van ContextHub-configuraties {#replicating-contexthub-configurations}

1. Navigeer naar **Gereedschappen** > **Implementatie** > **Distributie** > **Publicatieagent** en klik op de publicatieagent om uw instellingen te configureren.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!Nofferte]
   >U kunt de toepassing ook gebruiken `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` om rechtstreeks naar het scherm te navigeren om de verbinding te configureren en te testen.

1. Klik op Verbinding **** testen op de actiebalk om de communicatie van de auteur met de publicatie-instantie te valideren, zoals in de onderstaande afbeelding wordt getoond.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!Nofferte]
   >Als de test ontbreekt, moet u de configuratie van de replicatieagent tussen de auteur bevestigen en instantie publiceren. Raadpleeg Verbinding [testen voor](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) probleemoplossing voor meer informatie.

1. Selecteer **toevoegen** van de het schermboom van de Agent **van de** Distributie en selecteer de configuratiepad voor uw project, bijvoorbeeld, `/conf/screens/settings/cloudsettings/configuration`.

1. Klik op **Verzenden**.

### Het publiek repliceren {#replicating-audiences}

1. Navigeer naar uw AEM-instantie > **Aanpassing** aanpassen > **Soorten publiek** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` om rechtstreeks te navigeren.

1. Boor neer in uw projectomslag, bijvoorbeeld, `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Selecteer alle soorten publiek en segmenten in de gebruikersinterface.

1. Klik op Publicatie **beheren** op de actiebalk.

1. Klik op **Volgende** en **Publiceren**.

### Herhaling van de activiteiten {#replicating-activities}

1. Navigeer naar uw AEM-instantie > **Persoonlijk maken** > **Activiteiten** of gebruik `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` om rechtstreeks te navigeren.

1. Boor neer in uw projectomslag, namelijk `/content/campaigns/screens/…`.

1. Selecteer alle activiteiten in de gebruikersinterface.

1. Klik op Publicatie **beheren** op de actiebalk.

1. Klik op **Volgende** en **Publiceren**.

>[!IMPORTANT]
>
>Het repliceren van configuraties ContextHub en het publiek wordt gedaan tijdens de projectopstelling, terwijl het herhalen van activiteiten en zal worden vereist telkens als het richten binnen een kanaal wordt veranderd.

#### Resultaat {#result}

Als de replicatie succesvol is, zou u de volgende structuur op publiceren instantie (of gelijkaardig voor uw project) moeten bekijken:

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Problemen met testverbinding oplossen {#troubleshoot-test}

Als de testverbinding terwijl het herhalen van de configuraties ContextHub ontbreekt, volg de sectie hieronder voor het oplossen van problemen de kwestie:

1. Ga naar Extra > **Implementatie** > **Distributie** > **Publicatieagent**.

1. Klik **uitgeven** van de actiebar en zorg ervoor het eindpunt URL op het gebied van Eindpunten **van de** Importeur ook aan publicatieserver URL in de Agent van de Distributie richt.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. Als u niet de standaardadmin geloofsbrieven gebruikt, dan moet u de distributieagent met een verschillende gebruikersbenaming en een wachtwoord vormen.

   Voer de onderstaande stappen uit:

   1. Ga naar Gereedschappen > **Bewerkingen** > **Webconsole** `http://localhost:4502/system/console/configMgr`om het scherm **van de webconsole van** Adobe Experience Manager te openen.
   1. Zoeken naar **Apache Sling Distribution Transport Credentials - Gebruikersreferenties gebaseerd DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Maak een configuratie door **Naam**, **Gebruikersnaam** en **wachtwoord** te vullen, bijvoorbeeld *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Click **Save**
   1. Gebruik `Cmd +F` aan onderzoek naar de Agent van de Distributie van **Apache Sling - de Voorwaartse Fabrikant** van Agenten om de configuraties te openen en naar de **Vervoersgeheime Leverancier** te zoeken.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Werk de `(name=default)` bij met `(name=slingTransportSecretProvider)`.
   1. Klik op **Opslaan** en voer de testverbinding opnieuw uit vanuit het scherm **Distribution Agent** van uw AEM-instantie.
