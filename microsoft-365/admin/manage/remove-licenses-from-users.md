---
title: Ta bort tilldelningen av licenser från användare
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
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Lär dig hur du tar bort licenser från användarkonton.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114483"
---
# <a name="unassign-licenses-from-users"></a>Ta bort tilldelningen av licenser från användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

Du kan ta bort licenser från användare på **sidan Aktiva** användare eller på **sidan** Licenser. Vilken metod du använder beror på om du vill ta bort produktlicenser från specifika användare eller ta bort licenser för användare från en viss produkt.

::: moniker-end

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global, licens- och användaradministratör för att kunna ta bort licenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Du kan också [ta bort användarkonton](../add-users/delete-a-user.md) som har tilldelats en licens om du vill göra licensen tillgänglig för andra användare. När du tar bort ett användarkonto blir licensen direkt tillgänglig att tilldela till någon annan.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Använda sidan Licenser för att ta bort licenser

När du använder **sidan Licenser** för att ta bort licenser tar du bort licenser för en specifik produkt för upp till 20 användare.

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.
2. Välj den produkt som du vill ta bort licenser för.
3. Välj de användare som du vill ta bort licenser för.
4. Välj **Ta bort licenser.**
5. Välj **Ta bort tilldelning i** rutan Tilldela **licenser.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Använda sidan Aktiva användare för att ta bort licenser

När du använder **sidan Aktiva användare för** att ta bort licenser, tar du bort licenser från användare.

### <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera raden för den användare som du vill ta bort en licens för.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **Licenser,** avmarkera rutorna för de licenser som du vill ta bort tilldelning av och välj sedan **Spara ändringar.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill ta bort licensen för.
3. Välj Redigera på raden **Produktlicenser** till **höger.**
4. I fönstret **Produktlicenser** ändrar du växlingsknappen till **läget** Av för den licens du vill ta bort för användaren. Om du till exempel stänger av Office 365 Enterprise, E3-licensen, tilldelas den licensen och alla tjänster under den licensen för den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill ta bort licensen för.
3. Välj Redigera på raden **Produktlicenser** till **höger.**
4. I fönstret **Produktlicenser** ändrar du växlingsknappen till **läget** Av för den licens du vill ta bort för användaren. Om du till exempel stänger av Office 365 Enterprise, E3-licensen, tilldelas den licensen och alla tjänster under den licensen för den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera cirklarna bredvid namnen på de användare som du vill ta bort licenser för.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.
5. Markera kryssrutan Ta bort **alla produktlicenser** från de markerade användarna längst ned i fönstret Ersätt befintliga produkter och välj sedan **Ersätt**  \> **stäng.**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Markera kryssrutorna för de användare som du vill ta bort licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Markera kryssrutan Ta bort alla **produktlicenser** från de markerade användarna längst ned i fönstret Ersätt befintliga  produkter och välj sedan Ersätt  \> **stäng.** \> 

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Markera kryssrutorna för de användare som du vill ta bort licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Markera kryssrutan Ta bort alla **produktlicenser** från de markerade användarna längst ned i fönstret Ersätt befintliga  produkter och välj sedan Ersätt  \> **stäng.** \> 

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Vad händer med en användares data när du tar bort användarens licens?

- När en licens tas bort från en användare lagras data som är kopplade till kontot i 30 dagar. Efter respitperioden på 30 dagar tas data bort och kan inte återskapas.
- Filer som sparats i OneDrive för företag tas inte bort såvida inte användaren tas bort från administrationscentret för Microsoft 365 eller tas bort via Active Directory-synkronisering. Mer information finns i [OneDrive för bevarande och borttagning.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- När licensen tas bort är användarens postlåda inte längre sökbar med hjälp av ett eDiscovery-verktyg som Innehållssökning eller Avancerad eDiscovery. Mer information finns i "Söka frånkopplad eller delicensierad postlåda" i [Innehållssökning i Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise, E3, kan du med Exchange Online bevara postlådedata för ett borttagna användarkonto med hjälp av [inaktiva postlådor.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Mer information finns i Skapa [och hantera inaktiva postlådor i Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- Information om hur du blockerar en användares åtkomst till Microsoft 365-data efter att licensen har tagits bort och hur du får åtkomst till data efteråt finns i Ta bort en tidigare [anställd.](../add-users/remove-former-employee.md)
- Om du tar bort en användares licens och de fortfarande har Office-program installerade visas felmeddelanden om [olicensierad](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) produkt och aktivering i Office när de använder Office-program.

## <a name="next-steps"></a>Nästa steg

Om du inte tänker [](../../managed-desktop/get-started/assign-licenses.md)tilldela de oanvända licenserna [](../../commerce/licenses/buy-licenses.md) till andra användare kan du ta bort licenserna från prenumerationen så att du inte betalar för fler licenser än vad du behöver.

## <a name="related-content"></a>Relaterat innehåll

[Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)\
[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel)\
[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)