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
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="ad831-103">Ge användarna åtkomst till säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="ad831-103">Give users access to the Security & Compliance Center</span></span>

<span data-ttu-id="ad831-104">Användare måste tilldelas behörigheter i säkerhets & efterlevnad för att de ska kunna hantera alla dess säkerhets-eller efterlevnads funktioner.</span><span class="sxs-lookup"><span data-stu-id="ad831-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="ad831-105">Som global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center kan du ge dessa behörigheter till användare.</span><span class="sxs-lookup"><span data-stu-id="ad831-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="ad831-106">Användarna kan bara hantera de säkerhets-eller efterföljandekrav du ger dem till gång till.</span><span class="sxs-lookup"><span data-stu-id="ad831-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="ad831-107">Om du vill ha mer information om de olika behörigheter du kan ge användare i avsnittet om säkerhets & efterlevnad kan du läsa [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ad831-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad831-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ad831-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad831-109">Du måste vara global administratör eller medlem i roll gruppen i i säkerhets & Compliance Center för att slutföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ad831-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="ad831-110">Roll grupper för säkerhets & efterlevnad kan ha liknande namn för roll grupperna i Exchange Online, men de är inte samma.</span><span class="sxs-lookup"><span data-stu-id="ad831-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="ad831-111">Roll grupps medlemskap delas inte mellan Exchange Online och säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ad831-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="ad831-112">DAP-partners (delegerad Access permission) med administrera (AOBO) behörigheter får inte till gång till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ad831-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ad831-113">Använd säkerhets & Compliance Center för att ge en annan användare åtkomst till säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ad831-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ad831-114">Öppna säkerhets & Compliance Center på <https://protection.office.com> och gå sedan till **behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="ad831-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="ad831-115">Öppna för att gå direkt till fliken **behörigheter** <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="ad831-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="ad831-116">I listan över roll grupper väljer du roll gruppen och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="ad831-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="ad831-117">På roll gruppens egenskaps sida under **medlemmar**klickar du på **Lägg**till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.gif) och väljer namnet på den eller de användare som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="ad831-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="ad831-118">När du har valt alla användare som du vill lägga till i roll gruppen klickar du på \*\*Lägg till \> \*\* och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad831-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="ad831-119">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="ad831-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="ad831-120">Använda säkerhets & Compliance Center PowerShell för att ge en annan användare åtkomst till säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ad831-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="ad831-121">[Anslut till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad831-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="ad831-122">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="ad831-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="ad831-123">Detaljerad information om syntax och parametrar finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="ad831-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ad831-124">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="ad831-124">How do you know this worked?</span></span>

<span data-ttu-id="ad831-125">Gör något av följande om du vill verifiera att du har beviljats åtkomst till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ad831-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="ad831-126">Gå till **behörigheter** i säkerhets & efterlevnad och välj roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="ad831-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="ad831-127">I den utfällbara informationen som öppnas kontrollerar du medlemmarna i roll gruppen.</span><span class="sxs-lookup"><span data-stu-id="ad831-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="ad831-128">I säkerhets & Compliance Center PowerShell, Ersätt \<RoleGroupName\> med namnet på roll gruppen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ad831-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="ad831-129">Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="ad831-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
