---
title: Screens Replication-agents configureren
description: Leer hoe u Screens Replication Agents configureert.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
source-git-commit: cdff56f0807f6d5fea4a4b1d545aecb1e80245bb
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---

# Screens Replication Agents configureren {#configuring-screens-replication-agent}

In de volgende pagina wordt beschreven hoe u Screens Replication Agents configureert.

## Doelstelling {#objective}

De Agent van de Replicatie van Screens is verantwoordelijk voor het brengen van bevelsgegevens zoals *gebruiker*, *wachtwoord*, *rebootSchedule*, *maxNumberOfLogFilesToKeep*, en veel meer dergelijke waarden van publiceren aan auteur. Het is essentieel om deze agent te vormen zodat de auteur het apparaat kan tonen pingelt.

>[!NOTE]
>Meer over de Agenten van de Replicatie van Screens leren, zie {de Agenten en Bevelen van de Replicatie van 0} Screens [&#128279;](https://experienceleague.adobe.com/nl/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview#screens-replication-agents-and-commands).

Voltooi beide secties als u de configuratie voor de Agent van de Replicatie van Screens wilt voltooien:

1. [Gebruikers inschakelen en het wachtwoord bijwerken](#enable-users)
1. [Instellingen bijwerken voor Screens Replication Agent](#replicate-agent)

## Gebruikers inschakelen en het wachtwoord bijwerken {#enable-users}

Voer de onderstaande stappen uit om gebruikers in te schakelen en het wachtwoord voor `screens-receiver-user` bij te werken:

>[!NOTE]
>Om veiligheidsredenen is het raadzaam het beheerderswachtwoord voor `screens-receiver-user` niet te gebruiken.

1. Navigeer naar de instantie van AEM auteur.

1. Klik hulpmiddelen > **Veiligheid** > **Gebruikers**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Zoeken naar **`screens-receiver-user`** .

1. Klik **`screens-receiver-user`** en klik **toelaten** van de actiebar.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klik **O.K.** om te bevestigen.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Wanneer u de gebruiker hebt toegelaten, ziet u **`screens-receiver-user`** als **Toegelaten** onder het **4&rbrace; gebied van de Status &lbrace;.**

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Klik **`screens-receiver-user`** en klik **Eigenschappen** van de actiebar.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klik **Wachtwoord van de Verandering** onder **montages van de Rekening** van het **Details** lusje, zoals aangetoond in hieronder cijfer.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Ga een nieuw wachtwoord in het **de dialoogvakje van het Wachtwoord van de Verandering** in en klik **sparen**.

   >[!NOTE]
   >Ga het bestaande admin gebruikerswachtwoord op **in Uw Wachtwoord** gebied.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klik **sparen &amp; Sluiten**.

1. Klik **`screens-receiver-user`** en klik **activeren** van de actiebar.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klik **O.K.** om te bevestigen.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Klik **`screens-receiver-user`** en klik **onbruikbaar maken** van de actiebar.

   >[!IMPORTANT]
   > Als u **`screens-receiver-user`** uitschakelt, wordt alleen deze gebruiker uitgeschakeld in de instantie Authoring en blijven alle gebruikers in de instantie Publishing actief. Klik niet **Deactivate** van de actiebar, aangezien het deactiveren de gebruiker uit de het Publiceren instanties ook verwijdert.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klik **O.K.** om te bevestigen.

## Instellingen bijwerken voor Screens Replication Agent {#replicate-agent}

Volg de onderstaande sectie om de instellingen in de AEM Screens Replication Agent bij te werken:

>[!IMPORTANT]
>Voer de volgende stappen uit voor ALLE bestaande AEM Screens Replication Agents.

1. Navigeer naar de AEM.
1. Klik hulpmiddelen > **Plaatsing** > **Replicatie**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klik **Agenten op auteur**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Zoek naar alle Medewerkers van de Replicatie van AEM Screens op auteur en klik de verbinding, zoals aangetoond in het hieronder cijfer.

   >[!NOTE]
   >Zoeken naar alle AEM Screens Replication Agents. De naam van de Agent van de Replicatie van Screens omvat de brief **S** in de titel.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klik **uitgeven**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Controle **Toegelaten** van de **Montages** tabel.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigeer aan **Vervoer** lusje van het **de dialoogvakje van de Montages van de Agent** en werk de **Gebruiker** aan **`screens-receiver-user`** bij en ga het zelfde wachtwoord in dat u vóór in stap (8) van [ toelatend Gebruikers plaatst en het Wachtwoord ](#enable-users) bijwerkt.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klik **OK**.

1. Nadat u de voorafgaande stappen voltooit, klik **Verbinding van de Test** om de verbinding te verifiëren.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Als de verificatie van de verbinding is gelukt, hebt u de configuratie van de Screens Replication Agent voltooid.
