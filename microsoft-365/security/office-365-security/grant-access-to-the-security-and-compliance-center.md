---
title: Ge användarna åtkomst till Security & Compliance Center
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
description: Användare måste tilldelas behörigheter i Microsoft 365 Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfded9d3f75f57eca1097fec6f18dc55410b65fb
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616980"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Ge användarna åtkomst till Security & Compliance Center

Användare måste tilldelas behörigheter i Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner. Som global administratör eller medlem i rollgruppen OrganisationManagement i Security & Compliance Center kan du ge dessa behörigheter till användare. Användare kan bara hantera de säkerhets- eller efterlevnadsfunktioner som du ger dem åtkomst till.

Mer information om de olika behörigheter som du kan ge användare i Security & Compliance Center finns [i Behörigheter i Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste vara global administratör eller medlem i rollgruppen OrganizationManagement i Security & Compliance Center för att kunna utföra stegen i den här artikeln.

- Rollgrupper för Security & Compliance Center kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.

- Rollgruppsmedlemskap delas inte mellan Exchange Online och Security & Compliance Center.

- Dap-partner (Delegated Access Permission) med AOBO-behörigheter (Administrerat åtkomstbehörighet) kan inte komma åt Security & Compliance Center.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Använd administrationscentret för att ge en annan användare åtkomst till Security & Compliance Center

1. [Logga in och gå till administrationscentret](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Öppna **administrationscenter för** Microsoft 365 och klicka sedan på **Säkerhet & efterlevnad**.

3. Gå till **Behörigheter**i Säkerhets- & Compliance Center .

4. Välj den rollgrupp som du vill lägga till användaren i i listan och klicka på **Ikonen Redigera** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) redigera.

5. Klicka på **Lägg till**ikonen i rollgruppens egenskaper under **Medlemmar**och välj namnet på den eller de användare som du vill ![ lägga ](../../media/ITPro-EAC-AddIcon.gif) till.

6. När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **lägg \> till** och sedan **på OK**.

7. Klicka på **Spara** om du vill spara ändringarna i rollgruppen.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

1. Gå till **Behörigheter**i Säkerhets- & Compliance Center .

2. Välj den rollgrupp som ska visas i listan.

3. Till höger kan du visa medlemmarna i rollgruppen i rollgruppsinformationen.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Använda PowerShell för att ge en annan användare åtkomst till Security & Compliance Center

1. [Anslut till Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Använd kommandot **Lägg till rollgruppmedlem** för att lägga till en användare i organisationshanteringsrollen, vilket visas i följande exempel.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parametrar**:

   - _Identitet_ är den rollgrupp som du vill lägga till en medlem i.

   - _Medlem_ är postlådan, den universella säkerhetsgruppen (USG) eller datorn som ska läggas till i rollgruppen. Du kan bara ange en medlem i taget.

Detaljerad information om syntax och parametrar finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att du har gett användarna åtkomst till Security & Compliance Center använder du cmdleten **Get-RoleGroupMember** för att visa medlemmarna i rollgruppen Organisationshantering, vilket visas i följande exempel.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
