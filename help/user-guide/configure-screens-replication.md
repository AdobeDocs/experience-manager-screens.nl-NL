---
title: De agent voor schermreplicatie configureren
description: Volg deze pagina om informatie te krijgen over hoe te om de Agent van de Replicatie van het Scherm te vormen.
role: Developer
level: Intermediate
source-git-commit: 9f0beddf87d9f5473fdedc292d3c24e96b85cdd4
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---


# De agent voor schermreplicatie configureren {#configuring-screens-replication-agent}

Deze sectie beschrijft hoe te om de replicatieagent van Schermen te vormen.

## Gebruikers inschakelen en het wachtwoord bijwerken {#enable-users}

Voer de onderstaande stappen uit:

1. Navigeer naar de AEM.

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
   >U moet **beheerder** in **Uw wachtwoord** veld.

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

## De agent voor schermreplicatie bijwerken {#replicate-agent}

Volg de onderstaande sectie om instellingen in de agent voor schermreplicatie bij te werken:

1. Navigeer naar de AEM.

1. Klik op gereedschappen —> **Implementatie** —> **Replicatie**.

   ![afbeelding](/help/user-guide/assets/screens-replication/screens-replication1a.png)
