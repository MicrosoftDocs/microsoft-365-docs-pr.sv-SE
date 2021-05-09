---
title: Tilldela licenser till användare
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: Lär dig hur man tilldelar licenser till användare.
ms.openlocfilehash: ae088ab5c26df9b782bd4433bbd0c9f2d0ed9348
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274382"
---
# <a name="assign-licenses-to-users"></a>Tilldela licenser till användare

Du kan tilldela licenser till användare antingen på sidan **Aktiva användare** eller på sidan **Licenser**. Metoden du använder beror på om du vill tilldela produktlicenser till särskilda användare eller tilldela licenser för en särskild produkt till användare.

> [!NOTE]
> Som administratör kan du inte tilldela eller ta bort licenser för en självbetjäningsprenumeration som köpts av en användare i din organisation. Du kan [ta över en självbetjäningsprenumeration](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)och sedan tilldela eller ta bort licenser.

[Läs om hur du lägger till ett användare och tilldelar en licens samtidigt](../add-users/add-users.md).

## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara global-, licens- eller användaradministratör för att tilldela licenser. Mer information finns i [Om Microsoft 365-administratörsroller](../add-users/about-admin-roles.md).
- Du kan [tilldela Microsoft 365-licenser till användarkonton med PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Information om hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)
- Vissa tjänster, till exempel Sway, tilldelas automatiskt till användarna och behöver inte tilldelas individuellt.


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Använd sidan licenser för att tilldela licenser till användare

När du tilldelar licenser på sidan **Licenser** tilldelar du licenser för en särskild produkt till upp till 20 användare. På sidan **Licenser** ser du en lista över alla produkter som du har prenumerationer för. Du ser också det totala antalet licenser för varje produkt, hur många licenser som har tilldelats och hur många som är tillgängliga.

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.
::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.

::: moniker-end

2. Välj en produkt.
3. Välj **Tilldela licenser** på sidan produktinformation.
4. I fönstret **Tilldela licenser till användare** börjar du skriva ett namn och väljer sedan namnet från resultatet för att lägga till det i listan. Du kan lägga till upp till 20 användare åt gången.
4. Välj **Aktivera eller inaktivera appar och tjänster** för att tilldela eller ta bort åtkomst till särskilda objekt.
6. När du är klar väljer du **Tilldela** och sedan **Stäng**.

Vid konflikt visas ett meddelande som talar om vad problemet är och hur du åtgärdar det. Om du till exempel valt licenser där det finns tjänster som är i konflikt, står det i meddelandet att du ska granska de tjänster som ingår i varje licens och försöka igen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Ändra de appar och tjänster som en användare har åtkomst till:

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscenter</a> gå till sidan för **Fakturering**>**Licenser**.

::: moniker-end

2. På sidan **Licenser** väljer du raden för en enskild användare.
3. I det högra fönstret markerar eller avmarkerar du de appar och tjänster som du vill ge åtkomst till eller ta bort åtkomst för.
4. När du är klar väljer du **Spara** och sedan **Stäng**.

## <a name="use-the-active-users-page-to-assign-licenses"></a>Använd sidan Aktiva användare för att tilldela licenser

När du använder sidan **Aktiva användare** för att tilldela licenser tilldelar du användarlicenser till produkter.

### <a name="assign-licenses-to-multiple-users"></a>Tilldela licenser till flera användare

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.

::: moniker-end

2. Markera cirklarna bredvid namnen på de användare som du vill tilldela licenser till.
3. Välj **Fler alternativ (...)** högst upp och välj sedan **Hantera produktlicenser**.
4. I fönstret **Hantera produktlicenser** väljer du **Lägg till i befintliga produktlicenstilldelningar** \> **Nästa**.
5. I fönstret **Lägg till i befintliga produkter** ställer du reglaget i läget **På** för den licens som du vill att de valda användarna ska ha.\
    Som standard tilldelas alla tjänster, som är associerade till de licenserna, automatiskt till användarna. Du kan begränsa vilka tjänster som är tillgängliga för användarna. Ställ reglagen i läget **Av** för de tjänster som du inte vill att användarna ska ha.
6. Längst ned i fönstret väljer du **Lägg till** \> **Stäng**.  


> [!NOTE]
> Om du vill tilldela licenser för ett stort antal användare använder du [Tilldela användarlicenser efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-assign)

### <a name="assign-licenses-to-one-user"></a>Tilldela licenser till en användare

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> går du till sidan **Fakturering** > **Aktiva användare**.

::: moniker-end

2. Markerar raden för den användare som du vill tilldela en licens till.
3. I det högra fönstret väljer du **Licenser och appar**.
4. Expandera avsnittet **Licenser**, markera kryssrutorna för de licenser som du vill tilldela och välj sedan **Spara ändringar**.

## <a name="assign-a-license-to-a-guest-user"></a>Tilldela en licens till en gästanvändare

Du kan bjuda in gästanvändare att samarbeta med din organisation i Azure Active Directory administrationscenter. För information om gästanvändaren, se [Vad är gästanvändaråtkomst i Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b). Om du inte har någon gästanvändare se [Snabb start: lägga till gästanvändare i katalogen i Azure-portalen](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

> [!IMPORTANT]
> Du måste vara en global administratör för att utföra de här stegen.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory-administratörcenter</a>
2. Välj **Användare** i navigeringsfönstret.
3. På **Användare | Alla användare (Förhandsgranskning)** sidan väljer du **Lägg till filter**.
4. I **Välj ett fält** väljer du **Användartyp** och sedan **Verkställ**.
5. I nästa meny väljer du **Gäst**.
6. Välj den användare som behöver en licens i resultatlistan.
7. Under **Hantera** väljer du **Licenser**.
8. Välj **Uppgifter**.
9. På sidan **Uppdatera licenstilldelningar** väljer du den produkt som du vill tilldela en licens för.
10. Gå till höger och avmarkera kryssrutorna för de tjänster som du inte vill att gäst användaren ska ha tillgång till.
11. Välj **Spara**.

## <a name="next-steps"></a>Nästa steg

Om dina användare inte har installerat Office-apparna kan du dela [snabbstartsguide för anställda](../../business-video/employee-quick-setup.md) med dina användare att konfigurera saker, t. ex. [hur du laddar ned och installerar Microsoft 365 eller Office 2019 på en PC-eller Mac-](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och [hur du konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Relaterat innehåll

[Allmänt om prenumerationer och licenser](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)\
[Ta bort tilldelningen av licenser från användare](remove-licenses-from-users.md) (artikel)\
[Köpa eller ta bort licenser för prenumerationen](../../commerce/licenses/buy-licenses.md) (artikel)
