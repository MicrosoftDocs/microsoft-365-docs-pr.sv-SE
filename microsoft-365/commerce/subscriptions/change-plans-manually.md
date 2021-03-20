---
title: Ändra abonnemang för Microsoft 365 för företag manuellt
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
description: Ändra prenumerationer manuellt genom att köpa en ny prenumeration och se till att båda prenumerationerna visas och är aktiva.
ms.openlocfilehash: d6b0c822f9d3ceeb6c50a6ec872682d1db5decb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907910"
---
# <a name="change-plans-manually"></a>Ändra abonnemang manuellt

## <a name="step-1-decide-how-to-change-plans"></a>Steg 1: Bestäm hur du vill ändra abonnemang

Det bästa sättet att ändra alla dina användare från ett abonnemang till ett annat är [att använda fliken Uppgradera.](upgrade-to-different-plan.md) Ibland går inte det. Ändra abonnemang manuellt i stället:

- Om fliken **Uppgradera** anger att du inte kan uppgradera det aktuella abonnemanget.

- Om du väljer fliken **Uppgradera visas** inte det abonnemang du vill använda.

- Om du inte vill uppgradera alla användare på samma sätt. Vissa företag behöver ha olika abonnemang för olika användare. Gör en manuell ändring för detta.

Om du vill fortsätta med en manuell ändring läser du [Steg 2: Köpa en ny prenumeration i](#step-2-buy-a-new-subscription) det här avsnittet.

> [!IMPORTANT]
> Om du ändrar till ett abonnemang med färre datarelaterade tjänster än det aktuella abonnemanget (nedgradering) måste du manuellt era data som du vill behålla. Mer information finns i [Lagra data innan du ändrar abonnemang.](back-up-data-before-switching-plans.md)

## <a name="step-2-buy-a-new-subscription"></a>Steg 2: Köpa en ny prenumeration

**Har du redan köpt en prenumeration?** Om du redan har en prenumeration som du vill flytta användare till hoppar du över det här steget och går till Steg [3:](#step-3-check-your-new-subscription-and-licenses) Kontrollera din nya prenumeration och dina nya licenser i det här avsnittet.

ELLER

**Köp en ny prenumeration och nya licenser:** Följ anvisningarna i [Köpa en annan Microsoft 365 för företag-prenumeration om](../try-or-buy-microsoft-365.md) du vill köpa en ny prenumeration.

Se till att du köper en prenumeration för samma organisation som användarna finns i nu. Kontrollera till exempel e-postadresserna för de användare som du vill flytta. Om e-postadresserna \@ innehåller contoso.com måste du köpa en ny prenumeration för contoso.com.
Ta med en licens för varje användare som du vill flytta.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Steg 3: Kontrollera din nya prenumeration och dina nya licenser

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.

2. **Kontrollera att båda prenumerationerna visas och är aktiva** Den prenumeration du flyttar användare från och den prenumeration som du flyttar användare till måste listas tillsammans. Om den nya prenumerationen inte finns när du kontrollerar först försöker du igen senare. Kontrollera att båda prenumerationerna är aktiva. [Den nya prenumerationen visas inte eller är inte aktiv.](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Kontrollera att du har tillräckligt med licenser för varje användare** Varje användare måste ha en licens som överensstämmer med prenumerationen. Om du vill flytta tio användare till Microsoft 365 Business Premium måste du se till att tio licenser är tillgängliga.

4. **Behöver du köpa fler licenser för den nya prenumerationen?**
   Gå till sidan **Dina produkter** och köp [fler licenser.](../licenses/buy-licenses.md)

> [Vad gäller för de gamla licenserna?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Den nya prenumerationen visas inte eller är inte aktiv.

- **Om du har köpt två prenumerationer och båda inte visas här** kan de ha köpts för olika organisationer (för olika domäner). Prenumerationer kan inte användas över organisationsgränser.

- **Om du vet att du har ytterligare en** prenumeration och den inte finns med här, eller om den inte är aktiv, ringer du Microsoft [support.](../../admin/contact-support-for-business-products.md)

### <a name="what-about-the-old-licenses"></a>Vad gäller för de gamla licenserna?

Licenser för den aktuella prenumerationen tas bort senare. Du betalar då bara för de nya licenserna.

## <a name="step-4-reassign-licenses"></a>Steg 4: Fördela om licenser

### <a name="reassign-a-license-for-one-user"></a>Fördela om en licens för en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva** användare väljer du den användare som du vill tilldela en licens till.

3. På fliken **Licenser och appar** expanderar du **Licenser**, markerar rutorna för de licenser som du vill tilldela och väljer sedan **Spara ändringar.**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Tilldela om licenser för flera användare samtidigt

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

2. Markera cirklarna bredvid namnen på de användare som du vill ersätta befintliga licenser för.

3. Högst upp väljer du **Fler alternativ** (**...**) och sedan **Hantera produktlicenser.**

4. Välj **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.

5. Ställ reglaget i läget **På** för de produkter du vill lägga till för dessa användare.

    > [!TIP]
    > - Om du vill begränsa vilka tjänster som är tillgängliga för användaren drar du reglaget till positionen **Av** för de tjänster som du vill ta bort för den användaren. Om du till exempel vill att användaren ska ha tillgång till alla tillgängliga tjänster utom Skype för företag - Online kan du flytta reglaget för tjänsten Skype för företag - Online till positionen **Av**.
    > - Alla tidigare tilldelade licenser för de markerade användarna tas bort.

6. Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Steg 5: Avbryt prenumerationer eller ta bort licenser som du inte längre behöver (valfritt)

Om du har flyttat alla användare från ett abonnemang till ett annat och du inte behöver det ursprungliga abonnemanget längre kan du [avbryta abonnemanget](cancel-your-subscription.md).

Om du bara har flyttat vissa användare till en annan prenumeration kan du [ta bort licenser](../licenses/buy-licenses.md) som du inte längre behöver.

## <a name="call-support-to-help-you-change-plans"></a>Ring supporten som hjälper dig att byta abonnemang
[Kontakta Microsoft Support](../../admin/contact-support-for-business-products.md)