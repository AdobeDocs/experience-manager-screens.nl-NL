---
title: Beveiligingscontrolelijst voor AEM-schermen
seo-title: Beveiligingscontrolelijst voor AEM-schermen
description: De pagina beschrijft de lijst met beveiligingscontroles voor AEM-schermen
seo-description: De pagina beschrijft de lijst met beveiligingscontroles voor AEM-schermen
translation-type: tm+mt
source-git-commit: aa597424104880a79a8fcec4cfd08cd1a13a8aba

---


# Overwegingen met betrekking tot systeembeveiliging voor AEM-schermen {#security-checklist}

Deze pagina benadrukt de Overwegingen van de Veiligheid van het Systeem voor schermen AEM.


## Witboek voor AEM-schermbeveiliging {#faqs-screens}

In deze sectie wordt het witboek beschreven.


## Veelgestelde vragen over beveiliging van AEM-schermen {#faqs-screens}

De volgende FAQs veronderstelt een voor authentiek verklaarde, geregistreerde spelerarchitectuur gebruikend HTTPS als communicatie protocol tussen speler en Server AEM.

### Veelgestelde vragen 1 {#faq1}

Kan spelerverkeer aan een kwaadwillige server worden opnieuw verpletterd en worden opgedragen om kwaadwillige media inhoud te downloaden en te spelen?

**Antwoord** Het is niet mogelijk omdat de verbinding van HTTP zowel einden van de verbinding identificeert als het codeert. Als u probeert om in het midden te zijn en het te onderscheppen, ziet u slechts gecodeerde inhoud, en als u probeert om zich aan te passen aan de server, zal de speler u weigeren omdat uw certificaat verschillend is.


### Veelgestelde vragen 2 {#faq2}

Moet ik HTTP of HTTPs gebruiken?
**Antwoord** Gebruik HTTP&#39;s. Dit is een noodzaak als u zich zorgen maakt over veiligheid. Met HTTPs wordt de mededeling gecodeerd tussen speler en server, en het onderscheppen van de inhoud of het wijzigen van het zal vrijwel onmogelijk zijn.


### Veelgestelde vragen 3 {#faq3}

Is er bij het downloaden van inhoud enige vorm van ondertekening van de inhoud of hash?
**Antwoord**Elk element wordt door de server ondertekend en vervolgens door de speler voor dezelfde hash gevalideerd om integriteit te garanderen.
Als de hash niet overeenkomt, proberen we drie keer opnieuw te valideren. Na drie pogingen beschouwen we de downloadopdracht als ongeldig.


### Veelgestelde vragen 4 {#faq4}

Is AEM Server beveiligd?
**Antwoord** Ans 4. Ervan uitgaande dat u zich op AMS bevindt, zorgen we voor alle serverbeveiliging met dezelfde functies als Sites of Assets.


### Veelgestelde vragen 5 {#faq5}

Is het apparaat beveiligd?
**Antwoord** Een fysiek gecompromitteerde speler kan theoretisch worden gemanipuleerd om het even welke inhoud te spelen. U kunt de speler ook gewoon uit aansluiten en een USB/HDMI-stick aansluiten.

Zo adviseren wij het plaatsen van de apparaten buiten bereik, bij voorkeur in een beveiligde container, met aanleg van kabelnetten ook beveiligd. Schakel ook alle IR-externe poorten uit.

Als het apparaat OS niet regelmatig wordt bijgewerkt, kan het OS aan veiligheidsgaten worden blootgesteld en verre aanvallen over het netwerk toestaan.
[!NOTE]
>Aanbevolen wordt de apparaten te voorzien van behoorlijke mogelijkheden voor updates en besturing op afstand (externe desktop, MDM-oplossing, enz.)

Het zou ook aanbevelen om ze op een privénetwerk te zetten, bijvoorbeeld niet voor openbare wifi.


### Veelgestelde vragen 6 {#faq6}

Hoe zou een hacker proberen een speler te compromitteren?
**Antwoord** De enige manier om een spelerapparaat in gevaar te brengen is:

1. brengt DNS in gevaar om de server op zijn hostname na te leven en
1. compromis
   1. de server-kant van het certificaat om zich de server voor te doen
   1. apparaat en imiteren van de client-side van het certificaat

1 en 2a zijn in werkelijkheid meestal onpraktisch en met 2b hebt u toch toegang tot het apparaat nodig, dus u kunt het ook verwisselen voor uw eigen apparaat dat nep-inhoud uitvoert.

We zijn dus slechts zo veilig als hun netwerk en hun gebouwen.

>[!IMPORTANT]
>Zelfs als een apparaat gecompromitteerd is, kunt u het nog gemakkelijk intrekken zijn geloofsbrieven zodat het niet meer met AEM kan verbinden.





