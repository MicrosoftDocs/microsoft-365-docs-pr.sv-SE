---
title: Köpa eller ta bort prenumerationslicenser
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Läs om hur du köper fler licenser eller minskar antalet licenser för din Microsoft 365 för företag-prenumeration.
ms.date: 07/01/2020
ms.openlocfilehash: 85861379bbce30c3c071a47529d516d7d5170e39
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015905"
---
# <a name="buy-or-remove-subscription-licenses"></a>Köpa eller ta bort prenumerationslicenser

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Du kan köpa fler licenser eller minska antalet licenser för dina prenumerationer genom att använda dessa steg.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara antingen global administratör eller faktureringsadministratör för att kunna köpa licenser. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
- Du kan [lägga till användare och tilldela licenser samtidigt](../../admin/add-users/add-users.md).

## <a name="buy-or-remove-licenses-for-your-business-subscription"></a>Köpa eller ta bort licenser för din företagsprenumeration

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. Leta reda på den prenumeration som du vill köpa eller ta bort licenser för och välj sedan **Lägg till/ta bort licenser**. [Vad händer om du inte ser länken Lägg till/ta bort licenser?](#what-if-you-dont-see-the-addremove-licenses-link)
3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill ha för den här prenumerationen och väljer sedan Skicka **ändring**. Om du till exempel har 100 licenser och vill lägga till ytterligare fem anger du 105. Om du vill ta bort fem av dem anger du 95.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.
2. På sidan **Prenumerationer** väljer du den prenumeration som du vill köpa eller ta bort licenser till och väljer sedan **Lägg till/ta bort licenser**. [Vad händer om du inte ser länken Lägg till/ta bort licenser?](#what-if-you-dont-see-the-addremove-licenses-link)
3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill ha för den här prenumerationen och väljer sedan **Skicka** \> **stäng**. Om du till exempel har 100 licenser och vill lägga till ytterligare fem anger du 105. Om du vill ta bort fem licenser anger du 95.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.
2. På sidan **Prenumerationer** väljer du den prenumeration som du vill köpa eller ta bort licenser till och väljer sedan **Lägg till/ta bort licenser**. [Vad händer om du inte ser länken Lägg till/ta bort licenser?](#what-if-you-dont-see-the-addremove-licenses-link)
3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill ha för den här prenumerationen och väljer sedan **Skicka** \> **stäng**. Om du till exempel har 100 licenser och behöver lägga till ytterligare 5 skriver du 105. Om du vill ta bort 5 av dem anger du 95.

::: moniker-end

> [!NOTE]
> Du kan inte minska antalet licenser för din prenumeration om alla licenser för närvarande har tilldelats användare. Om du vill minska antalet licenser tar du först [bort tilldelningen](../../admin/manage/remove-licenses-from-users.md)av en eller flera licenser från användare och tar sedan bort licenserna från prenumerationen.

## <a name="what-if-you-dont-see-the-addremove-licenses-link"></a>Vad händer om du inte ser länken Lägg till/ta bort licenser?

I den här tabellen beskrivs varför länken **Lägg till/ta bort licenser** kanske inte är tillgänglig och vad du kan göra åt den.

|Anledning  |Beskrivning  |Lösning  |
|---------|---------|---------|
|En kreditkontroll väntar. |Om en kreditkontroll väntar visas meddelandet "Väntande kreditkontroll". Du kan inte köpa licenser förrän kreditkontrollen är klar.  | Kom tillbaka senare för att se om kreditkontrollen har slutförts. Kreditkontroller tar vanligtvis upp till två arbetsdagar.<br/>När kreditkontrollen är klar bör länken **Lägg till/ta bort licenser** visas. |
|Du aktiverade prenumerationen med hjälp av en produktnyckel.| Om prenumerationen köptes och aktiverades med hjälp av en produktnyckel på 25 tecken visas texten "Förutbetalda".  |Se [Lägga till licenser i en prenumeration som betalats för att använda en produktnyckel](add-licenses-using-product-key.md). |
|Du köpte din prenumeration via en partner. | Om prenumerationen köptes via en partner visas länken VLSC (Volume Licensing Service Center). | Se [Lägga till licenser i en prenumeration som köpts via Servicecenter för volymlicensiering](add-licenses-bought-through-vlsc.md). |
|Du har köpt din prenumeration via en återförsäljare.|| Om prenumerationen köptes via en CSP-partner (Cloud Solution Provider) kontaktar du din CSP-partner för att köpa fler licenser.        |
|Du har en provprenumeration. |En testversion av Microsoft 365 visar texten "Trial". | Först köpa din provprenumeration, sedan kan du lägga till fler licenser. Se [Köpa en prenumeration på Microsoft 365 för företag från den kostnadsfria provperioden](../buy-a-subscription-from-your-free-trial.md).|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>Vad du behöver veta om att köpa licenser för din företagsprenumeration

### <a name="license-availability"></a>Tillgänglighet för licenser

- **Om du har en faktureringsprofil**: Kreditkortet som är kopplat till din faktureringsprofil debiteras så fort du köper fler licenser för en prenumeration. Licenserna är omedelbart tillgängliga för användare. [Vad är en faktureringsprofil?](../billing-and-payments/manage-billing-profiles.md)
- **Om du inte har någon faktureringsprofil**: Om du betalar för din prenumeration med kredit- eller betalkort eller bankkonto är alla nya licenser som du köper omedelbart tillgängliga efter att du har fått en orderbekräftelse. Om du betalar med faktura kan du behöva vänta på en kreditkontroll innan de nya licenserna är tillgängliga för användning.
  > [!NOTE]
  > Betalning med bankkonto är inte tillgängligt i vissa länder eller regioner.
- **Om du förbetalt för din prenumeration med en produktnyckel:** Du kan lägga till fler licenser genom att lägga till ett kredit- eller betalkort eller bankkonto för att täcka merkostnaden för de nya licenserna. När du har köpt de nya licenserna lägger vi till en andra prenumeration med antalet nya licenser som du just har lagt till. Om du till exempel har en förbetald prenumeration med fem licenser och sedan har köpt ytterligare 10 licenser visas två prenumerationer: en med de fem förbetalda licenserna och en med de 10 nya licenserna.

### <a name="changing-your-payment-method"></a>Ändra betalningsmetod

- **Om du har en faktureringsprofil**: Kreditkortet som är kopplat till din faktureringsprofil debiteras så fort du köper fler licenser för en prenumeration. [Vad är en faktureringsprofil?](../billing-and-payments/manage-billing-profiles.md)
- **Om du inte har någon faktureringsprofil:** Om du betalar med kreditkort, betalkort eller bankkonto visas avgiften för att köpa nya licenser på din betalningsmetod om två dagar.

### <a name="billing-statements"></a>Faktureringsutdrag

- Licenser som läggs till mitt under faktureringsperioden visas på nästa faktura. Om du betalar årligen faktureras du inom en månad för dessa ändringar.
- På nästa faktureringsutdrag dras den tidigare avgiften för det ursprungliga antalet licenser av. Vi lägger till en proportionell avgift för tidsperioden med det ursprungliga antalet licenser och lägger till en avgift för det nya antalet licenser. Det finns också en avgift för det aktuella antalet licenser för återstoden av faktureringsperioden.

## <a name="next-steps"></a>Nästa steg

Om du har köpt fler licenser för din prenumeration bör du göra följande saker [att tilldela dessa licenser till användare i organisationen](../../admin/manage/assign-licenses-to-users.md).

Om du har minskat antalet licenser för din prenumeration på grund av att någon har lämnat organisationen kanske du vill ta bort användarens konto. Mer information finns i [Ta bort en tidigare anställd](../../admin/add-users/remove-former-employee.md).

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Förstå prenumerationer och licenser](subscriptions-and-licenses.md) (artikel)\
[Prova eller köpa en Microsoft 365-prenumeration](../try-or-buy-microsoft-365.md) (artikel)