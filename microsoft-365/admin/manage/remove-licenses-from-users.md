---
title: Ta bort tilldelningen av licenser från användare
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- manage_licenses
- okr_smb
- commerce
search.appverid:
- MET150
description: Lär dig hur du tar bort licenser från användarkonton.
ms.date: 07/01/2020
ms.openlocfilehash: 550136c2cfa8d81a31e52a4313dc9c967a55d56e
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398199"
---
# <a name="unassign-licenses-from-users"></a>Ta bort tilldelningen av licenser från användare

Du kan ta bort licenser från användare på **sidan Aktiva** användare eller på **sidan** Licenser. Vilken metod du använder beror på om du vill ta bort licenser från specifika användare eller ta bort licenser för användare från en viss produkt.

> [!NOTE]
> Som administratör kan du inte tilldela eller ta bort licenser för en prenumeration på självbetjäning som köpts av en användare i organisationen. Du kan [ta över en prenumeration på självbetjäning och](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)sedan tilldela eller ta bort licenser.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global, licens och användaradministratör för att kunna ta bort licenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Du kan också [ta bort användarkonton](../add-users/delete-a-user.md) som har tilldelats en licens om du vill göra licensen tillgänglig för andra användare. När du tar bort ett användarkonto blir licensen direkt tillgänglig att tilldela till någon annan.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Använda sidan Licenser för att ta bort licenser

När du använder sidan **Licenser** för att ta bort licenser tar du bort licenser för en viss produkt för upp till 20 användare.

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringslicenser.**
::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan  > **Faktureringslicenser.**

::: moniker-end

2. Välj den produkt som du vill ta bort licenser för.
3. Välj de användare som du vill ta bort licenser för.
4. Välj **Ta bort licenser**.
5. Välj **Ta bort tilldelning i** rutan Ta **bort licenser.**

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Använda sidan Aktiva användare för att ta bort licenser

När du använder sidan **Aktiva användare** för att ta bort licenser tar du bort produktlicenser från användare.

### <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare
  
::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan **Fakturering** > **för aktiva** användare.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan **Fakturering** > **för aktiva** användare.

::: moniker-end

2. Markera raden för den användare som du vill ta bort en licens för.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **Licenser,** avmarkera rutorna för de licenser som du vill ta bort och välj sedan **Spara ändringar.**

###  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan **Fakturering** > **för aktiva** användare.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan **Fakturering** > **för aktiva** användare.

::: moniker-end

2. Markera cirklarna bredvid namnen på de användare som du vill ta bort licenser för.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.
5. Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryssrutan Ta bort alla **produktlicenser** från de markerade användarna och väljer sedan **Ersätt** \> **Stäng.**

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Vad händer med en användares data när du tar bort deras licens?

- När en licens tas bort från en användare lagras data som är kopplade till kontot i 30 dagar. Efter respitperioden på 30 dagar tas data bort och kan inte återställas.
- Filer som har sparats i OneDrive för företag tas inte bort såvida inte användaren tas bort från administrationscentret för Microsoft 365 eller tas bort via Active Directory-synkronisering. Mer information finns i [OneDrive-bevarande och -borttagning.](/onedrive/retention-and-deletion)
- När licensen tas bort är användarens postlåda inte längre sökbar med hjälp av ett eDiscovery-verktyg som Innehållssökning eller Avancerad eDiscovery. Mer information finns i "Söka i frånkopplade eller avlicensierade postlådor" i [Innehållssökning i Microsoft 365.](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes)
- Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise E3, kan du behålla e-postdata för ett borttagna användarkonton med hjälp av [inaktiva postlådor](../../compliance/inactive-mailboxes-in-office-365.md)i Exchange Online. Mer information finns i Skapa [och hantera inaktiva postlådor i Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)
- Information om hur du blockerar en användares åtkomst till data i Microsoft 365 efter att licensen har tagits bort, och hur du får åtkomst till data efteråt, finns i Ta bort [en tidigare anställd](../add-users/remove-former-employee.md).
- Om du tar bort en [användares](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) licens och de fortfarande har Office-program installerade visas felmeddelanden om ej licensierad produkt och aktivering i Office när de använder Office-program.

## <a name="next-steps"></a>Nästa steg

Om du inte tänker [](../../managed-desktop/get-started/assign-licenses.md)omtilldela de oanvända [](../../commerce/licenses/buy-licenses.md) licenserna till andra användare bör du ta bort licenserna från prenumerationen så att du inte betalar för fler licenser än vad som behövs.

## <a name="related-content"></a>Relaterat innehåll

[Ta bort licenser från din prenumeration](../../commerce/licenses/buy-licenses.md) (artikel)\
[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel)\
[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)