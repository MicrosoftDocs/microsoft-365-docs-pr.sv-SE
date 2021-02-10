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
ms.openlocfilehash: 9e19825ce0f8224b2aee8e1419ef5d1ad425aadb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165421"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="f4e44-103">Ge användare tillgång till Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="f4e44-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4e44-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f4e44-104">**Applies to**</span></span>
- [<span data-ttu-id="f4e44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f4e44-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="f4e44-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f4e44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="f4e44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4e44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f4e44-108">Användare måste ha tilldelats behörigheter i Säkerhets- & center för efterlevnad innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="f4e44-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="f4e44-109">Som global administratör eller medlem i rollgruppen Organisationsmanagement i Säkerhets- & Efterlevnadscenter kan du ge de här behörigheterna till användare.</span><span class="sxs-lookup"><span data-stu-id="f4e44-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="f4e44-110">Användare kommer bara att kunna hantera de säkerhets- och efterlevnadsfunktioner som du ger dem åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="f4e44-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="f4e44-111">Mer information om de olika behörigheter du kan ge användare i Säkerhets- och & efterlevnadscenter finns i Behörigheter i Säkerhets- & [Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="f4e44-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4e44-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f4e44-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4e44-113">Du måste vara global administratör eller medlem i rollgruppen Organisationsadministration i Säkerhets- och & efterlevnadscenter för att slutföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f4e44-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="f4e44-114">Rollgrupper för Säkerhets- & Efterlevnadscenter kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.</span><span class="sxs-lookup"><span data-stu-id="f4e44-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="f4e44-115">Medlemskap i rollgrupper delas inte mellan Exchange Online och Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="f4e44-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="f4e44-116">DAP-partners (Delegated Access Permission) med AOBO-behörigheter (Administer On Behalf) har inte åtkomst till Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="f4e44-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="f4e44-117">Använd Säkerhets- & för att ge en annan användare åtkomst till Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="f4e44-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="f4e44-118">Öppna Säkerhets- & Efterlevnadscenter <https://protection.office.com> och gå sedan till **Behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="f4e44-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="f4e44-119">Gå direkt till fliken **Behörigheter** genom att <https://protection.office.com/permissions> öppna.</span><span class="sxs-lookup"><span data-stu-id="f4e44-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="f4e44-120">I listan över rollgrupper väljer du rollgruppen  och klickar sedan på ikonen ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Redigera.</span><span class="sxs-lookup"><span data-stu-id="f4e44-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="f4e44-121">På rollgruppens egenskapssida under  **Medlemmar** klickar du på Lägg till ikon och väljer namnet på den ![ användare ](../../media/ITPro-EAC-AddIcon.gif) (eller användare) du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="f4e44-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="f4e44-122">När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **lägg till och \>** sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="f4e44-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="f4e44-123">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f4e44-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="f4e44-124">Använda Säkerhets- & Efterlevnadscenter PowerShell för att ge en annan användare tillgång & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="f4e44-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="f4e44-125">[Anslut till Säkerhets- & Compliance Center PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="f4e44-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f4e44-126">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f4e44-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="f4e44-127">Detaljerade syntax- och parameterproblem finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="f4e44-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f4e44-128">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="f4e44-128">How do you know this worked?</span></span>

<span data-ttu-id="f4e44-129">Om du vill verifiera att du har beviljats åtkomst till Säkerhets- & Efterlevnadscenter gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="f4e44-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="f4e44-130">Gå till & i Säkerhets- **och efterlevnadscenter** och välj rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="f4e44-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="f4e44-131">Kontrollera rollgruppens medlemmar i informationsfällan som öppnas.</span><span class="sxs-lookup"><span data-stu-id="f4e44-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="f4e44-132">I Säkerhetscenter & PowerShell ersätter du med namnet på \<RoleGroupName\> rollgruppen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="f4e44-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="f4e44-133">Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="f4e44-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
