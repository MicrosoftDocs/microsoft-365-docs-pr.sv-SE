---
title: Hantera självbetjäningsköp (administratörer)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Administratörer kan lära sig att hantera självbetjäningsköp som görs av användare i organisationen.
ms.openlocfilehash: 991dc87c40f41a6cbd2f1c08d4bc72bbb34d28f1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141156"
---
# <a name="manage-self-service-purchases-admin"></a>Hantera självbetjäningsköp (administratörer)

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Som administratör kan du se självbetjäningsköp som görs av personer i organisationen. Du kan se produkten, köparens namn, köpta prenumerationer, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäningsköp. Om det behövs för din organisation kan du inaktivera självbetjäningsköp per produkt via PowerShell. Du har samma datahanterings- och åtkomstpolicyer över produkter som köpts via självbetjäningsköp eller centralt.

Du kan också styra om användare i organisationen kan göra självbetjäningsköp. Mer information finns i [Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visa självbetjäningsprenumerationer

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret. **Billing**

2. Välj **Självbetjäning**i listrutan **Kontotyp** bredvid **Förfina**resultat .

3. Om du vill visa mer information om en prenumeration väljer du en i listan.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visa vem som har licenser för en självbetjäningsköpsprenumeration

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**

2. Välj filterikonen och välj sedan **Självbetjäning**.

3. Välj en produkt om du vill visa licenser som tilldelats personer.

    > [!NOTE]
    > Om det finns flera inköp för en produkt visas den produkten bara en gång och kolumnen **Tillgänglig kvantitet** visar summan av alla prenumerationer som köpts för den produkten.

4. **Listan Användare** grupperas efter namnen på personer som gjort självbetjäningsköp.

5. Om du vill exportera en lista över användare med licenser för dessa prenumerationer väljer du de prenumerationer som du vill exportera och väljer sedan **Exportera användare**.

## <a name="disable-or-enable-self-service-purchases"></a>Inaktivera eller aktivera självbetjäningsköp

Du kan inaktivera eller aktivera självbetjäningsköp för användare i organisationen. **MSCommerce** PowerShell-modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som låter dig styra om användare i organisationen kan göra självbetjäningsköp och för vilka produkter.

Du kan använda **MSCommerce** PowerShell-modulen för att:

- Visa standardtillståndet för parametervärdet &mdash; Tillåt **självtjänstköpa** om det är aktiverat eller inaktiverat av produkten
- Visa en lista över tillämpliga produkter och om självbetjäningsköp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den

Mer information finns i [Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralisera licenser under en enda prenumeration

Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer via befintliga avtal för användare som tilldelats självbetjäningsköp. När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare säger upp sina befintliga prenumerationer.

1. Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a> med ditt globala administratörs- eller faktureringsadministratörskonto.

2. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Faktureringsköpstjänster.</a> **Billing**

3. Hitta och välj den produkt som du vill köpa och välj sedan **Köp.**

4. Slutför de återstående stegen för att slutföra köpet.

5. Följ stegen i [Visa vem som har licenser för en självbetjäningsköpt prenumeration för](#view-who-has-licenses-for-a-self-service-purchase-subscription) att exportera en lista över användare som ska referera till i steg 6.

6. Tilldela licenser till alla som har en licens i den andra prenumerationen. Fullständiga steg finns i [Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md).

7. Kontakta personen som köpte självbetjäningsköpsprenumerationen och be dem att avbryta den.

## <a name="need-help-contact-us"></a>Behöver du hjälp? Kontakta oss.

Vanliga frågor om självbetjäningsköp finns i [Vanliga frågor om självbetjäningsköp](self-service-purchase-faq.md).

Om du har frågor eller behöver hjälp med självbetjäningsköp [kontaktar du supporten](../../admin/contact-support-for-business-products.md).
