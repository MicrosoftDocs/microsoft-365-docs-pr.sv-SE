---
title: Contosos IT-infrastruktur och affärsbehov
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå den grundläggande strukturen i Contosos lokala IT-infrastruktur och hur företagets affärsbehov uppfylls av Microsoft 365 för företag.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558412"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="75295-103">Contosos IT-infrastruktur och affärsbehov</span><span class="sxs-lookup"><span data-stu-id="75295-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="75295-104">Contoso går över från en lokal, centraliserad IT-infrastruktur till en molnomfattande installation med molnbaserade arbetsbelastningar och program för personlig produktivitet.</span><span class="sxs-lookup"><span data-stu-id="75295-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="75295-105">Befintlig IT-infrastruktur i Contoso</span><span class="sxs-lookup"><span data-stu-id="75295-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="75295-106">Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="75295-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="75295-107">Här är huvudkontoret med programdatacenter, en DMZ och internet.</span><span class="sxs-lookup"><span data-stu-id="75295-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Befintlig IT-infrastruktur i Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="75295-109">Det lokala programdatacentret är värd för:</span><span class="sxs-lookup"><span data-stu-id="75295-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="75295-110">Anpassade affärsprogram som använder SQL Server och andra Linux-databaser.</span><span class="sxs-lookup"><span data-stu-id="75295-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="75295-111">En uppsättning äldre SharePoint-servrar.</span><span class="sxs-lookup"><span data-stu-id="75295-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="75295-112">Servar på organisations- och teamnivå för fillagring.</span><span class="sxs-lookup"><span data-stu-id="75295-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="75295-113">Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program.</span><span class="sxs-lookup"><span data-stu-id="75295-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="75295-114">Dessa servrar styrs av regionala IT-avdelningar.</span><span class="sxs-lookup"><span data-stu-id="75295-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="75295-115">Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.</span><span class="sxs-lookup"><span data-stu-id="75295-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="75295-116">I Contoso huvudkontor DMZ tillhandahåller olika uppsättningar av servrar:</span><span class="sxs-lookup"><span data-stu-id="75295-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="75295-117">Värd för den offentliga Contoso-webbplatsen, där kunderna kan beställa produkter, delar, varor och tjänster.</span><span class="sxs-lookup"><span data-stu-id="75295-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="75295-118">Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.</span><span class="sxs-lookup"><span data-stu-id="75295-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="75295-119">VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="75295-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="75295-120">Affärsbehov i Contoso</span><span class="sxs-lookup"><span data-stu-id="75295-120">Contoso business needs</span></span>

<span data-ttu-id="75295-121">Contosos affärsbehov indelar i fem huvudkategorier:</span><span class="sxs-lookup"><span data-stu-id="75295-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="75295-122">**Produktivitet**</span><span class="sxs-lookup"><span data-stu-id="75295-122">**Productivity**</span></span>

- <span data-ttu-id="75295-123">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="75295-123">Make collaboration easier</span></span>

  <span data-ttu-id="75295-124">Ersätt e-post- och filresursbaserat samarbete med en onlinemodell som tillåter ändringar i realtid i dokument, enklare onlinemöten och tagna konversationstrådar.</span><span class="sxs-lookup"><span data-stu-id="75295-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="75295-125">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="75295-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="75295-126">När många anställda arbetar hemifrån eller i fältet ersätter du den flaskhalsade VPN-lösningen med direktåtkomst till Contosos data och resurser i molnet.</span><span class="sxs-lookup"><span data-stu-id="75295-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="75295-127">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="75295-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="75295-128">Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.</span><span class="sxs-lookup"><span data-stu-id="75295-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="75295-129">**Säkerhet**</span><span class="sxs-lookup"><span data-stu-id="75295-129">**Security**</span></span>

- <span data-ttu-id="75295-130">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="75295-130">Identity and access management</span></span>

  <span data-ttu-id="75295-131">Använda multifaktorer och andra typer av autentisering och skydda autentiseringsuppgifter för användar- och administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="75295-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="75295-132">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="75295-132">Threat protection</span></span>

  <span data-ttu-id="75295-133">Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="75295-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="75295-134">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="75295-134">Information protection</span></span>

  <span data-ttu-id="75295-135">Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.</span><span class="sxs-lookup"><span data-stu-id="75295-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="75295-136">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="75295-136">Security management</span></span>

  <span data-ttu-id="75295-137">Övervaka säkerheten och identifiera och reagera på hot i realtid.</span><span class="sxs-lookup"><span data-stu-id="75295-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="75295-138">**Fjärr- och mobilåtkomst för affärspartner**</span><span class="sxs-lookup"><span data-stu-id="75295-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="75295-139">Förbättra säkerheten för fjärranslutna och mobila medarbetare</span><span class="sxs-lookup"><span data-stu-id="75295-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="75295-140">Implementera få din egen enhet (BYOD) och företagsägd enhetshantering för att säkerställa säker åtkomst, korrekt programbeteende och företagsdataskydd.</span><span class="sxs-lookup"><span data-stu-id="75295-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="75295-141">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="75295-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="75295-142">Minska kostnader för underhåll och support och förbättra prestandan för lösningen för fjärråtkomst genom att flytta resurser som ofta används till molnet.</span><span class="sxs-lookup"><span data-stu-id="75295-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="75295-143">Bättre anslutning och lägre overhead för B2B-transaktioner (företag till företag)</span><span class="sxs-lookup"><span data-stu-id="75295-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="75295-144">Ersätt ett föråldrings och dyr partnerextranät med en molnbaserad lösning som använder federerad autentisering.</span><span class="sxs-lookup"><span data-stu-id="75295-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="75295-145">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="75295-145">**Compliance**</span></span>

- <span data-ttu-id="75295-146">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="75295-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="75295-147">Säkerställa efterlevnad av bransch- och regionala bestämmelser för datalagring, kryptering, datasekretess och bestämmelser om personliga data, t.ex. dataskyddsförordningen (GDPR) för Europeiska unionen.</span><span class="sxs-lookup"><span data-stu-id="75295-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="75295-148">**Hantering**</span><span class="sxs-lookup"><span data-stu-id="75295-148">**Management**</span></span>

- <span data-ttu-id="75295-149">Lägre IT-kostnader vid hantering av programvara som körs på klientdatorer och -enheter</span><span class="sxs-lookup"><span data-stu-id="75295-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="75295-150">Automatisera installationen av uppdateringar Windows operativsystem och Microsoft 365-appar för företag i organisationen.</span><span class="sxs-lookup"><span data-stu-id="75295-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="75295-151">Mappa Contosos affärsbehov till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="75295-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="75295-152">Contosos IT-avdelning har fastställt följande mappning av affärsbehoven Microsoft 365 E5 funktioner före distributionen:</span><span class="sxs-lookup"><span data-stu-id="75295-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="75295-153">Kategori</span><span class="sxs-lookup"><span data-stu-id="75295-153">Category</span></span> | <span data-ttu-id="75295-154">Affärsknr</span><span class="sxs-lookup"><span data-stu-id="75295-154">Business need</span></span> | <span data-ttu-id="75295-155">Microsoft 365 för företagsprodukter eller -funktioner</span><span class="sxs-lookup"><span data-stu-id="75295-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="75295-156">Produktivitet</span><span class="sxs-lookup"><span data-stu-id="75295-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="75295-157">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="75295-157">Make collaboration easier</span></span> | <span data-ttu-id="75295-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="75295-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="75295-159">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="75295-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="75295-160">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="75295-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="75295-161">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="75295-161">Increase creativity and innovation</span></span> | <span data-ttu-id="75295-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="75295-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="75295-163">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="75295-163">Security</span></span> |  |  |
|  | <span data-ttu-id="75295-164">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="75295-164">Identity & access management</span></span> | <span data-ttu-id="75295-165">Dedikerade globala administratörskonton med Azure AD Multi-Factor Authentication (MFA) och Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="75295-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="75295-166">MFA för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="75295-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="75295-167">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="75295-167">Conditional Access</span></span> <BR> <span data-ttu-id="75295-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="75295-168">Windows Hello</span></span> <BR> <span data-ttu-id="75295-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="75295-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="75295-170">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="75295-170">Threat protection</span></span> | <span data-ttu-id="75295-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="75295-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="75295-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="75295-172">Windows Defender</span></span> <BR> <span data-ttu-id="75295-173">Defender förr Office 365</span><span class="sxs-lookup"><span data-stu-id="75295-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="75295-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="75295-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="75295-175">Microsoft 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="75295-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="75295-176">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="75295-176">Information protection</span></span> | <span data-ttu-id="75295-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="75295-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="75295-178">Skydd mot dataförlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="75295-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="75295-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="75295-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="75295-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75295-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="75295-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="75295-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="75295-182">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="75295-182">Security management</span></span> | <span data-ttu-id="75295-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="75295-183">Azure Defender</span></span>  <BR> <span data-ttu-id="75295-184">Windows Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="75295-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="75295-185">Fjärr- och mobilåtkomst för affärspartner</span><span class="sxs-lookup"><span data-stu-id="75295-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="75295-186">Högre säkerhet för arbetare och distansarbetare</span><span class="sxs-lookup"><span data-stu-id="75295-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="75295-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="75295-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="75295-188">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="75295-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="75295-189">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="75295-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="75295-190">Förbättra anslutningen och lägre overhead för B2B-transaktioner</span><span class="sxs-lookup"><span data-stu-id="75295-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="75295-191">Federerad autentisering och molnbaserade resurser</span><span class="sxs-lookup"><span data-stu-id="75295-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="75295-192">Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="75295-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="75295-193">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="75295-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="75295-194">GDPR-funktioner i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75295-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="75295-195">Hantering</span><span class="sxs-lookup"><span data-stu-id="75295-195">Management</span></span> |  |  |
|  | <span data-ttu-id="75295-196">Lägre IT-kostnader vid installation av klientuppdateringar</span><span class="sxs-lookup"><span data-stu-id="75295-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="75295-197">Windows 10 Enterprise-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="75295-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="75295-198">Microsoft 365-applikationer för företag uppdateringar</span><span class="sxs-lookup"><span data-stu-id="75295-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="75295-199">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="75295-199">Next step</span></span>

<span data-ttu-id="75295-200">Läs mer om det lokala Contoso [Corporation-nätverket](contoso-networking.md) och hur det optimerades för åtkomst och svarstid till Microsoft 365 molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="75295-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="75295-201">Se även</span><span class="sxs-lookup"><span data-stu-id="75295-201">See also</span></span>

[<span data-ttu-id="75295-202">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="75295-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="75295-203">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="75295-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
