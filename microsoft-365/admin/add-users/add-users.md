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
ms.openlocfilehash: 016c98fc93bfa1a92274a5b991cf8adbd1131bc9
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015893"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Lägga till användare och tilldela licenser samtidigt

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Personerna i teamet behöver var och en ett användarkonto innan de kan logga in och komma åt [Microsoft 365 för företag](https://go.microsoft.com/fwlink/?LinkID=519395). Det enklaste sättet att lägga till användarkonton är att lägga till dem en i taget i Microsoft 365 administrationscenter. När du har gjort det här steget har användarna Microsoft 365-licenser, inloggningsuppgifter och Microsoft 365-postlådor.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global, licens eller användaradministratör för att kunna lägga till användare och tilldela licenser. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Titta: Lägga till användare i administrationscentret

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Stegen som används i videon visar en annan startpunkt för att lägga till användare, men de återstående stegen är desamma som följande procedur.

## <a name="add-users-one-at-a-time"></a>Lägga till användare en i taget

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.
2. Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.
3. I fönstret **Konfigurera grunderna** fyller du i grundläggande användarinformation och väljer sedan **Nästa**.
    - **Namn** Fyll i för- och efternamn, visningsnamn och användarnamn.
    - **Domän** Välj domän för användarens konto. Om användarens användarnamn till exempel är Jakob och domänen är contoso.com loggar de in med hjälp av jakob@contoso.com.
    - **Inställningar för lösenord** Välj att använda det automatiskt skapade lösenordet eller att skapa ditt eget starka lösenord för användaren.
    - Användaren måste ändra sitt lösenord efter 90 dagar. Du kan också välja att **kräva att användaren ändrar sitt lösenord när de loggar in för första gången.**
    - Välj om du vill skicka lösenordet via e-post när användaren läggs till.
4. I fönstret **Tilldela produktlicenser** väljer du platsen och lämplig licens för användaren. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser. Expandera **appar** och välj eller avmarkera appar för att begränsa vilka appar användaren har en licens för. Välj **Nästa**.
5. Expandera **Roller i** fönstret **Valfria inställningar** för att göra den här användaren till administratör. Expandera **profilinformation** om du vill lägga till ytterligare information om användaren.
6. Välj **Nästa**, granska den nya användarens inställningar, gör de ändringar du vill och välj sedan **Slutför att lägga till**och stäng sedan . **Close**

::: moniker-end

::: moniker range="o365-germany"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.
2. Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.
3. Fyll i följande information i fönstret **Nytt användar.** När du är klar väljer du **Lägg till**.
    - **Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.
    - **Domän** Om användarens användarnamn till exempel är Jakob och domänen är contoso.com loggar de in på genom att skriva jakob@contoso.com.
    - **Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.
    - **Lösenord** Använd lösenordet för automatiskt uppradade eller expandera för att ange ett starkt lösenord för användaren. De måste ändra sitt lösenord efter 90 dagar. Du kan även välja att **Uppmana användaren att byta lösenord vid första inloggningen**.
    - **Roller** Expandera det här avsnittet om du vill göra användaren till administratör.
    - **Produktlicenser** Expandera det här avsnittet och välj rätt licens. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.
2. Gå till **Aktiva** > **användare**och välj Lägg till **en användare**.
3. Fyll i följande information i fönstret **Nytt användar.** När du är klar väljer du **Lägg till**.
    - **Namn** Fylla i förnamn, efternamn, visningsnamn och användarnamn.
    - **Domän** Om användarens användarnamn till exempel är Jakob och domänen är contoso.com loggar de in på genom att skriva jakob@contoso.com.
    - **Kontaktinformation** Expandera det här avsnittet för att fylla i mobiltelefonnummer, adress och så vidare.
    - **Lösenord** Använd lösenordet för automatiskt uppradade eller expandera för att ange ett starkt lösenord för användaren. De måste ändra sitt lösenord efter 90 dagar. Du kan även välja att **Uppmana användaren att byta lösenord vid första inloggningen**.
    - **Roller** Expandera det här avsnittet om du vill göra användaren till administratör.
    - **Produktlicenser** Expandera det här avsnittet och välj rätt licens. Även om du inte har några tillgängliga licenser kan du alltid lägga till en ny användare och köpa fler licenser.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Lägga till flera användare samtidigt

Du kan använda någon av följande metoder för att lägga till flera användare samtidigt:
  
- **Lägga till användare i grupp med hjälp av ett kalkylblad.** Se [Lägga till flera användare samtidigt](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).
- **Automatisera processen att lägga till och tilldela licenser.** Se [Skapa användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell). Välj det här alternativet om du redan vet hur du använder cmdlets i Windows PowerShell.
- **Använder du ActiveDirectory?** [Konfigurera katalogsynkronisering för Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization). Använd Azure AD Connect-verktyget för att replikera Active Directory-användarkonton (och andra Active Directory-objekt) i Microsoft 365. Synkroniseringen lägger bara till användarkonton. Du måste tilldela licenser till synkroniserade användare innan de kan använda e-post och andra Office-appar.
- **Migrera från Exchange?** Se [Olika sätt att migrera flera e-postkonton till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). När du migrerar flera postlådor till Microsoft 365 med hjälp av antingen cutover, staged eller en hybrid Exchange-metod lägger du automatiskt till användare som en del av migreringen. Migreringen lägger bara till användarkonton. Du måste tilldela licenser till användarna innan de kan använda e-post och andra Office-appar. Om du inte tilldelar en licens till en användare inaktiveras postlådan efter en respitperiod på 30 dagar. Lär dig hur du [tilldelar licenser till användare](../manage/assign-licenses-to-users.md) i Microsoft 365 administrationscenter.

## <a name="next-steps"></a>Nästa steg

När du har lagt till en användare får du ett e-postmeddelande från Microsoft. E-postmeddelandet innehåller personens användar-ID och lösenord så att de kan logga in på Microsoft 365. Använd din vanliga process för att förmedla nya lösenord. Dela [snabbstartsguiden](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) för medarbetare med dina nya användare för att konfigurera saker, till exempel hur du [hämtar och installerar Office-appar på en PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) och hur du [konfigurerar Office-appar och e-post på en mobil enhet](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Relaterat innehåll

[Lägga till en ny anställd i Microsoft 365](add-new-employee.md) (artikel)\
[Lägg till flera användare samtidigt i Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time) (artikel)\
[Återställa en användare i Microsoft 365](restore-user.md) (artikel)\
[Tilldela licenser till användare](../manage/assign-licenses-to-users.md) (artikel)\
[Ta bort en användare från organisationen](delete-a-user.md) (artikel)