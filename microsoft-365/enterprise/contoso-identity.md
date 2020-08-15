---
title: ID för Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Hur Contoso använder sig av IDaaS (identitet som tjänst) och tillhandahåller molnbaserad autentisering för anställda och federerad autentisering för partner och kunder.
ms.openlocfilehash: 795fb7dcb886c792c80d3bb251c9cb5774f1bf97
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686040"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="acf7b-103">ID för Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="acf7b-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="acf7b-104">Microsoft tillhandahåller IDaaS (identitet som tjänst) i molnet med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="acf7b-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="acf7b-105">För att kunna använda Microsoft 365 för Enterprise, måste Contosos IDaaS-lösning utnyttja sin lokala identitets leverantör och ändå inkludera federerad identitet med sina befintliga betrodda tredjepartsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="acf7b-105">To adopt Microsoft 365 for enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="acf7b-106">Contosos Active Directory Domain Services-skog</span><span class="sxs-lookup"><span data-stu-id="acf7b-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="acf7b-107">Contoso använder en enda AD DS-skog (Active Directory Domain Services) för contoso.com med sju underdomäner, en för varje region i världen.</span><span class="sxs-lookup"><span data-stu-id="acf7b-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="acf7b-108">Huvudkontoret, regionala navkontor och satellitkontor innehåller domänkontrollanter för lokal autentisering och verifiering.</span><span class="sxs-lookup"><span data-stu-id="acf7b-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="acf7b-109">Här är Contoso-skogen med regionala domäner för de olika delar av världen som innehåller regionala nav.</span><span class="sxs-lookup"><span data-stu-id="acf7b-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Contosos skogar och domäner över hela världen](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="acf7b-111">Contoso ville använda konton och grupper i contoso.com-skogen för autentisering och auktorisering för sina Microsoft 365-arbetsbelastningar och -tjänster.</span><span class="sxs-lookup"><span data-stu-id="acf7b-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="acf7b-112">Contosos infrastruktur för federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="acf7b-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="acf7b-113">Med contoso kan:</span><span class="sxs-lookup"><span data-stu-id="acf7b-113">Contoso allows:</span></span>

- <span data-ttu-id="acf7b-114">Kunder använda Microsoft, Facebook eller Google Mail för att logga in på sina offentliga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="acf7b-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="acf7b-115">Leverantörer och partner använda sina LinkedIn-, Salesforce- eller Google Mail-konton för att logga in på partnerextranätet.</span><span class="sxs-lookup"><span data-stu-id="acf7b-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="acf7b-116">Här är Contosos DMZ som innehåller en offentlig webbplats, ett partnerextranät och en uppsättning AD FS-servrar (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="acf7b-116">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="acf7b-117">DMZ är ansluten till Internet som innehåller tjänster för kunder, partner och Internet.</span><span class="sxs-lookup"><span data-stu-id="acf7b-117">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso-support för federerad autentisering för kunder och partner](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="acf7b-119">AD FS-servrar i DMZ underlättar autentiseringen av kundens identitetsuppgifter via identitetsleverantörerna för åtkomst till den offentliga webbplatsen och partneruppgifter för åtkomst till partnerextranätet.</span><span class="sxs-lookup"><span data-stu-id="acf7b-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="acf7b-120">Contoso bestämde sig för att behålla denna infrastruktur och dedikera den till kund- och partnerautentiseringar.</span><span class="sxs-lookup"><span data-stu-id="acf7b-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="acf7b-121">Contosos identitetsarkitekter undersöker konverteringen av den här infrastrukturen till Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations)- och [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)-lösningar.</span><span class="sxs-lookup"><span data-stu-id="acf7b-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="acf7b-122">Hybrididentitet med synkronisering av lösenordshash för molnbaserad autentisering</span><span class="sxs-lookup"><span data-stu-id="acf7b-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="acf7b-123">Contoso ville använda sin lokala AD DS-skog för autentisering för Microsoft 365-molnresurser.</span><span class="sxs-lookup"><span data-stu-id="acf7b-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="acf7b-124">De bestämde sig för synkronisering av lösenordshash (PHS).</span><span class="sxs-lookup"><span data-stu-id="acf7b-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="acf7b-125">PHS synkroniserar den lokala AD DS-skogen med Azure AD-innehavaren av sitt Microsoft 365 för företags prenumeration, kopierar användare och grupp konton och en hash-version av användar konto lösen ord.</span><span class="sxs-lookup"><span data-stu-id="acf7b-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="acf7b-126">För att utföra en pågående katalogsynkronisering har Contoso distribuerat Azure AD Connect-verktyget på en server i sitt datacenter i Paris.</span><span class="sxs-lookup"><span data-stu-id="acf7b-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="acf7b-127">Här är den server som kör Azure AD Connect-omröstningen för Contoso AD DS-skogen när det gäller ändringar och sedan synkroniserar ändringarna med Azure AD-klienten.</span><span class="sxs-lookup"><span data-stu-id="acf7b-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contosos infrastruktur för PHS-katalogsynkronisering](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="acf7b-129">Principer för villkorlig åtkomst för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="acf7b-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="acf7b-130">Contoso skapade en uppsättning [principer för villkorlig åtkomst](identity-access-policies.md) för Azure AD och Intune för tre skyddsnivåer:</span><span class="sxs-lookup"><span data-stu-id="acf7b-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="acf7b-131">**Grundskydd** gäller för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="acf7b-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="acf7b-132">**Känsliga** skydd gäller cheferna och ledningen</span><span class="sxs-lookup"><span data-stu-id="acf7b-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="acf7b-133">**Strikt reglerat** skydd med gäller för vissa användare på ekonomi-, juridik- och forskningsavdelningarna som har tillgång till data som är mycket strikta</span><span class="sxs-lookup"><span data-stu-id="acf7b-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="acf7b-134">Här är Contosos resulterande uppsättning principer för villkorsstyrd åtkomst av identitets- och enhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="acf7b-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contosos principer för villkorlig åtkomst för identitet och enheterer](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="acf7b-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="acf7b-136">Next step</span></span>

<span data-ttu-id="acf7b-137">[Ta reda på mer](contoso-win10.md) om hur Contoso använder sin Microsoft Endpoint Configuration Manager-infrastruktur för att distribuera och hålla Windows 10 Enterprise uppdaterat i organisationen.</span><span class="sxs-lookup"><span data-stu-id="acf7b-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="acf7b-138">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="acf7b-138">See also</span></span>

[<span data-ttu-id="acf7b-139">Identitets översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="acf7b-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="acf7b-140">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="acf7b-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="acf7b-141">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="acf7b-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
