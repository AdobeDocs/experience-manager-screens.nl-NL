---
title: ACLs van de vestiging
seo-title: ACLs van de vestiging
description: Volg deze pagina leren hoe te om projecten te segregeren gebruikend ACLs zodat elk individu of team hun eigen project behandelt.
seo-description: Volg deze pagina leren hoe te om projecten te segregeren gebruikend ACLs zodat elk individu of team hun eigen project behandelt.
uuid: d5609bd9-3f13-4f11-ad4f-23c2ac3aa8fc
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 64e4d6ae-3fd3-41ec-84e1-cc2cac7b2519
translation-type: tm+mt
source-git-commit: ad7f18b99b45ed51f0393a0f608a75e5a5dfca30

---


# ACLs van de vestiging {#setting-up-acls}

De volgende sectie verklaart hoe te om projecten te segregeren gebruikend ACLs zodat elk individu of team hun eigen project behandelt.

Als beheerder AEM, wilt u ervoor zorgen dat de teamleden van een project zich niet in andere projecten mengen en elk van de gebruikers specifieke rollen zoals per projectvereisten worden toegewezen.

## Machtigingen instellen {#setting-up-permissions}

De volgende stappen vatten de procedure voor vestiging ACLs voor een project samen:

1. Meld u aan bij AEM en navigeer naar **Gereedschappen** > **Beveiliging**.

   ![screen_shot_2018-02-16at10156pm](assets/screen_shot_2018-02-16at10156pm.png)

1. Klik op **Groepen** en voer een id in (bijvoorbeeld Acme).

   U kunt ook deze koppeling gebruiken `http://localhost:4502/libs/granite/security/content/groupadmin.html`.

   Klik vervolgens op **Opslaan**.

   ![screen_shot_2018-02-16at12648pm](assets/screen_shot_2018-02-16at12648pm.png)

1. Selecteer **Medewerkers** in de lijst en dubbelklik erop.

   ![screen_shot_2018-02-18at33938pm](assets/screen_shot_2018-02-18at33938pm.png)

1. Voeg de **Acme** (project u) creeerde toe om Leden aan Groep **toe te** voegen. Click **Save**.

   ![screen_shot_2018-02-18at35630pm](assets/screen_shot_2018-02-18at35630pm.png)

   >[!NOTE]
   >
   >Als u projectteamleden spelers wilt registreren (wat het creëren van een gebruiker voor elke speler impliceert) zoek de groep gebruiker-beheerders en voeg de ACME groep aan gebruiker-beheerders toe

1. Voeg alle gebruikers die aan het Project van **Acme** aan de **Acme** groep zullen werken toe.

   ![screen_shot_2018-02-18at41320pm](assets/screen_shot_2018-02-18at41320pm.png)

1. Stel de machtigingen voor de groep **Acme** in met deze `(http://localhost:4502/useradmin)`.

   Selecteer de groep **Acme** en klik de **toestemmingen**.

   ![screen_shot_2018-02-18at41534pm](assets/screen_shot_2018-02-18at41534pm.png)

### Machtigingen {#permissions}

De volgende lijst vat de weg met de toestemmingen op het projectniveau samen:

| **Pad** | **Machtiging** | **Beschrijving** |
|---|---|---|
| `/apps/<project>` | LEZEN | Biedt toegang tot projectbestanden (indien van toepassing) |
| `/content/dam/<project>` | ALLES | Biedt toegang tot de projectelementen zoals afbeeldingen of video in DAM |
| `/content/screens/<project>` | ALLES | Verwijdert toegang tot alle andere projecten onder /content/screens |
| `/content/screens/svc` | LEZEN | Biedt toegang tot de registratieservice |
| `/libs/screens` | LEZEN | Biedt toegang tot DCC |
| `/var/contentsync/content/screens/` | ALLES | Hiermee kunt u offline inhoud voor het project bijwerken |

>[!NOTE]
>
>In sommige gevallen kunt u auteurfuncties (zoals het beheren van activa en het creëren van kanalen) van adminfuncties (zoals het registreren van spelers) scheiden. In zulk een scenario, creeer twee groepen en voeg de auteursgroep aan contribuanten en de admingroep aan zowel auteurs als gebruiker-beheerders toe.

### Groepen maken {#creating-groups}

Het creëren van een nieuw project zou standaardgebruikersgroepen met een basisreeks toegewezen toestemmingen ook moeten tot stand brengen. U zou de toestemmingen tot de typische rollen moeten uitbreiden wij voor Schermen AEM hebben.

U kunt bijvoorbeeld de volgende projectspecifieke groepen maken:

* Scherm Projectbeheerders
* Schert Projectoperators (registreer spelers en beheer locaties en apparaten)
* Schermen van de Gebruikers van het Project (werk met kanalen, programma&#39;s en kanaaltaken)

De volgende tabel geeft een overzicht van de groepen met een beschrijving en machtigingen voor een AEM Screens-project:

<table>
 <tbody>
  <tr>
   <td><strong>Groepsnaam</strong></td>
   <td><strong>Beschrijving</strong></td>
   <td><strong>Machtigingen</strong></td>
  </tr>
  <tr>
   <td>Schermbeheerders<br /> <em>schermbeheerders</em></td>
   <td>Toegang op beheerniveau voor AEM-rastermogelijkheden</td>
   <td>
    <ul>
     <li>Lid van contribuanten</li>
     <li>Lid van gebruikersbeheerders</li>
     <li>ALLE /content/screens</li>
     <li>ALLE /content/dam</li>
     <li>ALL /content/experience-fragments</li>
     <li>ALLE /etc/ontwerp/schermen</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Schermen gebruikers<br /> <em>schermgebruikers</em></td>
   <td>Kanalen en schema's maken en bijwerken en toewijzen aan locatie in AEM-schermen</td>
   <td>
    <ul>
     <li>Lid van contribuanten</li>
     <li>&lt;project&gt; /content/screens</li>
     <li>&lt;project&gt; /content/dam</li>
     <li>&lt;project&gt; /content/experience-fragments</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Schermoperatoren<br /> , <em>schermoperatoren</em></td>
   <td>Locatiestructuur maken en bijwerken en spelers registreren in AEM-schermen</td>
   <td>
    <ul>
     <li>Lid van contribuanten</li>
     <li>jcr:alle /home/users/screens</li>
     <li>jcr:alle /home/groups/screens</li>
     <li>&lt;project&gt; /content/screens</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Schermen Players<br /> <em>schermen-wij-kleinhandelsapparaten</em></td>
   <td>Hiermee worden alle spelers en alle spelers/apparaten automatisch gegroepeerd als leden van de contribuanten.</td>
   <td><p> Lid van contribuanten</p> </td>
  </tr>
 </tbody>
</table>
