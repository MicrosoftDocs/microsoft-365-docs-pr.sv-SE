---
title: Tilldela administratörsroller microsoft 365-administrationscentret
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Lär dig hur du tilldelar administratörsroller till en användare eller flera användare i företaget så att de kan utföra specifika uppgifter i administrationscentret.
ms.openlocfilehash: 3f22ef22571dd04dd3364a95ed860f53b8ff207b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211925"
---
# <a name="assign-admin-roles"></a>Tilldela administratörsroller

Om du är den person som har köpt din Microsoft-företagsprenumeration är du den globala administratören. Det innebär att du har obegränsad kontroll över produkterna i dina prenumerationer och att du kan komma åt de flesta data.

Mer information finns i [Om administratörsroller](about-admin-roles.md).

När du lägger till nya användare, om du inte tilldelar dem en administratörsroll, är de i *användarrollen* och har inte administratörsbehörighet till någon av Microsofts administrationscenter. Men om du behöver hjälp med att få saker gjorda kan du tilldela en administratörsroll till en användare. Om du till exempel behöver någon som kan återställa lösenord bör du inte tilldela dem den globala administratörsrollen, du bör tilldela dem rollen för lösenordsadministratör. Att ha för många globala administratörer, med obegränsad tillgång till dina data och online-verksamhet, är en säkerhetsrisk.

Titta på en kort video om att lägga till en administratör.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

::: moniker-end

## <a name="assign-admin-roles"></a>Tilldela administratörsroller 

::: moniker range="o365-worldwide"

Du kan tilldela användare till en roll på två olika sätt:

- Du kan gå till användarens information och **Hantera roller** för att tilldela en roll till användaren.
- Du kan också gå till **Roller** och välja rollen och sedan lägga till flera användare i den.

### <a name="assign-admin-roles-to-users-using-roles"></a>Tilldela administratörsroller till användare med roller

1. Gå till Roller **roller i** **administrationscentret** > och visa alla administratörsroller som är tillgängliga för organisationen.
2. Välj den administratörsroll som du vill tilldela användaren till.
3. Välj **Tilldelade administratörer** > **Lägg till**.
4. Skriv användarens **visningsnamn** eller **användarnamn**och välj sedan användaren i listan med förslag.
5. Lägg till flera användare tills du är klar.
6. Välj **Spara**och sedan läggs användaren till i listan över tilldelade administratörer.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Tilldela en användare till en administratörsroll från aktiva användare

1. Gå till sidan Aktiva [användare](https://go.microsoft.com/fwlink/p/?linkid=834822) **i administrationscentret.** >

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Hantera roller bredvid Roller i det utfällbara fönstret **bredvid** **Roller.**

3. Välj den administratörsroll som du vill tilldela användaren. Om du inte ser den roll du letar efter väljer du **Visa alla** längst ned i listan.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Redigera bredvid Roller i det utfällbara fönstret **bredvid** **Roller**. 

    Om du inte ser alternativet **Redigera** har du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer. Be en global administratör i ditt företag att tilldela roller åt dig. I ett litet företag är företagsägaren (personen som köpte prenumerationen) en global administratör. I ett stort företag är nyckelpersoner på IT-avdelningen globala administratörer.

3. Välj **Anpassad administratör** om du vill visa en lista över roller som vi har anpassat åt dig. En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. På sidan **Aktiva användare** väljer du den användare vars administratörsroll du vill ändra. Välj Redigera bredvid Roller i det utfällbara fönstret **bredvid** **Roller**. 

    Om du inte ser alternativet **Redigera** har du inte behörighet att redigera och kan inte tilldela administratörsroller till andra personer. Be en global administratör i ditt företag att tilldela roller åt dig. I ett litet företag är företagsägaren (personen som köpte prenumerationen) en global administratör. I ett stort företag är nyckelpersoner på IT-avdelningen globala administratörer.

3. Välj **Anpassad administratör** om du vill visa en lista över roller som vi har anpassat åt dig. En beskrivning av varje roll finns i [Om administratörsroller.](about-admin-roles.md)

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a>Tilldela administratörsroller till flera användare

Om du känner till PowerShell läser du [Tilldela roller till användarkonton med PowerShell](https://go.microsoft.com/fwlink/?linkid=854257). Det är ett bra sätt att tilldela roller till hundratals användare.
  
Använd följande instruktioner för att tilldela roller till mer än tio användare åt gången.

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a>Fungerade det inte för dig?

Du kanske inte har rätt behörigheter och har därför inte åtkomst till att tilldela administratörsroller till andra användare. Be en annan administratör att tilldela roller åt dig.

::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Tilldela roller till användarkonton med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[Auktorisera eller ta bort partnerrelationer](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)

[Lägga till en alternativ e-postadress med administrationscentret för Exchange](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)

