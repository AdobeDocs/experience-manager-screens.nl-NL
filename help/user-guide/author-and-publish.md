---
title: Auteur en publicatie configureren in AEM Screens
seo-title: Auteur en publicatie configureren in AEM Screens
description: AEM Screens-architectuur lijkt op een traditionele AEM Sites-architectuur. De inhoud wordt ontworpen op een AEM auteursinstantie en dan voorwaarts-herhaald aan veelvoudige publiceer instanties. Volg deze pagina om te leren hoe u auteur kunt configureren en publiceren voor AEM Screens.
seo-description: AEM Screens-architectuur lijkt op een traditionele AEM Sites-architectuur. De inhoud wordt ontworpen op een AEM auteursinstantie en dan voorwaarts-herhaald aan veelvoudige publiceer instanties. Volg deze pagina om te leren hoe u auteur kunt configureren en publiceren voor AEM Screens.
translation-type: tm+mt
source-git-commit: 235aa979543455882c72fa262cf7320c4298de5e
workflow-type: tm+mt
source-wordcount: '1910'
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
>Als u meer dan één publicatieexemplaar met dispatcher wilt gebruiken, moet u de dispatcher.om het even welk dossier in uw verzender bijwerken. Zie [Vaste sessies inschakelen](dispatcher-configurations-aem-screens.md#enable-sticky-session) voor meer informatie.

## Instanties {#configuring-author-and-publish-instances} configureren voor auteur en publiceren

>[!NOTE]
>
>Als u meer wilt weten over de auteur en het architecturale overzicht wilt publiceren en wilt weten hoe de inhoud is geschreven op een AEM instantie van de auteur en vervolgens wordt gerepliceerd naar meerdere publicatie-instanties, raadpleegt u [Overzicht van architectuur voor auteurs en publiceren](author-publish-architecture-overview.md).

De volgende sectie verklaart hoe te om replicatieagenten op auteur te plaatsen en topologie te publiceren.

U kunt een eenvoudig voorbeeld instellen, waarin u een auteur en twee publicatie-instanties host:

* Auteur —> localhost:4502
* Publiceren 1 (pub1) —> localhost:4503
* Publiceren 2 (pub2) —> localhost:4504

## Replicatieagents instellen op auteur {#setting-replication-agents}

Om replicatieagenten tot stand te brengen, moet u leren hoe te om een standaardreplicatieagent tot stand te brengen.

Er zijn 3 replicatieagenten die voor de Schermen nodig zijn:

1. **Standaard replicatieagent  ***(opgegeven*** als standaard replicatieagent**)
1. **Screens Replication Agent**
1. **Replicatieagent omkeren**

### Stap 1: Een standaardreplicatieagent {#step-creating-a-default-replication-agent} maken

Voer de onderstaande stappen uit om een standaardreplicatieagent te maken:

1. Navigeer naar uw AEM-instantie —> hamerpictogram —> **Bewerkingen** —> **Configuratie**.

   ![screen_shot_2019-02-25at24621pm](assets/screen_shot_2019-02-25at24621pm.png)

1. Selecteer **Replication** van de linkernavigatieboom.

   ![screen_shot_2019-02-25at24715pm](assets/screen_shot_2019-02-25at24715pm.png)

1. Selecteer **Medewerkers op auteur** van **Replication** omslag en klik **Nieuw** om een nieuwe standaardreplicatieagent tot stand te brengen.

   ![screen_shot_2019-02-25at25400pm](assets/screen_shot_2019-02-25at25400pm.png)

1. Voer de **Titel** en **Naam** in om de replicatieagent te maken en klik **Maken**.

   ![screen_shot_2019-02-25at25737pm](assets/screen_shot_2019-02-25at25737pm.png)

1. Klik met de rechtermuisknop op de replicatieagent en klik op **Openen** om de instellingen te bewerken.

   ![screen_shot_2019-02-25at30018pm](assets/screen_shot_2019-02-25at30018pm.png)

1. Klik **Bewerken** om het dialoogvenster **Agent-instellingen** te openen en de details in te voeren.

   >[!NOTE]
   >
   >Gebruiker moet **Enabled** controleren om replicatieagent toe te laten. U moet deze optie op Gebrek controleren, de Agenten van de Replicatie van de Schermen en Omgekeerde.

   ![screen_shot_2019-02-25at30134pm](assets/screen_shot_2019-02-25at30134pm.png)

1. Navigeer naar het tabblad **Vervoer** en voer **URI**, **Gebruiker** en **Wachtwoord** in.

   ![screen_shot_2019-03-04at34955pm](assets/screen_shot_2019-03-04at34955pm.png)

   >[!NOTE]
   >
   >U kunt een bestaande standaardreplicatieagent ook kopiëren en anders noemen.


#### Standaardreplicatieagents {#creating-standard-replication-agents} maken

1. Creeer standaard replicatieagent voor pub1 (uit-van-de-doos standaardagent zou reeds moeten worden gevormd) (bijvoorbeeld, *https://&lt;hostname>:4503/bin/receive?sling:authRequestLogin=1*)
1. Creeer standaard replicatieagent voor pub2. U kunt rep agent voor pub1 kopiëren en het vervoer bijwerken dat voor pub2 moet worden gebruikt door de haven in de vervoerconfiguratie te veranderen. (bijvoorbeeld *https://&lt;hostname>:4504/bin/receive?sling:authRequestLogin=1*)

#### Apparaten voor schermreplicatie {#creating-screens-replication-agents} maken

1. Maak AEM Screens-replicatieagent voor pub1. Buiten-de-doos, is er één genoemde Agent van de Replicatie van het Scherm die aan haven 4503 richt. Dit moet worden ingeschakeld.
1. Maak AEM Screens-replicatieagent voor pub2. Kopieer de de replicatieagent van Schermen voor pub1 en verander de haven aan punt 4504 voor pub2.

#### Schermen omkeren replicatieagents {#creating-screens-reverse-replication-agents} maken

1. Creeer standaard omgekeerde replicatieagent voor pub1.
1. Creeer standaard omgekeerde replicatieagent voor pub2. U kunt omgekeerde rep agent voor pub1 kopiëren en het vervoer bijwerken dat voor pub2 moet worden gebruikt door de haven in de vervoerconfiguratie te veranderen.

## Publicatietopologie instellen {#setting-up-publish-topology}

### Stap 1: Detectie op basis van Apache Sling-eiken {#step-configure-apache-sling-oak-based-discovery} configureren

Apache Sling Oak-Gebaseerde Ontdekking voor alle Publish instanties in de topologie opzetten

Voor elke publicatie-instantie:

1. Ga naar `https://<host>:<port>/system/console/configMgr`
1. Selecteer **Apache Sling Oak-Based Discovery Service** Configuration.
1. Update Topology schakelaar-URL&#39;s: Voeg URL&#39;s toe van alle publicatieinstanties die voor parseren worden gebruikt:
   * `https://localhost:4503/libs/sling/topology/connector`
   * `https://localhost:4504/libs/sling/topology/connector`
1. **Whitelist List** voor topologieconnector: aanpassen aan IPs of subnets die het ontleden publicatieinstanties behandelen
1. **Lokale-lusbewerkingen automatisch stoppen inschakelen**

De configuratie moet identiek zijn voor elke publicatie-instantie en de Local-loop met de auto-stop voorkomt een oneindige lus.

#### Stap 2: Publicatietopologie {#step-verify-publish-topology} verifiëren

Navigeer voor elk van de publicatie-instanties naar `https://:/system/console/topology`. U zou elke publiceer instanties moeten zien die in de topologie onder **Uitgaande topologieschakelaars** worden vertegenwoordigd.

#### Stap 3: ActiveMQ Artemis-cluster instellen {#step-setup-activemq-artemis-cluster}

Met deze stap kunt u een gecodeerd wachtwoord maken voor de ActiveMQ Artemis-cluster.
De clustergebruiker en het wachtwoord van alle publiceer instanties in de topologie moeten identiek zijn. Het wachtwoord van de configuratie van de Artemis ActiveMQ moet worden gecodeerd. Aangezien elke instantie zijn eigen coderingssleutel heeft, is het nodig om Crypto Support te gebruiken om een gecodeerde wachtwoordtekenreeks te maken. Dan zal het gecodeerde wachtwoord in OSGi config voor ActiveMQ worden gebruikt.

Op elke publicatie-instantie:

1. Navigeer in de OSGi-console naar **MAIN** —> **Crypto Support** (`https://&lt;host&gt;:&lt;port&gt;/system/console/crypto`).
1. Typ het gewenste wachtwoord voor normale tekst (voor alle instanties hetzelfde) in **Onbewerkte tekst**
1. Klik **Protect**.
1. Kopieer de waarde **Beveiligde tekst** naar het aantekenblok of de teksteditor. Deze waarde zal in OSGi config voor ActiveMQ worden gebruikt.

Aangezien elke publicatieinstantie door gebrek unieke crypto sleutels heeft moet u deze stap op elke pub instantie uitvoeren en de unieke sleutel voor de volgende configuratie opslaan.

>[!NOTE]
>
>Het wachtwoord moet beginnen en eindigen met accolades. Bijvoorbeeld:
>`{1ec346330f1c26b5c48255084c3b7272a5e85260322edd59119828d1fa0a610e}`

#### Stap 4: ActiveMQ-artemiscluster activeren {#step-activate-activemq-artemis-cluster}

Op elke publicatie-instantie:

1. Navigeer naar de manager van OSGi Config `https://&lt;host&gt;:&lt;port&gt;/system/console/configMgr`
1. Selecteer **Apache ActiveMQ Artemis JMS Provider** Configuration
1. Werk het volgende bij:

   * ***Clusterwachtwoord***: (gebruik gecodeerde waarde uit vorige stap per instantie)
   * ***Onderwerpen***: {name: &#39;commands&#39;, adres: &#39;com.adobe.cq.screens.commands&#39;, maxConsumers: 50}

#### Verifieer ActiveMQ Artemis Cluster {#verify-activemq-artemis-cluster}

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

Als de volgende configuratie niet wordt weergegeven vanuit */system/console/mq*, navigeert u naar */system/console/mq* en klikt u op **Opnieuw starten** om de broker opnieuw te starten.

![image-2018-06-18-18-14-55-449](assets/image-2018-06-18-18-14-55-449.png)

#### Vereiste {#remove-referrer-header-requirement} voor verwijzingskoptekst verwijderen

Voer de stappen uit op elke instantie Publiceren:

1. Navigeer naar **OSGi Console** > **Configuratiebeheer**
1. Selecteer **Filter Apache Sling Referrer**
1. Configuratie bijwerken en **controleren Lege waarden toestaan**

### Instantie voor auteur en publicatie {#configuring-author-and-publish-instance} configureren

Zodra u opstelling publiceert topologie, moet u de auteur vormen en instanties publiceren, om de praktische resultaten van implementatie te bekijken:

>[!NOTE]
>
>**Vereisten**
>
>U begint met dit voorbeeld door een nieuw AEM Screens-project te maken, gevolgd door een locatie, weergave en kanaal in uw project te maken. Voeg inhoud aan uw kanaal toe en wijs het kanaal aan een vertoning toe.

#### Stap 1: AEM Screens Player (apparaat) {#step-starting-an-aem-screens-player-device} starten

1. Open een apart browservenster.
1. Ga naar de schermspeler met de *webbrowser*, dat wil zeggen`https://localhost:4502/content/mobileapps/cq-screens-player/firmware.html`, of start de AEM Screens-app. Wanneer u het apparaat opent, zult u merken dat de status van het apparaat niet is geregistreerd.

>[!NOTE]
>
>U kunt een AEM Screens-speler openen met de AEM Screens-app die u hebt gedownload of met de webbrowser.

#### Stap 2: Een apparaat registreren op auteur {#step-registering-a-device-on-author}

1. Ga naar `https://localhost:4502/screens.html/content/screens/we-retail` of selecteer uw project en navigeer naar Apparaten > Apparaatbeheer.
1. Selecteer **Apparaat registreren**.
1. Klik **Apparaatregistratie** om het apparaat weer te geven.
1. Selecteer het apparaat dat u wilt registreren en klik **Apparaat registreren**.
1. Verifieer de registratiecode en klik **Valideren**.
1. Voer een titel voor het apparaat in en klik op **Registreren**.

#### Stap 3: Apparaat toewijzen aan weergave {#step-assigning-the-device-to-display}

1. Klik **Weergave toewijzen** in het dialoogvenster van de vorige stap.
1. Selecteer het weergavepad voor uw kanaal in de map **Locations**.
1. Klik **Toewijzen**.
1. Klik **Voltooien** om het proces te voltooien, en nu wordt het apparaat toegewezen.

Controleer de speler en u ziet de inhoud die u in het kanaal hebt toegevoegd.

#### Stap 4: Apparaatconfiguratie publiceren om exemplaren {#step-publishing-device-configuration-to-publish-instances} te publiceren

**Het apparaat controleren**

Voer voordat u de onderstaande stappen uitvoert, de apparaat-id controleren. Zoek naar de apparaat-id in CRXDE Lite, met het pad als */home/users/screens/we-retail/devices*.

Voer de onderstaande stappen uit om de gebruiker van het apparaat te repliceren:

1. Navigeer naar de pagina voor gebruikersbeheer (bijvoorbeeld: `https://localhost:4502/useradmin`
1. Zoeken naar de **screens-devices-master** groep
1. Klik met de rechtermuisknop op de groep en klik op **Activeren**

>[!CAUTION]
>
>Activeer de auteur-publish-screens-service niet omdat dit een systeemgebruiker is, die wordt gebruikt door de Auteur-taak.

U kunt het apparaat ook activeren via de apparaatbeheerconsole. Voer de onderstaande stappen uit:

1. Navigeer naar uw project Schermen —> **Apparaten**.
1. Klik **Apparaatbeheer** op de actiebalk.
1. Selecteer het apparaat en klik op **Activeren** in de actiebalk, zoals in de onderstaande afbeelding wordt getoond.

![screen_shot_2019-02-21at111036am](assets/screen_shot_2019-02-21at111036am.png)

>[!NOTE]
>
>Als u het apparaat hebt geactiveerd, kunt u ook de URL van de server bewerken of bijwerken door te klikken op **Server-URL bewerken** in de actiebalk, zoals in de onderstaande afbeelding wordt getoond, en de wijzigingen worden doorgegeven aan de AEM Screens-speler.

![screen_shot_2019-02-21at105527am](assets/screen_shot_2019-02-21at105527am.png)

### Lijst met publicatiecontrole {#publishing-check-list}

De volgende punten geven een overzicht van de lijst Publishing Check:

* *Scherm Apparaatgebruiker*  - Dit wordt opgeslagen als een AEM gebruiker en geactiveerd via  **Gereedschappen**  >  **Beveiliging**  >  **Gebruikers**. De gebruiker zal met &quot;schermen&quot;met een lange geserialiseerde koord worden vooraf bepaald.

* *Project* : het AEM Screens-project.
* *Locatie*  - Locatie waarmee het apparaat is verbonden.
* *Kanaal* - een of meer kanalen die op de locatie worden weergegeven
* *Plan*  - als het gebruiken van een programma ervoor zorgt dit wordt gepubliceerd
* *Locatie, Planningen en Kanaalmap*  - als de bijbehorende bronnen zich in een map bevinden.

Voer de onderstaande stappen uit om het gedrag van de auteur/publicatie te verifiëren:

1. Kanaalinhoud bijwerken op auteurinstantie
1. **Publicatie beheren** uitvoeren om nieuwe wijzigingen in alle publicatievarianten te publiceren
1. Druk op **Activeren** om het apparaat te activeren vanuit **Apparaatbeheer**
1. **URL** van auteurinstantie-URL naar een van de URL van publicatieinstanties bewerken
1. Controleren of de bijgewerkte kanaalinhoud wordt weergegeven op de AEM Screens-speler
1. Deze stappen herhalen met een andere publicatie-instantie


#### Stap 5: Apparaat aanwijzen om instantie te publiceren in het deelvenster Beheer {#step-pointing-the-device-to-publish-instance-in-the-admin-panel}

1. Bekijk de interface voor het beheer van de schermspeler, druk lang op de linkerbovenhoek om het menu Admin te openen, op de AEM Screens-speler met aanraakbediening of met een muis.
1. Klik op de optie **Configuratie** in het zijpaneel.
1. Schrijverinstantie wijzigen om instantie te publiceren in **Server**.

Bekijk de wijzigingen in je AEM Screens-speler.

U kunt de URL van de server ook bijwerken/bewerken vanuit de apparaatbeheerconsole met de volgende stappen:

1. Navigeer naar uw AEM Screens-project en selecteer de map **Devices**.
1. Klik **Apparaatbeheer** op de actiebalk.
1. Selecteer het apparaat en klik op **Server-URL bewerken** in de actiebalk, zoals in de onderstaande afbeelding wordt weergegeven. Uw wijzigingen worden doorgegeven aan de AEM Screens-speler.

![screen_shot_2019-02-07at31028pm](assets/screen_shot_2019-02-07at31028pm.png)

Met de functie **Publicatie beheren** kunt u inhoud-updates van de auteur leveren en op het apparaat publiceren. U kunt inhoud voor uw gehele AEM Screens-project publiceren of de publicatie ervan ongedaan maken, of alleen voor een van uw kanalen, locatie, apparaat, toepassing of schema. Voor meer informatie over deze eigenschap, verwijs naar [On-Demand Content Update](on-demand-content.md).


