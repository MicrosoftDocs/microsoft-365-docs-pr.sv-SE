---
title: Hantera självbetjänings köp (administratörer)
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
description: Administratörer kan lära sig att hantera självbetjänings köp som görs av användare i organisationen.
ms.openlocfilehash: ca25bf0c3e3539196e81dcc289592028cc4dfa47
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546680"
---
# <a name="manage-self-service-purchases-admin"></a>Hantera självbetjäningsköp (administratörer)

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Som administratör kan du se självbetjänings köp som görs av personer i din organisation. Du ser produkt namn, köpar namn, köpta abonnemang, utgångs datum, inköps pris och tilldelade användare för varje själv service-inköp. Om organisationen kräver det, kan du stänga av självbetjänings köp per produkt med hjälp av PowerShell. Du har samma data hanterings-och åtkomst principer som gäller för produkter som köpts via eget köp eller centralt.

Du kan också kontrol lera om användare i din organisation kan göra självbetjänings köp. Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visa självbetjänings abonnemang

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. På fliken **produkter** väljer du filter ikonen och sedan **själv service**.
3. Om du vill visa mer information om ett abonnemang väljer du en i listan.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Visa vem som har licenser för ett självbetjänings abonnemang

1. Gå till sidan för **fakturerings**licenser i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .
2. Välj filter ikonen och välj sedan **själv service**.
3. Välj en produkt för att se licenser tilldelade till personer.
    > [!NOTE]
    > Om det finns flera köp för en produkt visas produkten endast en gång och kolumnen **disponibelt antal** visar summan av alla abonnemang som har köpts för produkten.
4. Listan **användare** är grupperad efter namnen på personer som gjorde själv service inköp.
5. Om du vill exportera en lista över användare med licenser för dessa prenumerationer väljer du de abonnemang som du vill exportera och väljer sedan **exportera användare**.

## <a name="disable-or-enable-self-service-purchases"></a>Inaktivera eller aktivera självbetjänings köp

Du kan inaktivera eller aktivera självbetjänings köp för användare i organisationen. **MSCommerce** PowerShell-modulen innehåller ett **PolicyID** parameter värde för **AllowSelfServicePurchase** där du kan kontrol lera om användare i din organisation kan göra självbetjänings köp och för vilka produkter.

Du kan använda **MSCommerce** PowerShell-modulen till att:

- Visa standard tillståndet för parametervärdet för **AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat av produkten
- Visa en lista över tillämpliga produkter och om självbetjänings inköp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att aktivera eller inaktivera den

Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralisera licenser under en enda prenumeration

Du kan tilldela befintliga licenser eller köpa ytterligare abonnemang genom befintliga avtal för användare tilldelade till självbetjänings köp. När du har kopplat dessa licenser kan du begära att dessa inköpare annullerar sina befintliga abonnemang.

1. Gå till sidan **fakturerings** tjänster i administrations centret \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> .
2. Leta reda på och välj den produkt som du vill köpa och välj sedan **köp**.
3. Utför resten av stegen för att slutföra köpet.
4. Följ stegen i [Visa vilka som har licenser för en självbetjänings prenumeration](#view-who-has-licenses-for-a-self-service-purchase-subscription) för att exportera en lista med användare som ska referera till nästa steg.
5. Tilldela licenser till alla som har en licens i det andra abonnemanget. Fullständiga anvisningar finns i [tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md).
6. Kontakta den person som köpte självbetjänings abonnemanget och be dem att [annullera det](manage-self-service-purchases-users.md#cancel-a-subscription).

## <a name="take-over-a-self-service-purchase-subscription"></a>Ta över ett självbetjänings abonnemang

Du kan ta över ett abonnemang för självbetjäning som görs av en användare i organisationen. När du tar över ett själv service abonnemang har du två alternativ:

1. Flytta användarna till ett annat abonnemang och Avbryt det ursprungliga abonnemanget.
2. Avbryt självbetjänings abonnemanget och ta bort licenser från tilldelade användare.

### <a name="move-users-to-a-different-subscription"></a>Flytta användare till en annan prenumeration

När du flyttar användare till ett annat abonnemang avbryts det gamla abonnemanget automatiskt. Den användare som ursprungligen köpte självbetjänings köpet får ett e-postmeddelande om att abonnemanget har annullerats.

> [!NOTE]
> Du måste ha en tillgänglig licens för varje användare som du flyttar i prenumerationen som du flyttar användare till.

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. På fliken **produkter** väljer du filter ikonen och sedan **själv service**.
3. Välj den prenumeration som du vill ta över.
4. På sidan prenumerations information i avsnittet **prenumerationer och inställningar** väljer du **ta kontroll för det här abonnemanget**.
5. I det högra fönstret väljer **du flytta användare**.
6. Välj den produkt som du vill flytta användarna till och välj sedan **flytta användare**.
7. I rutan **flytta användare till väljer du** **flytta användare**. Det kan ta flera minuter att flytta. Stäng inte webbläsaren medan processen körs.
8. När flytt processen är klar stänger du **fönstret flytta slutfört**.
9. På sidan prenumerations information visas **prenumerations statusen** för det självbetjänings abonnemang som har **tagits bort**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Avbryta ett självbetjänings abonnemang

När du väljer att avbryta ett abonnemang för självbetjäning, förlorar användare med licenser åtkomst till produkten. Den användare som ursprungligen köpte självbetjänings köpet får ett e-postmeddelande om att abonnemanget har annullerats.

1. Gå till sidan fakturering i administrations centret **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> .
2. På fliken **produkter** väljer du filter ikonen och sedan **själv service**.
3. Välj den prenumeration som du vill avbryta.
4. På sidan prenumerations information i avsnittet **prenumerationer och inställningar** väljer du **ta kontroll för det här abonnemanget**.
5. I det högra fönstret väljer du **Avbryt prenumeration**.
6. Välj en anledning till annulleringen i list rutan och välj sedan **Avbryt prenumeration**.
7. I rutan **är du säker på att du vill avbryta?** väljer du **Avbryt prenumeration**.
8. Stänga fönstret till höger.
9. På sidan prenumerations information visas **prenumerationens status** som **borttagen**.

## <a name="need-help-contact-us"></a>Behöver du hjälp? Kontakta oss.

Vanliga frågor om självbetjänings köp finns i [vanliga frågor och svar om inköp](self-service-purchase-faq.md).

Om du har frågor eller behöver hjälp med självbetjänings köp kan du [kontakta supporten](../../admin/contact-support-for-business-products.md).