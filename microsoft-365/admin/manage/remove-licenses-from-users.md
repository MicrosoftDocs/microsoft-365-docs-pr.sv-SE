---
title: Ta bort tilldelningen av licenser från användare
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
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Läs om hur du avtillvisar licenser från användarkonton.
ms.date: 07/01/2020
ms.openlocfilehash: 29dbdb89550d5bd9bd13071b184ffe1ca340f2a6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015941"
---
# <a name="unassign-licenses-from-users"></a>Ta bort tilldelningen av licenser från användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Du kan ta bort tilldelning av licenser från användare på sidan **Aktiva användare** eller på sidan **Licenser.** Vilken metod du använder beror på om du vill ta bort tilldelningen av produktlicenser från specifika användare eller ta bort tilldelning av användarlicenser från en viss produkt.

::: moniker-end

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global, licens, användaradministratör för att ta bort tilldelningslicenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).
- Du kan också [ta bort användarkonton](../add-users/delete-a-user.md) som har tilldelats en licens för att göra deras licens tillgänglig för andra användare. När du tar bort ett användarkonto är deras licens omedelbart tillgänglig för att tilldela någon annan.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Använd sidan Licenser för att ta bort tilldelning av licenser

När du använder sidan **Licenser** för att ta bort tilldelning av licenser avtar du licenser för en viss produkt för upp till 20 användare.

1. Gå till sidan **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret.
2. Välj den produkt som du vill ta bort licenser för.
3. Välj de användare som du vill ta bort licenser för.
4. Välj **Licenser för ta bort tilldelning**.
5. Välj **Ta bort tilldelning**i rutan Licenser för **avtilldelning** .

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Använd sidan Aktiva användare för att ta bort tilldelning av licenser

När du använder sidan **Aktiva användare** för att ta bort tilldelning av licenser avtar du produktlicenser från användare.

### <a name="unassign-licenses-from-one-user"></a>Ta bort tilldelning av licenser från en användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera raden för den användare som du vill ta bort en licens för.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **Licenser,** rensa rutorna för de licenser som du vill ta bort och välj sedan **Spara ändringar**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Ta bort tilldelning av licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill ta bort tilldelningen av licensen för.
3. Välj **Redigera**på raden **Produktlicenser** till höger .
4. I fönstret **Produktlicenser** växlar du växlingsknappen till **avpositionen** för den licens som du vill ta bort tilldelningen för användaren. Om du till exempel stänger av Office 365 Enterprise E3-licensen avtilldelningar den licensen och alla tjänster under den licensen för den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Ta bort tilldelning av licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill ta bort tilldelningen av licensen för.
3. Välj **Redigera**på raden **Produktlicenser** till höger .
4. I fönstret **Produktlicenser** växlar du växlingsknappen till **avpositionen** för den licens som du vill ta bort tilldelningen för användaren. Om du till exempel stänger av Office 365 Enterprise E3-licensen avtilldelningar den licensen och alla tjänster under den licensen för den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Ta bort tilldelning av licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera cirklarna bredvid namnen på de användare som du vill ta bort licenser för.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.
5. Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **stäng**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort tilldelning av licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Markera rutorna bredvid namnen på de användare som du vill ta bort alla licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **Close** \> **Stäng Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort tilldelning av licenser från flera användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Markera rutorna bredvid namnen på de användare som du vill ta bort alla licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Markera kryssrutan **Ta bort alla produktlicenser från de markerade användarna** längst ned i fönstret Ersätt befintliga **produkter** och välj sedan **Ersätt** \> **Close** \> **Stäng Stäng**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Vad händer med en användares data när du tar bort deras licens?

- När en licens tas bort från en användare lagras data som är associerade med det kontot i 30 dagar. Efter respitperioden på 30 dagar tas data bort och kan inte återställas.
- Filer som sparats i OneDrive för företag tas inte bort om inte användaren tas bort från administrationscentret för Microsoft 365 eller tas bort via Active Directory-synkronisering. Mer information finns i [OneDrive-lagring och borttagning](https://docs.microsoft.com/onedrive/retention-and-deletion).
- När licensen tas bort kan användarens postlåda inte längre sökas med hjälp av ett eDiscovery-verktyg som Content Search eller Advanced eDiscovery. Mer information finns i "Söka frånkopplade eller avlicensierade postlådor" i [Innehållssökning i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise E3, kan du bevara postlådedata för ett borttaget användarkonto med hjälp av [inaktiva postlådor](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Mer information finns i [Skapa och hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Mer information om hur du blockerar en användares åtkomst till Microsoft 365-data efter att licensen har tagits bort och hur du får åtkomst till data efteråt finns i [Ta bort en tidigare anställd](../add-users/remove-former-employee.md).
- Om du tar bort en användares licens och de fortfarande har Office-appar installerade visas [Olicensierade produkt- och aktiveringsfel i Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) när de använder Office-appar.

## <a name="next-steps"></a>Nästa steg

Om du inte tänker [tilldela om de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)kan du överväga att ta bort [licenserna från prenumerationen](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.

## <a name="related-content"></a>Relaterat innehåll

[Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel)\
[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel)\
[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)