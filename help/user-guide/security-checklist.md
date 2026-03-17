---
title: Beveiligingscontrolelijst
description: Meer informatie over de belangrijkste beveiligingsgebieden van AEM Screens met een checklist met vragen en overwegingen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
source-git-commit: ad8509deaff9f90df5f6b50947f587a74e420661
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# AEM Screens Security Checklist {#security-checklist}

Op de pagina met de AEM Screens-beveiligingscontrolelijst worden de belangrijkste beveiligingsgebieden beschreven met een checklist met vragen en overwegingen.

## Checklist-tabel {#checklist-table}

| **Gebied van de Veiligheid** | **Checklist** | **ja/Neen/NA** |
|---|---|---|
| **de updates van de Software van AEM en van Screens** | **a.** *Is het nieuwste Adobe Experience Manager (AEM) service pack toegepast?* <br>**b.** *Is het nieuwste AEM Screens Feature Pack toegepast?* <br>**c.** *Gebruikt u de recentste beschikbare software van de Speler van AEM Screens van [ de Downloads van de Speler van AEM Screens ](https://download.macromedia.com/screens/)?* | |
| **Fysieke Veiligheid** | **a.** *Hebt u alle onnodige poorten uitgeschakeld?* <br>**b.** *Hebt u bekabeling en hardware beveiligd?* <br>**c.** *Gebruikt u om het even welke containers indien van toepassing?* | |
| **Veiligheid van het Netwerk** | **a.** *Gebruikt u geïsoleerde subnet voor uw ondertekeningsapparaten?* <br>**b.** *Staat geïsoleerde subnet toegang tot de vereiste eindpunten met inbegrip van AEM, Adobe Analytics, of andere vereiste diensten toe?* <br>**c.** *Hebt u uw Wi-Fi beveiligd met best practices op bedrijfsgebied?* <br>**d.** *Als het gebruiken van gesynchroniseerde playback, hebt u TCP 24503 voor WebSocket slechts op de primaire apparaten toegestaan?* <br>**e.** *Hebt u de waaier van IP adressen van de spelerapparaten zodat slechts de erkende apparaten tot de registratiedienst op de auteursinstantie kunnen toegang hebben?* | |
| **de Veiligheid van het Werkende Systeem** | **a.** *Hebt u een upgrade uitgevoerd naar de nieuwste versie van het besturingssysteem en hebt u alle vereiste beveiligingspatches toegepast?* <br>**b.** *Hebt u alle overbodige services uitgeschakeld en overbodige toepassingen verwijderd?* <br>**c.** *Hebt u het apparaat in apparatenbeheer ingeschreven om ondernemingsbeleid af te dwingen?* <br>**d.** *Hebt u het apparaat vergrendeld op één toepassings (speler) kiosk?* <br>**e.** *Hebt u een StandaardWerkende Procedures (SOP) op zijn plaats om OS veiligheidsupdates in tijd te installeren?*<br>**f.***Hebt u de veiligheids beste praktijken voor het werkende systeem in gebruik zoals anti-malwaresoftware, niet-administratieve gebruiker gevolgd?* | |
| **de Veiligheid van de Toepassing** | **a.** *Hebt u Admin UI, de Schakelaar van het Kanaal, en de UI van de Activiteit voor productie onbruikbaar gemaakt?* <br>**b.** *Hebt u het logniveau voor productie geminimaliseerd?* <br>**c.** *Gebruikt u https om verbinding te maken met AEM?* <br>**d.** *Gebruikt u een CA-ondertekend certificaat of een ondernemingPKI? (niet zelf-ondertekende certificaten)*<br>**e.***Gebruikt u TLS en niet SSL v3?*<br>**f.** *Bevestigt u het registratietoken op het apparaat en AEM wanneer het registreren?*<br> **g.** *Hebt u de gegevens in gebruik geclassificeerd en dat geen PII of PHI op het apparaat bestaat?*<br> **h.** *Hebt u de gegevens in gebruik geclassificeerd en dat er geen persoonlijk identificeerbare informatie (PII) of beschermde gezondheidsinformatie (PHI) op het apparaat bestaat?*<br> **i.** *Hebt u controle e-mail gevormd? Hebt u een SOP op zijn plaats voor het antwoorden aan controle e-mail en het behandelen van non-pingende apparaten?* | |
| **Controle van de Toegang** | **a.** *Hebt u een op rol-Gebaseerd Toegangsbeheer (RBAC) geïdentificeerd en binnen beheerd?* <br>**b.** *Hebt u het beginsel van minste voorrecht in het verlenen van toegang tot auteurs, beheerders, en spelers gebruikend beste praktijken van Adobe gevolgd?* | |

### Beveiligingscontrolelijst downloaden {#download-checklist}

Om de veiligheidscontrolelijst van AEM Screens te downloaden, klik [ hier ](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
