---
title: Automatische registratie van spelers
description: Volg deze pagina om meer te weten te komen over de automatische registratie van spelers met AMS/On-Prem Screens.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
source-git-commit: 873e6ff8b506416bce8660f5eb2cbea75227a9c8
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Automatische registratie van spelers {#auto-registration}

Bulk die duizenden spelers handmatig registreert, kan omslachtig worden en zorgt voor meer tijd en kosten. Om dit proces te vereenvoudigen, laat de bulkregistratiefunctie u een pre-gedeelde sleutel in AEM specificeren die in een speler of door een configuratiedossier of een Mobiel Apparaatbeheer (MDM) oplossing kan worden provisioned.

## Automatische registratie van spelers implementeren {#bulk-registering-implementation}

Voer de volgende stappen uit om automatische registratie van spelers te implementeren:

1. Login aan uw AEM instantie en klik uw project van AEM Screens en klik **Eigenschappen** van de actiebar.
1. Klik het **Geavanceerde** lusje zodat kunt u de **registratie van het Apparaat** sectie bekijken.

1. Specificeer een autoregistratiecode op het **gebied van de de registratiecode van het Bulk**. Dan een facultatieve standaardvertoning in de **Standaard vertoningstaak** om aan de speler toe te wijzen die auto wordt geregistreerd.

   >[!NOTE]
   >Voer desgewenst een code van uw keuze in en klik op een standaardweergave.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Verstrek uw spelers van de aangewezen server URL en registratiecode gebruikend een MDM of configuratie JSON dossier.

   >[!NOTE]
   >Raadpleeg de implementatiepagina voor de specifieke speler voor uw besturingssysteem voor meer informatie. U kunt ook de interface voor beheerders gebruiken om de registratiecode in te voeren.

1. Als het kenmerk `registrationKey` overeenkomt met het kenmerk dat in AEM is geconfigureerd, registreert de speler zichzelf automatisch en als een standaardweergave is geconfigureerd, wordt die inhoud gedownload en afgespeeld.

   ![afbeelding](/help/user-guide/assets/auto-registration/auto-register2.png)

## Aanbevolen werkwijzen voor beveiliging {#security-best-practices}

Volg de onderstaande sectie om een aantal van de beste praktijken voor Veiligheid te overwegen:

* Zorg ervoor dat de registratiecode niet gecompromitteerd is - vorm de code in AEM enkel alvorens de bulkregistratie te beginnen en wanneer gedaan, ontruim dat gebied, en sparen in AEM.

* U kunt het pad `/bin/screens/registration` zo configureren dat het, indien mogelijk, alleen toegankelijk is vanuit bekende IP-bereiken.

* Overweeg het gebruiken van een MDM aan voorziening de speler met de configuratie.

* Gebruik altijd `HTTPS` en niet `HTTP` voor spelercommunicatie met AEM.

  >[!NOTE]
  >De standaardweergave werkt momenteel alleen voor bulkregistratie. Deze functie werkt niet voor handmatige registratie wanneer een registratiecode niet beschikbaar is.
