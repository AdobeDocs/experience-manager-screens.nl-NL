---
title: ACLs van de vestiging
description: Leer hoe te om projecten te scheiden gebruikend ACLs zodat elk individu of team hun eigen project behandelt.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: b40bcc9f-307c-422c-8abb-5c15965772d4
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# ACLs van de vestiging {#setting-up-acls}

De volgende sectie verklaart hoe te om projecten te segregeren gebruikend ACLs zodat elk individu of team hun eigen project behandelt.

Als AEM beheerder, wilt u ervoor zorgen dat de teamleden van een project zich niet in andere projecten mengen. Elke gebruiker wordt toegewezen specifieke rollen zoals per projectvereisten.

## Machtigingen instellen {#setting-up-permissions}

De volgende stappen vatten de procedure voor vestiging ACLs voor een project samen:

1. Aanmelden om te AEM en naar **Gereedschappen** > **Beveiliging**.

   ![screen_shot_2018-02-16at10156pm](assets/screen_shot_2018-02-16at10156pm.png)

1. Klikken **Groepen** en voer een id in (bijvoorbeeld Acme).

   U kunt ook deze koppeling gebruiken, `http://localhost:4502/libs/granite/security/content/groupadmin.html`.

   Klik op Volgende **Opslaan**.

   ![screen_shot_2018-02-16at12648pm](assets/screen_shot_2018-02-16at12648pm.png)

1. Klikken **Medewerkers** in de lijst en dubbelklik erop.

   ![screen_shot_2018-02-18at33938pm](assets/screen_shot_2018-02-18at33938pm.png)

1. Voeg de **Acme** (project dat u hebt gemaakt) naar **Leden toevoegen aan de groep**. Klikken **Opslaan**.

   ![screen_shot_2018-02-18at35630pm](assets/screen_shot_2018-02-18at35630pm.png)

   >[!NOTE]
   >
   >Als u projectteamleden spelers wilt registreren (wat het creëren van een gebruiker voor elke speler impliceert) zoek de groep gebruiker-beheerders en voeg de ACME groep aan gebruiker-beheerders toe

1. Voeg alle gebruikers toe die aan de **Acme** Project aan de **Acme** groep.

   ![screen_shot_2018-02-18at41320pm](assets/screen_shot_2018-02-18at41320pm.png)

1. De machtigingen voor de groep instellen **Acme** gebruiken `(http://localhost:4502/useradmin)`.

   Klik op de groep **Acme** en klik op de knop **machtigingen**.

   ![screen_shot_2018-02-18at41534pm](assets/screen_shot_2018-02-18at41534pm.png)

### Machtigingen {#permissions}

De volgende lijst vat de weg met de toestemmingen op het projectniveau samen:

| **Pad** | **Machtiging** | **Beschrijving** |
|---|---|---|
| `/apps/<project>` | LEZEN | Indien van toepassing toegang verlenen tot projectbestanden. |
| `/content/dam/<project>` | ALLES | Toegang bieden tot de opslag van de projectmiddelen, zoals afbeeldingen of video in DAM. |
| `/content/screens/<project>` | ALLES | Verwijdert toegang tot alle andere projecten onder /content/screens. |
| `/content/screens/svc` | LEZEN | Toegang verlenen tot de registratieservice. |
| `/libs/screens` | LEZEN | Toegang tot DCC bieden. |
| `/var/contentsync/content/screens/` | ALLES | Help u offline inhoud voor het project bij te werken. |

>[!NOTE]
>
>Soms kunt u auteurfuncties (zoals het beheren van activa en het creëren van kanalen) van adminfuncties (zoals het registreren van spelers) scheiden. In zulk een scenario, creeer twee groepen en voeg de auteursgroep aan contribuanten en de admingroep aan zowel auteurs als gebruiker-beheerders toe.

### Groepen maken {#creating-groups}

Het creëren van een project zou standaardgebruikersgroepen met een basisreeks toegewezen toestemmingen ook moeten tot stand brengen. Breid de toestemmingen tot de typische rollen uit die in AEM Screens worden bepaald.

U kunt bijvoorbeeld de volgende projectspecifieke groepen maken:

* Scherm Projectbeheerders
* Schert Projectoperators (registreer spelers en beheer locaties en apparaten)
* De Gebruikers van het Project van schermen (werk met kanalen, programma&#39;s, en kanaaltaken)

De volgende tabel geeft een overzicht van de groepen met een beschrijving en machtigingen voor een AEM Screens-project:

<table>
 <tbody>
  <tr>
   <td><strong>Groepsnaam</strong></td>
   <td><strong>Beschrijving</strong></td>
   <td><strong>Machtigingen</strong></td>
  </tr>
  <tr>
   <td>Schermbeheerders<br /> <em><code>screens-admins</code></em></td>
   <td>Toegang op beheerniveau voor AEM Screens-mogelijkheden</td>
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
   <td>Schermgebruikers<br /> <em><code>screens-users</code></em></td>
   <td>Kanalen en schema's maken en bijwerken en toewijzen aan locaties in AEM Screens</td>
   <td>
    <ul>
     <li>Lid van contribuanten</li>
     <li><code>&lt;project&gt; /content/screens</code></li>
     <li><code>&lt;project&gt; /content/dam</code></li>
     <li><code>&lt;project&gt; /content/experience-fragments</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Schermoperatoren<br /> <em><code>screens-operators</code></em></td>
   <td>Locatiestructuur maken en bijwerken en spelers registreren in AEM Screens</td>
   <td>
    <ul>
     <li>Lid van contribuanten</li>
     <li><code>jcr:all /home/users/screens</code></li>
     <li><code>jcr:all /home/groups/screens</code></li>
     <li><code>&lt;project&gt; /content/screens</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Schermspelers<br /> <em><code>screens-&lt;project&gt;-devices</code></em></td>
   <td>Alle spelers en alle spelers/apparaten zijn automatisch lid van de contribuanten.</td>
   <td><p> Lid van contribuanten</p> </td>
  </tr>
 </tbody>
</table>
