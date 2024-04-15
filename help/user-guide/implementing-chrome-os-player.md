---
title: Chrome OS Player implementeren
description: Meer informatie over de implementatie van de Chrome OS Player met de Chrome Management Console.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
source-git-commit: 3b44fd920dd6c98ecc0e2b45bf95b81685647c0f
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 0%

---

# Chrome OS Player implementeren  {#implementing-chrome-os-player}

In deze sectie wordt beschreven hoe u de Chrome OS Player implementeert met de Chrome Management Console.

## Chrome Management Console gebruiken {#using-chrome-management-console}

Voer de onderstaande stappen uit om de chrome beheerconsole in te stellen:

1. Registreer u voor de Chrome Management Console. U moet een licentie voor Chrome Management Console aanvragen. Contact [Google-ondersteuning](https://support.google.com/chrome/a/answer/1375678?hl=en&amp;ref_topic=2935995) om Chrome-apparaatinstellingen te beheren voor meer informatie.
1. Voer uw Chrome OS-apparaat in het domein in en wacht 15 minuten totdat het apparaat synchroniseert met de Chrome Management Console. Als u meer wilt weten over het inschrijven van chroomapparaten, selecteert u [hier](https://support.google.com/chrome/a/answer/1360534?hl=en).
1. De Chrome Player is beschikbaar in de Chrome Web store.

>[!NOTE]
>
>Een oplossing voor apparaatbeheer, zoals de Chrome Management Console, wordt aanbevolen voor de implementatie en het beheer van Chrome OS-apparaten. Hoewel dit document implementatie voor de Chrome Management Console biedt, zijn er andere leveranciers die beweren soortgelijke functionaliteit te bieden. Neem contact op met de leverancier van de software voor apparaatbeheer.

## Naam van Chrome OS Player {#name-chrome}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Chrome-speler toewijzen en zo de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de Chrome-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam te configureren in Chrome Player:

1. U kunt desgewenst audio-/video-integrators of IT-beheerders toestaan de id en locatie van het element in te stellen als onderdeel van de inschrijving voor de onderneming.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome1.png)

1. U krijgt de opties te zien wanneer u het apparaat kunt inschrijven.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. U kunt de id van het element instellen als onderdeel van de inschrijving op de onderneming en in de Chrome-beheerconsole.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome Players moeten in ondernemingsinschrijving worden ingeschreven en de speler van Chrome moet door de Console van het Beheer van Chrome worden opgesteld, anders keert identiteitskaart van activa leeg terug (bijvoorbeeld, chroom als uitbreiding). De apparaatnaam wordt alleen opgenomen op het moment van registratie. Toekomstige wijzigingen worden niet opgepikt door Adobe Experience Manager (AEM).

### Modus Kiosk inschakelen {#enabling-kiosk-mode}

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

1. Meld u aan bij de Chrome Developer Console.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Bladeren naar **Apparaatbeheer** > **Chrome-beheer** > **Apparaatinstellingen**.
1. Omlaag schuiven naar **Kiosk-instellingen** en selecteert u **Kiosktoepassingen beheren**.

   ![kiosk](assets/kiosk.png)

1. Selecteer AEM Screens Player in de Chrome Web Store.

   >[!NOTE]
   >
   >Het kan ongeveer 15 minuten duren voordat een onlangs gepubliceerde app in deze lijst wordt weergegeven.

1. Selecteren **AEM Screens Player** van de **Kiosk-app automatisch starten** vervolgkeuzelijst.

   Het kan een paar notulen afhankelijk van het netwerk voor de veranderingen duren om van kracht te worden. Het wordt aanbevolen opnieuw op te starten.

#### De status van extern apparaat controleren {#checking-remote-device-status}

1. Meld u aan bij de Chrome Developer Console.
1. Bladeren naar **Apparaatbeheer** > **Chrome-apparaten** en selecteert u het apparaat dat u wilt besturen.
1. Selecteren **Systeemactiviteit en probleemoplossing**.
1. Controleer de **Apparaat opnieuw opstarten** en **Schermvastlegging** eigenschappen van het apparaat. U kunt ook de status en gezondheidsgegevens van het apparaat controleren.

>[!NOTE]
>
>Deze instellingen kunnen enkele minuten nadat het apparaat is ingeschreven, worden ingeschakeld. Elke optie kan na verloop van tijd worden ingeschakeld.

### Externe configuratie van Chrome OS Players configureren {#configuring-remote-configuration-of-chrome-os-players}

De AEM Screens Player is een toepassing waarvoor Kiosk is ingeschakeld en waarmee ook Externe beleidsconfiguratie voor Chrome OS Players wordt ingeschakeld.

Voer de onderstaande stappen uit om verschillende opties van de speler te configureren:

1. Meld u aan bij de Chrome Management Console.
1. Selecteren **Apparaatbeheer** > **Chrome-beheer** > **Toepassingsbeheer**. De AEM Screens Player wordt in de lijst weergegeven.
1. Selecteer de toepassing **AEM Screens Player**.
1. Selecteren **Kiosk-instellingen** en selecteer uw org (*bij gebruik van een testomgeving*).
1. Selecteren **uploadconfiguratiebestand** en uploadt het configuratiebeleid (*JSon-bestand*).
1. Selecteren **Opslaan**. Start het apparaat opnieuw op zodat u het beleid kunt synchroniseren.

>[!NOTE]
>
>Start het apparaat opnieuw op zodat u beleidswijzigingen kunt synchroniseren.

#### JSON-bestand voorbeeldbeleid {#example-policy-json-file}

```java
{
  "server": {
    "Value": "https://aemscreensdemo.adobeitc.com"
  },
  "resolution": {
    "Value": "auto"
  },
  "rebootSchedule": {
    "Value": "at 4:00am"
  },
  "enableAdminUI": {
    "Value": true
  },
  "enableOSD": {
    "Value": true
  },
  "enableActivityUI": {
    "Value": true
  }
}
```

### Beleidskenmerken en -doel {#policy-attributes-and-purpose}

In de volgende tabel wordt een overzicht gegeven van de beleidsfuncties.

| **Beleidsnaam** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals, zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in zodat u de voortgang van activiteiten, zoals downloaden en synchroniseren, kunt weergeven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Chrome-speler verbinding maakt met as a Cloud Service schermen. Ingesteld op false om verbinding te maken met AMS of on-prem AEM. |
| cloudToken | Registratietoken voor registratie tegen as a Cloud Service schermen. |

>[!NOTE]
>
>De configuraties van het beleid worden strikt afgedwongen en worden niet manueel met voeten getreden bij admin UI van de speler. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in ***beleidsconfiguratie***. Als u bijvoorbeeld handmatige configuratie wilt toestaan voor het opnieuw opstarten, geeft u de sleutel niet op ***rebootSchedule*** in de beleidsconfiguratie.

### De afstandsbediening voor schermen gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Meer informatie over deze functie vindt u hier: [Schermen afstandsbediening](implementing-remote-control.md)
