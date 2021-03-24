---
title: Ge användare tillgång till Säkerhets- & Säkerhets- och efterlevnadscenter
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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Användare måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscenter för Microsoft 365 & innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 16dbbe81d1131821dfdbf75caff5b5121f8cc45b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071417"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Ge användare tillgång till Säkerhets- & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Användare måste ha tilldelats behörigheter i Säkerhets- & efterlevnadscenter innan de kan hantera dess säkerhets- eller efterlevnadsfunktioner. Som global administratör eller medlem i rollgruppen Organisationsmanagement i Säkerhets- & efterlevnadscenter kan du ge de här behörigheterna till användarna. Användare kan bara hantera de säkerhets- och efterlevnadsfunktioner som du ger dem åtkomst till.

Mer information om de olika behörigheter som du kan ge användare i Säkerhets- och & efterlevnadscenter finns i Behörigheter i Säkerhets- & [Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara global administratör eller medlem i rollgruppen Organisationsadministration i säkerhets- och efterlevnadscentret för & för att slutföra stegen i den här artikeln.

- Rollgrupper för säkerhets- & efterlevnadscenter kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.

- Medlemskap i rollgrupper delas inte mellan Exchange Online och Säkerhets- och & Efterlevnadscenter.

- DAP-partner (Delegerad åtkomstbehörighet) med AOBO-behörighet (Administer On Behalf Of) har inte åtkomst & Säkerhets- och efterlevnadscenter.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd Säkerhets- & efterlevnadscenter för att ge en annan användare tillgång till säkerhets- & efterlevnadscentret

1. Öppna Säkerhets- & säkerhets- och <https://protection.office.com> efterlevnadscenter och gå sedan till **Behörigheter.** Gå direkt till fliken **Behörigheter** genom att öppna <https://protection.office.com/permissions> .

2. I listan över rollgrupper väljer du rollgruppen och klickar sedan på **redigeringsikonen** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. På rollgruppens egenskapssida **under** Medlemmar klickar du på Lägg till ikon och väljer namnet på den  ![ användare ](../../media/ITPro-EAC-AddIcon.gif) (eller användare) du vill lägga till.

4. När du har valt alla användare som du vill lägga till i rollgruppen klickar du på **lägg till \> och** sedan på **OK.**

5. Klicka på **Spara** när du är klar.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använd Säkerhets- & Compliance Center PowerShell för att ge en annan användare tillgång till Säkerhets- & efterlevnadscenter

1. [Anslut till Säkerhets- & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

2. Använd följande syntax:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Detaljerade syntax- och parameterproblem finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill verifiera att du har beviljats åtkomst till säkerhets- & efterlevnadscenter gör du något av följande:

- I Säkerhets- & säkerhets- och efterlevnadscenter **går du till** Behörigheter och väljer rollgruppen. Kontrollera medlemmarna i rollgruppen i den utfällällo för informationen som öppnas.

- I Säkerhets& Compliance Center PowerShell ersätter du med \<RoleGroupName\> namnet på rollgruppen och kör följande kommando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember.](/powershell/module/exchange/Get-RoleGroupMember)