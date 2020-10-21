---
title: Skype IT-infrastruktur och företags behov
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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå den grundläggande strukturen i den lokala IT-infrastrukturen för Contoso och hur företagets företags behov uppfylls av Microsoft 365 för företag.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637181"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="a0762-103">Skype IT-infrastruktur och företags behov</span><span class="sxs-lookup"><span data-stu-id="a0762-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="a0762-104">Contoso övergår från en lokal, centraliserad IT-infrastruktur till en molnbaserade konfiguration som innehåller molnbaserade privat arbets belastning och applikationer.</span><span class="sxs-lookup"><span data-stu-id="a0762-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="a0762-105">Befintlig infrastruktur för Contoso-IT</span><span class="sxs-lookup"><span data-stu-id="a0762-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="a0762-106">Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="a0762-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="a0762-107">Bild 1 visar huvud kontoret med program Data Center, en DMZ och Internet.</span><span class="sxs-lookup"><span data-stu-id="a0762-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Befintlig infrastruktur för Contoso-IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="a0762-109">**Bild 1: befintlig contoso IT-infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="a0762-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="a0762-110">Det lokala programdatacentret är värd för:</span><span class="sxs-lookup"><span data-stu-id="a0762-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="a0762-111">Anpassade affärs program som använder SQL Server och andra Linux-databaser.</span><span class="sxs-lookup"><span data-stu-id="a0762-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="a0762-112">En uppsättning äldre SharePoint-servrar.</span><span class="sxs-lookup"><span data-stu-id="a0762-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="a0762-113">Servar på organisations- och teamnivå för fillagring.</span><span class="sxs-lookup"><span data-stu-id="a0762-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="a0762-114">Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program.</span><span class="sxs-lookup"><span data-stu-id="a0762-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="a0762-115">Dessa servrar styrs av regionala IT-avdelningar.</span><span class="sxs-lookup"><span data-stu-id="a0762-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="a0762-116">Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.</span><span class="sxs-lookup"><span data-stu-id="a0762-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="a0762-117">I DMZ med contoso Headquarters kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="a0762-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="a0762-118">Värd för den offentliga contoso-webbplatsen, där kunder kan beställa produkter, delar, tillbehör och tjänster.</span><span class="sxs-lookup"><span data-stu-id="a0762-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="a0762-119">Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.</span><span class="sxs-lookup"><span data-stu-id="a0762-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="a0762-120">VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="a0762-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="a0762-121">Contoso företags behov</span><span class="sxs-lookup"><span data-stu-id="a0762-121">Contoso business needs</span></span>

<span data-ttu-id="a0762-122">Contoso företags behov tillhör fem kategorier:</span><span class="sxs-lookup"><span data-stu-id="a0762-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="a0762-123">**Produktivitet**</span><span class="sxs-lookup"><span data-stu-id="a0762-123">**Productivity**</span></span>

- <span data-ttu-id="a0762-124">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="a0762-124">Make collaboration easier</span></span>

  <span data-ttu-id="a0762-125">Byt ut samarbete via e-post och fildelning med en online-modell som möjliggör ändringar i real tid i dokument, enklare onlinemöten och fångade konversations trådar.</span><span class="sxs-lookup"><span data-stu-id="a0762-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="a0762-126">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="a0762-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="a0762-127">Med många anställda som arbetar hemifrån eller i fältet ersätter du den Flask halsbaserade VPN-lösningen med åtkomst till contoso-data och resurser i molnet.</span><span class="sxs-lookup"><span data-stu-id="a0762-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="a0762-128">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="a0762-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="a0762-129">Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.</span><span class="sxs-lookup"><span data-stu-id="a0762-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="a0762-130">**Säkerhet**</span><span class="sxs-lookup"><span data-stu-id="a0762-130">**Security**</span></span>

- <span data-ttu-id="a0762-131">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="a0762-131">Identity and access management</span></span>

  <span data-ttu-id="a0762-132">Tvinga högfaktaare och andra former av autentisering samt skydda användar-och administratörs konto uppgifter.</span><span class="sxs-lookup"><span data-stu-id="a0762-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="a0762-133">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="a0762-133">Threat protection</span></span>

  <span data-ttu-id="a0762-134">Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a0762-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="a0762-135">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="a0762-135">Information protection</span></span>

  <span data-ttu-id="a0762-136">Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.</span><span class="sxs-lookup"><span data-stu-id="a0762-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="a0762-137">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="a0762-137">Security management</span></span>

  <span data-ttu-id="a0762-138">Övervaka säkerhets Posture och upptäcka och svara på hot i real tid.</span><span class="sxs-lookup"><span data-stu-id="a0762-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="a0762-139">**Fjärr- och mobilåtkomst för affärspartner**</span><span class="sxs-lookup"><span data-stu-id="a0762-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="a0762-140">Förbättra säkerheten för fjärranslutna och mobila användare</span><span class="sxs-lookup"><span data-stu-id="a0762-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="a0762-141">Implementera skaffa din egen enhet (BYOD) och företagets enhets hantering för att säkerställa skyddad åtkomst, korrekta program beteenden och företagets data skydd.</span><span class="sxs-lookup"><span data-stu-id="a0762-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="a0762-142">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="a0762-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="a0762-143">Reducera underhålls-och support kostnader och förbättra prestandan för fjärråtkomst genom att flytta vanliga resurser till molnet.</span><span class="sxs-lookup"><span data-stu-id="a0762-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="a0762-144">Ge bättre anslutning och lägre omkostnader för B2B-transaktioner (Business-to-susiness)</span><span class="sxs-lookup"><span data-stu-id="a0762-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="a0762-145">Ersätt en ålders fördelning och dyra partner nät med en molnbaserad lösning som använder federerad användning.</span><span class="sxs-lookup"><span data-stu-id="a0762-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="a0762-146">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="a0762-146">**Compliance**</span></span>

- <span data-ttu-id="a0762-147">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="a0762-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="a0762-148">Säkerställa efterlevnad av bransch-och regionala regler för data lagring, kryptering, data integritet och personliga data regler, till exempel GDPR (General Data Protection reglemente) för Europa unionen.</span><span class="sxs-lookup"><span data-stu-id="a0762-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="a0762-149">**Hantering**</span><span class="sxs-lookup"><span data-stu-id="a0762-149">**Management**</span></span>

- <span data-ttu-id="a0762-150">Minska IT-kostnaderna för att hantera program vara som körs på klient datorer och enheter</span><span class="sxs-lookup"><span data-stu-id="a0762-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="a0762-151">Automatisera installationen av uppdateringar av Windows operativ system och Microsoft 365-appar för företag i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="a0762-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="a0762-152">Mappa contoso företags behov till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a0762-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="a0762-153">Contosos IT-avdelning har fastställt följande mappning av företags behov till Microsoft 365 E5-funktioner innan distribution:</span><span class="sxs-lookup"><span data-stu-id="a0762-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="a0762-154">Kategori</span><span class="sxs-lookup"><span data-stu-id="a0762-154">Category</span></span> | <span data-ttu-id="a0762-155">Affärsbehov</span><span class="sxs-lookup"><span data-stu-id="a0762-155">Business need</span></span> | <span data-ttu-id="a0762-156">Microsoft 365 för företags produkter eller funktioner</span><span class="sxs-lookup"><span data-stu-id="a0762-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="a0762-157">Produktivitet</span><span class="sxs-lookup"><span data-stu-id="a0762-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="a0762-158">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="a0762-158">Make collaboration easier</span></span> | <span data-ttu-id="a0762-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="a0762-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="a0762-160">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="a0762-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="a0762-161">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="a0762-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a0762-162">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="a0762-162">Increase creativity and innovation</span></span> | <span data-ttu-id="a0762-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a0762-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="a0762-164">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="a0762-164">Security</span></span> |  |  |
|  | <span data-ttu-id="a0762-165">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="a0762-165">Identity & access management</span></span> | <span data-ttu-id="a0762-166">Dedikerade globala administratörs konton med Azure Multi-Factority (MFA) och Azure Active Directory-privilegierad identitets hantering (PIM)</span><span class="sxs-lookup"><span data-stu-id="a0762-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="a0762-167">MFA för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="a0762-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="a0762-168">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="a0762-168">Conditional Access</span></span> <BR> <span data-ttu-id="a0762-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="a0762-169">Windows Hello</span></span> <BR> <span data-ttu-id="a0762-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="a0762-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="a0762-171">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="a0762-171">Threat protection</span></span> | <span data-ttu-id="a0762-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="a0762-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="a0762-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="a0762-173">Windows Defender</span></span> <BR> <span data-ttu-id="a0762-174">Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="a0762-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a0762-175">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="a0762-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a0762-176">Microsoft 365 hot undersökningar och svar</span><span class="sxs-lookup"><span data-stu-id="a0762-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="a0762-177">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="a0762-177">Information protection</span></span> | <span data-ttu-id="a0762-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="a0762-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="a0762-179">Skydd mot dataförlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="a0762-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="a0762-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="a0762-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="a0762-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a0762-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="a0762-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a0762-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a0762-183">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="a0762-183">Security management</span></span> | <span data-ttu-id="a0762-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="a0762-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="a0762-185">Windows Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="a0762-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="a0762-186">Fjärr- och mobilåtkomst för affärspartner</span><span class="sxs-lookup"><span data-stu-id="a0762-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="a0762-187">Högre säkerhet för arbetare och distansarbetare</span><span class="sxs-lookup"><span data-stu-id="a0762-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="a0762-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a0762-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a0762-189">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="a0762-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="a0762-190">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="a0762-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a0762-191">Förbättra anslutningen och lägre omkostnader för B2B-transaktioner</span><span class="sxs-lookup"><span data-stu-id="a0762-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="a0762-192">Federerad autentisering och molnbaserade resurser</span><span class="sxs-lookup"><span data-stu-id="a0762-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="a0762-193">Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="a0762-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="a0762-194">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="a0762-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="a0762-195">GDPR funktioner i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a0762-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="a0762-196">Hantering</span><span class="sxs-lookup"><span data-stu-id="a0762-196">Management</span></span> |  |  |
|  | <span data-ttu-id="a0762-197">Minska IT-omkostnader för installation av klient uppdateringar</span><span class="sxs-lookup"><span data-stu-id="a0762-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="a0762-198">Distributionsringar</span><span class="sxs-lookup"><span data-stu-id="a0762-198">Deployment rings</span></span> <BR> <span data-ttu-id="a0762-199">Windows 10 Enterprise-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="a0762-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="a0762-200">Microsoft 365-applikationer för företag uppdateringar</span><span class="sxs-lookup"><span data-stu-id="a0762-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="a0762-201">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a0762-201">Next step</span></span>

<span data-ttu-id="a0762-202">[Lär dig mer](contoso-networking.md) om det lokala nätverket Contoso Corporation och hur det optimerades för åtkomst och svars tider till Microsoft 365-molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="a0762-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0762-203">Se även</span><span class="sxs-lookup"><span data-stu-id="a0762-203">See also</span></span>

[<span data-ttu-id="a0762-204">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a0762-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a0762-205">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="a0762-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
