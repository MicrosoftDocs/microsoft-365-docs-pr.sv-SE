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
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754658"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="fba51-103">ID för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="fba51-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="fba51-104">Microsoft tillhandahåller identitets tjänst (IDaaS) över dess moln tjänster via Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fba51-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="fba51-105">För att kunna använda Microsoft 365 för företag måste lösningen contoso IDaaS ha använt sin lokala identitets leverantör och inkludera federerad identitet med sina befintliga betrodda tredjepartsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="fba51-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="fba51-106">Contoso Active Directory Domain Services-skogen</span><span class="sxs-lookup"><span data-stu-id="fba51-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="fba51-107">Contoso använder en enda AD DS-skog (Active Directory Domain Services) för Contoso \. com med sju under domäner, en för varje region i världen.</span><span class="sxs-lookup"><span data-stu-id="fba51-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="fba51-108">Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.</span><span class="sxs-lookup"><span data-stu-id="fba51-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="fba51-109">Här är contoso-skogen med regionala domäner för de olika delar av världen som innehåller regionala hubbar.</span><span class="sxs-lookup"><span data-stu-id="fba51-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="fba51-111">Contoso bestämde sig för att använda kontona och grupperna i Contoso \. com-skog för autentisering och godkännande för dess Microsoft 365-arbets belastning och tjänster.</span><span class="sxs-lookup"><span data-stu-id="fba51-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="fba51-112">Infrastrukturen contoso federerad Infrastructure</span><span class="sxs-lookup"><span data-stu-id="fba51-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="fba51-113">Med contoso kan:</span><span class="sxs-lookup"><span data-stu-id="fba51-113">Contoso allows:</span></span>

- <span data-ttu-id="fba51-114">Kunderna kan använda sina Microsoft-, Facebook-eller Google Mail-konton för att logga in på företagets offentliga webbplats.</span><span class="sxs-lookup"><span data-stu-id="fba51-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="fba51-115">Leverantörer och partners för att kunna använda sina LinkedIn-, Salesforce-eller Google Mail-konton för att logga in på företagets extra nät för partner.</span><span class="sxs-lookup"><span data-stu-id="fba51-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="fba51-116">Här är contoso-DMZ som innehåller en offentlig webbplats, ett extra nät för partner och en uppsättning AD FS-servrar (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="fba51-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="fba51-117">DMZ är ansluten till Internet som innehåller kunder, partners och Internet tjänster.</span><span class="sxs-lookup"><span data-stu-id="fba51-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso-support för extern inloggningsautentisering för kunder och partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="fba51-119">AD FS-servrar i DMZ underlättar autentisering av kund uppgifter genom sin identitets leverantör för åtkomst till den offentliga webbplatsen och partner uppgifterna för åtkomst till partner nätet.</span><span class="sxs-lookup"><span data-stu-id="fba51-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="fba51-120">Contoso bestämde sig för att behålla denna infrastruktur och tilldela den till kund-och partner-inloggningsautentisering.</span><span class="sxs-lookup"><span data-stu-id="fba51-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="fba51-121">Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations)- och [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-lösningar.</span><span class="sxs-lookup"><span data-stu-id="fba51-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="fba51-122">Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering</span><span class="sxs-lookup"><span data-stu-id="fba51-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="fba51-123">Contoso ville använda sin lokala AD DS-skog för att verifiera till Microsoft 365 Cloud Resources.</span><span class="sxs-lookup"><span data-stu-id="fba51-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="fba51-124">Det beslutade att använda Lösenordssynkronisering (PHS).</span><span class="sxs-lookup"><span data-stu-id="fba51-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="fba51-125">PHS synkroniserar den lokala AD DS-skogen med Azure AD-innehavaren av sitt Microsoft 365 för företags prenumeration, kopierar användare och grupp konton och en hash-version av användar konto lösen ord.</span><span class="sxs-lookup"><span data-stu-id="fba51-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="fba51-126">Om du vill göra en katalog-synkronisering distribuerar contoso verktyget Azure AD Connect på en server i Paris data centret.</span><span class="sxs-lookup"><span data-stu-id="fba51-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="fba51-127">Här är den server som kör Azure AD Connect-avsökning av contoso AD DS-skogen för ändringar och sedan synkroniserar dessa ändringar med Azure AD-klienten.</span><span class="sxs-lookup"><span data-stu-id="fba51-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infrastrukturen för Contoso PHS Directory-synkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="fba51-129">Principer för villkorlig åtkomst för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="fba51-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="fba51-130">Contoso skapade en uppsättning [principer för villkorlig åtkomst](identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:</span><span class="sxs-lookup"><span data-stu-id="fba51-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="fba51-131">*Grundläggande* skydd gäller för alla användar konton.</span><span class="sxs-lookup"><span data-stu-id="fba51-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="fba51-132">*Känsliga* skydd gäller för chefens ledarskap och direktör.</span><span class="sxs-lookup"><span data-stu-id="fba51-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="fba51-133">*Starkt reglerade* skydd gäller för specifika användare i ekonomi-, juridik-och forsknings avdelningar som har till gång till högreglerade data.</span><span class="sxs-lookup"><span data-stu-id="fba51-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="fba51-134">Här är den resulterande uppsättningen med principer för villkorsstyrd åtkomst via contoso och Device.</span><span class="sxs-lookup"><span data-stu-id="fba51-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="fba51-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fba51-136">Next step</span></span>

<span data-ttu-id="fba51-137">Lär dig hur Contoso använder sin Microsoft Endpoint Configuration Manager-infrastruktur för att [distribuera och hålla nuvarande Windows 10-företag](contoso-win10.md) i sin organisation.</span><span class="sxs-lookup"><span data-stu-id="fba51-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fba51-138">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="fba51-138">See also</span></span>

[<span data-ttu-id="fba51-139">Identitets översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fba51-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fba51-140">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fba51-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fba51-141">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="fba51-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
