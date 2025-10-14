---
title: Beveiligingscontrolelijst
description: Meer informatie over de belangrijkste beveiligingsgebieden van AEM Screens met een checklist met vragen en overwegingen.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
source-git-commit: dcaaa1c7ab0a55cecce70f593ed4fded8468130b
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# AEM Screens Security Checklist {#security-checklist}

Op de pagina met de AEM Screens-beveiligingscontrolelijst worden de belangrijkste beveiligingsgebieden beschreven met een checklist met vragen en overwegingen.

## Checklist-tabel {#checklist-table}

| **Gebied van de Veiligheid** | **Checklist** | **ja/Neen/NA** |
|---|---|---|
| **de updates van de Software van AEM en van Screens** | **a.** *Is het recentste de dienstpak van Adobe Experience Manager (AEM) toegepast?* <br>**b.** *Is het recentste Pak van de Eigenschap van AEM Screens toegepast?* <br>**c.** *Gebruikt u de recentste beschikbare software van de Speler van AEM Screens van [&#x200B; de Downloads van de Speler van AEM Screens &#x200B;](https://download.macromedia.com/screens/)?* |
| **Fysieke Veiligheid** | **a.** *hebt u alle onnodige havens onbruikbaar gemaakt?* <br>**b.** *hebt u aanleg van kabelnetten en hardware beveiligd?* <br>**c.** *Gebruikt u om het even welke containers indien van toepassing?* |
| **Veiligheid van het Netwerk** | **a.** *Gebruikt u geïsoleerde subnet voor uw ondertekeningsapparaten?* <br>**b.** *verleent geïsoleerde subnet toegang tot de vereiste eindpunten met inbegrip van AEM, Adobe Analytics, of andere vereiste diensten?* <br>**c.** *hebt u uw WiFi gebruikend ondernemings beste praktijken beveiligd?* <br>**d.** *Als het gebruiken van gesynchroniseerde playback, hebt u TCP 24503 voor WebSocket slechts op de primaire apparaten toegestaan?* <br>**e.** *hebt u de waaier van IP adressen van de spelerapparaten opengemaakt zodat slechts kunnen de erkende apparaten tot de registratiedienst op de auteursinstantie toegang hebben?* |
| **de Veiligheid van het Werkende Systeem** | **a.** *Hebt u aan de recentste versie van het werkende systeem bevorderd en alle noodzakelijke veiligheidspatches toegepast?* <br>**b.** *hebt u alle onnodige diensten onbruikbaar gemaakt en onnodige toepassingen verwijderd?* <br>**c.** *hebt u het apparaat in apparatenbeheer ingeschreven om ondernemingsbeleid af te dwingen?* <br>**d.** *hebt u onderaan het apparaat aan één enkele toepassing (speler) kiosk vergrendeld?* <br>**e.** *hebt u een Standaard Werkende Procedures (SOP) op zijn plaats om OS veiligheidsupdates in tijd te installeren?*<br>**f.*** hebt u de veiligheid beste praktijken voor het werkende systeem in gebruik zoals anti-malware software, niet-administratieve gebruiker gevolgd?* |
| **de Veiligheid van de Toepassing** | **a.** *hebt u Admin UI, de Schakelaar van het Kanaal, en Activiteit UI voor productie onbruikbaar gemaakt?* <br>**b.** *hebt u het logboekniveau voor productie geminimaliseerd?* <br>**c.** *Gebruikt u https voor het verbinden met AEM?* <br>**d.** *Gebruikt u een CA-ondertekend certificaat of een ondernemingPKI? (niet zelf-ondertekende certificaten)*<br>**e.*** gebruikt u TLS en niet SSL v3?*<br>**f.** *Bevestigt u het registratietoken op het apparaat en AEM wanneer het registreren?*<br> **g.** *hebt u de gegevens in gebruik geclassificeerd en dat geen PII of PHI op het apparaat bestaat?*<br> **h.** *hebt u de gegevens in gebruik geclassificeerd en dat geen Persoonlijk Identificeerbare Informatie (PII) of Beschermde Informatie van de Gezondheid (PHI) op het apparaat bestaat?*<br> **i.** *hebt u controle e-mail gevormd? Hebt u een SOP op zijn plaats voor het antwoorden aan controle e-mail en het behandelen van non-pingende apparaten?* |
| **Controle van de Toegang** | **a.** *hebt u een Op rol-Gebaseerd Controle van de Toegang (RBAC) geïdentificeerd en binnen beheerd?* <br>**b.** *hebt u het beginsel van minste voorrecht gevolgd in het verlenen van toegang tot auteurs, beheerders, en spelers die beste praktijken van Adobe gebruiken?* |

### Beveiligingscontrolelijst downloaden {#download-checklist}

Om de veiligheidscontrolelijst van AEM Screens te downloaden, klik [&#x200B; hier &#x200B;](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
