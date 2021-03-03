---
title: Het gebruiken van MDM of EMM aan bulklevering Android Player
seo-title: Bulkprovisioning van Android Player met EMM of MDM
description: Volg deze pagina om meer te weten te komen over bulkprovisioning van Android Player met EMM of MDM
translation-type: tm+mt
source-git-commit: 56432654d0895b892223677c8a03f10181864271
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# Bulkprovisioning van Android Player met gebruik van Enterprise Mobility Management {#bulk-provisioning}

Wanneer u de Android-speler bulksgewijs implementeert, wordt het vervelend om elke speler handmatig te registreren bij AEM. Het wordt ten zeerste aanbevolen om een EMM-oplossing (Enterprise Mobility Management), zoals VMWare Airwatch, MobileIron of Samsung Knox, te gebruiken om uw implementatie op afstand te voorzien en te beheren. AEM Screens Android-speler ondersteunt de industriestandaard EMM AppConfig voor externe provisioning.

## Bulkprovisioning van Android Player implementeren met gebruik van Enterprise Mobility Management {#implementation}

Voer de onderstaande stappen uit om bulkprovisioning in Android Player toe te staan:

1. Zorg ervoor dat uw Android-apparaat ondersteuning biedt voor Google Play-services.
1. U kunt uw Android-spelerapparaten inschrijven met uw favoriete EMM-oplossing die AppConfig ondersteunt.
1. Meld u aan bij uw EMM-console en haalt de AEM Screens Player-toepassing uit Google Play.
1. Selecteer beheerde configuratie (of verwante optie).
1. Er wordt nu een lijst weergegeven met speleropties die kunnen worden geconfigureerd (zoals server- en bulkregistratiecode).
1. Vorm deze parameters, sparen, en stel het beleid aan de apparaten op.

   >[!NOTE]
   >De apparaten zouden de toepassing samen met de configuratie en punt aan de correcte AEM server met de geselecteerde configuratie moeten ontvangen. Als u ervoor hebt gekozen de bulkregistratiecode te configureren en deze op dezelfde wijze te handhaven als in AEM is geconfigureerd, moet de speler zichzelf automatisch kunnen registreren. Als u een standaardweergave had geconfigureerd, kan deze ook standaardinhoud downloaden en weergeven (die later naar wens kan worden gewijzigd).

Bovendien dient u contact op te nemen met uw EMM-leverancier op AppConfig-ondersteuning. Meest populaire voorbeelden zoals [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobile Iron](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) en [Samsung Knox a11/> biedt ondersteuning voor deze industriestandaard.](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm)


