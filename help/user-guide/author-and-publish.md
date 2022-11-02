---
title: Auteur en publicatie configureren in AEM Screens
description: AEM Screens-architectuur lijkt op een traditionele AEM Sites-architectuur. De inhoud wordt ontworpen op een AEM auteursinstantie en dan voorwaarts-herhaald aan veelvoudige publiceer instanties. Volg deze pagina om te leren hoe u auteur kunt configureren en publiceren voor AEM Screens.
exl-id: 5aef5f35-d946-4bf8-a2a8-c3ed532b7eef
source-git-commit: 458ecfbbfb072a07d97d68f2a7ef1eb51f3db598
workflow-type: tm+mt
source-wordcount: '1974'
ht-degree: 0%

---


# Auteur en publicatie configureren in AEM Screens {#configuring-author-and-publish-in-aem-screens}

Deze pagina benadrukt de volgende onderwerpen:

* **Auteur- en publicatie-instanties configureren**
* **Publicatietopologie instellen**
* **Publicatie beheren: Inhoud-updates leveren van auteur voor publicatie op apparaat**

## Vereisten {#prerequisites}

Voordat u aan de slag gaat met auteur- en publicatieservers, hebt u eerst kennis van:

* **AEM**
* **AEM Screens-project maken en beheren**
* **Registratieproces van apparaat**

>[!NOTE]
>
>Deze AEM Screens-functionaliteit is alleen beschikbaar als u AEM 6.4 Screens Feature Pack 2 hebt geïnstalleerd. Als u toegang wilt krijgen tot dit pakket functies, moet u contact opnemen met de Adobe Support en toegang aanvragen. Als u beschikt over de juiste machtigingen, kunt u deze downloaden via Pakket delen.

>[!IMPORTANT]
>
>Als u meer dan één publicatieexemplaar met dispatcher wilt gebruiken, moet u de dispatcher.om het even welk dossier in uw verzender bijwerken. Zie [Vaste sessies inschakelen](dispatcher-configurations-aem-screens.md#enable-sticky-session) voor meer informatie .

## Instanties voor auteur en publiceren configureren {#configuring-author-and-publish-instances}

>[!NOTE]
>
>Als u meer wilt weten over de auteur en het architecturale overzicht wilt publiceren en wilt weten hoe de inhoud is geschreven op een AEM auteur-instantie en vervolgens naar meerdere publicatie-instanties moet worden gerepliceerd, raadpleegt u [Overzicht van auteur- en publicatiearchitectuur](author-publish-architecture-overview.md).

De volgende sectie verklaart hoe te om replicatieagenten op auteur te plaatsen en topologie te publiceren.

U kunt een eenvoudig voorbeeld instellen, waarin u een auteur en twee publicatie-instanties host:

* Auteur —> localhost:4502
* Publiceren 1 (pub1) —> localhost:4503
* Publiceren 2 (pub2) —> localhost:4504

## Replication Agents instellen op auteur {#setting-replication-agents}

Om replicatieagenten tot stand te brengen, moet u leren hoe te om een standaardreplicatieagent tot stand te brengen.

Er zijn 3 replicatieagenten die voor de Schermen nodig zijn:

1. **Standaardreplicatieagent ***(opgegeven als*** Standard Replication Agent**)
1. **Screens Replication Agent**
1. **Replicatieagent omkeren**

### Stap 1: Een standaardreplicatieagent maken {#step-creating-a-default-replication-agent}

Voer de onderstaande stappen uit om een standaardreplicatieagent te maken:

1. Ga naar uw AEM-exemplaar —> hamerpictogram —> **Bewerkingen** —> **Configuratie**.

   ![screen_shot_2019-02-25at24621pm](assets/screen_shot_2019-02-25at24621pm.png)

1. Selecteer **Replicatie** in de linkernavigatiestructuur.

   ![screen_shot_2019-02-25at24715pm](assets/screen_shot_2019-02-25at24715pm.png)

1. Selecteer **Medewerkers op auteur** van de **Replicatie** map en klik op **Nieuw** om een nieuwe standaardreplicatieagent tot stand te brengen.

   ![screen_shot_2019-02-25at25400pm](assets/screen_shot_2019-02-25at25400pm.png)

1. Voer de **Titel** en **Naam** om de replicatieagent te creëren en klik **Maken**.

   ![screen_shot_2019-02-25at25737pm](assets/screen_shot_2019-02-25at25737pm.png)

1. Klik met de rechtermuisknop op de replicatieagent en klik op **Openen** om de instellingen te bewerken.

   ![screen_shot_2019-02-25at30018pm](assets/screen_shot_2019-02-25at30018pm.png)

1. Klikken **Bewerken** om de **Instellingen agent** om de details in te voeren.

   >[!NOTE]
   >
   >Gebruiker moet controleren **Ingeschakeld** om replicatieagent toe te laten. U moet deze optie op Gebrek controleren, de Agenten van de Replicatie van de Schermen en Omgekeerde.

   ![screen_shot_2019-02-25at30134pm](assets/screen_shot_2019-02-25at30134pm.png)

1. Ga naar de **Vervoer** en voert u de **URI**, **Gebruiker** en **Wachtwoord**.

   ![screen_shot_2019-03-04at34955pm](assets/screen_shot_2019-03-04at34955pm.png)

   >[!NOTE]
   >
   >U kunt een bestaande standaardreplicatieagent ook kopiëren en anders noemen.


#### Standaardreplicatieagents maken  {#creating-standard-replication-agents}

1. Creeer standaard replicatieagent voor pub1 (uit-van-de-doos standaardagent zou reeds moeten worden gevormd) (bijvoorbeeld, *https://&lt;hostname>:4503/bin/receive?sling:authRequestLogin=1*)
1. Creeer standaard replicatieagent voor pub2. U kunt rep agent voor pub1 kopiëren en het vervoer bijwerken dat voor pub2 moet worden gebruikt door de haven in de vervoerconfiguratie te veranderen. (bijvoorbeeld *https://&lt;hostname>:4504/bin/receive?sling:authRequestLogin=1*)

#### Schermreplicatieagents maken {#creating-screens-replication-agents}

1. Maak AEM Screens-replicatieagent voor pub1. Buiten-de-doos, is er één genoemde Agent van de Replicatie van het Scherm die aan haven 4503 richt. Dit moet worden ingeschakeld.
1. Maak AEM Screens-replicatieagent voor pub2. Kopieer de de replicatieagent van Schermen voor pub1 en verander de haven aan punt 4504 voor pub2.

   >[!NOTE]
   >Om te leren hoe te om de Agenten van de Replicatie van het Scherm te vormen, zie [De agent voor schermreplicatie configureren](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/configure-screens-replication.html?lang=en).

#### Screens Reverse Replication Agents maken {#creating-screens-reverse-replication-agents}

1. Creeer standaard omgekeerde replicatieagent voor pub1.
1. Creeer standaard omgekeerde replicatieagent voor pub2. U kunt omgekeerde rep agent voor pub1 kopiëren en het vervoer bijwerken dat voor pub2 moet worden gebruikt door de haven in de vervoerconfiguratie te veranderen.

## Publicatietopologie instellen {#setting-up-publish-topology}

### Stap 1: Detectie op basis van Apache Sling-eiken configureren {#step-configure-apache-sling-oak-based-discovery}

Apache Sling Oak-Gebaseerde Ontdekking voor alle Publish instanties in de topologie opzetten

Voor elke publicatie-instantie:

1. Ga naar `https://<host>:<port>/system/console/configMgr`
1. Selecteren **Apache Sling Oak-based Discovery Service** Configuratie.
1. Update Topology schakelaar-URL&#39;s: Voeg URL&#39;s toe van alle publicatieinstanties die voor parseren worden gebruikt:
   * `https://localhost:4503/libs/sling/topology/connector`
   * `https://localhost:4504/libs/sling/topology/connector`
1. **Whitelist-lijst met topologiecontracten**: aanpassen aan IPs of subnets die het ontleden publicatieinstanties behandelen
1. Inschakelen **Lokale lussen automatisch stoppen**

De configuratie moet identiek zijn voor elke publicatie-instantie en de Local-loop met de auto-stop voorkomt een oneindige lus.

#### Stap 2: Publicatietopologie verifiëren {#step-verify-publish-topology}

Blader voor elk van de publicatie-instanties naar `https://:/system/console/topology`. U zou elke publicatieinstanties moeten zien die in de topologie onder worden vertegenwoordigd **Uitgaande topologieschakelaars**.

#### Stap 3: ActiveMQ Artemis-cluster instellen {#step-setup-activemq-artemis-cluster}

Met deze stap kunt u een gecodeerd wachtwoord maken voor de ActiveMQ Artemis-cluster.
De clustergebruiker en het wachtwoord van alle publiceer instanties in de topologie moeten identiek zijn. Het wachtwoord van de configuratie van de Artemis ActiveMQ moet worden gecodeerd. Aangezien elke instantie zijn eigen coderingssleutel heeft, is het nodig om Crypto Support te gebruiken om een gecodeerde wachtwoordtekenreeks te maken. Dan zal het gecodeerde wachtwoord in OSGi config voor ActiveMQ worden gebruikt.

Op elke publicatie-instantie:

1. Navigeer in de OSGi-console naar **BELANGRIJK** —> **Crypto-ondersteuning** (`https://&lt;host&gt;:&lt;port&gt;/system/console/crypto`).
1. Typ het gewenste wachtwoord voor normale tekst (voor alle instanties hetzelfde) in **Onbewerkte tekst**
1. Klikken **Protect**.
1. De waarde kopiëren **Beveiligde tekst** op notitiepad of teksteditor. Deze waarde zal in OSGi config voor ActiveMQ worden gebruikt.

Aangezien elke publicatieinstantie door gebrek unieke crypto sleutels heeft moet u deze stap op elke pub instantie uitvoeren en de unieke sleutel voor de volgende configuratie opslaan.

>[!NOTE]
>
>Het wachtwoord moet beginnen en eindigen met accolades. Bijvoorbeeld:
>`{1ec346330f1c26b5c48255084c3b7272a5e85260322edd59119828d1fa0a610e}`

#### Stap 4: ActiveMQ-artemiscluster activeren {#step-activate-activemq-artemis-cluster}

Op elke publicatie-instantie:

1. Navigeer naar de manager van OSGi Config `https://&lt;host&gt;:&lt;port&gt;/system/console/configMgr`
1. Selecteren **Apache ActiveMQ Artemis JMS Provider** Configuratie
1. Werk het volgende bij:

   * ***Clusterwachtwoord***: gebruik gecodeerde waarde van vorige stap per respectieve instantie
   * ***Onderwerpen***: `{name: 'commands', address: 'com.adobe.cq.screens.commands', maxConsumers: 50}`

#### ActiveMQ Artemis-cluster verifiëren {#verify-activemq-artemis-cluster}

Voer de onderstaande stappen uit voor elke instantie Publiceren:

1. Navigeer naar de OSGi-console -> Hoofd > ActiveMQ-artemis `https://localhost:4505/system/console/mq`.
1. Verifieer en controleer om de havens van andere instanties onder de Informatie van de Cluster te bekijken > Topology > knopen=2, members=2.
1. Een testbericht verzenden (boven aan het scherm onder Informatie over kiezer)
1. Voer de volgende wijzigingen in velden in:

   1. **Doel**: /com.adobe.cq.screens/devTestTopic
   1. **Tekst**: Hallo wereld
   1. Bekijk error.log van elke instantie om te zien dat het bericht over de cluster werd verzonden en werd ontvangen

>[!NOTE]
>
>Navigeer aan console OSGi, kan een paar seconden na het bewaren van de configuratie in de voorafgaande stap nemen. U kunt error.log voor meer details ook controleren.

Als voorbeeld, toont het volgende beeld op succesvolle configuratie van de Server van Artemis ActiveMQ.

Als u de volgende configuratie niet ziet van */system/console/mq* en navigeer vervolgens naar */system/console/mq* en klik op **Opnieuw starten** om de makelaar opnieuw te starten.

![image-2018-06-18-18-14-55-449](assets/image-2018-06-18-18-14-55-449.png)

#### Vereiste koptekst verwijzing verwijderen {#remove-referrer-header-requirement}

Voer de stappen uit op elke instantie Publiceren:

1. Ga naar de **OSGi Console** > **Configuratiebeheer**
1. Selecteren **Filter Apache Sling Referrer**
1. Configuratie bijwerken en **selectievakje Lege waarden toestaan**

### Instantie voor auteur en publicatie configureren {#configuring-author-and-publish-instance}

Zodra u opstelling publiceert topologie, moet u de auteur vormen en instanties publiceren, om de praktische resultaten van implementatie te bekijken:

>[!NOTE]
>
>**Vereisten**
>
>U begint met dit voorbeeld door een nieuw AEM Screens-project te maken, gevolgd door een locatie, weergave en kanaal in uw project te maken. Voeg inhoud aan uw kanaal toe en wijs het kanaal aan een vertoning toe.

#### Stap 1: AEM Screens Player (apparaat) starten {#step-starting-an-aem-screens-player-device}

1. Open een apart browservenster.
1. Ga naar de schermspeler met de *webbrowser*, dat wil zeggen:`https://localhost:4502/content/mobileapps/cq-screens-player/firmware.html` of start de AEM Screens-app. Wanneer u het apparaat opent, zult u merken dat de status van het apparaat niet is geregistreerd.

>[!NOTE]
>
>U kunt een AEM Screens-speler openen met de AEM Screens-app die u hebt gedownload of met de webbrowser.

#### Stap 2: Een apparaat registreren bij auteur {#step-registering-a-device-on-author}

1. Ga naar `https://localhost:4502/screens.html/content/screens/we-retail` of selecteer uw project en navigeer naar Apparaten > Apparaatbeheer.
1. Selecteren **Apparaat registreren**.
1. Klikken **Apparaatregistratie** om het apparaat weer te geven.
1. Selecteer het apparaat dat u wilt registreren en klik op **Apparaat registreren**.
1. Verifieer de registratiecode en klik **Valideren**.
1. Voer een titel in voor uw apparaat en klik op **Registreren**.

#### Stap 3: Apparaat toewijzen aan weergave {#step-assigning-the-device-to-display}

1. Klikken **Weergave toewijzen** in het dialoogvenster van de vorige stap.
1. Selecteer het weergavepad voor uw kanaal in het menu **Locaties** map.
1. Klikken **Toewijzen**.
1. Klikken **Voltooien** om het proces te voltooien, en nu wordt het apparaat toegewezen.

Controleer de speler en u ziet de inhoud die u in het kanaal hebt toegevoegd.

#### Stap 4: Apparaatconfiguratie publiceren om instanties te publiceren {#step-publishing-device-configuration-to-publish-instances}

**Het apparaat controleren**

Voer de onderstaande stappen uit om de gebruiker van het apparaat te repliceren:

1. Navigeer naar de pagina voor gebruikersbeheer (bijvoorbeeld: `https://localhost:4502/useradmin`
1. Zoeken naar **schermen-apparaten-master** groep
1. Klik met de rechtermuisknop op de groep en klik op **Activeren**

>[!CAUTION]
>
>Activeer de auteur-publish-screens-service niet omdat dit een systeemgebruiker is, die wordt gebruikt door de Auteur-taak.

U kunt het apparaat ook activeren via de apparaatbeheerconsole. Voer de onderstaande stappen uit:

1. Ga naar uw project Schermen —> **Apparaten**.
1. Klikken **Apparaatbeheer** in de actiebalk.
1. Selecteer het apparaat en klik op **Activeren** op de actiebalk, zoals in de onderstaande afbeelding.

![screen_shot_2019-02-21at111036am](assets/screen_shot_2019-02-21at111036am.png)

>[!NOTE]
>
>Als u het apparaat hebt geactiveerd, kunt u ook de URL van de server bewerken of bijwerken door op **URL van server bewerken** in de actiebalk, zoals in de onderstaande afbeelding wordt getoond, worden uw wijzigingen doorgegeven aan de AEM Screens-speler.

![screen_shot_2019-02-21at105527am](assets/screen_shot_2019-02-21at105527am.png)

### Lijst met publicatiecontrole {#publishing-check-list}

De volgende punten geven een overzicht van de lijst Publishing Check:

* *Apparaatgebruiker voor schermen* - Dit wordt opgeslagen als een AEM gebruiker en geactiveerd van **Gereedschappen** > **Beveiliging** > **Gebruikers**. De gebruiker zal met &quot;schermen&quot;met een lange geserialiseerde koord worden vooraf bepaald.

* *Project* - Het AEM Screens-project.
* *Locatie* - Locatie waarmee het apparaat is verbonden.
* *Kanaal/kanalen* - een of meer kanalen die op de locatie worden weergegeven
* *Schema* - indien een schema wordt gebruikt, zorg ervoor dat dit wordt gepubliceerd
* *Locatie, planningen en kanaalmap* - als de bijbehorende bronnen zich in een map bevinden.

Voer de onderstaande stappen uit om het gedrag van de auteur/publicatie te verifiëren:

1. Kanaalinhoud bijwerken op auteurinstantie
1. Uitvoeren **Publicatie beheren** om nieuwe wijzigingen te publiceren in alle publicatievarianten
1. Druk **Activeren** om het apparaat te activeren van **Apparaatbeheer**
1. **URL bewerken** van auteur-instantie-URL naar een publicatie-instantie-URL
1. Controleren of de bijgewerkte kanaalinhoud wordt weergegeven op de AEM Screens-speler
1. Deze stappen herhalen met een andere publicatie-instantie


#### Stap 5: Het apparaat aanwijzen om een instantie te publiceren in het deelvenster Beheer {#step-pointing-the-device-to-publish-instance-in-the-admin-panel}

1. Bekijk de interface voor het beheer van de schermspeler, druk lang op de linkerbovenhoek om het menu Admin te openen, op de AEM Screens-speler met aanraakbediening of met een muis.
1. Klik op de knop **Configuratie** in het zijpaneel.
1. Instantie van auteur wijzigen in **Server**.

Bekijk de wijzigingen in je AEM Screens-speler.

U kunt de URL van de server ook bijwerken/bewerken vanuit de apparaatbeheerconsole met de volgende stappen:

1. Ga naar uw AEM Screens-project en selecteer het **Apparaten** map.
1. Klikken **Apparaatbeheer** in de actiebalk.
1. Selecteer het apparaat en klik op **URL van server bewerken** in de actiebalk, zoals in de onderstaande afbeelding wordt getoond, worden uw wijzigingen doorgegeven aan de AEM Screens-speler.

![screen_shot_2019-02-07at31028pm](assets/screen_shot_2019-02-07at31028pm.png)

De **Publicatie beheren** met deze functie kunt u inhoud-updates van de auteur leveren en op het apparaat publiceren. U kunt inhoud voor uw gehele AEM Screens-project publiceren of de publicatie ervan ongedaan maken, of alleen voor een van uw kanalen, locatie, apparaat, toepassing of schema. Voor meer informatie over deze functie raadpleegt u [Update voor on-demand inhoud](on-demand-content.md).

## Tips voor het oplossen van problemen {#troubleshoot-tips}

Volg de onderstaande sectie om antwoorden te krijgen op veelgestelde vragen met betrekking tot auteur/publicatie-instellingen.

### Hoe voegt u een omleiding van https naar http toe na de eerste registratie en toewijzing? {#add-redirect}

**Oplossing**
Inschakelen instellen `Proxy/Load Balancer Connection in the Jetty configuration` tot `true`.

### Offline-inhoud en downloadproblemen met speler bijwerken met externe middelen `/content/dam/projects/<project>`? {#update-offline-content}

**Oplossing**
Leesmachtigingen geven voor de groep met meerdere offlineupdatefrasters-service voor gebruikers en schermen-apparaten-master voor alle `/content/dam` of de specifieke elementen die u wilt gebruiken, als u restrictiever wilt zijn.

### Hoe te om de fouten van de Agent van de Replicatie van het Scherm op te lossen? {#replication-agent}

**Oplossing**
Zorg ervoor u niet Gebruik voor omgekeerde replicatieoptie in de agentenconfiguratie hebt gecontroleerd. De Agent van de Replicatie van schermen kan niet als omgekeerde replicatieagent worden gebruikt en het werkingsgebied van deze eigenschap moet apparatenbevelen van auteur door:sturen om te publiceren.