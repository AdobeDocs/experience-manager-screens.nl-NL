---
title: Automatische registratie van spelers
seo-title: Automatische registratie van spelers
description: Volg deze pagina voor meer informatie over automatische registratie van afspeelapparatuur met AMS-/On-Prem-schermen.
translation-type: tm+mt
source-git-commit: 793507b266b99051544b377e4a7effb92dc6feb6
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Automatische registratie van spelers {#auto-registration}

Bulk die duizenden spelers handmatig registreert, kan zeer omslachtig worden en zorgt voor meer tijd en kosten. Om dit proces te vereenvoudigen, staat de bulkregistratiefunctie u toe om een pre-gedeelde sleutel in AEM te specificeren die in een speler of door een configuratiedossier of een Mobiel Apparaatbeheer (MDM) oplossing kan worden voorzien.

## Automatische registratie van spelers {#bulk-registering-implementation} implementeren

Voer de volgende stappen uit om automatische registratie van spelers te implementeren:

1. Meld u aan bij de AEM en selecteer het project AEM schermen en klik op **Eigenschappen** op de actiebalk.
1. Selecteer het tabblad **Geavanceerd** om de sectie **Apparaatregistratie** weer te geven.

1. Geef een automatische registratiecode op in het veld **Bulkregistratiecode** en een optionele standaardweergave in **Standaardweergave toewijzen** om toe te wijzen aan de automatisch geregistreerde speler.
   >[!NOTE]
   >Voer desgewenst een code van uw keuze in en selecteer een standaardweergave.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Verstrek uw spelers van de aangewezen server URL en registratiecode gebruikend een MDM of configuratie JSON dossier.

   >[!NOTE]
   >Raadpleeg de implementatiepagina voor de specifieke speler voor uw besturingssysteem voor meer informatie. U kunt ook de interface voor beheerders gebruiken om de registratiecode in te voeren.

1. Als het `registrationKey` attribuut in AEM gevormd aanpast, zal de speler zich automatisch registreren en als een standaardvertoning wordt gevormd, zal die inhoud downloaden en spelen.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register2.png)

## Aanbevolen werkwijzen voor beveiliging {#security-best-practices}

Volg de onderstaande sectie om een aantal van de beste praktijken voor Veiligheid te overwegen:

* Om ervoor te zorgen dat de registratiecode niet gecompromitteerd is, vorm de code in AEM enkel alvorens de bulkregistratie te beginnen en wanneer gedaan, gelieve dat gebied te ontruimen en in AEM op te slaan.

* U kunt de weg `/bin/screens/registration` vormen om slechts van bekende IP waaiers indien mogelijk toegankelijk te zijn.

* Overweeg het gebruiken van een MDM aan voorziening de speler met de configuratie.

* Gebruik altijd `HTTPS` en niet `HTTP` voor spelermededeling met AEM.

   >[!NOTE]
   >De standaardweergave werkt momenteel alleen voor bulkregistratie en niet voor handmatige registratie zonder registratiecode.