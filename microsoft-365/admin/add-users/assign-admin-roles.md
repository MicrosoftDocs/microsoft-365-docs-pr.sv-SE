---
title: Tilldela administratörs roller administrations centret för Microsoft 365
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
description: Lär dig hur du tilldelar administratörs roller till en användare eller flera användare i företaget så att de kan utföra specifika uppgifter i administrations centret.
ms.openlocfilehash: c0dfef0860e5729a135a142383bdb60aa9d310be
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906257"
---
# <a name="assign-admin-roles"></a>Tilldela administratörsroller

Om du är den person som köpte ditt Microsoft Business-abonnemang blir du den globala administratören. Det innebär att du har obegränsad kontroll över produkterna i dina prenumerationer och att du kan komma åt de flesta data.

Mer information finns i [Om administratörsroller](about-admin-roles.md).

När du lägger till nya användare och inte tilldelar dem en administratörs roll är de i *användar rollen* och har inte administratörs behörighet till något administratörs Center för Microsoft. Men om du behöver hjälp med att få saker gjorda kan du tilldela en användare en administratörs roll. Om du till exempel behöver någon som hjälper dig att återställa lösen ord ska du inte tilldela dem rollen som global administratör. Att få för många globala administratörer har obegränsad till gång till dina data och online-affärer är en säkerhets risk.

## <a name="watch-add-an-adminbrbr"></a>Titta: Lägg till en administratör.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="assign-admin-roles"></a>Tilldela administratörsroller 

::: moniker range="o365-worldwide"

Du kan tilldela användare till en roll på två olika sätt:

- Du kan gå till användarens uppgifter och **hantera roller** för att tilldela användaren en roll.
- Eller så kan du gå till **roller** och välja rollen och sedan lägga till flera användare.

### <a name="assign-admin-roles-to-users-using-roles"></a>Tilldela administratörs roller till användare som använder roller

1. I administrations centret går du till **roll** > **roller** för att visa alla administratörs roller som är tillgängliga för din organisation.
2. Välj den administratörs roll du vill tilldela användaren till.
3. Välj **tilldelade administratörer** > **Add**.
4. Ange användarens **visnings namn** eller användar **namn** och välj sedan användaren i listan med förslag.
5. Lägg till flera användare tills du är klar.
6. Välj **Spara** så läggs användaren till i listan över tilldelade administratörer.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Koppla en användare till en administratörs roll från aktiva användare

1. Gå till sidan **användare** > [aktiva användare](https://go.microsoft.com/fwlink/p/?linkid=834822) i administrations centret.

2. På sidan **aktiva användare** väljer du den användare vars administratörs roll du vill ändra. I fönstret utfällbar, bredvid **roller** väljer du **Manage roles**.

3. Välj den administratörs roll du vill tilldela användaren. Om du inte ser den roll du letar efter väljer du **Visa alla** längst ned i listan.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. På sidan **aktiva användare** väljer du den användare vars administratörs roll du vill ändra. I fönstret utfällbar bredvid **roller** väljer du **Redigera**. 

    Om du inte ser **redigerings** alternativet har du inte behörighet att redigera och kan inte tilldela administratörs roller till andra. Be en global administratör att tilldela roller åt dig. I ett litet företag är affärs innehavaren (personen som köpte ditt abonnemang) en global administratör. I ett stort företag är viktiga personer på IT-avdelningen globala administratörer.

3. Välj **anpassad administratör** för att se en lista över de roller som vi har anpassat åt dig. En beskrivning av varje roll finns i [om administratörs roller.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. På sidan **aktiva användare** väljer du den användare vars administratörs roll du vill ändra. I fönstret utfällbar bredvid **roller** väljer du **Redigera**.

    Om du inte ser **redigerings** alternativet har du inte behörighet att redigera och kan inte tilldela administratörs roller till andra. Be en global administratör att tilldela roller åt dig. I ett litet företag är affärs innehavaren (personen som köpte ditt abonnemang) en global administratör. I ett stort företag är viktiga personer på IT-avdelningen globala administratörer.

3. Välj **anpassad administratör** för att se en lista över de roller som vi har anpassat åt dig. En beskrivning av varje roll finns i [om administratörs roller.](about-admin-roles.md)

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>Tilldela administratörsroller till flera användare

Om du känner till PowerShell kan du läsa [tilldela roller till användar konton med PowerShell](https://go.microsoft.com/fwlink/?linkid=854257). Det är ett bra sätt att tilldela roller till hundratals användare.
  
Använd följande instruktioner för att tilldela roller till mer än tio användare åt gången.

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>Kontrol lera administratörs rollerna i din organisation

Du kanske inte har rätt behörighet för att tilldela administratörs roller till andra användare. Kontrol lera att du har rätt behörighet eller be en annan administratör att tilldela roller åt dig.

Du kan kontrol lera behörigheter för administratörs roller på två olika sätt:

- Du kan gå till användarens uppgifter och titta under **roller** på **konto** sidan.
- Eller så kan du gå till **roller** och välja administratörs rollen och välja tilldelade administratörer för att se vilka användare som har tilldelats.

::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Om administratörsroller i Microsoft 365](about-admin-roles.md)

[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[Tilldela roller till användar konton med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell)

[Auktorisera eller ta bort partner relationer](../misc/add-partner.md)