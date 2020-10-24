---
title: Hantera gäst åtkomst i Microsoft 365-grupper
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
description: Lär dig hur du lägger till gäster i en Microsoft 365-grupp, visar gäst användare och använder PowerShell för att kontrol lera gäst åtkomst.
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753283"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="01baf-103">Hantera gäst åtkomst i Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="01baf-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="01baf-104">Gäst åtkomst för Microsoft 365-grupper är aktive rad som standard för din organisation.</span><span class="sxs-lookup"><span data-stu-id="01baf-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="01baf-105">Administratörer kan kontrol lera om gäst åtkomst ska tillåtas till grupper för hela organisationen eller för enskilda grupper.</span><span class="sxs-lookup"><span data-stu-id="01baf-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="01baf-106">När den är aktive rad kan grupp medlemmar bjuda in gäst användare till en Microsoft 365-grupp via Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="01baf-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="01baf-107">Inbjudningar skickas till gruppens ägare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="01baf-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="01baf-108">När gäst användaren har godkänts läggs den till i katalogen och i gruppen.</span><span class="sxs-lookup"><span data-stu-id="01baf-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="01baf-109">Yammer Enterprise-nätverk i enhetligt läge eller [EU geo](https://go.microsoft.com/fwlink/?linkid=2107357) stöder inte nätverks gäster.</span><span class="sxs-lookup"><span data-stu-id="01baf-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="01baf-110">Microsoft 365 anslöt Yammer-grupper stöder för närvarande inte gäst åtkomst, men du kan skapa icke anslutna externa grupper i Yammer-nätverket.</span><span class="sxs-lookup"><span data-stu-id="01baf-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="01baf-111">Se [skapa och hantera externa grupper i Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="01baf-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="01baf-112">Gäst åtkomst i grupper används ofta som en del av ett bredare scenario som innehåller SharePoint eller teams.</span><span class="sxs-lookup"><span data-stu-id="01baf-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="01baf-113">Dessa tjänster har sina egna inställningar för gäst delning.</span><span class="sxs-lookup"><span data-stu-id="01baf-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="01baf-114">Fullständiga anvisningar för hur du konfigurerar gäst delning i grupper, SharePoint och Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="01baf-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="01baf-115">Samar beta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="01baf-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="01baf-116">Samar beta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="01baf-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="01baf-117">Hantera grupper gäst åtkomst</span><span class="sxs-lookup"><span data-stu-id="01baf-117">Manage groups guest access</span></span>

<span data-ttu-id="01baf-118">Om du vill aktivera eller inaktivera gäst åtkomst i grupper kan du göra det i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01baf-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="01baf-119">I administrations centret går du till **Visa alla** \> **Inställningar** \> **organisations inställningar** och väljer **Microsoft 365 Groups**på fliken **tjänster** .</span><span class="sxs-lookup"><span data-stu-id="01baf-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="01baf-120">På sidan **Microsoft 365-grupper** väljer du om du vill låta personer utanför organisationen komma åt grupp resurserna eller låta grupp ägarna lägga till personer utanför organisationen till grupper.</span><span class="sxs-lookup"><span data-stu-id="01baf-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="01baf-121">Lägga till gäster i en Microsoft 365-grupp från administrations centret</span><span class="sxs-lookup"><span data-stu-id="01baf-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="01baf-122">Om gästen redan finns i katalogen kan du lägga till den i dina grupper från administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01baf-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="01baf-123">Gå till sidan grupper i administrations centret **Groups**  >  **Groups** .</span><span class="sxs-lookup"><span data-stu-id="01baf-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="01baf-124">Klicka på den grupp där du vill lägga till gästen och välj **Visa alla och hantera medlemmar** på fliken **medlemmar** .</span><span class="sxs-lookup"><span data-stu-id="01baf-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="01baf-125">Välj **Lägg till medlemmar**och välj namnet på den gäst du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="01baf-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="01baf-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="01baf-126">Select **Save**.</span></span>

<span data-ttu-id="01baf-127">Om du vill lägga till en gäst i katalogen direkt kan du [lägga till användare i Azure Active Directory B2B-samarbete i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="01baf-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="01baf-128">Om du vill redigera ett gäst konto kan du [lägga till eller uppdatera en användares profil information med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="01baf-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="01baf-129">Se även</span><span class="sxs-lookup"><span data-stu-id="01baf-129">See also</span></span>

[<span data-ttu-id="01baf-130">Blockera gäst användare i en viss grupp</span><span class="sxs-lookup"><span data-stu-id="01baf-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="01baf-131">Hantera grupp medlemskap i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01baf-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="01baf-132">Åtkomst granskning för Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01baf-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="01baf-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="01baf-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
