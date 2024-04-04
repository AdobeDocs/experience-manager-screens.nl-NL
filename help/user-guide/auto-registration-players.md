---
title: Automatische registratie van spelers
description: Volg deze pagina om meer te weten te komen over de automatische registratie van spelers met AMS-/On-Prem-schermen.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
source-git-commit: d1adadbab2cb13626dd8ce70deacced9f55aa4c9
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Automatische registratie van spelers {#auto-registration}

Bulk die duizenden spelers handmatig registreert, kan omslachtig worden en zorgt voor meer tijd en kosten. Om dit proces te vereenvoudigen, staat de bulkregistratiefunctie u toe om een pre-gedeelde sleutel in AEM te specificeren die in een speler of door een configuratiedossier of een Mobiel Apparaatbeheer (MDM) oplossing kan worden voorzien.

## Automatische registratie van spelers implementeren {#bulk-registering-implementation}

Voer de volgende stappen uit om automatische registratie van spelers te implementeren:

1. Meld u aan bij uw AEM en selecteer uw AEM Screens-project en klik op **Eigenschappen** in de actiebalk.
1. Selecteer de **Geavanceerd** zodat u de **Apparaatregistratie** sectie.

1. Geef een code voor automatische registratie op in **Registratiecode voor bulk** veld en een optionele standaardweergave in **Standaardweergavetoewijzing** om toe te wijzen aan de automatisch geregistreerde speler.

   >[!NOTE]
   >Voer desgewenst een code van uw keuze in en selecteer een standaardweergave.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Verstrek uw spelers van de aangewezen server URL en registratiecode gebruikend een MDM of configuratie JSON dossier.

   >[!NOTE]
   >Raadpleeg de implementatiepagina voor de specifieke speler voor uw besturingssysteem voor meer informatie. U kunt ook de interface voor beheerders gebruiken om de registratiecode in te voeren.

1. Als de `registrationKey` kenmerk komt overeen met het kenmerk dat in AEM is geconfigureerd, de speler registreert zichzelf automatisch en als een standaardweergave is geconfigureerd, wordt die inhoud gedownload en afgespeeld.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register2.png)

## Aanbevolen werkwijzen voor beveiliging {#security-best-practices}

Volg de onderstaande sectie om een aantal van de beste praktijken voor Veiligheid te overwegen:

* Zorg ervoor dat de registratiecode niet gecompromitteerd is - vorm de code in AEM enkel alvorens de bulkregistratie te beginnen en wanneer gedaan, ontruim dat gebied, en sparen in AEM.

* U kunt het pad configureren `/bin/screens/registration` om slechts van bekende IP waaiers indien mogelijk toegankelijk te zijn.

* Overweeg het gebruiken van een MDM aan voorziening de speler met de configuratie.

* Altijd gebruiken `HTTPS` en niet `HTTP` voor spelercommunicatie met AEM.

  >[!NOTE]
  >De standaardweergave werkt momenteel alleen voor bulkregistratie en niet voor handmatige registratie zonder registratiecode.
