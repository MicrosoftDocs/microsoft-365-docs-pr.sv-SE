---
title: Hantera gäståtkomst i Microsoft 365 grupper
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
description: Lär dig hur du lägger till gäster Microsoft 365 grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomst.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571943"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="f7e37-103">Hantera gäståtkomst i Microsoft 365 grupper</span><span class="sxs-lookup"><span data-stu-id="f7e37-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="f7e37-104">Som standard är gäståtkomst för Microsoft 365 grupper aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="f7e37-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="f7e37-105">Administratörer kan styra om de vill tillåta gäståtkomst till grupper för hela organisationen eller för enskilda grupper.</span><span class="sxs-lookup"><span data-stu-id="f7e37-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="f7e37-106">När det är aktiverat kan gruppmedlemmar bjuda in gästanvändare till en Microsoft 365 via Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="f7e37-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="f7e37-107">Inbjudningar skickas till gruppägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="f7e37-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="f7e37-108">När den har godkänts läggs gästanvändaren till i katalogen och gruppen.</span><span class="sxs-lookup"><span data-stu-id="f7e37-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="f7e37-109">Yammer Enterprise nätverk som är i inbyggt läge eller [som GEO inte](/yammer/manage-security-and-compliance/manage-data-compliance) har stöd för nätverksgäster.</span><span class="sxs-lookup"><span data-stu-id="f7e37-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="f7e37-110">Microsoft 365 Anslutna Yammer grupper stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna, externa grupper i ditt Yammer nätverk.</span><span class="sxs-lookup"><span data-stu-id="f7e37-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="f7e37-111">Instruktioner [finns i Skapa och hantera externa grupper Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) grupper.</span><span class="sxs-lookup"><span data-stu-id="f7e37-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="f7e37-112">Gäståtkomst i grupper används ofta som en del av ett bredare scenario som omfattar SharePoint eller Teams.</span><span class="sxs-lookup"><span data-stu-id="f7e37-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="f7e37-113">De här tjänsterna har egna inställningar för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="f7e37-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="f7e37-114">Fullständiga instruktioner för hur du inställningar gästdelning mellan grupper, SharePoint och Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="f7e37-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="f7e37-115">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="f7e37-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="f7e37-116">Samarbeta med gäster i en grupp</span><span class="sxs-lookup"><span data-stu-id="f7e37-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="f7e37-117">Hantera gäståtkomst i grupper</span><span class="sxs-lookup"><span data-stu-id="f7e37-117">Manage groups guest access</span></span>

<span data-ttu-id="f7e37-118">Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f7e37-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f7e37-119">I administrationscentret går du till Visa **Inställningar** organisationsinställningar och på fliken \>  \>  **Tjänster** väljer du **Microsoft 365 grupper.**</span><span class="sxs-lookup"><span data-stu-id="f7e37-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="f7e37-120">På sidan **Microsoft 365 grupper** väljer du om du vill låta personer utanför organisationen få åtkomst till gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.</span><span class="sxs-lookup"><span data-stu-id="f7e37-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="f7e37-121">Lägga till gäster i Microsoft 365 grupp från administrationscentret</span><span class="sxs-lookup"><span data-stu-id="f7e37-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="f7e37-122">Om gästen redan finns i katalogen kan du lägga till dem i grupperna från Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="f7e37-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f7e37-123">(Grupper med dynamiskt medlemskap måste [hanteras i Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="f7e37-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="f7e37-124">Gå till sidan Grupper i **administrationscentret.**  >  </span><span class="sxs-lookup"><span data-stu-id="f7e37-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="f7e37-125">Klicka på den grupp som du vill lägga till gästen i och **välj Visa alla och hantera** medlemmar på **fliken** Medlemmar.</span><span class="sxs-lookup"><span data-stu-id="f7e37-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="f7e37-126">Välj **Lägg till** medlemmar och välj namnet på gästen som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="f7e37-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="f7e37-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f7e37-127">Select **Save**.</span></span>

<span data-ttu-id="f7e37-128">Om du vill lägga till en gäst i katalogen direkt kan du lägga [till Azure Active Directory B2B-samarbetsanvändare i Azure Portal.](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="f7e37-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="f7e37-129">Om du vill redigera någon gästinformation kan du lägga till eller uppdatera en användares [profilinformation med hjälp av Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="f7e37-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="f7e37-130">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="f7e37-130">Related content</span></span>

<span data-ttu-id="f7e37-131">[Blockera gästanvändare från en viss grupp](../../solutions/per-group-guest-access.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f7e37-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="f7e37-132">[Hantera gruppmedlemskap i Microsoft 365 (artikel)](add-or-remove-members-from-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f7e37-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="f7e37-133">[Azure Active Directory granskningar av åtkomst](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f7e37-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="f7e37-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f7e37-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>