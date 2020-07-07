---
title: Tilldela licenser till användare
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Lär dig hur man tilldelar licenser till användare.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015953"
---
# <a name="assign-licenses-to-users"></a>Tilldela licenser till användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Du kan tilldela licenser till användare antingen på sidan **Aktiva användare** eller på sidan **Licenser**. Metoden du använder beror på om du vill tilldela produktlicenser till särskilda användare eller tilldela licenser för en särskild produkt till användare.

::: moniker-end

[Läs om hur du lägger till ett användare och tilldelar en licens samtidigt](../add-users/add-users.md).

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global-, licens- eller användaradministratör för att tilldela licenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [tilldela licenser till användarkonton med Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).
- Information om hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
- Vissa tjänster, till exempel Sway, tilldelas automatiskt till användarna och behöver inte tilldelas individuellt.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Använd sidan licenser för att tilldela licenser till användare

När du tilldelar licenser på sidan **Licenser** tilldelar du licenser för en särskild produkt till upp till 20 användare. På sidan **Licenser** ser du en lista över alla produkter som du har prenumerationer för. Du ser också det totala antalet licenser för varje produkt, hur många licenser som har tilldelats och hur många som är tillgängliga.

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.
2. Välj en produkt.
3. Välj **Tilldela licenser**på sidan produktinformation.
4. I fönstret **Tilldela licenser till användare** börjar du skriva ett namn och väljer sedan namnet från resultatet för att lägga till det i listan. Du kan lägga till upp till 20 användare åt gången.
5. Välj **Aktivera eller inaktivera appar och tjänster** för att tilldela eller ta bort åtkomst till särskilda objekt.
6. När du är klar väljer du **Tilldela** och sedan **Stäng**.

Vid konflikt visas ett meddelande som talar om vad problemet är och hur du åtgärdar det. Om du till exempel valt licenser där det finns tjänster som är i konflikt, står det i meddelandet att du ska granska de tjänster som ingår i varje licens och försöka igen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Ändra de appar och tjänster som en användare har åtkomst till:

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.
2. På sidan **Licenser** väljer du raden för en enskild användare.
3. I det högra fönstret markerar eller avmarkerar du de appar och tjänster som du vill ge åtkomst till eller ta bort åtkomst för.
4. När du är klar väljer du **Spara** och sedan **Stäng**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Använd sidan Aktiva användare för att tilldela licenser

När du använder sidan **Aktiva användare** för att tilldela licenser tilldelar du användarlicenser till produkter.

### <a name="assign-licenses-to-multiple-users"></a>Tilldela licenser till flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera cirklarna bredvid namnen på de användare som du vill tilldela licenser till.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.
5. I fönstret **Lägg till i befintliga produkter** ställer du reglaget i läget **På** för den licens som du vill att de valda användarna ska ha.\
    Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna. Du kan begränsa vilka tjänster som är tillgängliga för användarna. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.
6. Längst ned i fönstret väljer du **Lägg till** \> **Stäng**.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Tilldela licenser till flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Markera kryssrutorna bredvid namnen på de användare som du vill tilldela licenser till.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Tilldela produkter** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.
5. Ställ reglaget i läget **På** för de licenser som du vill att de valda användarna ska ha.\
    Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna. Du kan begränsa vilka tjänster som är tillgängliga för användarna. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.
6. Längst ned i fönstret **Lägg till i befintliga produkter** väljer du **Lägg till** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Tilldela licenser till flera användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Markera kryssrutorna bredvid namnen på de användare som du vill tilldela licenser till.
3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.
4. I fönstret **Tilldela produkter** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.
5. Ställ reglaget i läget **På** för de licenser som du vill att de valda användarna ska ha.\
    Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna. Du kan begränsa vilka tjänster som är tillgängliga för användarna. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.
6. Längst ned i fönstret **Lägg till i befintliga produkter** väljer du **Lägg till** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Tilldela licenser till en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markerar raden för den användare som du vill tilldela en licens till.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **Licenser**, markera kryssrutorna för de licenser som du vill tilldela och välj sedan **Spara ändringar**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Tilldela licenser till en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.
2. Markera kryssrutan bredvid namnet på den användare som du vill tilldela en licens till.
3. I det högra fönstret väljer du **Redigera** på raden **Produktlicenser**.
4. I fönstret **Produktlicenser** flyttar du reglaget till positionen **På** för den licens du vill tilldela användaren\
    Som standard är tilldelas alla tjänster som är associerade till den licensen automatiskt till användaren. Du kan begränsa vilka tjänster som är tillgängliga för användaren. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användaren ska ha.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Tilldela licenser till en användare

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.
2. Markera kryssrutan bredvid namnet på den användare som du vill tilldela en licens till.
3. I det högra fönstret väljer du **Redigera** på raden **Produktlicenser**.
4. I fönstret **Produktlicenser** flyttar du reglaget till positionen **På** för den licens du vill tilldela användaren\
    Som standard är tilldelas alla tjänster som är associerade till den licensen automatiskt till användaren. Du kan begränsa vilka tjänster som är tillgängliga för användaren. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användaren ska ha.
5. Längst ned i fönstret **Produktlicenser** väljer du **Spara** \> **Stäng** \> **Stäng**.

::: moniker-end

## <a name="next-steps"></a>Nästa steg

Om dina användare inte har installerat Office-apparna kan du dela [snabbstartsguide för anställda](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) med dina användare att konfigurera saker, t. ex. [hur du laddar ned och installerar Microsoft 365 eller Office 2019 på en PC-eller Mac-](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och [hur du konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Relaterat innehåll

[Allmänt om prenumerationer och licenser](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)\
[Ta bort tilldelningen av licenser från användare](remove-licenses-from-users.md) (artikel)\
[Köpa eller ta bort licenser för prenumerationen](../../commerce/licenses/buy-licenses.md) (artikel)