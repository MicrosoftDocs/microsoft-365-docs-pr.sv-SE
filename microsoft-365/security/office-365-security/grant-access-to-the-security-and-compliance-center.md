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
ms.openlocfilehash: b51007221257b9adac46c31295e13b20b12342ab
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868927"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Ge användarna åtkomst till säkerhets & efterlevnad

Användare måste tilldelas behörigheter i säkerhets & efterlevnad för att de ska kunna hantera alla dess säkerhets-eller efterlevnads funktioner. Som global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center kan du ge dessa behörigheter till användare. Användarna kan bara hantera de säkerhets-eller efterföljandekrav du ger dem till gång till.

Om du vill ha mer information om de olika behörigheter du kan ge användare i avsnittet om säkerhets & efterlevnad kan du läsa [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center för att slutföra stegen i den här artikeln.

- Roll grupper för säkerhets & efterlevnad kan ha liknande namn för roll grupperna i Exchange Online, men de är inte samma.

- Roll grupps medlemskap delas inte mellan Exchange Online och säkerhets & Compliance Center.

- DAP-partners (delegerad Access permission) med administrera (AOBO) behörigheter får inte till gång till säkerhets & Compliance Center.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd säkerhets & Compliance Center för att ge en annan användare åtkomst till säkerhets & Compliance Center

1. Öppna säkerhets & Compliance Center på <https://protection.office.com> och gå sedan till **behörigheter**. Öppna för att gå direkt till fliken **behörigheter** <https://protection.office.com/permissions> .

2. I listan över roll grupper väljer du roll gruppen och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. På roll gruppens egenskaps sida under **medlemmar**klickar du på **Lägg**till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.gif) och väljer namnet på den eller de användare som du vill lägga till.

4. När du har valt alla användare som du vill lägga till i roll gruppen klickar du på **Lägg till \> ** och sedan på **OK**.

5. Klicka på **Spara** när du är klar.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använda säkerhets & Compliance Center PowerShell för att ge en annan användare åtkomst till säkerhets & Compliance Center

1. [Anslut till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Använd följande syntax:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Detaljerad information om syntax och parametrar finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör något av följande om du vill verifiera att du har beviljats åtkomst till säkerhets & Compliance Center.

- Gå till **behörigheter** i säkerhets & efterlevnad och välj roll gruppen. I den utfällbara informationen som öppnas kontrollerar du medlemmarna i roll gruppen. 

- I säkerhets & Compliance Center PowerShell, Ersätt \<RoleGroupName\> med namnet på roll gruppen och kör följande kommando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
