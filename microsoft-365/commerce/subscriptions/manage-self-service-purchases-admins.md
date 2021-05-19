---
title: Hantera köp via självbetjäning (administratörer)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: Administratörer kan lära sig att hantera självbetjäning som görs av användare i organisationen.
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536100"
---
# <a name="manage-self-service-purchases-admin"></a>Hantera självbetjäningsköp (administratörer)

Som administratör kan du se köp av självbetjäning som görs av personer i organisationen. Du ser produktnamn, inköpare, prenumerationer köpta, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäning köp. Om det krävs av din organisation kan du inaktivera självbetjäning för köp per produkt via PowerShell. Du har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.

Du kan också ange om användarna i organisationen ska kunna göra självbetjäning. Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visa prenumerationer med självbetjäning

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Dina produkter</a>.
::: moniker-end

2. På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.
3. Om du vill visa mer information om en prenumeration väljer du en prenumeration i listan.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visa vem som har licenser för en prenumeration med självbetjäning för köp av självbetjäning

> [!NOTE]
> Som administratör kan du inte tilldela eller ta bort licenser för en självbetjäningsprenumeration som köpts av en användare i din organisation. Du kan [ta över en självbetjäningsprenumeration](#take-over-a-self-service-purchase-subscription)och sedan tilldela eller ta bort licenser.

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

 1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

2. Välj filterikonen och välj **sedan Självbetjäning**.
3. Välj en produkt för att se licenser som är tilldelade till användare.
    > [!NOTE]
    > Om det finns flera köp för en produkt visas  den produkten bara en gång och i kolumnen Tillgängligt antal visas totalt för alla prenumerationer som har köpts för den produkten.
4. Listan **Användare** grupperas efter namnen på personer som har gjort självbetjäning för inköp.
5. Om du vill exportera en lista med användare med licenser för de här prenumerationerna väljer du de prenumerationer som du vill exportera och väljer sedan **Exportera användare.**

## <a name="disable-or-enable-self-service-purchases"></a>Inaktivera eller aktivera självbetjäning för köp

Du kan inaktivera eller aktivera självbetjäning för användare i organisationen. **Modulen MSCommerce** PowerShell innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning och för vilka produkter.

Du kan använda **modulen MSCommerce** PowerShell för att:

- Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten
- Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den

Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralisera licenser under en enda prenumeration

Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer genom befintliga avtal för användare som tilldelas till självbetjäning för köp via självbetjäning. När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare avbryter sina befintliga prenumerationer.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Tjänster** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">för faktureringsköp.</a>

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringsköpstjänster.**

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringsköpstjänster.**

::: moniker-end

2. Leta upp och välj den produkt du vill köpa och välj sedan **Köp**.
3. Genomför köpet i de återstående stegen.
4. Följ stegen i Visa vem som har licenser för en [självbetjäning](#view-who-has-licenses-for-a-self-service-purchase-subscription) köpt prenumeration för att exportera en lista över användare att referera till i nästa steg.
5. Tilldela licenser till alla som har en licens för den andra prenumerationen. Fullständiga steg finns i [Tilldela licenser till användare.](../../admin/manage/assign-licenses-to-users.md)
6. Kontakta personen som köpte självköpsprenumerationen och be honom eller henne [att avbryta den.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Ta över en prenumeration på självbetjäning för köp

Du kan ta över en prenumeration på självbetjäning som gjorts av en användare i organisationen. När du tar över en prenumeration på självbetjäning har du två alternativ:

1. Flytta användarna till en annan prenumeration och avbryt den ursprungliga prenumerationen.
2. Avbryt prenumerationen på självbetjäning för köp och ta bort licenser från tilldelade användare.

### <a name="move-users-to-a-different-subscription"></a>Flytta användare till en annan prenumeration

När du flyttar användare till en annan prenumeration avbryts den gamla prenumerationen automatiskt. Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.

> [!NOTE]
> Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.

::: moniker-end

2. På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.
3. Välj den prenumeration som du vill ta över.
4. Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**
5. Välj Flytta användare i det **högra fönstret.**
6. Välj den produkt som du vill flytta användarna till och välj sedan **Flytta användare.**
7. Välj **Flytta användare i** rutan **Flytta användare till.** Flytten kan ta flera minuter. Stäng inte webbläsaren medan processen körs.
8. När flyttningsprocessen är klar stänger du **fönstret Flytta slutförd .**
9. På sidan prenumerationsinformation visas **prenumerationsstatusen** för den köpta självbetjäningsprenumerationen som **Borttagna.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Avbryta en prenumeration på köp via självbetjäning

När du väljer att avbryta en prenumeration på självköp förlorar användare med licenser åtkomsten till produkten. Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>går du  till sidan > **Fakturering dina** produkter.

::: moniker-end

2. På fliken **Produkter** väljer du filterikonen och sedan **Självbetjäning**.
3. Välj den prenumeration du vill avsluta.
4. Välj Ta kontroll över den här **prenumerationen i avsnittet Prenumerationer** och inställningar **på sidan prenumerationsinformation.**
5. I den högra rutan väljer du **Avbryt prenumeration.**
6. Välj en orsak för att avsluta prenumerationen i listrutan och välj sedan **Avbryt prenumeration.**
7. I rutan **Vill du avbryta? väljer** du Avbryt **prenumeration.**
8. Stäng det högra fönstret.
9. På sidan prenumerationsinformation visas **prenumerationsstatusen** **Borttagna.**

## <a name="need-help-contact-us"></a>Behöver du hjälp? Kontakta oss.

Vanliga frågor om självbetjäning för köp finns i Vanliga frågor [och svar om självbetjäning.](self-service-purchase-faq.yml)

Om du har frågor eller behöver hjälp med köp via självbetjäning kontaktar [du supporten.](../../business-video/get-help-support.md)
