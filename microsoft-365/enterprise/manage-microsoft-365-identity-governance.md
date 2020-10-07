---
title: Hantera Microsoft 365 Identity styrelse
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lär dig mer om hur du använder Microsoft 365 Identity styrelse-funktioner.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370352"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="e8389-103">Hantera Microsoft 365 Identity styrelse</span><span class="sxs-lookup"><span data-stu-id="e8389-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="e8389-104">Identitetsstyrning handlar om att skydda, övervaka och granska åtkomst till kritiska tillgångar och samtidigt säkerställa den anställdas produktivitet.</span><span class="sxs-lookup"><span data-stu-id="e8389-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="e8389-105">Med identitetsstyrning kan du till exempel se till att rätt användare har rätt åtkomst till rätt resurser och fastställa om åtkomsten förändras med tiden.</span><span class="sxs-lookup"><span data-stu-id="e8389-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="e8389-106">Mer information finns i den här [översikten över identitets styrning för Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="e8389-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="e8389-107">Konfigurera Azure AD-åtkomstgranskningar</span><span class="sxs-lookup"><span data-stu-id="e8389-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="e8389-108">Med granskning av Azure AD Access kan du granska en användares åtkomst för att kontrol lera att endast rätt personer har fortsatt åtkomst.</span><span class="sxs-lookup"><span data-stu-id="e8389-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="e8389-109">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e8389-109">For example:</span></span>

- <span data-ttu-id="e8389-110">När en ny medarbetare ansluter sig till din organisation måste du se till att personen har rätt åtkomst för att kunna vara produktiv.</span><span class="sxs-lookup"><span data-stu-id="e8389-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="e8389-111">När den anställde flyttar till andra team, platser eller avdelningar måste du se till att personens åtkomst till tidigare grupper, platser eller avdelningar tas bort efter behov.</span><span class="sxs-lookup"><span data-stu-id="e8389-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="e8389-112">När den anställde eller en gäst lämnar din organisation måste du se till att åtkomsten tas bort.</span><span class="sxs-lookup"><span data-stu-id="e8389-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="e8389-113">Det här är särskilt viktigt om organisationen genomgår säkerhetsgranskningar för att avgöra om användarkonton har för mycket åtkomst, vilket kan resultera i böter om branschregler eller regionala föreskrifter överträds.</span><span class="sxs-lookup"><span data-stu-id="e8389-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="e8389-114">Mer information finns i [Översikt över Access-granskningar](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="e8389-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="e8389-115">I följande artiklar beskrivs hur olika typer av åtkomstgranskningar konfigureras:</span><span class="sxs-lookup"><span data-stu-id="e8389-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="e8389-116">Grupper och appar</span><span class="sxs-lookup"><span data-stu-id="e8389-116">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="e8389-117">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="e8389-117">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="e8389-118">Azure-resursroller</span><span class="sxs-lookup"><span data-stu-id="e8389-118">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="e8389-119">Konfigurera hantering av Azure AD Management</span><span class="sxs-lookup"><span data-stu-id="e8389-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="e8389-120">Rummet Azure AD Management-hantering, du kan hantera livs cykeln för identitet och åtkomst i skalan genom att automatisera arbets flöden för åtkomst förfrågningar, få till gång till uppgifter, recensioner och förfallo datum.</span><span class="sxs-lookup"><span data-stu-id="e8389-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="e8389-121">Dina anställda behöver åtkomst till olika grupper, program och webbplatser för att utföra sina jobb.</span><span class="sxs-lookup"><span data-stu-id="e8389-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="e8389-122">Det kan vara svårt att hantera den här åtkomsten eftersom kraven ändras, nya program läggs till eller att användare behöver ytterligare åtkomst rättigheter.</span><span class="sxs-lookup"><span data-stu-id="e8389-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="e8389-123">När du samarbetar med andra organisationer kanske du inte vet vem som finns i den andra organisationen som behöver åtkomst till organisationens resurser, och användare som inte vet vilka program, grupper eller webbplatser som organisationen använder.</span><span class="sxs-lookup"><span data-stu-id="e8389-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="e8389-124">Hantering av Azure AD Management kan hjälpa dig att effektivt hantera åtkomst till grupper, program och SharePoint-webbplatser för interna och externa användare.</span><span class="sxs-lookup"><span data-stu-id="e8389-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="e8389-125">Mer information finns i [Översikt över hantering av Azure AD Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e8389-125">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
