---
title: Chrome OS Player implementeren
seo-title: Chrome OS Player implementeren
description: Volg deze pagina voor meer informatie over de implementatie van Chrome OS Player met de Chrome Management Console.
seo-description: Volg deze pagina voor meer informatie over de implementatie van Chrome OS Player met de Chrome Management Console.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Schermen beheren
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
source-git-commit: acf925b7e4f3bba44ffee26919f7078dd9c491ff
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 0%

---

# Chrome OS Player implementeren  {#implementing-chrome-os-player}

In deze sectie wordt beschreven hoe u de Chrome OS Player implementeert met de Chrome Management Console.

## Chrome Management Console gebruiken {#using-chrome-management-console}

Voer de onderstaande stappen uit om de chrome beheerconsole in te stellen:

1. Registreer u voor de Chrome Management Console. U moet een licentie aanvragen voor Chrome Management Console. Neem contact op met [Google Support](https://support.google.com/chrome/a/answer/1375678?hl=en&amp;ref_topic=2935995) om de instellingen van Chrome-apparaten te beheren voor meer informatie.
1. Voer uw Chrome OS-apparaat in het domein in en wacht 15 minuten totdat het apparaat synchroniseert met de Chrome Management Console. Klik [hier](https://support.google.com/chrome/a/answer/1360534?hl=en) voor meer informatie over het inschrijven van een chroomapparaat.
1. De Chrome Player is beschikbaar in de Chrome Web Store.

>[!NOTE]
>
>Een oplossing voor apparaatbeheer, zoals de Chrome Management Console, wordt aanbevolen voor de implementatie en het beheer van Chrome OS-apparaten. Hoewel dit document implementatie voor de Chrome Management Console biedt, zijn er andere leveranciers die beweren soortgelijke functionaliteit te bieden. Neem contact op met de leverancier van de software voor apparaatbeheer.

## Naam van Chrome OS Player {#name-chrome}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Chrome-speler toewijzen en daarbij de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen de Chrome-speler een naam geven, maar kunt u ook gemakkelijk de juiste inhoud toewijzen.

Voer de onderstaande stappen uit om de naam te configureren in Chrome Player:

1. U kunt desgewenst AV-integrators of IT-beheerders toestaan de id en locatie van de bedrijfsmiddelen in te stellen als onderdeel van de inschrijving voor de onderneming.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome1.png)

1. U krijgt de opties te zien wanneer u het apparaat kunt inschrijven.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. U kunt de id van het element instellen als onderdeel van de inschrijving op de onderneming en in de Chrome-beheerconsole.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome Players moeten in ondernemingsinschrijving worden ingeschreven en de speler van Chrome moet door de Console van het Beheer van Chrome worden opgesteld, anders zal identiteitskaart van activa leeg terugkeren (bijvoorbeeld, chroom als uitbreiding). De apparaatnaam wordt alleen opgenomen op het moment van registratie. Toekomstige wijzigingen worden niet opgepikt door Adobe Experience Manager (AEM).

### Modus Kiosk inschakelen {#enabling-kiosk-mode}

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

1. Meld u aan bij de Chrome Developer Console.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Blader naar **Apparaatbeheer** > **Chrome Management** > **Apparaatinstellingen**.
1. Schuif omlaag naar **Kiosk Settings** en klik **Kiosk Applications** beheren.

   ![kiosk](assets/kiosk.png)

1. Selecteer AEM Screens Player in de Chrome Web Store.

   >[!NOTE]
   >
   >Het kan ongeveer 15 minuten duren voordat een onlangs gepubliceerde app in deze lijst wordt weergegeven.

1. Selecteer **AEM Screens Player** in het vervolgkeuzemenu **Kiosk App automatisch starten**.

   Het kan een paar notulen afhankelijk van het netwerk voor de veranderingen duren om van kracht te worden. Het wordt aanbevolen opnieuw op te starten.

#### Status van extern apparaat controleren {#checking-remote-device-status}

1. Meld u aan bij de Chrome Developer Console.
1. Blader naar **Apparaatbeheer** > **Chrome Devices** en selecteer het apparaat dat u wilt besturen.
1. Klik **Systeemactiviteit en probleemoplossing**.
1. Controleer de eigenschappen **Opnieuw opstarten Device** en **Schermvastlegging** van het apparaat. U kunt ook de status en gezondheidsgegevens van het apparaat controleren.

>[!NOTE]
>
>Houd er rekening mee dat deze instellingen mogelijk enkele minuten nadat het apparaat is ingeschreven, zijn ingeschakeld. Elke optie kan na verloop van tijd worden ingeschakeld.

### Externe configuratie van Chrome OS Players configureren {#configuring-remote-configuration-of-chrome-os-players}

De AEM Screens Player is een toepassing waarvoor Kiosk is ingeschakeld en waarmee ook Externe beleidsconfiguratie voor Chrome OS Players wordt ingeschakeld.

Voer de onderstaande stappen uit om verschillende opties van de speler te configureren:

1. Meld u aan bij de Chrome Management Console.
1. Klik **Apparaatbeheer** > **Chrome Management** > **App Management**. De AEM Screens Player wordt in de lijst weergegeven.
1. Klik op de toepassing **AEM Screens Player**.
1. Klik **Kiosk montages** en selecteer uw org (*als het gebruiken van een testmilieu*).
1. Klik op **upload configuratiedossier** en upload het configuratiebeleid (*Json dossier*).
1. Klik **Opslaan**. U moet het apparaat opnieuw opstarten om het beleid te synchroniseren.

>[!NOTE]
>
>Start het apparaat opnieuw op om beleidswijzigingen te synchroniseren.

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

### Beleidskenmerken en doel {#policy-attributes-and-purpose}

In de volgende tabel wordt een overzicht gegeven van de beleidsfuncties.

| **Beleidsnaam** | **Doel** |
|---|---|
| *server* | De URL naar de Adobe Experience Manager-server |
| *resolutie* | De resolutie van het Chrome OS-apparaat |
| *rebootSchedule* | Het programma om de Chrome-speler opnieuw op te starten |
| *enableAdminUI* | Schakel de interface van Admin voor technici in om het apparaat op locatie te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| *enableOSD* | Schakel de interface van de kanaalschakelaar voor gebruikers in om kanalen op het apparaat te schakelen. Denk na plaatsend aan vals zodra het volledig en in productie wordt gevormd. |
| *enableActivityUI* | Schakel deze optie in om de voortgang van activiteiten zoals downloaden en synchroniseren weer te geven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |

>[!NOTE]
>
>De configuraties van het beleid worden strikt afgedwongen en worden niet manueel met voeten getreden bij admin UI van de speler. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in ***beleidsconfiguratie,*** bijvoorbeeld, als u handconfiguratie voor reboot programma wilt toestaan, specificeer niet de sleutel ***rebootSchedule*** in de beleidsconfiguratie.
