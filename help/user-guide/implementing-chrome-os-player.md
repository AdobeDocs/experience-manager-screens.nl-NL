---
title: Chrome OS Player implementeren
description: Meer informatie over de implementatie van de Chrome OS Player via de Chrome Management Console.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# Chrome OS Player implementeren {#implementing-chrome-os-player}

In deze sectie wordt beschreven hoe u de Chrome OS Player implementeert met de Chrome Management Console.

## Chrome Management Console gebruiken {#using-chrome-management-console}

Voer de onderstaande stappen uit om de Chrome-beheerconsole in te stellen:

1. Registreer u voor de Chrome Management Console. U moet een licentie aanvragen voor Chrome Management Console. Contact [&#x200B; de Steun van Google &#x200B;](https://support.google.com/chrome/a/answer/1375678?hl=en&ref_topic=2935995) om het apparatenmontages van Chrome voor meer informatie te beheren.
1. Schrijf uw Chrome OS-apparaat in het domein en wacht 15 minuten tot het apparaat gesynchroniseerd is met de Chrome Management Console. Meer over het inschrijven van het apparaat van Chrome leren, klik [&#x200B; hier &#x200B;](https://support.google.com/chrome/a/answer/1360534?hl=en).
1. De Chrome Player is beschikbaar in de Chrome Web Store.

>[!NOTE]
>
>Een oplossing voor apparaatbeheer, zoals de Chrome Management Console, wordt aanbevolen voor de implementatie en het beheer van Chrome OS-apparaten. Hoewel dit document implementatie voor Chrome Management Console biedt, zijn er andere leveranciers die beweren soortgelijke functionaliteit te bieden. Neem contact op met de leverancier van de software voor apparaatbeheer.

## Naam van Chrome OS Player {#name-chrome}

U kunt een gebruikersvriendelijke apparaatnaam aan uw Chrome Player toewijzen en zo de toegewezen apparaatnaam naar Adobe Experience Manager (AEM) verzenden. Met deze functie kunt u niet alleen uw Chrome Player een naam geven, maar kunt u ook eenvoudig de juiste inhoud toewijzen.

>[!NOTE]
>U kunt de Player-naam alleen vóór de registratie kiezen. Nadat de Speler wordt geregistreerd, kan de naam van de Speler niet meer worden veranderd.

Voer de onderstaande stappen uit om de naam in Chrome Player te configureren:

1. U kunt desgewenst audio-video-integrators of IT-beheerders toestaan de id en locatie van het element in te stellen als onderdeel van de inschrijving voor de onderneming.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome1.png)

1. U krijgt de opties te zien wanneer u het apparaat kunt inschrijven.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. U kunt de id van het element instellen als onderdeel van de inschrijving op een bedrijf en in de Chrome Management Console.

   ![afbeelding](/help/user-guide/assets/chrome-device/chrome3.png)

   >[!NOTE]
   >Chrome Players moet in ondernemingsinschrijving worden ingeschreven en de Speler van Chrome moet door de Console van het Beheer van Chrome worden opgesteld, anders keert identiteitskaart van Activa leeg terug (bijvoorbeeld, Chrome als uitbreiding). De apparaatnaam wordt alleen opgenomen op het moment van registratie. Toekomstige veranderingen worden niet opgepikt door Adobe Experience Manager (AEM).

### Modus Kiosk inschakelen {#enabling-kiosk-mode}

Voer de onderstaande stappen uit om de modus Kiosk in te schakelen:

1. Meld u aan bij de Chrome Developer Console.

   ![&#x200B; screen_shot_2017-12-08at20303pm &#x200B;](assets/screen_shot_2017-12-08at20303pm.png)

1. Blader naar **Beheer van het Apparaat** > **Chrome Beheer** > **Montages van het Apparaat**.
1. De rol neer aan **Montages van Kiosk** en klikt **de Toepassingen van Kiosk beheren**.

   ![&#x200B; kiosk &#x200B;](assets/kiosk.png)

1. Klik op AEM Screens Player in de Chrome Web Store.

   >[!NOTE]
   >
   >Het kan ongeveer 15 minuten duren voordat een onlangs gepubliceerde app in deze lijst wordt weergegeven.

1. Klik **Speler van AEM Screens** van **AutoLounch Kiosk App** dropdown.

   Het kan een paar notulen afhankelijk van het netwerk voor de veranderingen duren om van kracht te worden. Het wordt aanbevolen opnieuw op te starten.

#### De status van extern apparaat controleren {#checking-remote-device-status}

1. Meld u aan bij de Chrome Developer Console.
1. Blader naar **Apparaatbeheer** > **de Apparaten van Chrome** en klik het apparaat u wilt controleren.
1. Klik **Activiteit van het Systeem en het oplossen van problemen**.
1. Controleer **Reboot Apparaat** en **het Scherm vangen** eigenschappen van het apparaat. U kunt ook de status en gezondheidsgegevens van het apparaat controleren.

>[!NOTE]
>
>Deze instellingen kunnen enkele minuten nadat het apparaat is ingeschreven, worden ingeschakeld. Elke optie kan na verloop van tijd worden ingeschakeld.

### Externe configuratie van Chrome OS Players configureren {#configuring-remote-configuration-of-chrome-os-players}

De AEM Screens Player is een toepassing die geschikt is voor Kiosk en waarmee ook configuratie van extern beleid voor Chrome OS-spelers is ingeschakeld.

Voer de onderstaande stappen uit om de verschillende opties van de speler te configureren:

1. Meld u aan bij de Chrome Management Console.
1. Klik **Beheer van het Apparaat** > **het Beheer van Chrome** > **App Beheer**. De AEM Screens Player wordt in de lijst weergegeven.
1. Klik de toepassing **Speler van AEM Screens**.
1. Klik **montages van Kiosk** en klik uw org (*als het gebruiken van een testmilieu*).
1. Klik **uploadt configuratiedossier** en uploadt het configuratiebeleid (*JSon dossier*).
1. Klik **sparen**. Start het apparaat opnieuw op zodat u het beleid kunt synchroniseren.

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

| **Naam van het Beleid** | **Doel** |
|---|---|
| server | De URL naar de Adobe Experience Manager-server (AEM). |
| registrationKey | Wordt gebruikt voor de bulkregistratie van apparaten met behulp van een vooraf gedeelde sleutel. |
| resolutie | De resolutie van het apparaat. |
| rebootSchedule | Het programma om de speler opnieuw op te starten. |
| enableAdminUI | Schakel de interface van Admin in om het apparaat op de site te configureren. Ingesteld op false zodra deze volledig is geconfigureerd en in productie is. |
| enableOSD | Schakel de interface van de kanaalschakelaar voor gebruikers in om naar een ander kanaal op het apparaat te gaan. Overweeg het plaatsen van het aan vals zodra het volledig en in productie wordt gevormd. |
| enableActivityUI | Schakel deze optie in zodat u de voortgang van activiteiten, zoals downloaden en synchroniseren, kunt weergeven. Laat voor het oplossen van problemen toe en maak onbruikbaar zodra het volledig en in productie wordt gevormd. |
| cloudMode | Stel dit in op true als u wilt dat de Chrome Player verbinding maakt met Screens as a Cloud Service. Ingesteld op false om verbinding te maken met AMS of on-prem AEM. |
| cloudToken | Registertoken voor Screens as a Cloud Service. |

>[!NOTE]
>
>De beleidsconfiguraties worden strikt gehandhaafd en de Admin UI van de speler treedt manueel niet met voeten. Om handspelerconfiguratie voor een bepaald beleid toe te staan, specificeer niet het beleid in de ***beleidsconfiguratie***. Bijvoorbeeld, als u handconfiguratie voor reboot programma wilt toestaan, specificeer niet de sleutel ***rebootSchedule*** in de beleidsconfiguratie.

### De afstandsbediening van Screens gebruiken {#using-remote-control}

AEM Screens biedt functionaliteit voor afstandsbediening. Leer meer over deze eigenschap hier: [&#x200B; de Verre Controle van Screens &#x200B;](implementing-remote-control.md)
