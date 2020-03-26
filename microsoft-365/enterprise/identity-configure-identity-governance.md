---
title: 'Steg 7: Konfigurera identitetsstyrning'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera identitetsstyrning för Azure AD-innehavaren.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812597"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="57ed6-103">Step 6: Konfigurera identitetsstyrning</span><span class="sxs-lookup"><span data-stu-id="57ed6-103">Step 6: Configure identity governance</span></span>

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="57ed6-105">Identitetsstyrning handlar om att skydda, övervaka och granska åtkomst till kritiska tillgångar och samtidigt säkerställa den anställdas produktivitet.</span><span class="sxs-lookup"><span data-stu-id="57ed6-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="57ed6-106">Med identitetsstyrning kan du till exempel se till att rätt användare har rätt åtkomst till rätt resurser och fastställa om åtkomsten förändras med tiden.</span><span class="sxs-lookup"><span data-stu-id="57ed6-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="57ed6-107">Mer information om identitets styrning för Azure Active Directory (Azure AD) finns [den här artikeln](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="57ed6-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="57ed6-108">*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="57ed6-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="57ed6-109">Konfigurera Azure AD-åtkomstgranskningar</span><span class="sxs-lookup"><span data-stu-id="57ed6-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="57ed6-110">*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="57ed6-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="57ed6-111">I det här steget konfigurerar du Azure AD-åtkomstgranskningar, som gör att du kan granska en användares åtkomst för att säkerställa att bara rätt personer har fortsatt åtkomst.</span><span class="sxs-lookup"><span data-stu-id="57ed6-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="57ed6-112">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="57ed6-112">For example:</span></span>

- <span data-ttu-id="57ed6-113">När en ny medarbetare ansluter sig till din organisation måste du se till att personen har rätt åtkomst för att kunna vara produktiv.</span><span class="sxs-lookup"><span data-stu-id="57ed6-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="57ed6-114">När den anställde flyttar till andra team, platser eller avdelningar måste du se till att personens åtkomst till tidigare grupper, platser eller avdelningar tas bort efter behov.</span><span class="sxs-lookup"><span data-stu-id="57ed6-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="57ed6-115">När den anställde eller en gäst lämnar din organisation måste du se till att åtkomsten tas bort.</span><span class="sxs-lookup"><span data-stu-id="57ed6-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="57ed6-116">Det här är särskilt viktigt om organisationen genomgår säkerhetsgranskningar för att avgöra om användarkonton har för mycket åtkomst, vilket kan resultera i böter om branschregler eller regionala föreskrifter överträds.</span><span class="sxs-lookup"><span data-stu-id="57ed6-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="57ed6-117">I [den här artikeln](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) finns mer information om Azure AD-åtkomstgranskningar.</span><span class="sxs-lookup"><span data-stu-id="57ed6-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="57ed6-118">Azure AD-privilegierad identitetshantering (PIM) tillhandahåller ytterligare kontroller som är anpassade för att skydda åtkomsträttigheter för resurser, på Azure AD, Azure och andra Microsoft-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="57ed6-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="57ed6-119">Med Azure AD PIM får du en omfattande uppsättning styrningskontroller som hjälper dig att skydda företagets resurser, till exempel Directory, Office 365 och Azure-resursroller.</span><span class="sxs-lookup"><span data-stu-id="57ed6-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="57ed6-120">Precis som med andra former av åtkomst kan organisationer använda åtkomstgranskningar för att konfigurera återkommande åtkomst för alla användare i administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="57ed6-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="57ed6-121">Azure AD PIM finns bara i E5-versionen av Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="57ed6-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="57ed6-122">I följande artiklar beskrivs hur olika typer av åtkomstgranskningar konfigureras:</span><span class="sxs-lookup"><span data-stu-id="57ed6-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="57ed6-123">Grupper och appar</span><span class="sxs-lookup"><span data-stu-id="57ed6-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="57ed6-124">Azure AD-roller</span><span class="sxs-lookup"><span data-stu-id="57ed6-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="57ed6-125">Azure-resursroller</span><span class="sxs-lookup"><span data-stu-id="57ed6-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="57ed6-126">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-access-reviews) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="57ed6-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="57ed6-127">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="57ed6-127">Next step</span></span>

[<span data-ttu-id="57ed6-128">Avslutsvillkor för identitetsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="57ed6-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

