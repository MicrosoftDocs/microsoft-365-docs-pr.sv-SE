---
title: Ge användarna åtkomst till Office 365 Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Användare måste tilldelas behörigheter i Office 365 Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.
ms.openlocfilehash: cccf44a64d20dc1304dbc5145d6ae50441cfacef
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805446"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>Ge användarna åtkomst till Office 365 Security & Compliance Center

Användare måste tilldelas behörigheter i Office 365 Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner. Som en global Office 365-administratör eller medlem i rollgruppen OrganizationManagement i Security & Compliance Center kan du ge användarna dessa behörigheter. Användare kan bara hantera de säkerhets- eller efterlevnadsfunktioner som du ger dem åtkomst till.

Mer information om de olika behörigheter du kan ge användarna i Security & Compliance Center finns [i Behörigheter i Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara en global Office 365-administratör eller medlem i rollgruppen OrganizationManagement i Security & Compliance Center för att kunna slutföra stegen i den här artikeln.

- Rollgrupper för Security & Compliance Center kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.

- Rollgruppsmedlemskap delas inte mellan Exchange Online och Security & Compliance Center.

- DAP-partner (DAP) med Administration på uppdrag av (AOBO) behörighet kan inte komma åt Säkerhets- & Compliance Center.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd administrationscentret för att ge en annan användare åtkomst till Security & Compliance Center

1. [Logga in på Office 365 och gå till administrationscentret](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Öppna **Administrationscenter** för Microsoft 365 och klicka sedan på **Säkerhet & efterlevnad**.

3. Gå till **Behörigheter**i säkerhets-& Compliance Center .

4. Välj den rollgrupp som du vill lägga till användaren **Edit** ![i i](../../media/O365-MDM-CreatePolicy-EditIcon.gif)listan .

5. Klicka på **Lägg till**![ikon](../../media/ITPro-EAC-AddIcon.gif) på rollgruppens egenskapssida under **Medlemmar**och välj namnet på den användare (eller användare) som du vill lägga till.

6. När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **Lägg\> till** och **sedan OK**.

7. Klicka på **Spara** om du vill spara ändringarna i rollgruppen.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

1. Gå till **Behörigheter**i säkerhets-& Compliance Center .

2. Välj rollgruppen för att visa medlemmarna i listan.

3. Till höger, i rollgruppens information, kan du visa medlemmarna i rollgruppen.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använd PowerShell för att ge en annan användare åtkomst till Security & Compliance Center

1. [Anslut till Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Använd kommandot **Lägg till rollgruppSmedlem** för att lägga till en användare i rollen Organisationshantering, som visas i följande exempel.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parametrar:**

   - _Identitet_ är den rollgrupp som en medlem ska lägga till.

   - _Medlem_ är postlådan, den universella säkerhetsgruppen (USG) eller dator som ska läggas till i rollgruppen. Du kan bara ange en medlem i taget.

Detaljerad information om syntax och parametrar finns [i Lägg till rollgruppsmedlem](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att du har gett användarna åtkomst till Security & Compliance Center använder du cmdleten **Get-RoleGroupMember** för att visa medlemmarna i rollgruppen Organisationshantering, som visas i följande exempel.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).
