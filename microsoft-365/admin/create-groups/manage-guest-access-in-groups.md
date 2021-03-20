---
title: Hantera gäståtkomst i Microsoft 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lär dig hur du lägger till gäster i en Microsoft 365-grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomst.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908612"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="f97ef-103">Hantera gäståtkomst i Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="f97ef-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="f97ef-104">Som standard är gäståtkomst för Microsoft 365-grupper aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f97ef-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="f97ef-105">Administratörer kan styra om de vill tillåta gäståtkomst till grupper för hela organisationen eller för enskilda grupper.</span><span class="sxs-lookup"><span data-stu-id="f97ef-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="f97ef-106">När det är aktiverat kan gruppmedlemmar bjuda in gästanvändare till en Microsoft 365-grupp via Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="f97ef-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="f97ef-107">Inbjudningar skickas till gruppägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="f97ef-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="f97ef-108">När den har godkänts läggs gästanvändaren till i katalogen och gruppen.</span><span class="sxs-lookup"><span data-stu-id="f97ef-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="f97ef-109">Yammer Enterprise-nätverk som är i inbyggt läge eller [SOM GEO inte](/yammer/manage-security-and-compliance/manage-data-compliance) har stöd för nätverksgäster.</span><span class="sxs-lookup"><span data-stu-id="f97ef-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="f97ef-110">Microsoft 365-anslutna Yammer-grupper stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna, externa grupper i Yammer-nätverket.</span><span class="sxs-lookup"><span data-stu-id="f97ef-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="f97ef-111">Instruktioner [finns i Skapa och hantera externa grupper i Yammer.](/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="f97ef-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="f97ef-112">Gäståtkomst i grupper används ofta som en del av ett bredare scenario som inkluderar SharePoint eller Teams.</span><span class="sxs-lookup"><span data-stu-id="f97ef-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="f97ef-113">De här tjänsterna har egna inställningar för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="f97ef-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="f97ef-114">Fullständiga instruktioner för hur du inställningar gästdelning mellan grupper, SharePoint och Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="f97ef-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="f97ef-115">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="f97ef-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="f97ef-116">Samarbeta med gäster i en grupp</span><span class="sxs-lookup"><span data-stu-id="f97ef-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="f97ef-117">Hantera gäståtkomst i grupper</span><span class="sxs-lookup"><span data-stu-id="f97ef-117">Manage groups guest access</span></span>

<span data-ttu-id="f97ef-118">Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f97ef-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f97ef-119">I administrationscentret går du till Visa **alla inställningar** \> **Organisationsinställningar** och på fliken \>  **Tjänster** väljer du **Microsoft 365-grupper.**</span><span class="sxs-lookup"><span data-stu-id="f97ef-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="f97ef-120">På sidan **Microsoft 365 Grupper** väljer du om du vill låta personer utanför organisationen få åtkomst till gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.</span><span class="sxs-lookup"><span data-stu-id="f97ef-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="f97ef-121">Lägga till gäster i en Microsoft 365-grupp från administrationscentret</span><span class="sxs-lookup"><span data-stu-id="f97ef-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="f97ef-122">Om gästen redan finns i katalogen kan du lägga till dem i dina grupper från administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f97ef-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f97ef-123">(Grupper med dynamiskt medlemskap måste [hanteras i Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="f97ef-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="f97ef-124">Gå till sidan Grupper i **administrationscentret.**  >  </span><span class="sxs-lookup"><span data-stu-id="f97ef-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="f97ef-125">Klicka på den grupp som du vill lägga till gästen i och **välj Visa alla och hantera** medlemmar på **fliken** Medlemmar.</span><span class="sxs-lookup"><span data-stu-id="f97ef-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="f97ef-126">Välj **Lägg till** medlemmar och välj namnet på gästen som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="f97ef-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="f97ef-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f97ef-127">Select **Save**.</span></span>

<span data-ttu-id="f97ef-128">Om du vill lägga till en gäst i katalogen direkt kan du lägga [till Azure Active Directory B2B-samarbetsanvändare i Azure-portalen.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="f97ef-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="f97ef-129">Om du vill redigera någon gästinformation kan du lägga till eller uppdatera en användares [profilinformation med hjälp av Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="f97ef-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="f97ef-130">Se även</span><span class="sxs-lookup"><span data-stu-id="f97ef-130">See also</span></span>

[<span data-ttu-id="f97ef-131">Blockera gästanvändare från en viss grupp</span><span class="sxs-lookup"><span data-stu-id="f97ef-131">Block guest users from a specific group</span></span>](../../solutions/per-group-guest-access.md)

[<span data-ttu-id="f97ef-132">Hantera gruppmedlemskap i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f97ef-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="f97ef-133">Åtkomstgranskningar i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f97ef-133">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="f97ef-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="f97ef-134">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)