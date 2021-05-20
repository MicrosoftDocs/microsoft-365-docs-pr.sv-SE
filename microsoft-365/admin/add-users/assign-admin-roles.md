---
title: Tilldela administratörsroller Microsoft 365 administrationscenter
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Lär dig hur du tilldelar administratörsroller till en eller flera användare i företaget så att de kan utföra specifika uppgifter i administrationscentret.
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571871"
---
# <a name="assign-admin-roles"></a>Tilldela administratörsroller

Om du är den person som köpte Microsoft Business-prenumerationen är du global administratör. Det innebär att du har obegränsad kontroll över produkterna i dina prenumerationer och att du kan komma åt de flesta data.

Mer information finns i [Om administratörsroller](about-admin-roles.md).

Om du lägger till nya användare och inte tilldelar dem  en administratörsroll kommer de att ha användarrollen och inte ha administratörsbehörighet till något av Microsofts administrationscenter. Men om du behöver hjälp med att få saker gjorda kan du tilldela en administratörsroll till en användare. Om du till exempel behöver någon som ska hjälpa till att återställa lösenord, ska du inte tilldela dem rollen som global administratör, bör du tilldela dem rollen som lösenordsadministratör. Att ha för många globala administratörer, med obegränsad åtkomst till dina data och online-företag, är en säkerhetsrisk.

## <a name="watch-add-an-adminbrbr"></a>Titta: Lägg till en administratör.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Tilldela administratörsroller 

::: moniker range="o365-worldwide"

Du kan tilldela användare till en roll på 2 olika sätt:

- Du kan gå till användarens information och Hantera **roller och** tilldela en roll till användaren.
- Du kan också gå **till Roller** och välja rollen och sedan lägga till flera användare i den.

### <a name="assign-admin-roles-to-users-using-roles"></a>Tilldela administratörsroller till användare med hjälp av Roller

1. I administrationscentret går du till **Roller**. Välj **flikarna Azure AD** **eller Intune för** att visa de administratörsroller som är tillgängliga för din organisation.
2. Välj den administratörsroll som du vill tilldela användaren.
3. Välj **Tilldelade administratörer Lägg** > **till.**
4. Skriv användarens **visningsnamn** **eller användarnamn** och välj sedan användaren i listan med förslag.
5. Lägg till flera användare tills du är klar.
6. Välj **Spara** så läggs användaren till i listan över tilldelade administratörer.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Tilldela en användare till en administratörsroll från aktiva användare

1. I administrationscentret går du till **sidan** > [Användare aktiva](https://go.microsoft.com/fwlink/p/?linkid=834822) användare.

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Hantera roller under Roller i **den utfäll** **du fönsterrutan.**

3. Välj den administratörsroll som du vill tilldela användaren. Om du inte ser den roll du letar efter väljer du **Visa alla** längst ned i listan.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Redigera bredvid Roller i det **utfällade** **fönstret.** 

    Om du inte ser alternativet Redigera **har** du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer. Be en global administratör i företaget att tilldela roller åt dig. I ett litet företag är företagsägaren (den person som köpte prenumerationen) en global administratör. I ett stort företag är viktiga personer i IT-avdelningen globala administratörer.

3. Välj **Anpassad administratör** för att se en lista över roller som är anpassad för dig. En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Redigera bredvid Roller i det **utfällade** **fönstret.**

    Om du inte ser alternativet Redigera **har** du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer. Be en global administratör i företaget att tilldela roller åt dig. I ett litet företag är företagsägaren (den person som köpte prenumerationen) en global administratör. I ett stort företag är viktiga personer i IT-avdelningen globala administratörer.

3. Välj **Anpassad administratör** för att se en lista över roller som är anpassad för dig. En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>Tilldela administratörsroller till flera användare

Om du känner till PowerShell kan du [gå till Tilldela roller till användarkonton med PowerShell.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) Det är ett bra sätt att tilldela roller till hundratals användare.
  
Använd följande instruktioner för att tilldela roller till mer än tio användare åt gången.

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>Kontrollera administratörsroller i organisationen

Du kanske inte har rätt behörighet för att tilldela administratörsroller till andra användare. Kontrollera att du har rätt behörigheter eller be en annan administratör att tilldela roller åt dig.

Du kan kontrollera administratörsrollbehörigheter på 2 olika sätt:

- Du kan gå till användarens information och titta under **Roller** på **kontosidan.**
- Du kan också gå **till Roller** och välja administratörsroll och välja tilldelade administratörer för att se vilka användare som har tilldelats.

::: moniker-end

## <a name="related-content"></a>Relaterat innehåll

[Om Microsoft 365 administratörsroller](about-admin-roles.md) (artikel)

[Administratörsrollbehörigheter i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (artikel)

[Tilldela roller till användarkonton med PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artikel)

[Auktorisera eller ta bort partnerrelationer](../misc/add-partner.md) (artikel)