---
title: Ge användare tillgång till Säkerhets- & Efterlevnadscenter
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
description: Användare måste ha tilldelats behörigheter i Säkerhets- och & Microsoft 365 innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289883"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Ge användare tillgång till Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Användare måste ha tilldelats behörigheter i Säkerhets- & center för efterlevnad innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner. Som global administratör eller medlem i rollgruppen Organisationsmanagement i Säkerhets- & Efterlevnadscenter kan du ge de här behörigheterna till användare. Användare kommer bara att kunna hantera de säkerhets- och efterlevnadsfunktioner som du ger dem åtkomst till.

Mer information om de olika behörigheter du kan ge användare i Säkerhets- och & efterlevnadscenter finns i Behörigheter i Säkerhets- & [Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara global administratör eller medlem i rollgruppen Organisationsadministration i Säkerhets- och & efterlevnadscenter för att slutföra stegen i den här artikeln.

- Rollgrupper för Säkerhets- & Efterlevnadscenter kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.

- Medlemskap i rollgrupper delas inte mellan Exchange Online och Säkerhets- & Efterlevnadscenter.

- DAP-partners (Delegated Access Permission) med AOBO-behörigheter (Administer On Behalf Of) har inte åtkomst till Säkerhets- & Efterlevnadscenter.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd Säkerhets- & för att ge en annan användare åtkomst till Säkerhets- & Efterlevnadscenter

1. Öppna Säkerhets- & Efterlevnadscenter <https://protection.office.com> och gå sedan till **Behörigheter.** Gå direkt till fliken **Behörigheter** genom att <https://protection.office.com/permissions> öppna.

2. I listan över rollgrupper väljer du rollgruppen  och klickar sedan på ikonen ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Redigera.

3. På egenskapssidan för rollgruppen under  **Medlemmar** klickar du på Lägg till ikon och väljer namnet på den ![ användare ](../../media/ITPro-EAC-AddIcon.gif) (eller användare) du vill lägga till.

4. När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **lägg till och \>** sedan på **OK.**

5. Klicka på **Spara** när du är klar.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använda Säkerhets- & Efterlevnadscenter PowerShell för att ge en annan användare tillgång & Säkerhets- och efterlevnadscenter

1. [Anslut till Säkerhets- & Compliance Center PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

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

Om du vill verifiera att du har beviljats åtkomst till Säkerhets- & efterlevnadscenter gör du något av följande:

- Gå till & i Säkerhets- **och efterlevnadscenter** och välj rollgruppen. Kontrollera medlemmarna i rollgruppen i den utfäll plats för information som öppnas.

- I Säkerhetscenter & PowerShell ersätter du med namnet på \<RoleGroupName\> rollgruppen och kör följande kommando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)
