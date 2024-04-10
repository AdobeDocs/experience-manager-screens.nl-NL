---
title: Apparaten voor schermreplicatie configureren
description: Leer over hoe te om de Agenten van de Replicatie van het Scherm te vormen.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
source-git-commit: 67560ae17646424985032c81f33c937c6eeb5957
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 3%

---

# Apparaten voor schermreplicatie configureren {#configuring-screens-replication-agent}

Deze volgende pagina beschrijft hoe te om de Agenten van de Replicatie van het Scherm te vormen.

## Doelstelling {#objective}

De agent van de Replicatie van het Scherm is verantwoordelijk voor het brengen van bevelgegevens zoals, *user*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep* en nog veel meer van dergelijke waarden, van publiceren naar auteur. Het is essentieel om dit te vormen zodat de auteur het apparaat kan tonen pingelen.

>[!NOTE]
>Voor meer informatie over de Agent van de Replicatie van het Scherm, zie [Screens Replication Agents and Commands](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview#screens-replication-agents-and-commands).

Voltooi beide secties als u de configuratie voor de Agent van de Replicatie van het Scherm wilt voltooien:

1. [Gebruikers inschakelen en het wachtwoord bijwerken](#enable-users)
1. [Instellingen bijwerken voor de agent voor schermreplicatie](#replicate-agent)

## Gebruikers inschakelen en het wachtwoord bijwerken {#enable-users}

Voer de onderstaande stappen uit om gebruikers in te schakelen en het wachtwoord voor `screens-receiver-user`:

>[!NOTE]
>Om veiligheidsredenen is het raadzaam het beheerderswachtwoord niet te gebruiken voor `screens-receiver-user`.

1. Navigeer naar de AEM Author-instantie.

1. Klik op Gereedschappen > **Beveiliging** > **Gebruikers**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Zoeken naar **`screens-receiver-user`**.

1. Selecteer de **`screens-receiver-user`** en klik op **Inschakelen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klikken **OK** ter bevestiging.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Wanneer u de gebruiker hebt ingeschakeld, ziet u de **`screens-receiver-user`** als **Ingeschakeld** onder de **Status** veld.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Selecteer de **`screens-receiver-user`** en klik op **Eigenschappen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klikken **Wachtwoord wijzigen** krachtens **Accountinstellingen** van de **Details** zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Voer een nieuw wachtwoord in het dialoogvenster **Wachtwoord wijzigen** en klik op **Opslaan**.

   >[!NOTE]
   >Voer het bestaande beheerderswachtwoord in **Uw wachtwoord** veld.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klikken **Opslaan en sluiten**.

1. Selecteer de **`screens-receiver-user`** en klik op **Activeren** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klikken **OK** ter bevestiging.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Selecteer de **`screens-receiver-user`** en klik op **Uitschakelen** in de actiebalk.

   >[!IMPORTANT]
   > Uitschakelen **`screens-receiver-user`** Hiermee wordt deze gebruiker alleen uitgeschakeld voor de instantie Authoring en blijven alle gebruikers in de instantie Publishing actief. Niet klikken **Deactiveren** als u de code deactiveert, wordt de gebruiker ook uit de publicatie-instanties verwijderd.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klikken **OK** ter bevestiging.

## Instellingen bijwerken voor de agent voor schermreplicatie {#replicate-agent}

Volg de onderstaande sectie om de instellingen in de AEM Screens Replication Agent bij te werken:

>[!IMPORTANT]
>Voer de volgende stappen uit voor ALLE bestaande AEM Screens-replicatiemiddelen.

1. Navigeer naar de AEM.
1. Klik op Gereedschappen > **Implementatie** > **Replicatie**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klikken **Medewerkers op auteur**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Zoek naar alle agenten van de Replicatie van AEM Screens op auteur en klik de verbinding, zoals aangetoond in het hieronder cijfer.

   >[!NOTE]
   >Zoeken naar alle AEM Screens Replication-agents. De naam van de agent voor schermreplicatie bevat de letter **S** in de titel.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klikken **Bewerken**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Controleren **Ingeschakeld** van de **Instellingen** tab.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigeren naar **Vervoer** van de **Instellingen agent** en werkt het dialoogvenster **Gebruiker** tot **`screens-receiver-user`** en voert u hetzelfde wachtwoord in dat u eerder hebt ingesteld in stap 8 van [Gebruikers inschakelen en het wachtwoord bijwerken](#enable-users).

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klikken **OK**.

1. Nadat u de voorgaande stappen hebt uitgevoerd, kunt u op **Verbinding testen** om de verbinding te verifiëren.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Als de verificatie van de verbinding is gelukt, hebt u de configuratie van de agent voor schermreplicatie voltooid.
