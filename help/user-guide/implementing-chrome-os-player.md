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
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# Chrome OS Player implementeren {#implementing-chrome-os-player}

In deze sectie wordt beschreven hoe u de Chrome OS Player implementeert met de Chrome Management Console.

## Chrome Management Console gebruiken {#using-chrome-management-console}

Voer de onderstaande stappen uit om de chrome beheerconsole in te stellen:

1. Registreer u voor de Chrome Management Console. U moet een licentie aanvragen voor Chrome Management Console. Neem contact op met de [Google-ondersteuning](https://support.google.com/chrome/a/answer/1375678?hl=en&ref_topic=2935995) om de instellingen van Chrome-apparaten te beheren voor meer informatie.
1. Voer uw Chrome OS-apparaat in het domein in en wacht 15 minuten totdat het apparaat synchroniseert met de Chrome Management Console. Klik [hier](https://support.google.com/chrome/a/answer/1360534?hl=en)voor meer informatie over het inschrijven van een chroomapparaat.
1. De Chrome Player is beschikbaar in de Chrome Web Store.

>[!NOTE]
>
>Een oplossing voor apparaatbeheer, zoals de Chrome Management Console, wordt aanbevolen voor de implementatie en het beheer van Chrome OS-apparaten. Hoewel dit document implementatie voor de Chrome Management Console biedt, zijn er andere leveranciers die beweren soortgelijke functionaliteit te bieden. Neem contact op met de leverancier van de software voor apparaatbeheer.

### Modus Kiosk inschakelen {#enabling-kiosk-mode}

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

1. Meld u aan bij de Chrome Developer Console.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Blader naar **Apparaatbeheer** > **Chrome Management** > **Apparaatinstellingen**.
1. Blader omlaag naar **Kiosk Settings** en klik op **Manage Kiosk Applications**.

   ![kiosk](assets/kiosk.png)

1. Selecteer AEM Screens Player van de Winkel van het Web van de Chroom.

   >[!NOTE]
   >
   >Het kan ongeveer 15 minuten duren voordat een onlangs gepubliceerde app in deze lijst wordt weergegeven.

1. Selecteer **AEM Screens Player** van de **AutoLounch Kiosk App** dropdown.

   Het kan een paar notulen afhankelijk van het netwerk voor de veranderingen duren om van kracht te worden. Het wordt aanbevolen opnieuw op te starten.

#### Status van extern apparaat controleren {#checking-remote-device-status}

1. Meld u aan bij de Chrome Developer Console.
1. Blader naar **Apparaatbeheer** > **Chrome-apparaten** en selecteer het apparaat dat u wilt besturen.
1. Klik op **Systeemactiviteit en probleemoplossing**.
1. Controleer de eigenschappen **Reboot Device** en **Screen Capture** van het apparaat. U kunt ook de status en gezondheidsgegevens van het apparaat controleren.

>[!NOTE]
>
>Houd er rekening mee dat deze instellingen mogelijk enkele minuten nadat het apparaat is ingeschreven, zijn ingeschakeld. Elke optie kan na verloop van tijd worden ingeschakeld.

### Externe configuratie van Chrome OS Players configureren {#configuring-remote-configuration-of-chrome-os-players}

De AEM Screens Player is een toepassing die geschikt is voor Kiosk en waarmee ook Externe beleidsconfiguratie voor Chrome OS Players wordt ingeschakeld.

Voer de onderstaande stappen uit om verschillende opties van de speler te configureren:

1. Meld u aan bij de Chrome Management Console.
1. Klik op **Apparaatbeheer** > **Chrome Management** > **App Management**. De AEM-schermspeler wordt in de lijst weergegeven.
1. Klik op de **AEM Screens Player** van de toepassing.
1. Klik op de **Kiosk-instellingen** en selecteer uw org (*als u een testomgeving* gebruikt).
1. Klik op het configuratiebestand **voor** uploaden en upload het configuratiebeleid (*Json-bestand*).
1. Click **Save**. U moet het apparaat opnieuw opstarten om het beleid te synchroniseren.

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
>De configuraties van het beleid worden strikt afgedwongen en worden niet manueel met voeten getreden bij admin UI van de speler. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in de ***beleidsconfiguratie,*** bijvoorbeeld, als u handconfiguratie voor reboot programma wilt toestaan, specificeer niet de sleutel ***rebootSchedule*** in de beleidsconfiguratie.
