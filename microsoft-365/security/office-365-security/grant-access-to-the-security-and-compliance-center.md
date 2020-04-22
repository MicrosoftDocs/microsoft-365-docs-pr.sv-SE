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
description: Användare måste tilldelas behörigheter i Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.
ms.openlocfilehash: 5110bcecb6731cbf51023c6df19bed30bcba72c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638064"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="da9e1-103">Ge användarna åtkomst till Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="da9e1-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="da9e1-104">Användare måste tilldelas behörigheter i Security & Compliance Center innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="da9e1-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="da9e1-105">Som global administratör eller medlem i rollgruppen OrganisationManagement i Security & Compliance Center kan du ge dessa behörigheter till användare.</span><span class="sxs-lookup"><span data-stu-id="da9e1-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="da9e1-106">Användare kan bara hantera de säkerhets- eller efterlevnadsfunktioner som du ger dem åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="da9e1-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="da9e1-107">Mer information om de olika behörigheter som du kan ge användare i Security & Compliance Center finns [i Behörigheter i Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="da9e1-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="da9e1-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="da9e1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="da9e1-109">Du måste vara global administratör eller medlem i rollgruppen OrganizationManagement i Security & Compliance Center för att kunna utföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="da9e1-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="da9e1-110">Rollgrupper för Security & Compliance Center kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.</span><span class="sxs-lookup"><span data-stu-id="da9e1-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="da9e1-111">Rollgruppsmedlemskap delas inte mellan Exchange Online och Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="da9e1-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="da9e1-112">Dap-partner (Delegated Access Permission) med AOBO-behörigheter (Administrerat åtkomstbehörighet) kan inte komma åt Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="da9e1-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="da9e1-113">Använd administrationscentret för att ge en annan användare åtkomst till Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="da9e1-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="da9e1-114">[Logga in och gå till administrationscentret](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="da9e1-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="da9e1-115">Öppna **administrationscenter för** Microsoft 365 och klicka sedan på **Säkerhet & efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="da9e1-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="da9e1-116">Gå till **Behörigheter**i Säkerhets- & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="da9e1-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="da9e1-117">Välj den rollgrupp som du vill lägga till användaren i](../../media/O365-MDM-CreatePolicy-EditIcon.gif)i listan och klicka på **Ikonen Redigera** ![redigera.</span><span class="sxs-lookup"><span data-stu-id="da9e1-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="da9e1-118">Klicka på **Lägg till**![ikonen](../../media/ITPro-EAC-AddIcon.gif) i rollgruppens egenskaper under **Medlemmar**och välj namnet på den eller de användare som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="da9e1-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="da9e1-119">När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **lägg\> till** och sedan **på OK**.</span><span class="sxs-lookup"><span data-stu-id="da9e1-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="da9e1-120">Klicka på **Spara** om du vill spara ändringarna i rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="da9e1-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="da9e1-121">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="da9e1-121">How do you know this worked?</span></span>

1. <span data-ttu-id="da9e1-122">Gå till **Behörigheter**i Säkerhets- & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="da9e1-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="da9e1-123">Välj den rollgrupp som ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="da9e1-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="da9e1-124">Till höger kan du visa medlemmarna i rollgruppen i rollgruppsinformationen.</span><span class="sxs-lookup"><span data-stu-id="da9e1-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="da9e1-125">Använda PowerShell för att ge en annan användare åtkomst till Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="da9e1-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="da9e1-126">[Anslut till Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="da9e1-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="da9e1-127">Använd kommandot **Lägg till rollgruppmedlem** för att lägga till en användare i organisationshanteringsrollen, vilket visas i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="da9e1-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="da9e1-128">**Parametrar**:</span><span class="sxs-lookup"><span data-stu-id="da9e1-128">**Parameters**:</span></span>

   - <span data-ttu-id="da9e1-129">_Identitet_ är den rollgrupp som du vill lägga till en medlem i.</span><span class="sxs-lookup"><span data-stu-id="da9e1-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="da9e1-130">_Medlem_ är postlådan, den universella säkerhetsgruppen (USG) eller datorn som ska läggas till i rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="da9e1-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="da9e1-131">Du kan bara ange en medlem i taget.</span><span class="sxs-lookup"><span data-stu-id="da9e1-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="da9e1-132">Detaljerad information om syntax och parametrar finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="da9e1-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="da9e1-133">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="da9e1-133">How do you know this worked?</span></span>

<span data-ttu-id="da9e1-134">Om du vill kontrollera att du har gett användarna åtkomst till Security & Compliance Center använder du cmdleten **Get-RoleGroupMember** för att visa medlemmarna i rollgruppen Organisationshantering, vilket visas i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="da9e1-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="da9e1-135">Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="da9e1-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).</span></span>
