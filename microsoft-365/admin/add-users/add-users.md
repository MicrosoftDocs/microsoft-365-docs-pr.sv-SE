---
title: Lägga till användare och tilldela licenser
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
description: Varje teammedlem behöver ett användarkonto innan de kan logga in och komma åt Microsoft 365 för företag. Så här lägger du till användare och tilldelar licenser.
ms.date: 07/01/2020
ms.openlocfilehash: 390576f46bed57929471b16848f9e1fd7e95304d
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536004"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Lägga till användare och tilldela licenser samtidigt

Alla i din grupp behöver varsitt användarkonto innan de kan logga in och använda [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/business). Det enklaste sättet att lägga till användarkonton är att lägga till ett i taget i administrationscentret för Microsoft 365. När det är klart har användarna fått en Microsoft 365-licens, inloggningsuppgifter och en Office 365-postlåda.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global-, licens- eller användaradministratör för att tilldela licenser. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-user-in-the-admin-simplified-view"></a>Lägga till en användare i den förenklade vyn för administratörer

Om du ser den här sidan i administrationscentret är du på den **förenklade vyn för administratörer**. Lär dig hur du gör det genom att lägga till en användare.

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="Skärmbild: förenklad vy för administratörer":::

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <https://admin.microsoft.com>.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Välj **Skapa ett konto för en annan person**.
3. På sidan **Lägg till ett användarkonto** fyller du i för- och efternamn, visningsnamn och användarnamn som de använder för att logga in.
4. Lägg till användarens e-postadress i textrutan **Upp till 5 e-postadresser**. På så sätt ser du till att den nya användaren får den information de behöver för att logga in på Microsoft 365-tjänsterna.
5. Välj **Lägg till användare** och **Ned inloggningsinformation** om du vill spara den här informationen.

## <a name="watch-add-users-in-the-dashboard-view"></a>Video: Lägga till användare i Instrumentpanelsvy

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Stegen som används i videon visar en annan utgångspunkt för att lägga till användare, men de återstående stegen är desamma som i följande procedur.

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>Lägga till en användare i taget i instrumentpanelsvy

:::image type="content" source="../../media/classic-admin-center.png" alt-text="Skärmbild: Instrumentpanelsvy i administrationscentret":::

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <https://admin.microsoft.com>.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Gå till **Användare** > **Aktiva användare** och välj **Lägg till en användare**.
3. Fyll i grundläggande användarinformation i fönstret **Konfigurera grunderna** och välj sedan **Nästa**.
    - **Namn** Fyll i för- och efternamn, visningsnamn och användarnamn.
    - **Domän** Välj domänen för användarens konto.Om användarens användarnamn till exempel är Jakob och domänen är contoso.com loggar hen in med hjälp av jakob@contoso.com.
    - **Lösenordsinställningar** Välj att använda det automatiskt genererade lösenordet eller skapa ett eget starkt lösenord för användaren.
    - Användaren måste ändra sitt lösenord efter 90 dagar. Du kan även välja att **Uppmana användaren att byta lösenord vid första inloggningen**.
    - Välj om du vill skicka lösenordet via e-post när användaren läggs till.
4. I fönstret **Tilldela produktlicenser** väljer du plats och rätt licens för användaren. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser. Visa menyn **Appar** och markera eller avmarkera appar för att begränsa vilka appar användaren har en licens för. Välj **Nästa**.
5. I fönstret **Valfria inställningar** visar du menyn **Roller** för att göra användaren till administratör. Visa menyn **Profilinformation** för att lägga till ytterligare information om användaren.
6. Välj **Nästa**, granska inställningarna för din nya användare, gör eventuella ändringar du vill göra och välj sedan **Slutför tillägg** och sedan **Stäng**.

## <a name="add-multiple-users-at-the-same-time"></a>Lägga till flera användare samtidigt

Du kan använda någon av följande metoder för att lägga till flera användare samtidigt:

- **Masstillägg av användare med hjälp av ett kalkylblad.** Se [Lägga till flera användare samtidigt](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatisera processen att lägga till och tilldela licenser.** Se [Skapa användarkonto med Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Välj det här alternativet om du redan vet hur du använder cmdlets i Windows PowerShell.
- **Använder du ActiveDirectory?**[Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Använd verktyget Azure AD Connect för att kopiera Active Directory-användarkonton (och andra Active Directory-objekt) i Microsoft 365. Synkroniseringen lägger bara till användarkonton. Du behöver tilldela licenser till de synkroniserade användarna för att de ska kunna använda e-post och andra Office-program.
- **Migrerar du från Exchange?** Se [Olika sätt att migrera flera e-postkonton till Office 365](/Exchange/mailbox-migration/mailbox-migration). Om du migrerar flera postlådor till Microsoft 365 med hjälp av snabbmigrering, stegvis migrering eller en hybrid Exchange-metod kommer du att lägga till användare automatiskt som en del av migreringen. Migreringen lägger bara till användarkonton. Du behöver tilldela licenser till användarna för att de ska kunna använda e-post och andra Office-program. Om du inte tilldelar en licens till en användare inaktiveras postlådan efter en tidsfrist på 30 dagar. Lär dig hur [tilldelar licenser till användare](../manage/assign-licenses-to-users.md) i administrationscentret för Microsoft 365.

## <a name="next-steps"></a>Nästa steg

Efter du lagt till en användare får du en avisering från Microsoft via e-post. E-postmeddelandet innehåller personens användar-ID och lösenord för så att hen kan logga in på Microsoft 365. Använd din vanliga process för att förmedla nya lösenord. Om dina användare inte har installerat Office-apparna kan du dela [snabbstartsguiden för anställda](../../business-video/employee-quick-setup.md) med dina användare för att konfigurera saker, t. ex. hur man [laddar ned och installerar Office-program på PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och hur man [konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Relaterat innehåll

[Lägga till en ny anställd i Microsoft 365](add-new-employee.md) (artikel)\
[Lägga till flera användare samtidigt i Microsoft 365 för](../../enterprise/add-several-users-at-the-same-time.md) (artikel)\
[Återställa en användare i Microsoft 365](restore-user.md) (artikel)\
[Tilldela licenser till användare](../manage/assign-licenses-to-users.md) (artikel)\
[Ta bort en användare från organisationen](delete-a-user.md) (artikel)
