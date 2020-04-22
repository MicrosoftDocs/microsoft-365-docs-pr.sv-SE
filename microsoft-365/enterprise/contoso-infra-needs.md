---
title: Contosos IT-infrastruktur och affärsbehov
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå den grundläggande strukturen i Contosos lokala IT-infrastruktur och hur företagets behov uppfylldes av Microsoft 365 Enterprise.
ms.openlocfilehash: 38d2b8df611cb06e19abba074f49e00d95496c30
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625296"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="3a321-103">Contosos IT-infrastruktur och affärsbehov</span><span class="sxs-lookup"><span data-stu-id="3a321-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="3a321-104">Contoso har övergått från en lokal, centraliserad IT-infrastruktur till molnbaserade personliga arbetsbelastningar och program.</span><span class="sxs-lookup"><span data-stu-id="3a321-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="3a321-105">Contosos befintliga IT-infrastruktur</span><span class="sxs-lookup"><span data-stu-id="3a321-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="3a321-106">Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="3a321-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="3a321-107">Bild 1 visar ett huvudkontor med datacenter, en DMZ och Internet.</span><span class="sxs-lookup"><span data-stu-id="3a321-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contosos befintliga IT-infrastruktur](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="3a321-109">**Bild 1: Contosos befintliga IT-infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="3a321-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="3a321-110">Det lokala programdatacentret är värd för:</span><span class="sxs-lookup"><span data-stu-id="3a321-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="3a321-111">Egna affärsprogram som använder SQL Server- och andra Linux-databaser.</span><span class="sxs-lookup"><span data-stu-id="3a321-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="3a321-112">En uppsättning äldre SharePoint-servrar.</span><span class="sxs-lookup"><span data-stu-id="3a321-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="3a321-113">Servar på organisations- och teamnivå för fillagring.</span><span class="sxs-lookup"><span data-stu-id="3a321-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="3a321-114">Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program.</span><span class="sxs-lookup"><span data-stu-id="3a321-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="3a321-115">Dessa servrar styrs av regionala IT-avdelningar.</span><span class="sxs-lookup"><span data-stu-id="3a321-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="3a321-116">Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.</span><span class="sxs-lookup"><span data-stu-id="3a321-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="3a321-117">I Contosos huvudkvarters DMZ kan du använda olika uppsättningar av servrar:</span><span class="sxs-lookup"><span data-stu-id="3a321-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="3a321-118">Värd för den offentliga Contoso-webbplatsen, där kunderna kan beställa produkter, delar, materiel och tjänster.</span><span class="sxs-lookup"><span data-stu-id="3a321-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="3a321-119">Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.</span><span class="sxs-lookup"><span data-stu-id="3a321-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="3a321-120">VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="3a321-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="3a321-121">Contosos affärsbehov</span><span class="sxs-lookup"><span data-stu-id="3a321-121">Contoso's business needs</span></span>

<span data-ttu-id="3a321-122">Organisationens affärsbehov delas in i fem huvudkategorier.</span><span class="sxs-lookup"><span data-stu-id="3a321-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="3a321-123">Produktivitet:</span><span class="sxs-lookup"><span data-stu-id="3a321-123">Productivity:</span></span>

- <span data-ttu-id="3a321-124">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="3a321-124">Make collaboration easier</span></span>

  <span data-ttu-id="3a321-125">Ersätt e-post och dela dokument med hjälp av en onlinemodell som möjliggör ändringar i realtid i dokument, enklare onlinemöten och hämtade konversationstrådar.</span><span class="sxs-lookup"><span data-stu-id="3a321-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="3a321-126">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="3a321-127">Med många medarbetare som arbetar från hemmet eller ute på fältet ersätter du VPN-lösningens flaskhals med omfattande åtkomst till Contoso-data och -resurser i molnet.</span><span class="sxs-lookup"><span data-stu-id="3a321-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="3a321-128">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="3a321-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="3a321-129">Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.</span><span class="sxs-lookup"><span data-stu-id="3a321-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="3a321-130">Säkerhet:</span><span class="sxs-lookup"><span data-stu-id="3a321-130">Security:</span></span>

- <span data-ttu-id="3a321-131">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="3a321-131">Identity and access management</span></span>

  <span data-ttu-id="3a321-132">Använd multifaktorautentisering och andra typer av autentisering och skydda användar- och administratörskontouppgifter.</span><span class="sxs-lookup"><span data-stu-id="3a321-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="3a321-133">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="3a321-133">Threat protection</span></span>

  <span data-ttu-id="3a321-134">Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="3a321-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="3a321-135">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="3a321-135">Information protection</span></span>

  <span data-ttu-id="3a321-136">Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3a321-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="3a321-137">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="3a321-137">Security management</span></span>

  <span data-ttu-id="3a321-138">Övervaka säkerheten så att du kan upptäcka och reagera på hot i realtid.</span><span class="sxs-lookup"><span data-stu-id="3a321-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="3a321-139">Fjärr- och mobilåtkomst för affärspartner:</span><span class="sxs-lookup"><span data-stu-id="3a321-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="3a321-140">Högre säkerhet för arbetare och distansarbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="3a321-141">Upprätta BYOD (Bring Your Own Device) och företagsägd enhetshantering för att säkerställa skyddad åtkomst, korrekta programbeteenden och skydd av företagsdata.</span><span class="sxs-lookup"><span data-stu-id="3a321-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="3a321-142">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="3a321-143">Minska kostnader för underhåll och support och förbättra prestanda för lösningen för fjärråtkomst genom att flytta vanligt förekommande resurser till molnet.</span><span class="sxs-lookup"><span data-stu-id="3a321-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="3a321-144">Ge bättre anslutningsbarhet och lägre kostnad för B2B-transaktioner (företag till företag)</span><span class="sxs-lookup"><span data-stu-id="3a321-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="3a321-145">Ersätt föråldrade och dyra partnerextranät med en molnbaserad lösning som använder federerad autentisering.</span><span class="sxs-lookup"><span data-stu-id="3a321-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="3a321-146">Efterlevnad:</span><span class="sxs-lookup"><span data-stu-id="3a321-146">Compliance:</span></span>

- <span data-ttu-id="3a321-147">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="3a321-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="3a321-148">Bli och fortsätt att vara kompatibla med branscher och regionala föreskrifter för datalagring, kryptering, datasekretess och föreskrifter för personliga data, t.ex. GDPR (allmän dataskyddsförordning) för EU.</span><span class="sxs-lookup"><span data-stu-id="3a321-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="3a321-149">Hantering:</span><span class="sxs-lookup"><span data-stu-id="3a321-149">Management:</span></span>

- <span data-ttu-id="3a321-150">Minska IT-omkostnaderna för hantering av programvara som körs på klientdatorer och -enheter</span><span class="sxs-lookup"><span data-stu-id="3a321-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="3a321-151">Automatisera installationen av uppdateringar av Windows-operativsystemet och Microsoft Office ProPlus i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="3a321-151">Automate the installation of updates to the Windows operating system and Microsoft Office ProPlus across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="3a321-152">Koppla Contosos affärsbehov till Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3a321-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3a321-153">Contosos IT-avdelning fastställde följande affärsbehov för Microsoft 365 E5 före distributionen:</span><span class="sxs-lookup"><span data-stu-id="3a321-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="3a321-154">**Kategori**</span><span class="sxs-lookup"><span data-stu-id="3a321-154">**Category**</span></span> | <span data-ttu-id="3a321-155">**Affärsbehov**</span><span class="sxs-lookup"><span data-stu-id="3a321-155">**Business need**</span></span> | <span data-ttu-id="3a321-156">**Microsoft 365 Enterprise-produkter eller -funktioner**</span><span class="sxs-lookup"><span data-stu-id="3a321-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="3a321-157">Produktivitet</span><span class="sxs-lookup"><span data-stu-id="3a321-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="3a321-158">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="3a321-158">Make collaboration easier</span></span> | <span data-ttu-id="3a321-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="3a321-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="3a321-160">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="3a321-161">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="3a321-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="3a321-162">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="3a321-162">Increase creativity and innovation</span></span> | <span data-ttu-id="3a321-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3a321-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="3a321-164">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="3a321-164">Security</span></span> |  |  |
|  | <span data-ttu-id="3a321-165">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="3a321-165">Identity & access management</span></span> | <span data-ttu-id="3a321-166">Dedikerade globala administratörskonton med Azure Multi-Factor Authentication (MFA) och Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="3a321-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="3a321-167">MFA för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="3a321-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="3a321-168">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="3a321-168">Conditional Access</span></span> <BR> <span data-ttu-id="3a321-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="3a321-169">Windows Hello</span></span> <BR> <span data-ttu-id="3a321-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="3a321-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="3a321-171">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="3a321-171">Threat protection</span></span> | <span data-ttu-id="3a321-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="3a321-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="3a321-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="3a321-173">Windows Defender</span></span> <BR> <span data-ttu-id="3a321-174">Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="3a321-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="3a321-175">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="3a321-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="3a321-176">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="3a321-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="3a321-177">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="3a321-177">Information protection</span></span> | <span data-ttu-id="3a321-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="3a321-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="3a321-179">Skydd mot dataförlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="3a321-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="3a321-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="3a321-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="3a321-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3a321-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="3a321-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a321-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="3a321-183">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="3a321-183">Security management</span></span> | <span data-ttu-id="3a321-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="3a321-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="3a321-185">Windows Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="3a321-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="3a321-186">Fjärr- och mobilåtkomst för affärspartner</span><span class="sxs-lookup"><span data-stu-id="3a321-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="3a321-187">Högre säkerhet för arbetare och distansarbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="3a321-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a321-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="3a321-189">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="3a321-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="3a321-190">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="3a321-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="3a321-191">Ge bättre anslutningsbarhet och lägre kostnad för B2B-transaktioner</span><span class="sxs-lookup"><span data-stu-id="3a321-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="3a321-192">Federerad autentisering och molnbaserade resurser</span><span class="sxs-lookup"><span data-stu-id="3a321-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="3a321-193">Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="3a321-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="3a321-194">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="3a321-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="3a321-195">GDPR-funktioner i Office 365</span><span class="sxs-lookup"><span data-stu-id="3a321-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="3a321-196">Hantering</span><span class="sxs-lookup"><span data-stu-id="3a321-196">Management</span></span> |  |  |
|  | <span data-ttu-id="3a321-197">Minska IT-omkostnaderna för installation av klientuppdateringar</span><span class="sxs-lookup"><span data-stu-id="3a321-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="3a321-198">Distributionsringar</span><span class="sxs-lookup"><span data-stu-id="3a321-198">Deployment rings</span></span> <BR> <span data-ttu-id="3a321-199">Windows 10 Enterprise-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="3a321-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="3a321-200">Microsoft 365-applikationer för företag uppdateringar</span><span class="sxs-lookup"><span data-stu-id="3a321-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="3a321-201">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3a321-201">Next step</span></span>

<span data-ttu-id="3a321-202">[Läs](contoso-networking.md) om Contoso Corporations lokala nätverk och hur det optimerades för åtkomst och svarstider för molnbaserade resurser i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3a321-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a321-203">Se även</span><span class="sxs-lookup"><span data-stu-id="3a321-203">See also</span></span>

[<span data-ttu-id="3a321-204">Distributionsguide</span><span class="sxs-lookup"><span data-stu-id="3a321-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3a321-205">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="3a321-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
