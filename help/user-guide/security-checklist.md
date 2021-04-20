---
title: Beveiligingscontrolelijst
seo-title: Beveiligingscontrolelijst
description: De pagina beschrijft de belangrijkste veiligheidsgebieden met een controlelijst van vragen en overwegingen.
seo-description: De pagina beschrijft de lijst met beveiligingscontroles
feature: Administering Screens
role: Administrator
level: Intermediate
translation-type: tm+mt
source-git-commit: 9d36c0ebc985b815ab41d3f3ef44baefa22db915
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---


# AEM Screens Security Checklist {#security-checklist}

Op de pagina AEM Screens Security Checklist worden de belangrijkste beveiligingsgebieden beschreven met een checklist met vragen en overwegingen.

## Checklist-tabel {#checklist-table}

| **Beveiligingsgebied** | **Checklist** | **Ja/Nee/NA** |
|---|---|---|
| **Software-updates voor AEM en schermen** | ***a.*** *Is het laatste Adobe Experience Manager (AEM) servicepakket toegepast?* <br>***b.***  *Is het nieuwste AEM Screens Feature Pack toegepast?* <br>***c.*** *Gebruikt u de nieuwste AEM Screens Player-software van  [AEM Screens Player-downloads](https://download.macromedia.com/screens/)?* |
| **Fysieke beveiliging** | ***a.*** *Hebt u alle onnodige poorten uitgeschakeld?* <br>***b.***  *Hebt u bekabeling en hardware beveiligd?* <br>***c.*** *Gebruikt u eventueel containers?* |
| **Netwerkbeveiliging** | ***a.*** *Gebruikt u geïsoleerde subnet voor uw ondertekeningsapparaten?* <br>***b.***  *Verleent geïsoleerde subnet toegang tot de vereiste eindpunten met inbegrip van AEM, Adobe Analytics of andere vereiste diensten?* <br>***c.*** *Hebt u uw Wi-Fi beveiligd met best practices voor bedrijven?* <br>***d.*** *Als u gesynchroniseerd afspelen gebruikt, hebt u TCP 24503 for WebSocket alleen toegestaan op het master apparaat of de  apparaten?* <br>***e.*** *Hebt u de blokkering van het bereik van IP-adressen van de spelerapparaten opgeheven zodat alleen geautoriseerde apparaten toegang hebben tot de registratieservice bij de auteur?* |
| **Beveiliging besturingssysteem** | ***a.*** *Hebt u een upgrade uitgevoerd naar de nieuwste versie van het besturingssysteem en hebt u alle vereiste beveiligingspatches toegepast?* <br>***b.*** *Hebt u alle onnodige services uitgeschakeld en overbodige toepassingen verwijderd?* <br>***c.*** *Hebt u het apparaat in apparatenbeheer ingeschreven om ondernemingsbeleid af te dwingen?* <br>***d.*** *Hebt u het apparaat vergrendeld op één toepassings (speler) kiosk?* <br>***e.*** *Hebt u een Standard Operating Procedures (SOP) voor het installeren van beveiligingsupdates van het besturingssysteem?*<br>***f.*** *Hebt u de best practices op het gebied van beveiliging voor het gebruikte besturingssysteem gevolgd, zoals antimalwaresoftware, niet-administratieve gebruiker?* |
| **Toepassingsbeveiliging** | ***a.*** *Hebt u de interface voor beheer, kanaalswitches en gebruikersinterface voor activiteiten uitgeschakeld voor productie?* <br>***b.*** *Hebt u het logniveau voor productie geminimaliseerd?* <br>***c.*** *Gebruikt u https om verbinding te maken met AEM?* <br>***d.*** *Gebruikt u een CA-ondertekend certificaat of een Enterprise-PKI? (geen zelfondertekende certificaten)*<br>***e.*** *Gebruikt u TLS en niet SSL v3?*<br>***f.*** *Valideert u de registratietoken op het apparaat en AEM tijdens de registratie?*<br> ***g.*** *Hebt u de gegevens geclassificeerd die worden gebruikt en dat er geen PII of PHI op het apparaat bestaat?*<br> ***h.*** *Hebt u de gebruikte gegevens geclassificeerd en hebt u vastgesteld dat er geen persoonlijk identificeerbare informatie (PII) of beschermde gezondheidsinformatie (PHI) op het apparaat aanwezig is?*<br> ***i.*** *Hebt u controle-e-mails geconfigureerd en beschikt u over een SOP om te reageren op het controleren van e-mails en het afhandelen van niet-pingapparaten?* |
| **Toegangsbeheer** | ***a.*** *Hebt u een rol Gebaseerd Toegangsbeheer (RBAC) geïdentificeerd en binnen beheerd?* <br>***b.*** *Hebt u het beginsel van het minst bevoorrecht in het verlenen van toegang tot auteurs, beheerders en spelers gebruikend beste praktijken van Adobe gevolgd?* |

### Beveiligingschecklist {#download-checklist} downloaden

Als u de AEM Screens Security Checklist wilt downloaden, klikt u [hier](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).