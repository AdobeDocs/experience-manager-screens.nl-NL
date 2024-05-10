---
title: Beveiligingscontrolelijst voor AEM Screens
description: Meer weten over de lijst met beveiligingscontroles voor AEM Screens?
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Overwegingen met betrekking tot systeembeveiliging voor AEM Screens {#security-checklist}

>[!IMPORTANT]
>Een interne it-bron.

Deze pagina benadrukt de Overwegingen van de Veiligheid van het Systeem voor AEM Screens.


## Witboek voor AEM Screens-beveiliging {#white-paper}

In deze sectie wordt het witboek beschreven. (Bijlage witboek in behandeling)


## Veelgestelde vragen over beveiliging van AEM Screens {#faqs-screens}

De volgende veelgestelde vragen gaan uit van een geverifieerde, geregistreerde spelerarchitectuur. Het gebruikt HTTPS als communicatie protocol tussen de speler en AEM Server.

### Veelgestelde vragen 1 {#faq1}

Kan spelerverkeer naar een kwaadwillige server worden geleid en om kwaadwillige media inhoud te downloaden en te spelen?

**Antwoord**

Dit is niet mogelijk omdat de HTTPs-verbinding beide uiteinden van de verbinding identificeert en deze versleutelt. Als u probeert om in het midden te zijn en het te onderscheppen, ziet u slechts gecodeerde inhoud. Als u de server probeert na te bootsen, weigert de speler u omdat uw certificaat anders is.


### Veelgestelde vragen 2 {#faq2}

Moet ik HTTP of HTTPs gebruiken?

**Antwoord**

Gebruik HTTP&#39;s. Dit protocol is een must-have als u zich over veiligheid bekommert. Met HTTPs, wordt de mededeling gecodeerd tussen speler en server, en het onderscheppen van de inhoud of het wijzigen van het is onmogelijk.


### Veelgestelde vragen 3 {#faq3}

Is er bij het downloaden van inhoud enige vorm van ondertekening van de inhoud of hash?

**Antwoord**

Elk element is ondertekend (SHA) door de server. De speler valideert deze vervolgens voor dezelfde hash om integriteit te garanderen.
Als de hash niet overeenkomt, probeert de software driemaal opnieuw te valideren. Na drie pogingen wordt de opdracht Downloaden als ongeldig beschouwd.


### Veelgestelde vragen 4 {#faq4}

Is AEM Server veilig?

**Antwoord**

Ervan uitgaande dat u AMS gebruikt, zorgt de software voor alle serverbeveiliging met dezelfde functies als Sites of Assets.


### Veelgestelde vragen 5 {#faq5}

Is het apparaat beveiligd?

**Antwoord**

Een fysiek gecompromitteerde speler kan theoretisch worden gemanipuleerd om het even welke inhoud te spelen. U kunt de speler ook loskoppelen en een USB/HDMI-stick aansluiten.

Zet de apparaten uit bereik, bij voorkeur in een beveiligde container, met bekabeling ook beveiligd. Schakel ook alle IR-externe poorten uit.

Als het apparaat-besturingssysteem niet regelmatig wordt bijgewerkt, blijft het besturingssysteem mogelijk blootgesteld aan beveiligingslekken en kunnen externe aanvallen via het netwerk worden uitgevoerd.

>[!NOTE]
>
>Het wordt geadviseerd om de apparaten met behoorlijke verre update en controlemogelijkheden (verre Desktop, oplossing MDM, etc.) te voorzien. Het wordt ook aanbevolen een particulier netwerk te gebruiken dat bijvoorbeeld niet aan het openbare WIFI is blootgesteld.


### Veelgestelde vragen 6 {#faq6}

Hoe zou een hacker proberen een speler te compromitteren?

**Antwoord**

De enige manier om een spelerapparaat in gevaar te brengen is:

1. het DNS in gevaar brengen om de server op deze hostname na te leven, en,
1. compromis
   1. de server-kant van het certificaat om zich de server voor te doen
   1. apparaat en imiteren van de client-side van het certificaat

>[!IMPORTANT]
>Zelfs als een apparaat gecompromitteerd is, kunt u zijn geloofsbrieven nog gemakkelijk intrekken zodat het niet meer met AEM kan verbinden.





