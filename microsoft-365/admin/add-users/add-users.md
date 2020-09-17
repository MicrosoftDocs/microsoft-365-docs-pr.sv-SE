---
title: Lägga till användare och tilldela licenser
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Lär dig hur du lägger till användare och tilldelar licenser till Microsoft 365 samtidigt.
ms.date: 07/01/2020
ms.openlocfilehash: 95f84ead009b7510699e467bf5f12bf32d8097d8
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948802"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Lägga till användare och tilldela licenser samtidigt

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Personerna i gruppen behöver ett användar konto innan de kan logga in och komma åt [Microsoft 365 för företag](https://www.microsoft.com/microsoft-365/business). Det enklaste sättet att lägga till användar konton är att lägga till ett i taget i administrations centret för Microsoft 365. När du har gjort det här har användarna Microsoft 365-licenser, inloggnings uppgifter och Microsoft 365-postlådor.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global, licens eller en användar administratör för att lägga till användare och tilldela licenser. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Titta på: lägga till användare i administrations centret

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Stegen i videon visar en annan start punkt för att lägga till användare, men de återstående stegen är desamma som i den här proceduren.

## <a name="add-users-one-at-a-time"></a>Lägga till en användare åt gången

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <https://admin.microsoft.com>.
2. Gå till **användare** > **aktiva användare**och välj **Lägg till en användare**.
3. Fyll i grundläggande användar information i fönstret **Konfigurera grunderna** och välj **Nästa**.
    - **Namn** Fyll i för-och efter namn, visnings namn och användar namn.
    - **Domän** Välj domänen för användarens konto. Om användarens användar namn till exempel är Jakob och domänen är contoso.com loggar de in med jakob@contoso.com.
    - **Lösen ords inställningar** Välj att använda det automatiskt genererade lösen ordet eller för att skapa ett eget starkt lösen ord för användaren.
    - Användaren måste ändra sitt lösen ord efter 90 dagar. Eller så kan du välja att **begära att användaren ändrar sitt lösen ord när de loggar in för första gången**.
    - Välj om du vill skicka lösen ordet i e-post när användaren läggs till.
4. I fönstret **tilldela produkt licenser** väljer du platsen och lämplig licens för användaren. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser. Expandera **appar** och markera eller avmarkera appar för att begränsa vilka program användaren har en licens för. Välj **Nästa**.
5. I fönstret med **valfria inställningar** expanderar du **roller** för att göra användaren till administratör. Expandera **profil information** för att lägga till ytterligare information om användaren.
6. Välj **Nästa**, granska den nya användarens inställningar, gör de ändringar du vill och välj sedan **Slutför tillägg**och **Stäng**.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till administrationscentret på <https://portal.office.de/adminportal>.
2. Gå till **användare** > **aktiva användare**och välj **Lägg till en användare**.
3. Fyll i följande information i fönstret **ny användare** . När du är klar väljer du **Lägg till**.
    - **Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.
    - **Domän** Om användarens användar namn till exempel är Jakob och domänen är contoso.com loggar de in genom att skriva jakob@contoso.com.
    - **Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.
    - **Lösen ord** Använd det automatiskt genererade lösen ordet eller expandera för att ange ett starkt lösen ord för användaren. De måste ändra sitt lösen ord efter 90 dagar. Du kan även välja att **Uppmana användaren att byta lösenord vid första inloggningen**.
    - **Roller** Expandera det här avsnittet om du vill göra användaren till administratör.
    - **Produktlicenser** Expandera det här avsnittet och välj rätt licens. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <https://portal.partner.microsoftonline.cn>.
2. Gå till **användare** > **aktiva användare**och välj **Lägg till en användare**.
3. Fyll i följande information i fönstret **ny användare** . När du är klar väljer du **Lägg till**.
    - **Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.
    - **Domän** Om användarens användar namn till exempel är Jakob och domänen är contoso.com loggar de in genom att skriva jakob@contoso.com.
    - **Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.
    - **Lösen ord** Använd det automatiskt genererade lösen ordet eller expandera för att ange ett starkt lösen ord för användaren. De måste ändra sitt lösen ord efter 90 dagar. Du kan även välja att **Uppmana användaren att byta lösenord vid första inloggningen**.
    - **Roller** Expandera det här avsnittet om du vill göra användaren till administratör.
    - **Produktlicenser** Expandera det här avsnittet och välj rätt licens. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Lägga till flera användare samtidigt

Du kan använda någon av följande metoder för att lägga till flera användare samtidigt:

- **Lägga till användare i grupp med hjälp av ett kalkylblad.** Se [lägga till flera användare samtidigt](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).
- **Automatisera processen att lägga till och tilldela licenser.** Se [skapa användar konton med Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell). Välj det här alternativet om du redan vet hur du använder cmdlets i Windows PowerShell.
- **Använder du ActiveDirectory?** [Konfigurera profilsynkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization). Använd Azure AD Connect-verktyget för att replikera Active Directory-användarkonton (och andra Active Directory-objekt) i Microsoft 365. Synkroniseringen lägger bara till användarkonton. Du måste tilldela licenser till de synkroniserade användarna innan de kan använda e-post och andra Office-program.
- **Migrera från Exchange?** Se [olika sätt att migrera flera e-postkonton till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). När du migrerar flera post lådor till Microsoft 365 med antingen snabbmigrering, stageed eller en hybrid Exchange-metod lägger du automatiskt till användare som en del av migreringen. Migreringen lägger bara till användarkonton. Du måste tilldela licenser till användarna innan de kan använda e-post och andra Office-program. Om du inte tilldelar en licens till en användare inaktive RAS post lådan efter en respittid på 30 dagar. Lär dig hur du [tilldelar användare licenser](../manage/assign-licenses-to-users.md) i administrations centret för Microsoft 365.

## <a name="next-steps"></a>Nästa steg

När du har lagt till en användare får du ett e-postmeddelande från Microsoft. E-postmeddelandet innehåller personens användar-ID och lösen ord så att de kan logga in i Microsoft 365. Använd din vanliga process för att förmedla nya lösenord. Dela [Start guiden](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) för en arbets bok med nya användare för att konfigurera saker, till exempel hur du [laddar ner och installerar Office-appar på en PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och hur du [konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Relaterat innehåll

[Lägga till en ny anställd i Microsoft 365](add-new-employee.md) (artikel) \
[Lägga till flera användare samtidigt till Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (artikel) \
[Återställa en användare i Microsoft 365](restore-user.md) (artikel) \
[Tilldela licenser till användare](../manage/assign-licenses-to-users.md) (artikel) \
[Ta bort en användare från organisationen](delete-a-user.md) (artikeln)
