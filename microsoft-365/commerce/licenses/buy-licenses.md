---
title: Köpa eller ta bort prenumerationslicenser
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: Lär dig hur du köper fler licenser eller minskar antalet licenser för Microsoft 365 för företag-prenumerationen.
ms.date: 07/01/2020
ms.openlocfilehash: df9570649e1ba5d674f1f152afa9d4dcaee8fc5e
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324252"
---
# <a name="buy-or-remove-subscription-licenses"></a>Köpa eller ta bort prenumerationslicenser

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Du kan köpa fler licenser eller minska antalet licenser för dina abonnemang med hjälp av de här stegen.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global administratör eller fakturerings administratör för att kunna utföra åtgärderna i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
- Du kan [lägga till användare och tilldela licenser samtidigt](../../admin/add-users/add-users.md).

## <a name="buy-or-remove-licenses-for-your-business-subscription"></a>Köpa eller ta bort licenser för ditt företags abonnemang

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. Leta reda på den prenumeration som du vill köpa eller ta bort licenser för på fliken **produkter** . Välj **fler åtgärder** (tre punkter) och välj sedan **köp licenser**. [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)
3. Om du vill minska antalet licenser väljer du **ta bort licenser**högst upp i fönstret **köp licenser** .
4. För att köpa eller ta bort licenser, under **nytt antal** i rutan **Totalt antal licenser** , anger du det totala antalet licenser som du vill använda för abonnemanget. Om du till exempel har 100 licenser och vill lägga till ytterligare fem skriver du 105. Om du vill ta bort fem av dem skriver du 95.
5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.
2. På sidan **prenumerationer** väljer du den prenumeration där du vill köpa eller ta bort licenser och väljer sedan **Lägg till/ta bort licenser**. [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)
3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill använda för den här prenumerationen och väljer sedan **Skicka** \> **nära**. Om du till exempel har 100 licenser och vill lägga till ytterligare fem skriver du 105. Om du vill ta bort fem licenser skriver du 95.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.
2. På sidan **prenumerationer** väljer du den prenumeration där du vill köpa eller ta bort licenser och väljer sedan **Lägg till/ta bort licenser**. [Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?](#what-if-i-dont-see-the-addremove-licenses-link)
3. I rutan **Totalt antal licenser** anger du det totala antalet licenser som du vill använda för den här prenumerationen och väljer sedan **Skicka** \> **nära**. Om du till exempel har 100 licenser och behöver lägga till ytterligare 5 skriver du 105. Om du vill ta bort fem av dem skriver du 95.

::: moniker-end

> [!NOTE]
> Du kan inte minska antalet licenser för din prenumeration om alla licenser är tilldelade till användare. Om du vill minska antalet licenser måste du först ta bort [en eller flera licenser från användarna](../../admin/manage/remove-licenses-from-users.md)och sedan avlägsna licenser från prenumerationen.

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Vad gör jag om jag inte kan se länken Lägg till/ta bort licenser?

I den här tabellen beskrivs varför länken **Lägg till/ta bort licenser** kanske inte är tillgänglig och vad du kan göra åt det.

|Precision  |Beskrivning  |Lösning  |
|---------|---------|---------|
|En kredit kontroll pågår. |Om en kredit kontroll pågår visas meddelandet "väntande kredit kontroll". Du kan inte köpa licenser förrän kredit kontrollen är klar.  | Kom tillbaka senare för att se om kredit kontrollen är klar. Kreditkontroller tar vanligtvis upp till två arbetsdagar.<br/>När kredit kontrollen är klar ska du se länken **Lägg till/ta bort licenser** . |
|Du aktiverade prenumerationen med en produkt nyckeln.| Om prenumerationen har köpts in och Aktiver ATS med en 25-siffrig produkt nyckeln visas texten "förbetalt".  |Se [lägga till licenser för en prenumeration som betalats med en produkt nyckeln](add-licenses-using-product-key.md). |
|Du köpte ditt abonnemang via en partner. | Om prenumerationen har köpts via en partner ser du länken Volume Licensing Service Center (VLSC). | Se [lägga till licenser i en prenumeration som köpts via Volume Licensing Service Center](add-licenses-bought-through-vlsc.md). |
|Du köpte ditt abonnemang via en åter försäljare.|| Om prenumerationen har köpts via en KRYPTOGRAFIPROVIDER-partner kontaktar du din CSP-partner och köper fler licenser.        |
|Du har en prov prenumeration. |En utvärderings version av Microsoft 365 visar texten "test". | Köp din utvärderings prenumeration och sedan kan du lägga till fler licenser. Se [köpa ett abonnemang till Microsoft 365 för företag från din gratis prov period](../buy-a-subscription-from-your-free-trial.md).|

## <a name="what-you-need-to-know-about-buying-licenses-for-your-business-subscription"></a>Vad du behöver veta om att köpa licenser för ditt företags abonnemang

### <a name="license-availability"></a>Licens tillgänglighet

- **Om du har en fakturerings profil**: kredit kortet som är kopplat till din fakturerings profil så fort du köper fler licenser för en prenumeration. Dessa licenser är omedelbart tillgängliga för dig. [Vad är en fakturerings profil?](../billing-and-payments/manage-billing-profiles.md)
- **Om du inte har en betalnings profil**: om du betalar för din prenumeration med kredit-eller betalkort, eller bank konto, är alla nya licenser som du köper omedelbart tillgängliga när du har fått en beställnings bekräftelse. Om du betalar med faktura kan du behöva vänta på en kreditkontroll innan de nya licenserna är tillgängliga för användning.
  > [!NOTE]
  > Betalning med bankkonto är inte tillgängligt i vissa länder eller regioner.
- **Om du har betalat för ditt abonnemang med en produkt nyckeln**kan du lägga till fler licenser genom att lägga till ett kredit-eller betalkort, eller bank konto för att täcka avgiften för de nya licenserna. När du har köpt de nya licenserna lägger vi till en andra prenumeration med antalet nya licenser som du just har lagt till. Om du till exempel har ett förbetalt abonnemang med fem licenser och sedan köpt tio fler licenser visas två abonnemang: en med fem förbetalda licenser och en med de tio nya licenserna.

### <a name="changing-your-payment-method"></a>Ändra betalnings metod

- **Om du har en fakturerings profil**: kredit kortet som är kopplat till din fakturerings profil så fort du köper fler licenser för en prenumeration. [Vad är en fakturerings profil?](../billing-and-payments/manage-billing-profiles.md)
- **Om du inte har en fakturerings profil:** Om du betalar med kredit kort, betalkort eller bank konto kommer avgiften för att köpa nya licenser att visas på två dagar.

### <a name="billing-statements"></a>Fakturerings utdrag

- Licenser som lagts till i mitten av din fakturerings period visas på din nästa faktura. Om du betalar årligen får du en månad för dessa ändringar.
- På ditt nästa fakturerings utdrag dras den föregående avgiften för det ursprungliga antalet licenser. Vi lägger till en proportionell avgift för tids perioden med det ursprungliga antalet licenser och lägger till en avgift för det nya antalet licenser. Det finns också en avgift för det aktuella antalet licenser för resten av din fakturerings period.

## <a name="next-steps"></a>Nästa steg

Om du har köpt fler licenser för ditt abonnemang måste du [tilldela dessa licenser till användarna i organisationen](../../admin/manage/assign-licenses-to-users.md).

Om du har minskat antalet licenser för ditt abonnemang eftersom någon har lämnat organisationen kanske du vill ta bort användarens konto. Mer information finns i [ta bort en tidigare anställd](../../admin/add-users/remove-former-employee.md).

## <a name="related-content"></a>Relaterat innehåll

[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel) \
[Allmänt om prenumerationer och licenser](subscriptions-and-licenses.md) (artikel)\
[Prova eller Köp en Microsoft 365-prenumeration](../try-or-buy-microsoft-365.md) (artikel)