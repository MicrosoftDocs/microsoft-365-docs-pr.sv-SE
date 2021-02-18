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
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="43a6c-103">Ge användare tillgång till Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="43a6c-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="43a6c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="43a6c-104">**Applies to**</span></span>
- [<span data-ttu-id="43a6c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="43a6c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="43a6c-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="43a6c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="43a6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43a6c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="43a6c-108">Användare måste ha tilldelats behörigheter i Säkerhets- & center för efterlevnad innan de kan hantera någon av dess säkerhets- eller efterlevnadsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="43a6c-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="43a6c-109">Som global administratör eller medlem i rollgruppen Organisationsmanagement i Säkerhets- & Efterlevnadscenter kan du ge de här behörigheterna till användare.</span><span class="sxs-lookup"><span data-stu-id="43a6c-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="43a6c-110">Användare kommer bara att kunna hantera de säkerhets- och efterlevnadsfunktioner som du ger dem åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="43a6c-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="43a6c-111">Mer information om de olika behörigheter du kan ge användare i Säkerhets- och & efterlevnadscenter finns i Behörigheter i Säkerhets- & [Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="43a6c-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="43a6c-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="43a6c-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="43a6c-113">Du måste vara global administratör eller medlem i rollgruppen Organisationsadministration i Säkerhets- och & efterlevnadscenter för att slutföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="43a6c-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="43a6c-114">Rollgrupper för Säkerhets- & Efterlevnadscenter kan ha liknande namn som rollgrupperna i Exchange Online, men de är inte desamma.</span><span class="sxs-lookup"><span data-stu-id="43a6c-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="43a6c-115">Medlemskap i rollgrupper delas inte mellan Exchange Online och Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="43a6c-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="43a6c-116">DAP-partners (Delegated Access Permission) med AOBO-behörigheter (Administer On Behalf Of) har inte åtkomst till Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="43a6c-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="43a6c-117">Använd Säkerhets- & för att ge en annan användare åtkomst till Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="43a6c-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="43a6c-118">Öppna Säkerhets- & Efterlevnadscenter <https://protection.office.com> och gå sedan till **Behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="43a6c-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="43a6c-119">Gå direkt till fliken **Behörigheter** genom att <https://protection.office.com/permissions> öppna.</span><span class="sxs-lookup"><span data-stu-id="43a6c-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="43a6c-120">I listan över rollgrupper väljer du rollgruppen  och klickar sedan på ikonen ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Redigera.</span><span class="sxs-lookup"><span data-stu-id="43a6c-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="43a6c-121">På egenskapssidan för rollgruppen under  **Medlemmar** klickar du på Lägg till ikon och väljer namnet på den ![ användare ](../../media/ITPro-EAC-AddIcon.gif) (eller användare) du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="43a6c-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="43a6c-122">När du har markerat alla användare som du vill lägga till i rollgruppen klickar du på **lägg till och \>** sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="43a6c-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="43a6c-123">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="43a6c-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="43a6c-124">Använda Säkerhets- & Efterlevnadscenter PowerShell för att ge en annan användare tillgång & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="43a6c-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="43a6c-125">[Anslut till Säkerhets- & Compliance Center PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="43a6c-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="43a6c-126">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="43a6c-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="43a6c-127">Detaljerade syntax- och parameterproblem finns i [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="43a6c-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="43a6c-128">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="43a6c-128">How do you know this worked?</span></span>

<span data-ttu-id="43a6c-129">Om du vill verifiera att du har beviljats åtkomst till Säkerhets- & efterlevnadscenter gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="43a6c-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="43a6c-130">Gå till & i Säkerhets- **och efterlevnadscenter** och välj rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="43a6c-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="43a6c-131">Kontrollera medlemmarna i rollgruppen i den utfäll plats för information som öppnas.</span><span class="sxs-lookup"><span data-stu-id="43a6c-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="43a6c-132">I Säkerhetscenter & PowerShell ersätter du med namnet på \<RoleGroupName\> rollgruppen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="43a6c-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="43a6c-133">Detaljerad information om syntax och parametrar finns i [Get-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)</span><span class="sxs-lookup"><span data-stu-id="43a6c-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
