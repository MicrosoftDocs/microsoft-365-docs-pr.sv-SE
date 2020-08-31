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
description: Lär dig hur du tar bort tilldelning av licenser från användar konton.
ms.date: 07/01/2020
ms.openlocfilehash: 4441fd253c4cf5304562900bf31869eb4e0f21ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306545"
---
# <a name="unassign-licenses-from-users"></a>Ta bort tilldelningen av licenser från användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Du kan ta bort licenser från användare på sidan **aktiva användare** eller på sidan **licenser** . Vilken metod du använder beror på om du vill ta bort tilldelning av produkt licenser från specifika användare eller ta bort licenser för användare från en viss produkt.

::: moniker-end

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global licens och användar administratör för att ta bort licenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [ta bort licenser från användarkonton med Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Du kan också [ta bort användar konton](../add-users/delete-a-user.md) som har tilldelats en licens om du vill göra licensen tillgänglig för andra användare. När du tar bort ett användar konto är deras licens omedelbart tillgänglig och kan kopplas till någon annan.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Använd sidan licenser för att ta bort licenser

När du använder sidan **licenser** för att ta bort licenser tar du bort licenser för en viss produkt för upp till 20 användare.

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.
2. Välj den produkt som du vill ta bort tilldelning av licenser för.
3. Välj de användare som du vill ta bort tilldelning av licenser för.
4. Välj **ta bort licenser**.
5. Välj **ta bort tilldelning**i rutan **ta bort licenser** .

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Använd sidan aktiva användare för att ta bort licenser

När du använder sidan **aktiva användare** för att ta bort licenser tar du bort produkt licenser från användare.

### <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera raden för den användare som du vill ta bort en licens för.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **licenser** , avmarkera rutorna för de licenser du vill ta bort och välj sedan **Spara ändringar**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill koppla licensen för.
3. Välj **Redigera**till höger på raden **produkt licenser** .
4. I fönstret **produkt licenser** växlar du växlings knappen till **utanför** position för den licens du vill ta bort. Om du till exempel stänger av licensen för Office 365 Enterprise, E3 tilldelar den licensen och alla tjänster under den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Ta bort licenser från en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Välj den användare som du vill koppla licensen för.
3. Välj **Redigera**till höger på raden **produkt licenser** .
4. I fönstret **produkt licenser** växlar du växlings knappen till **utanför** position för den licens du vill ta bort. Om du till exempel stänger av licensen för Office 365 Enterprise, E3 tilldelar den licensen och alla tjänster under den användaren.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Välj cirklarna bredvid namnen på de användare som du vill ta bort licenser för.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Ersätt befintliga produktlicenstilldelningar** \> **Nästa**.
5. Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Markera kryss rutorna för de användare som du vill ta bort alla licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Ta bort licenser från flera användare
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Markera kryss rutorna för de användare som du vill ta bort alla licenser för.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Ersätt befintliga produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.
5. Längst ned i fönstret **Ersätt befintliga produkter** markerar du kryss rutan **ta bort alla produkt licenser från de markerade användarna** och väljer sedan **Ersätt** \> **Stäng** \> **Stäng**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Vad händer med en användares data när de tar bort sin licens?

- När en licens tas bort från en användare sparas data som är kopplade till kontot i 30 dagar. Efter 30 dagars perioden raderas data och kan inte återställas.
- Filer som sparats i OneDrive för företag tas inte bort om användaren inte tas bort från Microsoft 365 Admin Center eller tas bort med Active Directory-synkronisering. Mer information finns i [OneDrive-bevarande och borttagning](https://docs.microsoft.com/onedrive/retention-and-deletion).
- När licensen tas bort är användarens post låda inte längre sökbar genom att använda ett eDiscovery-verktyg som innehålls sökning eller Avancerad eDiscovery. Mer information finns i "söka efter frånkopplade eller de licensierade postlådor" i [innehålls sökning i Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Om du har en Enterprise-prenumeration, till exempel Office 365 Enterprise E3, kan du använda Exchange Online för att bevara post lådorna för ett borttaget användar konto med hjälp av [inaktiva post lådor](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Mer information finns i [skapa och hantera inaktiva post lådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Information om hur du blockerar en användares åtkomst till Microsoft 365-data efter att den har tagits bort och hur du får till gång till informationen finns i [ta bort en tidigare anställd](../add-users/remove-former-employee.md).
- Om du tar bort en användares licens och de fortfarande har Office-appar installerade visas olicensierad [produkt och aktiverings fel i Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) när de använder Office-appar.

## <a name="next-steps"></a>Nästa steg

Om du inte ska [koppla de oanvända licenserna till andra användare](../../managed-desktop/get-started/assign-licenses.md)bör du överväga att [ta bort licenserna från ditt abonnemang](../../commerce/licenses/buy-licenses.md) så att du inte betalar för fler licenser än du behöver.

## <a name="related-content"></a>Relaterat innehåll

[Ta bort licenser från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md) (artikel) \
[Tilldela licenser till användare](assign-licenses-to-users.md) (artikel) \
[Förstå prenumerationer och licenser i Microsoft 365 för företag](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)