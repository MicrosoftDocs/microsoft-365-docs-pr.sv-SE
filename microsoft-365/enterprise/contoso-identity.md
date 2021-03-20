---
title: ID för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hur Contoso använder sig av IDaaS (identitet som tjänst) och tillhandahåller molnbaserad autentisering för anställda och federerad autentisering för partner och kunder.
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911078"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="9e32b-103">ID för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="9e32b-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="9e32b-104">Microsoft tillhandahåller identitet som en tjänst (IDaaS) i sina molntjänster via Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9e32b-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9e32b-105">För att använda Microsoft 365 för företag var Contoso IDaaS-lösningen tvungen att använda deras lokala identitetsprovider och inkludera federerad autentisering med sina befintliga betrodda tredjepartsidentitetsproviders.</span><span class="sxs-lookup"><span data-stu-id="9e32b-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="9e32b-106">Contoso Active Directory Domain Services-skogen</span><span class="sxs-lookup"><span data-stu-id="9e32b-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="9e32b-107">Contoso använder en enda AD DS-skog (Active Directory Domain Services) för contoso com med sju underdomäner, en för varje \. region i världen.</span><span class="sxs-lookup"><span data-stu-id="9e32b-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="9e32b-108">Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.</span><span class="sxs-lookup"><span data-stu-id="9e32b-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="9e32b-109">Här är Contoso-skogen med regionala domäner för olika delar av världen som innehåller regionala nav.</span><span class="sxs-lookup"><span data-stu-id="9e32b-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="9e32b-111">Contoso beslutade att använda konton och grupper i Contoso com-skogen för autentisering och auktorisering för sina \. Microsoft 365-arbetsbelastningar och -tjänster.</span><span class="sxs-lookup"><span data-stu-id="9e32b-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="9e32b-112">Infrastrukturen för contoso-federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="9e32b-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="9e32b-113">Med contoso kan:</span><span class="sxs-lookup"><span data-stu-id="9e32b-113">Contoso allows:</span></span>

- <span data-ttu-id="9e32b-114">Kunder kan använda sina Microsoft-, Facebook- eller Google Mail-konton för att logga in på företagets offentliga webbplats.</span><span class="sxs-lookup"><span data-stu-id="9e32b-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="9e32b-115">Leverantörer och partner kan använda sina LinkedIn-, Salesforce- eller Google Mail-konton för att logga in på företagets partnerextranät.</span><span class="sxs-lookup"><span data-stu-id="9e32b-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="9e32b-116">Här är Contoso DMZ som innehåller en offentlig webbplats, ett extranät för partner och en uppsättning AD FS-servrar (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="9e32b-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="9e32b-117">DMZ är anslutet till internet som innehåller kunder, partners och internettjänster.</span><span class="sxs-lookup"><span data-stu-id="9e32b-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso stöd för federerad autentisering för kunder och partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="9e32b-119">AD FS-servrar i DMZ underlättar autentisering av kunduppgifter genom deras identitetsproviders för åtkomst till den offentliga webbplatsen och partnerautentiseringsuppgifter för åtkomst till partnerextranätet.</span><span class="sxs-lookup"><span data-stu-id="9e32b-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="9e32b-120">Contoso beslutade att behålla den här infrastrukturen och avsätta den till autentisering för kunder och partner.</span><span class="sxs-lookup"><span data-stu-id="9e32b-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="9e32b-121">Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations)- och [B2C](/azure/active-directory-b2c/solution-articles)-lösningar.</span><span class="sxs-lookup"><span data-stu-id="9e32b-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="9e32b-122">Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering</span><span class="sxs-lookup"><span data-stu-id="9e32b-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="9e32b-123">Contoso ville använda sin lokala AD DS-skog för autentisering på Microsoft 365-molnresurser.</span><span class="sxs-lookup"><span data-stu-id="9e32b-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="9e32b-124">Den valde att använda synkronisering av lösenordshashar (PHS).</span><span class="sxs-lookup"><span data-stu-id="9e32b-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="9e32b-125">PHS synkroniserar den lokala AD DS-skogen med Azure AD-klientorganisationen för deras Microsoft 365 för företag-prenumeration, kopiering av användar- och gruppkonton och en hash-version av lösenord för användarkonton.</span><span class="sxs-lookup"><span data-stu-id="9e32b-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="9e32b-126">För att göra katalogsynkronisering distribuerade Contoso Azure AD Connect-verktyget på en server i sitt Paris-datacenter.</span><span class="sxs-lookup"><span data-stu-id="9e32b-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="9e32b-127">Här är servern som kör Azure AD Connect och avsöker Contoso AD DS-skogen efter ändringar och synkroniserar sedan dessa ändringar med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="9e32b-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastrukturen för Contoso PHS-katalogsynkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="9e32b-129">Principer för villkorlig åtkomst för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="9e32b-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="9e32b-130">Contoso skapade en uppsättning [principer för villkorlig åtkomst](../security/office-365-security/identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:</span><span class="sxs-lookup"><span data-stu-id="9e32b-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/office-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="9e32b-131">*Baslinjeskydd* gäller för alla användarkonton.</span><span class="sxs-lookup"><span data-stu-id="9e32b-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="9e32b-132">*Känsliga* skydd gäller för ledningsgruppen och ledningsgruppen.</span><span class="sxs-lookup"><span data-stu-id="9e32b-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="9e32b-133">*Starkt reglerade* skydd gäller för specifika användare på ekonomi-, juridik- och forskningsavdelningen som har tillgång till högreglerade data.</span><span class="sxs-lookup"><span data-stu-id="9e32b-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="9e32b-134">Här är den resulterande uppsättningen principer för Contoso-identitet och villkorsstyrd åtkomst på enheter.</span><span class="sxs-lookup"><span data-stu-id="9e32b-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="9e32b-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9e32b-136">Next step</span></span>

<span data-ttu-id="9e32b-137">Lär dig hur Contoso använder sin infrastruktur för Microsoft Endpoint Configuration Manager för att distribuera [och behålla aktuella Windows 10 Enterprise](contoso-win10.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9e32b-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e32b-138">Se även</span><span class="sxs-lookup"><span data-stu-id="9e32b-138">See also</span></span>

[<span data-ttu-id="9e32b-139">Identitets översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e32b-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="9e32b-140">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="9e32b-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9e32b-141">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="9e32b-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)