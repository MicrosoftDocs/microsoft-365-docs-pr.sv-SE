---
title: Kontroller för administrativ åtkomst i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Den här artikeln innehåller en översikt över kontroller för administrativ åtkomst och data kategorisering i Microsoft 365.
ms.openlocfilehash: b5063f89e89b6cffffda53a5df3088a80f89c242
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694371"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="acb56-103">Kontroller för administrativ åtkomst i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="acb56-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="acb56-104">Microsoft har investerat i system och kontroller som automatiserar de flesta Microsoft 365-operationer samtidigt som det begränsar åtkomsten till kund innehållet via Microsoft.</span><span class="sxs-lookup"><span data-stu-id="acb56-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="acb56-105">Människor styr tjänsten och program varan fungerar med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="acb56-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="acb56-106">Detta gör att Microsoft kan hantera Microsoft 365 på skala och hantera riskerna med interna hot för kund innehållet.</span><span class="sxs-lookup"><span data-stu-id="acb56-106">This enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="acb56-107">Som standard har Microsoft-tekniker inga stå för administratörs behörighet och ingen ständig åtkomst till kund innehåll i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="acb56-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="acb56-108">En Microsoft-tekniker kan ha begränsad, granskad och skyddad till gång till kundens innehåll under en begränsad tid.</span><span class="sxs-lookup"><span data-stu-id="acb56-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="acb56-109">Access är bara när det behövs för tjänste åtgärder och endast när det godkänns av en medlem i Microsofts chefs hantering.</span><span class="sxs-lookup"><span data-stu-id="acb56-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="acb56-110">För att få kund säkra kunder får kunden åtkomst godkännande till innehållet på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="acb56-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="acb56-111">Microsoft tillhandahåller online tjänster med hjälp av flera former av moln leverans:</span><span class="sxs-lookup"><span data-stu-id="acb56-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="acb56-112">**Offentliga moln:** Inkluderar multi-Tenant-versioner av Microsoft 365, Azure och andra tjänster i Nord Amerika, Sydamerika, Europa, Asien, Australien, etc.</span><span class="sxs-lookup"><span data-stu-id="acb56-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="acb56-113">**Nationella moln:** Inkluderar alla suveräna och tredje parts drivna moln utanför USA (förutom dem som nämns ovan), till exempel Microsoft 365 i Kina (drivs av 21Vianet) och Microsoft 365 i Tyskland (drivs av Microsoft, men under en modell där en tysk data förvaltare, tyska telekom, styr och övervakar Microsofts åtkomst till kunddata och system som innehåller kunddata).</span><span class="sxs-lookup"><span data-stu-id="acb56-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="acb56-114">**Statliga moln:** Innehåller Microsoft 365 och Azure-tjänster som är tillgängliga för kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="acb56-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="acb56-115">I den här artikeln gäller följande för Microsoft 365-tjänster:</span><span class="sxs-lookup"><span data-stu-id="acb56-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="acb56-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="acb56-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="acb56-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="acb56-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="acb56-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="acb56-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="acb56-119">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="acb56-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="acb56-120">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="acb56-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="acb56-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="acb56-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="acb56-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="acb56-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="acb56-123">Microsoft 365 Access-kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="acb56-124">I syfte med åtkomst kontroll kategoriseras Microsoft 365-data som kunddata eller andra typer av data.</span><span class="sxs-lookup"><span data-stu-id="acb56-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="acb56-125">Kunddata</span><span class="sxs-lookup"><span data-stu-id="acb56-125">Customer data</span></span>

<span data-ttu-id="acb56-126">Kunddata är alla data tillhandahålls av eller på uppdrag av en kund vid användning av Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="acb56-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="acb56-127">Det här är kund innehållet som skapas eller laddas upp direkt av Microsoft 365-användare, inklusive:</span><span class="sxs-lookup"><span data-stu-id="acb56-127">This is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="acb56-128">E-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="acb56-128">Emails</span></span>
- <span data-ttu-id="acb56-129">SharePoint Online-innehåll</span><span class="sxs-lookup"><span data-stu-id="acb56-129">SharePoint Online content</span></span>
- <span data-ttu-id="acb56-130">Snabb meddelanden</span><span class="sxs-lookup"><span data-stu-id="acb56-130">Instant messages</span></span>
- <span data-ttu-id="acb56-131">Kalender objekt</span><span class="sxs-lookup"><span data-stu-id="acb56-131">Calendar items</span></span>
- <span data-ttu-id="acb56-132">Dokumentationen</span><span class="sxs-lookup"><span data-stu-id="acb56-132">Documents</span></span>
- <span data-ttu-id="acb56-133">Kontakter</span><span class="sxs-lookup"><span data-stu-id="acb56-133">Contacts</span></span>
- <span data-ttu-id="acb56-134">Specifik information för slutanvändare (EUII) (data som är unika för en användare eller som är länkad till en enskild användare, men som inte inkluderar kund innehåll)</span><span class="sxs-lookup"><span data-stu-id="acb56-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="acb56-135">Andra typer av data</span><span class="sxs-lookup"><span data-stu-id="acb56-135">Other types of data</span></span>

<span data-ttu-id="acb56-136">Andra typer av data är:</span><span class="sxs-lookup"><span data-stu-id="acb56-136">Other types of data include:</span></span>

- <span data-ttu-id="acb56-137">**Konto data:** Inkluderar administrativa uppgifter (information som tillhandahålls av administratörer när de loggar in eller köper tjänster) och betalnings uppgifter (information om betalnings instrument, till exempel kreditkorts uppgifter).</span><span class="sxs-lookup"><span data-stu-id="acb56-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="acb56-138">**Identifierbar information från organisationen:** Inkluderar data som används för att identifiera en klient organisation, användnings data och inte länkas till en enskild användare eller ingår i kund innehållet.</span><span class="sxs-lookup"><span data-stu-id="acb56-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="acb56-139">**Systemmetadata:** Innehåller tjänst loggar som innehåller konfigurations inställningar, system status, Microsoft IP-adresser och teknisk information om abonnemang och innehavare.</span><span class="sxs-lookup"><span data-stu-id="acb56-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="acb56-140">Microsoft har fastställt mekanismer för åtkomst kontroll för att säkerställa att ingen har godkänt åtkomst till kunddata eller åtkomst kontroll data.</span><span class="sxs-lookup"><span data-stu-id="acb56-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="acb56-141">Åtkomst kontroll data hanterar åtkomst till andra typer av data eller funktioner i miljön, inklusive åtkomst till kund innehåll eller EUII, Microsoft-lösenord, säkerhets certifikat och andra säkerhetsrelaterade data.</span><span class="sxs-lookup"><span data-stu-id="acb56-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="acb56-142">Åtkomst kontroll mekanismer skyddar också mot icke godkänd fysisk, logisk eller fjärråtkomst till Microsoft 365-produktions miljön.</span><span class="sxs-lookup"><span data-stu-id="acb56-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="acb56-143">Det finns tre kategorier av Access-kontroller som används av Microsoft för att använda Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="acb56-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="acb56-144">Isolerings kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-144">Isolation controls</span></span>
- <span data-ttu-id="acb56-145">Personal kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-145">Personnel controls</span></span>
- <span data-ttu-id="acb56-146">Teknik kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-146">Technology controls</span></span>

<span data-ttu-id="acb56-147">När de kombineras kan de här kontrollerna förhindra och upptäcka skadliga åtgärder i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="acb56-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="acb56-148">Utöver de isolerings-, personal-och teknik kontroller som används av Microsoft finns det en fjärde kategori med kontroller: de som implementeras av kunder.</span><span class="sxs-lookup"><span data-stu-id="acb56-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="acb56-149">Med Microsoft 365 kan du hantera data på samma sätt som data hanteras i lokala miljöer.</span><span class="sxs-lookup"><span data-stu-id="acb56-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="acb56-150">Personen som registrerar sig för Microsoft 365 blir automatiskt global administratör.</span><span class="sxs-lookup"><span data-stu-id="acb56-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="acb56-151">Den globala administratören har till gång till alla funktioner i hanterings portaler och kan:</span><span class="sxs-lookup"><span data-stu-id="acb56-151">The global admin has access to all features in management portals and can:</span></span>

- <span data-ttu-id="acb56-152">Skapa eller redigera användare</span><span class="sxs-lookup"><span data-stu-id="acb56-152">Create or edit users</span></span>
- <span data-ttu-id="acb56-153">Tilldela administratörs roller till andra</span><span class="sxs-lookup"><span data-stu-id="acb56-153">Assign admin roles to others</span></span>
- <span data-ttu-id="acb56-154">Återställa användar lösen ord</span><span class="sxs-lookup"><span data-stu-id="acb56-154">Reset user passwords</span></span>
- <span data-ttu-id="acb56-155">Hantera användar licenser</span><span class="sxs-lookup"><span data-stu-id="acb56-155">Manage user licenses</span></span>
- <span data-ttu-id="acb56-156">Hantera domäner</span><span class="sxs-lookup"><span data-stu-id="acb56-156">Manage domains</span></span>
- <span data-ttu-id="acb56-157">Godkänn begäranden för kund frågor</span><span class="sxs-lookup"><span data-stu-id="acb56-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="acb56-158">Vi rekommenderar att varje organisation konfigurerar minst två administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="acb56-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="acb56-159">För stora företags organisationer rekommenderar vi specialiserade administratörs konton med olika funktioner.</span><span class="sxs-lookup"><span data-stu-id="acb56-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="acb56-160">Information om hur du tilldelar administratörs roller och behörigheter finns i [tilldela administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) och [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="acb56-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="acb56-161">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="acb56-161">Related Links</span></span>

- [<span data-ttu-id="acb56-162">Isolerings kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-162">Isolation Controls</span></span>](microsoft-365-isolation-controls.md)
- [<span data-ttu-id="acb56-163">Personal kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-163">Personnel Controls</span></span>](microsoft-365-personnel-controls.md)
- [<span data-ttu-id="acb56-164">Teknik kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-164">Technology Controls</span></span>](microsoft-365-technology-controls.md)
- [<span data-ttu-id="acb56-165">Övervaka och granska Access-kontroller</span><span class="sxs-lookup"><span data-stu-id="acb56-165">Monitoring and Auditing Access Controls</span></span>](microsoft-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="acb56-166">Kontroller för Yammer Enterprise Access</span><span class="sxs-lookup"><span data-stu-id="acb56-166">Yammer Enterprise Access Controls</span></span>](microsoft-365-yammer-enterprise-access-controls.md)
