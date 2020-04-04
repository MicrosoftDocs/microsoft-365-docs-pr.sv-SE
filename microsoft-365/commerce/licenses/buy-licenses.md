---
title: Hantera prenumerationslicenser
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- SaRA
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 36081d8d-b3fa-4948-8c34-e217bba825e1
description: Läs om hur du lägger till och tar bort licenser för din Office 365 för företag-prenumeration.
ms.openlocfilehash: f596971016e18747ea2849c0dfcb0dd287a0c811
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142181"
---
# <a name="manage-subscription-licenses"></a>Hantera prenumerationslicenser

Du kan lägga till eller ta bort licenser från dina prenumerationer med hjälp av dessa steg.

Du kan inte ta bort en licens från en prenumeration om den är tilldelad till en användare. Om du vill ta bort en licens som för närvarande har tilldelats någon måste du [ta bort licenser från användare](../../admin/manage/remove-licenses-from-users.md) innan du kan ta bort licensen från prenumerationen.

::: moniker range="o365-worldwide"

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>Vad du behöver veta om att köpa licenser för din företagsprenumeration

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkter och tjänster</a>.

2. Leta reda på den prenumeration som du vill lägga till eller ta bort licenser till på sidan **Produkter & tjänster** och välj sedan Lägg **till/ta bort licenser**.

    [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)

3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du behöver för den här prenumerationen och väljer sedan Skicka **ändring**. Om du till exempel har 100 licenser och behöver lägga till ytterligare 5 skriver du 105. Om du vill ta bort 5 av dem anger du 95.

När du har köpt nya licenser måste du [tilldela licenserna till användarna](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

2. På sidan **Prenumerationer** väljer du den prenumeration som du vill lägga till eller ta bort licenser till och väljer sedan **Lägg till/ta bort licenser**.

    [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)

3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du behöver för den här prenumerationen och väljer sedan **Skicka** \> **stäng**. Om du till exempel har 100 licenser och behöver lägga till ytterligare 5 skriver du 105. Om du vill ta bort 5 av dem anger du 95.

När du har köpt nya licenser måste du [tilldela licenserna till användarna](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

2. På sidan **Prenumerationer** väljer du den prenumeration som du vill lägga till eller ta bort licenser till och väljer sedan **Lägg till/ta bort licenser**.

    [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)

3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du behöver för den här prenumerationen och väljer sedan **Skicka** \> **stäng**. Om du till exempel har 100 licenser och behöver lägga till ytterligare 5 skriver du 105. Om du vill ta bort 5 av dem anger du 95.

När du har köpt nya licenser måste du [tilldela licenserna till användarna](../../admin/manage/assign-licenses-to-users.md).

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?

I den här tabellen beskrivs varför länken **Lägg till/ta bort licenser** kanske inte är tillgänglig och vad du kan göra åt den.

|Orsak  |Beskrivning  |Lösning  |
|---------|---------|---------|
|En kreditkontroll väntar. |Om det finns en kreditkontroll som väntar visas ett meddelande om väntande kreditkontroll och du kan inte köpa licenser förrän kreditkontrollen är klar.  | Kom tillbaka senare för att se om kreditkontrollen har slutförts. Kreditkontroller tar vanligtvis upp till två arbetsdagar.<br>När kreditkontrollen är klar bör länken **Lägg till/ta bort licenser** visas i avsnittet **Användare**. Om så är fallet går du till [Hantera prenumerationslicenser](#manage-subscription-licenses). |
|Du aktiverade prenumerationen med hjälp av en produktnyckel.| Om prenumerationen har köpts och aktiverats med en 25 tecken lång produktnyckel visas texten "Förbetald".  |Se [Lägga till licenser i en prenumeration som betalats för att använda en produktnyckel](add-licenses-using-product-key.md). |
|Du köpte din prenumeration via en partner. | Om prenumerationen har köpts via en partner visas länken Volume Licensing Service Center (VLSC). | Se [Lägga till licenser i en prenumeration som köpts via Servicecenter för volymlicensiering](add-licenses-bought-through-vlsc.md). |
|Du har köpt din prenumeration via en återförsäljare.|| Om prenumerationen har köpts via en leverantör av molnlösningar (CSP) måste du kontakta CSP-partnern om du vill köpa fler licenser.        |
|Du har en utvärderingsprenumeration. |En utvärderingsversion av Office 365 visar texten "Utvärderingsversion". | Du måste först köpa din provprenumeration, sedan kan du lägga till fler licenser. Se [Köpa en prenumeration på Office 365 för företag från den kostnadsfria utvärderingsversionen](../buy-a-subscription-from-your-free-trial.md).|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>Vad du behöver veta om att köpa licenser för din företagsprenumeration

### <a name="buying-licenses"></a>Köpa licenser

- Du måste vara antingen global administratör eller faktureringsadministratör för att kunna köpa licenser. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
- Om du vill köpa en licens och lägga till en ny användare i prenumerationen samtidigt läser du [Lägga till användare individuellt eller flera samtidigt i Office 365 - administratörshjälp](../../admin/add-users/add-users.md).

### <a name="license-availability"></a>Tillgänglighet för licens

- Om du betalar för prenumerationen med kontokort eller via bankkonto får du direkt tillgång till nya licenser som du köper när du väl har tagit emot orderbekräftelsen. Om du betalar med faktura kan du behöva vänta på en kreditkontroll innan de nya licenserna är tillgängliga för användning.

  > [!NOTE]
  > Betalning med bankkonto är inte tillgängligt i vissa länder eller regioner.

- Om du har förbetalt för din prenumeration med en produktnyckel kan du lägga till fler licenser genom att lägga till ett kreditkort eller bankkonto för att täcka merkostnaden för de nya licenserna. När du har köpt de nya licenserna lägger vi till en andra prenumeration med det antal nya licenser som du just har lagt till. Om du till exempel har ett förbetalt abonnemang med 5 licenser och sedan köper ytterligare 10 licenser så visas två prenumerationer: en med de fem förbetalda licenserna och en med de tio nya licenserna.

### <a name="billing-statements"></a>Faktureringsutdrag

- Om du betalar med kreditkort eller via bankkonto visas avgiften för de köpta nya licenserna för betalningsmetoden inom två dagar.
- Om du betalar med faktura visas avgiften för de köpta nya licenserna på nästa faktureringsutdrag.
- Om du köper nya licenser mitt i din faktureringsperiod kanske det första faktureringsutdraget innehåller en del av avgiften. Det återstående beloppet kommer då att ingå i nästa faktureringsutdrag.

## <a name="related-articles"></a>Relaterade artiklar

[Allmänt om prenumerationer och licenser](subscriptions-and-licenses.md)

[Köpa licenser för prenumerationen](buy-licenses.md)

[Köpa en annan prenumeration](../buy-another-subscription.md)

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md)

[Hantera Yammer-användarlicenser](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)