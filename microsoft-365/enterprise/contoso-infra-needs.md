---
title: Skype IT-infrastruktur och företags behov
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
description: Förstå den grundläggande strukturen i den lokala IT-infrastrukturen för Contoso och hur företagets företags behov uppfylls av Microsoft 365 för företag.
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754592"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="b5751-103">Skype IT-infrastruktur och företags behov</span><span class="sxs-lookup"><span data-stu-id="b5751-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="b5751-104">Contoso övergår från en lokal, centraliserad IT-infrastruktur till en molnbaserade konfiguration som innehåller molnbaserade privat arbets belastning och applikationer.</span><span class="sxs-lookup"><span data-stu-id="b5751-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="b5751-105">Befintlig infrastruktur för Contoso-IT</span><span class="sxs-lookup"><span data-stu-id="b5751-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="b5751-106">Contoso använder främst centraliserad IT-infrastruktur med datacenter i huvudkontoret i Paris.</span><span class="sxs-lookup"><span data-stu-id="b5751-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="b5751-107">Här är huvud kontoret för program Data Center, en DMZ och Internet.</span><span class="sxs-lookup"><span data-stu-id="b5751-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Befintlig infrastruktur för Contoso-IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="b5751-109">Det lokala programdatacentret är värd för:</span><span class="sxs-lookup"><span data-stu-id="b5751-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="b5751-110">Anpassade affärs program som använder SQL Server och andra Linux-databaser.</span><span class="sxs-lookup"><span data-stu-id="b5751-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="b5751-111">En uppsättning äldre SharePoint-servrar.</span><span class="sxs-lookup"><span data-stu-id="b5751-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="b5751-112">Servar på organisations- och teamnivå för fillagring.</span><span class="sxs-lookup"><span data-stu-id="b5751-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="b5751-113">Dessutom har varje regionalt navkontor stöd för en uppsättning servrar med en liknande uppsättning program.</span><span class="sxs-lookup"><span data-stu-id="b5751-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="b5751-114">Dessa servrar styrs av regionala IT-avdelningar.</span><span class="sxs-lookup"><span data-stu-id="b5751-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="b5751-115">Sökbarheten i alla program och data i sådana separata flerspråkiga datacenter fortsätter att vara en utmaning.</span><span class="sxs-lookup"><span data-stu-id="b5751-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="b5751-116">I DMZ med contoso Headquarters kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="b5751-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="b5751-117">Värd för den offentliga contoso-webbplatsen, där kunder kan beställa produkter, delar, tillbehör och tjänster.</span><span class="sxs-lookup"><span data-stu-id="b5751-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="b5751-118">Värd för Contoso-partners extranät för kommunikation och samarbete mellan partner.</span><span class="sxs-lookup"><span data-stu-id="b5751-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="b5751-119">VPN-baserad (virtuellt privat nätverk) fjärråtkomst till Contosos intranät och webbproxyn för medarbetare på Paris-huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="b5751-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="b5751-120">Contoso företags behov</span><span class="sxs-lookup"><span data-stu-id="b5751-120">Contoso business needs</span></span>

<span data-ttu-id="b5751-121">Contoso företags behov tillhör fem kategorier:</span><span class="sxs-lookup"><span data-stu-id="b5751-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="b5751-122">**Produktivitet**</span><span class="sxs-lookup"><span data-stu-id="b5751-122">**Productivity**</span></span>

- <span data-ttu-id="b5751-123">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="b5751-123">Make collaboration easier</span></span>

  <span data-ttu-id="b5751-124">Byt ut samarbete via e-post och fildelning med en online-modell som möjliggör ändringar i real tid i dokument, enklare onlinemöten och fångade konversations trådar.</span><span class="sxs-lookup"><span data-stu-id="b5751-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="b5751-125">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="b5751-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="b5751-126">Med många anställda som arbetar hemifrån eller i fältet ersätter du den Flask halsbaserade VPN-lösningen med åtkomst till contoso-data och resurser i molnet.</span><span class="sxs-lookup"><span data-stu-id="b5751-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="b5751-127">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="b5751-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="b5751-128">Dra nytta av de senaste utvecklingsmetoderna för visuell inlärning och idé,er t. ex. pennanteckningar och 3D-visualisering.</span><span class="sxs-lookup"><span data-stu-id="b5751-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="b5751-129">**Säkerhet**</span><span class="sxs-lookup"><span data-stu-id="b5751-129">**Security**</span></span>

- <span data-ttu-id="b5751-130">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="b5751-130">Identity and access management</span></span>

  <span data-ttu-id="b5751-131">Tvinga högfaktaare och andra former av autentisering samt skydda användar-och administratörs konto uppgifter.</span><span class="sxs-lookup"><span data-stu-id="b5751-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="b5751-132">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="b5751-132">Threat protection</span></span>

  <span data-ttu-id="b5751-133">Skydda mot externa säkerhetshot, inklusive e-post och operativsystem som är baserade på skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="b5751-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="b5751-134">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="b5751-134">Information protection</span></span>

  <span data-ttu-id="b5751-135">Lås åtkomst till och kryptera digitala till gångar med höga värden, t. ex. kunddata, specifikationer för utformningen och tillverkningen samt information om medarbetare.</span><span class="sxs-lookup"><span data-stu-id="b5751-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="b5751-136">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="b5751-136">Security management</span></span>

  <span data-ttu-id="b5751-137">Övervaka säkerhets Posture och upptäcka och svara på hot i real tid.</span><span class="sxs-lookup"><span data-stu-id="b5751-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="b5751-138">**Fjärr- och mobilåtkomst för affärspartner**</span><span class="sxs-lookup"><span data-stu-id="b5751-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="b5751-139">Förbättra säkerheten för fjärranslutna och mobila användare</span><span class="sxs-lookup"><span data-stu-id="b5751-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="b5751-140">Implementera skaffa din egen enhet (BYOD) och företagets enhets hantering för att säkerställa skyddad åtkomst, korrekta program beteenden och företagets data skydd.</span><span class="sxs-lookup"><span data-stu-id="b5751-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="b5751-141">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="b5751-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="b5751-142">Reducera underhålls-och support kostnader och förbättra prestandan för fjärråtkomst genom att flytta vanliga resurser till molnet.</span><span class="sxs-lookup"><span data-stu-id="b5751-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="b5751-143">Ge bättre anslutning och lägre omkostnader för B2B-transaktioner (Business-to-susiness)</span><span class="sxs-lookup"><span data-stu-id="b5751-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="b5751-144">Ersätt en ålders fördelning och dyra partner nät med en molnbaserad lösning som använder federerad användning.</span><span class="sxs-lookup"><span data-stu-id="b5751-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="b5751-145">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="b5751-145">**Compliance**</span></span>

- <span data-ttu-id="b5751-146">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="b5751-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="b5751-147">Säkerställa efterlevnad av bransch-och regionala regler för data lagring, kryptering, data integritet och personliga data regler, till exempel GDPR (General Data Protection reglemente) för Europa unionen.</span><span class="sxs-lookup"><span data-stu-id="b5751-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="b5751-148">**Hantering**</span><span class="sxs-lookup"><span data-stu-id="b5751-148">**Management**</span></span>

- <span data-ttu-id="b5751-149">Minska IT-kostnaderna för att hantera program vara som körs på klient datorer och enheter</span><span class="sxs-lookup"><span data-stu-id="b5751-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="b5751-150">Automatisera installationen av uppdateringar av Windows operativ system och Microsoft 365-appar för företag i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b5751-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="b5751-151">Mappa contoso företags behov till Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="b5751-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="b5751-152">Contosos IT-avdelning har fastställt följande mappning av företags behov till Microsoft 365 E5-funktioner innan distribution:</span><span class="sxs-lookup"><span data-stu-id="b5751-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="b5751-153">Kategori</span><span class="sxs-lookup"><span data-stu-id="b5751-153">Category</span></span> | <span data-ttu-id="b5751-154">Affärsbehov</span><span class="sxs-lookup"><span data-stu-id="b5751-154">Business need</span></span> | <span data-ttu-id="b5751-155">Microsoft 365 för företags produkter eller funktioner</span><span class="sxs-lookup"><span data-stu-id="b5751-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="b5751-156">Produktivitet</span><span class="sxs-lookup"><span data-stu-id="b5751-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="b5751-157">Förenkla samarbetet</span><span class="sxs-lookup"><span data-stu-id="b5751-157">Make collaboration easier</span></span> | <span data-ttu-id="b5751-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="b5751-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="b5751-159">Förbättra produktiviteten för distans- och mobila arbetare</span><span class="sxs-lookup"><span data-stu-id="b5751-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="b5751-160">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="b5751-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b5751-161">Öka kreativiteten och innovationen</span><span class="sxs-lookup"><span data-stu-id="b5751-161">Increase creativity and innovation</span></span> | <span data-ttu-id="b5751-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b5751-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="b5751-163">Säkerhet</span><span class="sxs-lookup"><span data-stu-id="b5751-163">Security</span></span> |  |  |
|  | <span data-ttu-id="b5751-164">Identitets- och åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="b5751-164">Identity & access management</span></span> | <span data-ttu-id="b5751-165">Dedikerade globala administratörs konton med Azure Multi-Factority (MFA) och Azure Active Directory-privilegierad identitets hantering (PIM)</span><span class="sxs-lookup"><span data-stu-id="b5751-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="b5751-166">MFA för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="b5751-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="b5751-167">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="b5751-167">Conditional Access</span></span> <BR> <span data-ttu-id="b5751-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b5751-168">Windows Hello</span></span> <BR> <span data-ttu-id="b5751-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="b5751-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="b5751-170">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="b5751-170">Threat protection</span></span> | <span data-ttu-id="b5751-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="b5751-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="b5751-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b5751-172">Windows Defender</span></span> <BR> <span data-ttu-id="b5751-173">Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b5751-173">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b5751-174">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="b5751-174">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b5751-175">Microsoft 365 hot undersökningar och svar</span><span class="sxs-lookup"><span data-stu-id="b5751-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="b5751-176">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="b5751-176">Information protection</span></span> | <span data-ttu-id="b5751-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b5751-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="b5751-178">Skydd mot dataförlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="b5751-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="b5751-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="b5751-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="b5751-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b5751-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="b5751-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b5751-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b5751-182">Säkerhetshantering</span><span class="sxs-lookup"><span data-stu-id="b5751-182">Security management</span></span> | <span data-ttu-id="b5751-183">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="b5751-183">Azure Security Center</span></span>  <BR> <span data-ttu-id="b5751-184">Windows Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="b5751-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="b5751-185">Fjärr- och mobilåtkomst för affärspartner</span><span class="sxs-lookup"><span data-stu-id="b5751-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="b5751-186">Högre säkerhet för arbetare och distansarbetare</span><span class="sxs-lookup"><span data-stu-id="b5751-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="b5751-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b5751-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b5751-188">Minska infrastrukturen för fjärråtkomst för medarbetare</span><span class="sxs-lookup"><span data-stu-id="b5751-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="b5751-189">Microsoft 365-arbetsbelastningar och molnbaserade data</span><span class="sxs-lookup"><span data-stu-id="b5751-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b5751-190">Förbättra anslutningen och lägre omkostnader för B2B-transaktioner</span><span class="sxs-lookup"><span data-stu-id="b5751-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="b5751-191">Federerad autentisering och molnbaserade resurser</span><span class="sxs-lookup"><span data-stu-id="b5751-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="b5751-192">Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="b5751-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="b5751-193">Följa regionala efterlevnadskrav</span><span class="sxs-lookup"><span data-stu-id="b5751-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="b5751-194">GDPR funktioner i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5751-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="b5751-195">Hantering</span><span class="sxs-lookup"><span data-stu-id="b5751-195">Management</span></span> |  |  |
|  | <span data-ttu-id="b5751-196">Minska IT-omkostnader för installation av klient uppdateringar</span><span class="sxs-lookup"><span data-stu-id="b5751-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="b5751-197">Windows 10 Enterprise-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="b5751-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="b5751-198">Microsoft 365-applikationer för företag uppdateringar</span><span class="sxs-lookup"><span data-stu-id="b5751-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="b5751-199">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b5751-199">Next step</span></span>

<span data-ttu-id="b5751-200">Lär dig mer om det [lokala nätverket](contoso-networking.md) Contoso Corporation och hur det optimerades för åtkomst och svars tider till Microsoft 365-molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="b5751-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5751-201">Se även</span><span class="sxs-lookup"><span data-stu-id="b5751-201">See also</span></span>

[<span data-ttu-id="b5751-202">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="b5751-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b5751-203">Testlabbguider</span><span class="sxs-lookup"><span data-stu-id="b5751-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
