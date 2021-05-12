---
title: Köpa eller ta bort licenser
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: argani, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_o365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Läs om hur du köper fler licenser eller minskar antalet licenser för din Microsoft 365 för företag-prenumeration.
ms.date: 04/07/2021
ms.openlocfilehash: 6603b49ed7af8b5213141d5c2434093c3af9540a
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327124"
---
# <a name="buy-or-remove-licenses"></a>Köpa eller ta bort licenser

Du kan köpa fler licenser eller minska antalet licenser för dina prenumerationer med hjälp av följande steg.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global administratör eller faktureringsadministratör för att kunna utföra de uppgifter som beskrivs i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
- Du [kan lägga till användare och tilldela licenser samtidigt.](../../admin/add-users/add-users.md)
- Om du har köpt ditt Microsoft 365 för företag- eller Office 365 Enterprise-abonnemang genom en tredjepartspartner måste du köpa ytterligare licenser via den partnern.

## <a name="watch-buy-new-licenses"></a>Titta: Köp nya licenser

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4KWvE]

Om de användare som du köper licenser för inte är aktiva användare i organisationen ännu är nästa sak att lägga till användare och tilldela licenser [samtidigt.](../../admin/add-users/add-users.md)

## <a name="watch-remove-existing-licenses"></a>Titta: Ta bort befintliga licenser

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4L53r]

Om du har tagit bort licenser från en prenumeration är nästa sak att ta [bort användare från organisationen.](../../admin/add-users/delete-a-user.md)

## <a name="buy-or-remove-licenses-for-your-business-subscription"></a>Köpa eller ta bort licenser för din företagsprenumeration

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Dina produkter</a>.
::: moniker-end

2. På fliken **Produkter** hittar du den prenumeration som du vill köpa eller ta bort licenser för. Välj **Fler åtgärder** (tre punkter) och välj sedan Köp **licenser.** [Vad händer om jag inte ser knapparna Köp licenser eller Ta bort licenser?](#what-if-i-dont-see-the-buy-licenses-or-remove-licenses-buttons)
3. Om du vill minska antalet licenser väljer du ta bort licenser längst upp **i** fönstret Köp **licenser.**
4. Om du vill köpa eller ta  bort **licenser anger** du det totala antalet licenser som du vill använda för prenumerationen under Nytt antal i rutan Totalt antal licenser. Om du till exempel har 100 licenser och vill lägga till ytterligare 5 skriver du 105. Om du vill ta bort fem av dem skriver du 95.
5. Välj **Spara**.

> [!NOTE]
> Du kan inte minska antalet licenser för prenumerationen om alla licenser är tilldelade till användare. För att minska antalet licenser måste du först ta bort en eller [flera licenser från användarna](../../admin/manage/remove-licenses-from-users.md)och sedan ta bort licenserna från prenumerationen.

## <a name="what-if-i-dont-see-the-buy-licenses-or-remove-licenses-buttons"></a>Vad händer om jag inte ser knapparna Köp licenser eller Ta bort licenser?

I den här tabellen beskrivs orsakerna till **varför knapparna Köp licenser** eller Ta bort licenser inte är tillgängliga och möjliga lösningar. 

|Orsak  |Beskrivning  |Lösning  |
|---------|---------|---------|
|Det finns en kreditkontroll som väntar. |Om det finns en kreditkontroll som väntar kan du inte köpa eller ta bort licenser förrän kreditkontrollen är klar.  | Kom tillbaka senare för att se om kreditkontrollen är klar. Kreditkontroller tar vanligtvis upp till två arbetsdagar.<br/>När kreditkontrollen är klar bör du se knapparna **Köp licenser** och **Ta bort** licenser. |
|Du har aktiverat prenumerationen med hjälp av en produktnyckel.| Om prenumerationen har köpts och aktiverats med en 25 tecken stor produktnyckel  visas ordet "Förbetald" i kolumnen Köpkanal på **sidan Dina** produkter.  |Se [Lägga till licenser för en prenumeration som betalats med en produktnyckel.](add-licenses-using-product-key.md) |
|Du har köpt prenumerationen genom en återförsäljare.| Du ser ordet "Återförsäljare" i kolumnen **Köp kanal** på **sidan Dina** produkter. | Om prenumerationen har köpts via en leverantör av molnlösningar (CSP) kontaktar du din CSP-partner för att köpa fler licenser.        |
|Du har en utvärderingsprenumeration. | Om du vill visa dina utvärderingsprenumerationer väljer du filterknappen och sedan **Utvärderingsversion**. | Först köper du utvärderingsprenumerationen och sedan kan du köpa fler licenser.|

## <a name="when-will-the-new-licenses-be-available-to-assign"></a>När blir de nya licenserna tillgängliga för tilldelning?

Den betalningsmetod som är kopplad till din prenumeration eller faktureringsprofil debiteras så snart du köper fler licenser för en prenumeration. Licenserna är direkt tillgängliga så att du kan tilldela användare.

Om du har förbetalt för prenumerationen med en produktnyckel kan du lägga till fler licenser med hjälp av en annan produktnyckel eller genom att lägga till ett kreditkort eller bankkort eller bankkonto för att täcka den extra kostnaden för de nya licenserna. Om prenumerationen är förbetald kan du inte ta bort licenser.

## <a name="how-does-buying-or-removing-licenses-affect-my-billing-statements"></a>Hur påverkar köp och borttagning av licenser mina faktureringsutdrag?

- Licenser som lagts till mitt i din faktureringsperiod visas på nästa faktura. Om du betalar årsvis faktureras du inom en månad för dessa ändringar.
- På nästa faktureringsutdrag dras den föregående avgiften för det ursprungliga antalet licenser av. Vi lägger till en punkt för tidsperioden med det ursprungliga antalet licenser och lägger till en avgift för det nya antalet licenser. Det finns även en avgift för det aktuella antalet licenser för resten av faktureringsperioden.

## <a name="next-steps"></a>Nästa steg

Om du har köpt fler licenser för prenumerationen ska du därefter tilldela [licenserna till användare i organisationen.](../../admin/manage/assign-licenses-to-users.md)

Om du har minskat antalet licenser för din prenumeration eftersom någon har lämnat organisationen kanske du vill ta bort den användarens konto. Mer information finns i Ta [bort en tidigare anställd](../../admin/add-users/remove-former-employee.md).

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Allmänt om prenumerationer och licenser](subscriptions-and-licenses.md) (artikel)\
[Prova eller köp en Microsoft 365-prenumeration](../try-or-buy-microsoft-365.md) (artikel)