---
title: Bulkregistratie van spelers
seo-title: Bulkregistratie van spelers
description: Volg deze pagina voor meer informatie over de bulkregistratie van spelers met AMS-/On-Prem-schermen.
translation-type: tm+mt
source-git-commit: a00c761297b80239b741e68ef6f2ac611d3559f2
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Bulkregistratie van spelers {#bulk-registration}

Bulk die duizenden spelers handmatig registreert, kan zeer omslachtig worden en zorgt voor meer tijd en kosten. Om dit proces te vereenvoudigen, staat de bulkregistratiefunctie u toe om een pre-gedeelde sleutel in AEM te specificeren die in een speler of door een configuratiedossier of een Mobiel Apparaatbeheer (MDM) oplossing kan worden voorzien.

## Bulkregistratie van spelers {#bulk-registering-implementation} implementeren

Volg de onderstaande stappen om bulkregistratie van spelers in te voeren:

1. Meld u aan bij uw AEM en selecteer het project AEM schermen en klik op eigenschappen en het tabblad Geavanceerd.
1. Er moet een bulkregistratiesectie worden weergegeven waarin u een bulkregistratiecode en een optionele standaardweergave kunt opgeven die aan de in bulk geregistreerde speler wordt toegewezen
1. Voer desgewenst een code naar keuze in en selecteer een standaardweergave
1. Verstrek uw spelers van de aangewezen server URL en registratiecode gebruikend een MDM of configuratie JSON dossier. Raadpleeg de implementatiepagina voor de specifieke speler voor uw besturingssysteem voor exacte informatie. U kunt ook de interface voor beheerders gebruiken om de registratiecode in te voeren.
1. Als het `registrationKey` attribuut in AEM gevormd aanpast, zal de speler zich automatisch registreren en als een standaardvertoning wordt gevormd, zal die inhoud downloaden en spelen.

## Aanbevolen werkwijzen voor beveiliging {#security-best-practices}

Volg de onderstaande sectie om een aantal van de beste praktijken voor Veiligheid te overwegen:

* Om ervoor te zorgen dat de registratiecode niet gecompromitteerd is, vorm de code in AEM enkel alvorens de bulkregistratie te beginnen en wanneer gedaan, gelieve dat gebied te ontruimen en in AEM op te slaan.

* U kunt vormen dat de weg `/bin/screens/`registratie slechts van bekende IP waaiers kan worden betreden indien mogelijk.

* Overweeg het gebruiken van een MDM aan voorziening de speler met de configuratie.

* Gebruik altijd `HTTPS` en niet `HTTP` voor spelermededeling met AEM.

   >[!NOTE]
   >De standaardweergave werkt momenteel alleen voor bulkregistratie en niet voor handmatige registratie zonder registratiecode.