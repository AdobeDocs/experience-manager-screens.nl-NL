---
title: Beveiligingscontrolelijst voor AEM-schermen
seo-title: Beveiligingscontrolelijst voor AEM-schermen
description: De pagina beschrijft de lijst met beveiligingscontroles voor AEM-schermen
seo-description: De pagina beschrijft de lijst met beveiligingscontroles voor AEM-schermen
translation-type: tm+mt
source-git-commit: dd1198dbfb502287ae72c3ccef297606aef069a2
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---


# Overwegingen met betrekking tot systeembeveiliging voor AEM-schermen {#security-checklist}

>[!IMPORTANT]
>Dit is een interne Git Resource.

Deze pagina benadrukt de Overwegingen van de Veiligheid van het Systeem voor schermen AEM.


## Witboek voor AEM-schermbeveiliging {#white-paper}

In deze sectie wordt het witboek beschreven. (Bijlage witboek in behandeling)


## Veelgestelde vragen over beveiliging van AEM-schermen {#faqs-screens}

De volgende FAQs veronderstelt een voor authentiek verklaarde, geregistreerde spelerarchitectuur gebruikend HTTPS als communicatie protocol tussen speler en Server AEM.

### Veelgestelde vragen 1 {#faq1}

Kan spelerverkeer aan een kwaadwillige server worden opnieuw verpletterd en worden opgedragen om kwaadwillige media inhoud te downloaden en te spelen?

**Antwoord**

Dit is niet mogelijk omdat de HTTPs-verbinding beide uiteinden van de verbinding identificeert en deze versleutelt. Als u probeert om in het midden te zijn en het te onderscheppen, ziet u slechts gecodeerde inhoud, en als u probeert om zich aan te passen aan de server, zal de speler u weigeren omdat uw certificaat verschillend is.


### Veelgestelde vragen 2 {#faq2}

Moet ik HTTP of HTTPs gebruiken?

**Antwoord**

Gebruik HTTP&#39;s. Dit is een noodzaak als u zich zorgen maakt over veiligheid. Met HTTPs wordt de mededeling gecodeerd tussen speler en server, en het onderscheppen van de inhoud of het wijzigen van het zal vrijwel onmogelijk zijn.


### Veelgestelde vragen 3 {#faq3}

Is er bij het downloaden van inhoud enige vorm van ondertekening van de inhoud of hash?

**Antwoord**

Elk element wordt door de server ondertekend en vervolgens door de speler voor dezelfde hash gevalideerd om integriteit te garanderen.
Als de hash niet overeenkomt, proberen we drie keer opnieuw te valideren. Na drie pogingen beschouwen we de downloadopdracht als ongeldig.


### Veelgestelde vragen 4 {#faq4}

Is AEM Server beveiligd?

**Antwoord**

Ans 4. Ervan uitgaande dat u zich op AMS bevindt, zorgen we voor alle serverbeveiliging met dezelfde functies als Sites of Assets.


### Veelgestelde vragen 5 {#faq5}

Is het apparaat beveiligd?

**Antwoord**

Een fysiek gecompromitteerde speler kan theoretisch worden gemanipuleerd om het even welke inhoud te spelen. U kunt de speler ook gewoon uit aansluiten en een USB/HDMI-stick aansluiten.

Daarom wordt het geadviseerd om de apparaten, bij voorkeur in een beveiligde container, met de aanleg van kabelnetten te zetten die ook wordt beveiligd. Schakel ook alle IR-externe poorten uit.

Als het apparaat OS niet regelmatig wordt bijgewerkt, kan het OS aan veiligheidsgaten worden blootgesteld en verre aanvallen over het netwerk toestaan.
>[!NOTE]
>Het wordt aanbevolen de apparaten te voorzien van behoorlijke mogelijkheden voor updates en besturing op afstand (externe desktop, MDM-oplossing, enz.). Het wordt ook aanbevolen een particulier netwerk te gebruiken dat bijvoorbeeld niet aan het openbare WIFI is blootgesteld.


### Veelgestelde vragen 6 {#faq6}

Hoe zou een hacker proberen een speler te compromitteren?

**Antwoord**

De enige manier om een spelerapparaat in gevaar te brengen is:

1. de DNS in gevaar brengen om zich op zijn hostname voor te doen, en,
1. compromis
   1. de server-kant van het certificaat om zich de server voor te doen
   1. apparaat en imiteren van de client-side van het certificaat

>[!IMPORTANT]
>Zelfs als een apparaat gecompromitteerd is, kunt u het nog gemakkelijk intrekken zijn geloofsbrieven zodat het niet meer met AEM kan verbinden.





