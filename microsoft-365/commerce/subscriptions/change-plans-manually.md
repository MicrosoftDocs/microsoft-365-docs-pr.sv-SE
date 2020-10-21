---
title: Ändra Microsoft 365 för företag-abonnemang manuellt
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Ändra abonnemangen manuellt genom att köpa ett nytt abonnemang och kontrol lera att både abonnemangen är listade och aktiva.
ms.openlocfilehash: 09557b3556db1e6f17d7a4cd54a88ba34d0f0bd7
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647825"
---
# <a name="change-plans-manually"></a>Ändra abonnemang manuellt

## <a name="step-1-decide-how-to-change-plans"></a>Steg 1: Bestäm hur du vill ändra abonnemang

Det bästa sättet att ändra alla användare från ett abonnemang till ett annat är att [använda fliken uppgradering](upgrade-to-different-plan.md). Ibland är det inte möjligt. Ändra abonnemang manuellt i stället:

- Om fliken **uppgradering** visar att du inte kan uppgradera den aktuella planen.

- Om du väljer fliken **uppgradering** visas inte det abonnemang du vill använda.

- Om du inte vill uppgradera alla användare på samma sätt. Vissa företag behöver ha olika abonnemang för olika användare. Använd en manuell ändring för detta.

Om du vill fortsätta med en manuell ändring läser du [steg 2: Köp ett nytt abonnemang](#step-2-buy-a-new-subscription) i det här avsnittet.

> [!IMPORTANT]
> Om du byter till en plan med färre data-relaterade tjänster än den aktuella planen (nedgradering) måste du säkerhetskopiera alla data du vill behålla manuellt. Mer information finns i [säkerhetskopiera data innan du byter abonnemang](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Steg 2: Köpa en ny prenumeration

**Har du redan köpt en prenumeration?** Om du redan har en prenumeration som du vill flytta användare till hoppar du över det här steget och går till [steg 3: kontrol lera din nya prenumeration och dina licenser](#step-3-check-your-new-subscription-and-licenses) i det här avsnittet.

ELLER

**Köp ett nytt abonnemang och licenser:** Följ stegen i [köpa en annan Microsoft 365 för företag-prenumeration](../buy-another-subscription.md) för att köpa en ny prenumeration.

Se till att du köper en prenumeration för samma organisation som användarna finns i nu. Kontrol lera till exempel e-postadresserna för de användare som du vill flytta. Om deras e-postadresser innehåller \@ contoso.com måste du köpa ett nytt abonnemang för contoso.com.
Ta med en licens för varje användare som du vill flytta.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Steg 3: Kontrollera din nya prenumeration och dina nya licenser

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.

2. **Kontrol lera att båda prenumerationerna visas och är aktiva** Prenumerationen som du flyttar användare från och det abonnemang du flyttar användarna till måste finnas med i listan. Om den nya prenumerationen inte finns när du kontrollerar först försöker du igen senare. Kontrol lera att båda abonnemangen är aktiva. [Den nya prenumerationen visas inte eller är inte aktiv.](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Kontrol lera att du har tillräckligt många licenser för varje användare** Varje användare behöver en licens som matchar deras prenumeration. Så om du vill flytta tio användare till Microsoft 365 Business Premium måste du kontrol lera att det finns tio licenser.

4. **Behöver du köpa fler licenser för den nya prenumerationen?**
   Gå till sidan **produkter** och [köp fler licenser](../licenses/buy-licenses.md).

> [Vad gäller för de gamla licenserna?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Den nya prenumerationen visas inte eller är inte aktiv.

- **Om du har köpt två prenumerationer och båda inte visas här** kan de ha köpts för olika organisationer (för olika domäner). Prenumerationer kan inte användas över organisationsgränser.

- **Om du vet att du har ytterligare en prenumeration**, och den inte visas här eller inte är aktiv, kan du [ringa Microsoft Support](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Vad gäller för de gamla licenserna?

Licenser för den aktuella prenumerationen tas bort senare. Du betalar då bara för de nya licenserna.

## <a name="step-4-reassign-licenses"></a>Steg 4: Fördela om licenser

### <a name="reassign-a-license-for-one-user"></a>Fördela om en licens för en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. På sidan **aktiva användare** väljer du den användare som du vill tilldela en licens till.

3. Fliken te- **licenser och-appar** , expandera **licenser**, markera rutorna för de licenser som du vill tilldela och välj sedan **Spara ändringar**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Tilldela om licenser för flera användare samtidigt

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Välj cirklarna bredvid namnen på de användare som du vill ersätta befintliga licenser för.

3. Högst upp väljer du **fler alternativ** (**...**) och väljer sedan **Hantera produkt licenser**.

4. Välj **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.

5. Ställ reglaget i läget **På** för de produkter du vill lägga till för dessa användare.

    > [!TIP]
    > - Om du vill begränsa vilka tjänster som är tillgängliga för användaren drar du reglaget till positionen **Av** för de tjänster som du vill ta bort för den användaren. Om du till exempel vill att användaren ska ha tillgång till alla tillgängliga tjänster utom Skype för företag - Online kan du flytta reglaget för tjänsten Skype för företag - Online till positionen **Av**.
    > - Alla tidigare tilldelade licenser för de markerade användarna tas bort.

6. Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Steg 5: Avbryt prenumerationer eller ta bort licenser som du inte längre behöver (valfritt)

Om du har flyttat alla användare från ett abonnemang till ett annat och du inte behöver det ursprungliga abonnemanget längre kan du [avbryta abonnemanget](cancel-your-subscription.md).

Om du bara har flyttat vissa användare till en annan prenumeration kan du [ta bort licenser](../licenses/remove-licenses-from-subscription.md) som du inte längre behöver.

## <a name="call-support-to-help-you-change-plans"></a>Ring support för att hjälpa dig att ändra abonnemang
[Ring Microsoft Support](../../admin/contact-support-for-business-products.md)