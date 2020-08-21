---
title: Ge användarna åtkomst till säkerhets & efterlevnad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Användare måste tilldelas behörigheter i Microsoft 365 Security & Compliance Center innan de kan hantera säkerhets-eller efterlevnadsprinciper.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826607"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Ge användarna åtkomst till säkerhets & efterlevnad

Användare måste tilldelas behörigheter i säkerhets & efterlevnad för att de ska kunna hantera alla dess säkerhets-eller efterlevnads funktioner. Som global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center kan du ge dessa behörigheter till användare. Användarna kan bara hantera de säkerhets-eller efterföljandekrav du ger dem till gång till.

Om du vill ha mer information om de olika behörigheter du kan ge användare i avsnittet om säkerhets & efterlevnad kan du läsa [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center för att slutföra stegen i den här artikeln.

- Roll grupper för säkerhets & efterlevnad kan ha liknande namn för roll grupperna i Exchange Online, men de är inte samma.

- Roll grupps medlemskap delas inte mellan Exchange Online och säkerhets & Compliance Center.

- DAP-partners (delegerad Access permission) med administrera (AOBO) behörigheter får inte till gång till säkerhets & Compliance Center.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd administrations centret för att ge en annan användare åtkomst till sidan säkerhets & efterlevnad

1. [Logga in och gå till administrations centret](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Öppna **Administratörs** Center i administrations centret för Microsoft 365 och klicka sedan på **säkerhets & efterlevnad**.

3. Gå till **behörigheter**i säkerhets & efterlevnad.

4. Välj den roll grupp i listan som du vill lägga till användaren i och klicka på **Redigera** ![ redigerings ikon ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

5. På roll gruppens egenskaps sida under **medlemmar**klickar du på **Lägg**till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.gif) och väljer namnet på den eller de användare som du vill lägga till.

6. När du har valt alla användare som du vill lägga till i roll gruppen klickar du på **Lägg till \> ** och sedan på **OK**.

7. Klicka på **Spara** för att spara ändringarna i roll gruppen.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

1. Gå till **behörigheter**i säkerhets & efterlevnad.

2. I listan väljer du roll gruppen för att Visa medlemmarna.

3. Till höger i roll grupps informationen kan du Visa medlemmarna i roll gruppen.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använda PowerShell för att ge en annan användare åtkomst till säkerhets & Compliance Center

1. [Anslut till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Använd kommandot **Add-RoleGroupMember** för att lägga till en användare i rollen organisations hantering, enligt följande exempel.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parametrar**:

   - _Identitet_ är roll gruppen som du vill lägga till en medlem i.

   - _Medlem_ är post låda, universell säkerhets grupp (USG) eller dator som ska läggas till i roll gruppen. Du kan bara ange en medlem åt gången.

Detaljerad information om syntax och parametrar finns i avsnittet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

För att verifiera att du har gett användare åtkomst till säkerhets & Compliance Center använder du cmdleten **Get-RoleGroupMember** för att Visa medlemmarna i roll gruppen organisations hantering, enligt följande exempel.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
