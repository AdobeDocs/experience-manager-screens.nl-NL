---
title: Beveiligingscontrolelijst
seo-title: Beveiligingscontrolelijst
description: De pagina beschrijft de lijst met beveiligingscontroles
seo-description: De pagina beschrijft de lijst met beveiligingscontroles
translation-type: tm+mt
source-git-commit: 16361c016251a0ce0c86175eb6ef09ffb3150415
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---


# Beveiligingscontrolelijst voor AEM-schermen  {#security-checklist}

Op de pagina AEM Screens Security Checklist worden de belangrijkste beveiligingsgebieden beschreven met een checklist met vragen en overwegingen.

## Checklist-tabel {#checklist-table}

| **Beveiligingsgebied** | **Checklist** | **Ja/Nee/NA** |
|---|---|---|
| **Updates van AEM- en schermsoftware** | ***a.*** *Is het nieuwste Adobe Experience Manager (AEM)-servicepakket toegepast?* <br>***b.****Is het nieuwste AEM Screens Feature Pack toegepast?*<br>***c.*** *Gebruikt u de nieuwste AEM Screens Player-software van[AEM Screens Player Downloads](https://download.macromedia.com/screens/)?* |
| **Fysieke beveiliging** | ***a.*** *Hebt u alle onnodige poorten uitgeschakeld?* <br>***b.****Hebt u bekabeling en hardware beveiligd?*<br>***c.*** *Gebruikt u, indien van toepassing, containers?* |
| **Netwerkbeveiliging** | ***a.*** *Gebruikt u geïsoleerde subnet voor uw ondertekeningsapparaten?* <br>***b.****Staat geïsoleerde subnet toegang tot de vereiste eindpunten met inbegrip van AEM, de Analytics van Adobe of andere vereiste diensten toe?*<br>***c.*** *Hebt u uw Wi-Fi beveiligd met best practices op bedrijfsniveau?* <br>***d.****Als u gesynchroniseerd afspelen gebruikt, hebt u TCP 24503 voor WebSocket alleen toegestaan op het hoofdapparaat of de hoofdapparaten?*<br>***e.*** *Hebt u de waaier van IP waaiers van de spelerapparaten zodat slechts de erkende apparaten tot de registratiedienst op auteur kunnen toegang hebben?* |
| **Beveiliging besturingssysteem** | ***a.*** *Hebt u een upgrade uitgevoerd naar de nieuwste versie van het besturingssysteem en hebt u alle vereiste beveiligingspatches toegepast?* <br>***b.****Hebt u alle onnodige services uitgeschakeld en overbodige toepassingen verwijderd?*<br>***c.*** *Hebt u het apparaat in apparatenbeheer ingeschreven om ondernemingsbeleid af te dwingen?* <br>***d.****Hebt u het apparaat vergrendeld op één toepassings (speler) kiosk?*<br>***e.*** *Hebt u een Standard Operating Procedures (SOP) voor het installeren van beveiligingsupdates van het besturingssysteem in de loop van de tijd?*<br>***f.****Hebt u de best practices op het gebied van beveiliging voor het gebruikte besturingssysteem gevolgd, zoals antimalwaresoftware, niet-administratieve gebruiker?* |
| **Toepassingsbeveiliging** | ***a.*** *Hebt u de interface van Admin UI, de Schakelaar van het Kanaal en de UI van de Activiteit voor productie onbruikbaar gemaakt?* <br>***b.****Hebt u het logniveau voor productie geminimaliseerd?*<br>***c.*** *Gebruikt u https om verbinding te maken met AEM?* <br>***d.****Gebruikt u een CA ondertekend certificaat of een ondernemingPKI? (geen zelfondertekende certificaten)*<br>***e.**** Gebruikt u TLS en niet SSL v3?*<br>*** f.****Bevestigt u het registratietoken op apparaat en AEM wanneer het registreren?*<br> ***g.*** *Hebt u de gegevens geclassificeerd die worden gebruikt en dat er geen PII of PHI op apparaat bestaat?*<br> ***h.*** *Hebt u de gegevens geclassificeerd die worden gebruikt en dat er geen persoonlijk identificeerbare informatie (PII) of beschermde gezondheidsinformatie (PHI) op het apparaat bestaat?*<br> ***i.*** *Hebt u controle e-mail gevormd, en hebt u een SOP op zijn plaats voor het antwoorden aan controlemails en het behandelen van niet pingende apparaten?* |
| **Toegangsbeheer** | ***a.*** *Hebt u een Rol Gebaseerde Controle van de Toegang (RBAC) geïdentificeerd en binnen beheerd?* <br>***b.****Hebt u het beginsel van het minst bevoorrecht in het verlenen van toegang tot auteurs, beheerders en spelers gebruikend beste praktijken van Adobe gevolgd?* |

### Beveiligingschecklist downloaden {#download-checklist}

Klik [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf)om de AEM Screens Security Checklist te downloaden.