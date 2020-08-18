---
title: Microsoft 365-moln-Only-identitet
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Här beskrivs hur du skapar användare och grupper när Microsoft 365-prenumerationen använder moln-Only-identitet.
ms.openlocfilehash: 4c8e7d4a29f548fca2fef9696f488dc333743ef9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694461"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="e573b-103">Microsoft 365-moln-Only-identitet</span><span class="sxs-lookup"><span data-stu-id="e573b-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="e573b-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e573b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e573b-105">Med endast Cloud-identitet lagras alla användare, grupper och kontakter i Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="e573b-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="e573b-106">Här är de grundläggande komponenterna i moln-Only-identitet.</span><span class="sxs-lookup"><span data-stu-id="e573b-106">Here are the basic components of cloud-only identity.</span></span>
 
![Bas komponenterna i moln-Only-identitet](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="e573b-108">Användare och användar konton i organisationer kan kategoriseras på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="e573b-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="e573b-109">Vissa är anställda och har permanent status.</span><span class="sxs-lookup"><span data-stu-id="e573b-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="e573b-110">Vissa är leverantörer, entreprenörer eller partners med tillfällig status.</span><span class="sxs-lookup"><span data-stu-id="e573b-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="e573b-111">Vissa är externa användare som inte har några användar konton men måste ändå beviljas åtkomst till specifika tjänster och resurser för att stödja samverkan och samarbete.</span><span class="sxs-lookup"><span data-stu-id="e573b-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="e573b-112">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e573b-112">For example:</span></span>

- <span data-ttu-id="e573b-113">Klient konton representerar användare inom din organisation som du licensierar för moln tjänster</span><span class="sxs-lookup"><span data-stu-id="e573b-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="e573b-114">Konton för företag mot företag (B2B) representerar användare utanför organisationen som du bjuder in att delta i samarbete</span><span class="sxs-lookup"><span data-stu-id="e573b-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="e573b-115">Ta lager med olika typer av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e573b-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="e573b-116">Vad är grupperingarna?</span><span class="sxs-lookup"><span data-stu-id="e573b-116">What are the groupings?</span></span> <span data-ttu-id="e573b-117">Du kan till exempel gruppera användarna efter en hög nivå funktion eller ett syfte för din organisation.</span><span class="sxs-lookup"><span data-stu-id="e573b-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="e573b-118">Dessutom kan vissa moln tjänster delas med användare utanför organisationen utan några användar konton.</span><span class="sxs-lookup"><span data-stu-id="e573b-118">Additionally, some cloud services can be shared with users outside your organization without any user accounts.</span></span> <span data-ttu-id="e573b-119">Du behöver också identifiera dessa användar grupper.</span><span class="sxs-lookup"><span data-stu-id="e573b-119">You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="e573b-120">Du kan använda grupper i Azure AD för att förenkla hanteringen av moln miljön.</span><span class="sxs-lookup"><span data-stu-id="e573b-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="e573b-121">Med Azure AD-grupper kan du till exempel:</span><span class="sxs-lookup"><span data-stu-id="e573b-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="e573b-122">Använd gruppbaserad licensiering för att tilldela licenser för Microsoft 365 till dina användar konton automatiskt när de läggs till som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="e573b-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="e573b-123">Lägga till användar konton i specifika grupper dynamiskt baserat på attribut för användar konton, till exempel avdelnings namn.</span><span class="sxs-lookup"><span data-stu-id="e573b-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="e573b-124">Tillhandahålla automatiskt användare för program vara som tjänst program och för att skydda åtkomsten till dessa program med multifaktorautentisering (MFA) och andra regler för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="e573b-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access rules.</span></span>
- <span data-ttu-id="e573b-125">Tillhandahåll behörigheter och åtkomst nivåer för SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="e573b-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

<span data-ttu-id="e573b-126">Du skapar nya ***användare*** med:</span><span class="sxs-lookup"><span data-stu-id="e573b-126">You create new ***users*** with:</span></span>

- [<span data-ttu-id="e573b-127">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e573b-127">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [<span data-ttu-id="e573b-128">PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e573b-128">PowerShell for Microsoft 365</span></span>](create-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="e573b-129">Du skapar nya ***grupper*** med:</span><span class="sxs-lookup"><span data-stu-id="e573b-129">You create new ***groups*** with:</span></span>

- [<span data-ttu-id="e573b-130">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e573b-130">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [<span data-ttu-id="e573b-131">PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e573b-131">PowerShell for Microsoft 365</span></span>](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a><span data-ttu-id="e573b-132">Nästa steg för moln identitet</span><span class="sxs-lookup"><span data-stu-id="e573b-132">Next step for cloud-only identity</span></span>

[<span data-ttu-id="e573b-133">Tilldela licenser till användar konton</span><span class="sxs-lookup"><span data-stu-id="e573b-133">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)