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
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="cf5f1-103">Ge användarna åtkomst till säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cf5f1-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="cf5f1-104">Användare måste tilldelas behörigheter i säkerhets & efterlevnad för att de ska kunna hantera alla dess säkerhets-eller efterlevnads funktioner.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="cf5f1-105">Som global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center kan du ge dessa behörigheter till användare.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="cf5f1-106">Användarna kan bara hantera de säkerhets-eller efterföljandekrav du ger dem till gång till.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="cf5f1-107">Om du vill ha mer information om de olika behörigheter du kan ge användare i avsnittet om säkerhets & efterlevnad kan du läsa [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cf5f1-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf5f1-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cf5f1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf5f1-109">Du måste vara global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center för att slutföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="cf5f1-110">Roll grupper för säkerhets & efterlevnad kan ha liknande namn för roll grupperna i Exchange Online, men de är inte samma.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="cf5f1-111">Roll grupps medlemskap delas inte mellan Exchange Online och säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="cf5f1-112">DAP-partners (delegerad Access permission) med administrera (AOBO) behörigheter får inte till gång till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="cf5f1-113">Använd administrations centret för att ge en annan användare åtkomst till sidan säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cf5f1-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="cf5f1-114">[Logga in och gå till administrations centret](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="cf5f1-114">[Sign in and go to the admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="cf5f1-115">Öppna **Administratörs** Center i administrations centret för Microsoft 365 och klicka sedan på **säkerhets & efterlevnad**.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="cf5f1-116">Gå till **behörigheter**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="cf5f1-117">Välj den roll grupp i listan som du vill lägga till användaren i och klicka på **Redigera** ![ redigerings ikon ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="cf5f1-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="cf5f1-118">På roll gruppens egenskaps sida under **medlemmar**klickar du på **Lägg**till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.gif) och väljer namnet på den eller de användare som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="cf5f1-119">När du har valt alla användare som du vill lägga till i roll gruppen klickar du på \*\*Lägg till \> \*\* och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="cf5f1-120">Klicka på **Spara** för att spara ändringarna i roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cf5f1-121">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="cf5f1-121">How do you know this worked?</span></span>

1. <span data-ttu-id="cf5f1-122">Gå till **behörigheter**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="cf5f1-123">I listan väljer du roll gruppen för att Visa medlemmarna.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="cf5f1-124">Till höger i roll grupps informationen kan du Visa medlemmarna i roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="cf5f1-125">Använda PowerShell för att ge en annan användare åtkomst till säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cf5f1-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="cf5f1-126">[Anslut till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf5f1-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="cf5f1-127">Använd kommandot **Add-RoleGroupMember** för att lägga till en användare i rollen organisations hantering, enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="cf5f1-128">**Parametrar**:</span><span class="sxs-lookup"><span data-stu-id="cf5f1-128">**Parameters**:</span></span>

   - <span data-ttu-id="cf5f1-129">_Identitet_ är roll gruppen som du vill lägga till en medlem i.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="cf5f1-130">_Medlem_ är post låda, universell säkerhets grupp (USG) eller dator som ska läggas till i roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="cf5f1-131">Du kan bara ange en medlem åt gången.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="cf5f1-132">Detaljerad information om syntax och parametrar finns i avsnittet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="cf5f1-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cf5f1-133">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="cf5f1-133">How do you know this worked?</span></span>

<span data-ttu-id="cf5f1-134">För att verifiera att du har gett användare åtkomst till säkerhets & Compliance Center använder du cmdleten **Get-RoleGroupMember** för att Visa medlemmarna i roll gruppen organisations hantering, enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="cf5f1-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="cf5f1-135">Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="cf5f1-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
