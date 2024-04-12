---
title: Beveiligingscontrolelijst
description: Meer informatie over de belangrijkste beveiligingsgebieden van AEM Screens met een checklist met vragen en overwegingen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
source-git-commit: ba5327077e4a2d30cc7b77f02123da5a240c67ae
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# AEM Screens Security Checklist  {#security-checklist}

Op de pagina AEM Screens Security Checklist worden de belangrijkste beveiligingsgebieden beschreven met een checklist met vragen en overwegingen.

## Checklist-tabel {#checklist-table}

| **Beveiligingsgebied** | **Checklist** | **Ja/Nee/NA** |
|---|---|---|
| **Software-updates voor AEM en schermen** | **a.** *Is het laatste Adobe Experience Manager (AEM) servicepakket toegepast?* <br>**b.** *Is het nieuwste AEM Screens Feature Pack toegepast?* <br>**c.** *Gebruikt u de nieuwste AEM Screens Player-software van [Downloads voor AEM Screens Player](https://download.macromedia.com/screens/)?* |
| **Fysieke beveiliging** | **a.** *Hebt u alle onnodige poorten uitgeschakeld?* <br>**b.** *Hebt u bekabeling en hardware beveiligd?* <br>**c.** *Gebruikt u, indien van toepassing, containers?* |
| **Netwerkbeveiliging** | **a.** *Gebruikt u geïsoleerde subnet voor uw ondertekeningsapparaten?* <br>**b.** *Staat geïsoleerde subnet toegang tot de vereiste eindpunten met inbegrip van AEM, Adobe Analytics, of andere vereiste diensten toe?* <br>**c.** *Hebt u uw Wi-Fi beveiligd met best practices op bedrijfsniveau?* <br>**d.** *Als het gebruiken van gesynchroniseerde playback hebt u TCP 24503 voor WebSocket slechts op de primaire apparaten toegestaan?* <br>**e.** *Hebt u de bandbreedte van IP adressen van de spelerapparaten zodat slechts kunnen de erkende apparaten tot de registratiedienst op de auteursinstantie toegang hebben?* |
| **Beveiliging besturingssysteem** | **a.** *Hebt u een upgrade uitgevoerd naar de nieuwste versie van het besturingssysteem en hebt u alle vereiste beveiligingspatches toegepast?* <br>**b.** *Hebt u alle onnodige services uitgeschakeld en overbodige toepassingen verwijderd?* <br>**c.** *Hebt u het apparaat in apparatenbeheer ingeschreven om ondernemingsbeleid af te dwingen?* <br>**d.** *Hebt u het apparaat vergrendeld op één toepassings (speler) kiosk?* <br>**e.** *Hebt u een Standard Operating Procedures (SOP) voor het installeren van beveiligingsupdates van het besturingssysteem in de loop der tijd?*<br>**f.***Hebt u de best practices op het gebied van beveiliging voor het gebruikte besturingssysteem gevolgd, zoals antimalwaresoftware, niet-administratieve gebruiker?* |
| **Toepassingsbeveiliging** | **a.** *Hebt u Admin UI, de Schakelaar van het Kanaal, en de UI van de Activiteit voor productie onbruikbaar gemaakt?* <br>**b.** *Hebt u het logniveau voor productie geminimaliseerd?* <br>**c.** *Gebruikt u https om verbinding te maken met AEM?* <br>**d.** *Gebruikt u een CA-ondertekend certificaat of een ondernemingPKI? (geen zelfondertekende certificaten)*<br>**e.***Gebruikt u TLS en niet SSL v3?*<br>**f.** *Bevestigt u het registratietoken op apparaat en AEM wanneer het registreren?*<br> **g.** *Hebt u de gegevens geclassificeerd die worden gebruikt en dat er geen PII of PHI op apparaat bestaat?*<br> **h.** *Hebt u de gegevens geclassificeerd die worden gebruikt en dat er geen persoonlijk identificeerbare informatie (PII) of beschermde gezondheidsinformatie (PHI) op het apparaat bestaat?*<br> **i.** *Hebt u controle e-mail gevormd, en hebt u een SOP op zijn plaats voor het antwoorden aan controlemails en het behandelen van niet pingende apparaten?* |
| **Toegangsbeheer** | **a.** *Hebt u een Op rol-Gebaseerd Toegangsbeheer (RBAC) geïdentificeerd en binnen beheerd?* <br>**b.** *Hebt u het beginsel van het minste voorrecht in het verlenen van toegang tot auteurs, beheerders, en spelers gebruikend beste praktijken van Adobe gevolgd?* |

### Beveiligingschecklist downloaden {#download-checklist}

Klik op [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
