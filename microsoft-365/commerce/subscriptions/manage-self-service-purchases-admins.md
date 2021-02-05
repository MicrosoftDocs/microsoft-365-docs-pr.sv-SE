---
title: Hantera självbetjäning för köp (administratörer)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Administratörer kan lära sig hur de hanterar självbetjäning som görs av användare i organisationen.
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114699"
---
# <a name="manage-self-service-purchases-admin"></a>Hantera självbetjäningsköp (administratörer)

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Som administratör kan du se självbetjäning som gjorts av personer i organisationen. Du ser produktnamnet, inköparens namn, prenumerationer som köpts, utgångsdatum, inköpspris och tilldelade användare för varje självbetjäningsköp. Om det krävs av din organisation kan du inaktivera självbetjäning för köp per produkt via PowerShell. Du har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.

Du kan också styra om användarna i organisationen ska kunna göra självbetjäning. Mer information finns i [Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)

## <a name="view-self-service-subscriptions"></a>Visa prenumerationer med självbetjäning

1. Gå till sidan Fakturering för dina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produkter i administrationscentret.</a>
2. Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**
3. Om du vill visa mer information om en prenumeration väljer du en prenumeration i listan.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visa vem som har licenser för en prenumeration på självbetjäning

1. Gå till sidan Faktureringslicenser **i**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">administrationscentret.</a>
2. Välj filterikonen och välj sedan **Självbetjäning.**
3. Välj en produkt om du vill se licenser tilldelade till användare.
    > [!NOTE]
    > Om det finns flera köp för en produkt visas  den produkten bara en gång och i kolumnen Tillgängligt antal visas totalt för alla prenumerationer som har köpts för den produkten.
4. **Användarlistan** är grupperad efter namnen på personer som har gjort självbetjäning.
5. Om du vill exportera en lista med användare med licenser för dessa prenumerationer väljer du de prenumerationer du vill exportera och väljer sedan **Exportera användare.**

## <a name="disable-or-enable-self-service-purchases"></a>Inaktivera eller aktivera självbetjäning för köp

Du kan inaktivera eller aktivera självbetjäning för användare i organisationen. **MsCommerce** PowerShell-modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra självbetjäningsköp och för vilka produkter.

Du kan använda **MSCommerce** PowerShell-modulen för att:

- Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten
- Visa en lista över tillämpliga produkter och om självbetjäning för köp har aktiverats eller inaktiverats
- Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den

Mer information finns i [Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell.](allowselfservicepurchase-powershell.md)

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralisera licenser under en enda prenumeration

Du kan tilldela befintliga licenser eller köpa ytterligare prenumerationer genom befintliga avtal för användare som tilldelats till självbetjäning. När du har tilldelat dessa centralt köpta licenser kan du begära att inköpare avbryter sina befintliga prenumerationer.

1. Gå till sidan För **faktureringsköp** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">i administrationscentret.</a>
2. Leta upp och välj den produkt du vill köpa och välj sedan **Köp.**
3. Slutför de återstående stegen för att slutföra köpet.
4. Följ stegen i [Visa vem som har licenser](#view-who-has-licenses-for-a-self-service-purchase-subscription) för en självbetjänad prenumeration för att exportera en lista med användare som du vill referera till i nästa steg.
5. Tilldela licenser till alla som har en licens för den andra prenumerationen. Fullständiga steg finns i [Tilldela licenser till användare.](../../admin/manage/assign-licenses-to-users.md)
6. Kontakta personen som köpte prenumerationen på självbetjäning och be [honom/henne att avbryta den.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Ta över en prenumeration på självbetjäning

Du kan ta över en prenumeration på självbetjäning som gjorts av en användare i organisationen. När du tar över en prenumeration på självbetjäning har du två alternativ:

1. Flytta användarna till en annan prenumeration och avbryt den ursprungliga prenumerationen.
2. Avbryt självbetjäningsprenumerationen och ta bort licenser från tilldelade användare.

### <a name="move-users-to-a-different-subscription"></a>Flytta användare till en annan prenumeration

När du flyttar användare till en annan prenumeration avbryts den gamla prenumerationen automatiskt. Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.

> [!NOTE]
> Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.

1. Gå till sidan Fakturering för dina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produkter i administrationscentret.</a>
2. Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**
3. Välj den prenumeration du vill ta över.
4. Välj Ta kontroll över den här prenumerationen **i avsnittet** Prenumerationer och inställningar på **sidan Prenumerationsinformation.**
5. Välj Flytta användare i det **högra fönstret.**
6. Markera den produkt som du vill flytta användarna till och välj sedan **Flytta användare.**
7. Välj **Flytta användare i** rutan Flytta **användare till.** Flyttningsprocessen kan ta flera minuter. Stäng inte webbläsaren medan processen körs.
8. Stäng den slutförda rutan Flytta när **flyttningsprocessen är klar.**
9. Prenumerationsstatusen för **självbetjäning** köpta prenumerationer visas som Borttagna på **sidan prenumerationsinformation.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Avbryta en prenumeration på självbetjäning

När du väljer att avbryta en prenumeration på självbetjäning förlorar användare med licenser åtkomsten till produkten. Den användare som ursprungligen köpte självköpsprenumerationen får ett e-postmeddelande om att prenumerationen har avbrutits.

1. Gå till sidan Fakturering för dina produkter  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">i administrationscentret.</a>
2. Välj **filterikonen** på fliken Produkter och välj sedan **Självbetjäning.**
3. Välj den prenumeration som du vill avbryta.
4. Välj Ta kontroll över den här prenumerationen **i avsnittet** Prenumerationer och inställningar på **sidan Prenumerationsinformation.**
5. I den högra rutan väljer du **Avbryt prenumeration.**
6. Välj en orsak till att du avslutar prenumerationen i listrutan och välj sedan **Avbryt prenumeration.**
7. I rutan **Vill du avbryta? väljer** du Avbryt **prenumeration.**
8. Stäng det högra fönstret.
9. Prenumerationsstatus visas som **Borttagna** på sidan **prenumerationsinformation.**

## <a name="need-help-contact-us"></a>Behöver du hjälp? Kontakta oss.

Vanliga frågor om självbetjäning för köp finns i Vanliga frågor och svar [om självbetjäning.](self-service-purchase-faq.md)

Om du har frågor eller behöver hjälp med självbetjäning kan [du kontakta support.](../../admin/contact-support-for-business-products.md)