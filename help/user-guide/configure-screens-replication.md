---
title: Apparaten voor schermreplicatie configureren
description: Volg deze pagina om informatie te krijgen over hoe te om de Agenten van de Replicatie van het Scherm te vormen.
role: Developer
level: Intermediate
source-git-commit: ede0eb02c97c99732c64a92c603e51bedecdbac8
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 3%

---


# Apparaten voor schermreplicatie configureren {#configuring-screens-replication-agent}

Deze volgende pagina beschrijft hoe te om de Agenten van de Replicatie van het Scherm te vormen.

## Doelstelling {#objective}

De agent van de Replicatie van het Scherm is verantwoordelijk voor het brengen van bevelgegevens zoals, *user*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep* en nog veel meer van dergelijke waarden, van publiceren naar auteur. Het is essentieel om dit te vormen zodat de auteur het apparaat kan tonen pingelen.

>[!NOTE]
>Voor meer informatie over de Agent van de Replicatie van het Scherm, zie [Screens Replication Agents and Commands](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview.html?lang=en#screens-replication-agents-and-commands).

U moet beide secties voltooien om de configuratie voor de Agent van de Replicatie van het Scherm te voltooien:

1. [Gebruikers inschakelen en het wachtwoord bijwerken](#enable-users)
1. [Instellingen bijwerken voor de agent voor schermreplicatie](#replicate-agent)

## Gebruikers inschakelen en het wachtwoord bijwerken {#enable-users}

Voer de onderstaande stappen uit om gebruikers in te schakelen en het wachtwoord voor screens-receiver-user bij te werken:

>[!NOTE]
>Om veiligheidsredenen is het raadzaam het beheerderswachtwoord niet te gebruiken voor schermgebruikers.

1. Navigeer naar de instantie van uw AEM-auteur.

1. Klik op gereedschappen —> **Beveiliging** —> **Gebruikers**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Zoeken naar **screens-receiver-user**.

1. Selecteer **screens-receiver-user** en klik op **Inschakelen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Klikken op **OK** ter bevestiging.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Als u de gebruiker hebt ingeschakeld, ziet u de **screens-receiver-user** als **Ingeschakeld** onder de **Status** veld.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Selecteer **screens-receiver-user** en klik op **Eigenschappen** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Klikken op **Wachtwoord wijzigen** krachtens **Accountinstellingen** van de **Details** zoals weergegeven in de onderstaande afbeelding.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Voer een nieuw wachtwoord in het dialoogvenster **Wachtwoord wijzigen** en klik op **Opslaan**.

   >[!NOTE]
   >U moet het bestaande beheerderswachtwoord invoeren in **Uw wachtwoord** veld.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Klikken op **Opslaan en sluiten**.

1. Selecteer **screens-receiver-user** en klik op **Activeren** in de actiebalk.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Klikken op **OK** ter bevestiging.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Selecteer **screens-receiver-user** en klik op **Uitschakelen** in de actiebalk.

   >[!IMPORTANT]
   > Uitschakelen **screens-receiver-user** alleen wordt deze gebruiker uitgeschakeld voor de instantie van de auteur en blijven alle gebruikers in de instantie publish actief. Klik niet op **Deactiveren** uit de actiebalk, want door deactivering wordt de gebruiker ook uit de publicatie-instanties verwijderd.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Klikken op **OK** ter bevestiging.

## Instellingen bijwerken voor de agent voor schermreplicatie {#replicate-agent}

Volg de onderstaande sectie om instellingen in de agent voor schermreplicatie bij te werken:

>[!IMPORTANT]
>U moet de volgende stappen op ALLE bestaande agenten van de schermreplicatie voltooien.

1. Navigeer naar de AEM.

1. Klik op gereedschappen —> **Implementatie** —> **Replicatie**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Klikken op **Medewerkers op auteur**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Zoek naar alle agenten van de Replicatie van het Scherm op auteur en klik de verbinding, zoals aangetoond in het hieronder cijfer.

   >[!NOTE]
   >Zoek naar alle agenten van de Replicatie van het Scherm. De naam van de agent voor schermreplicatie bevat een letter **S** in de titel.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Klikken op **Bewerken**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Controleren **Ingeschakeld** van de **Instellingen** tab.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigeren naar **Vervoer** van de **Instellingen agent** en werkt het dialoogvenster **Gebruiker** tot **screens-receiver-user** en voert u hetzelfde wachtwoord in dat u eerder hebt ingesteld in stap 8 van [Gebruikers inschakelen en het wachtwoord bijwerken](#enable-users).

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Klikken op **OK**.

1. Nadat u de voorgaande stappen hebt uitgevoerd, kunt u klikken op **Verbinding testen** om de verbinding te verifiëren.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   Als de verbindingsverificatie is gelukt, hebt u de configuratie van de agent voor schermreplicatie voltooid.