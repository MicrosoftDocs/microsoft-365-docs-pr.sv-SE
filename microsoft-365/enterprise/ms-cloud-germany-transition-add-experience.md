---
title: Aktiviteter efter migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Efter migreringens aktiviteter efter flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 i den nya tyska datacenterområdet.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930421"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6c41d-103">Aktiviteter efter migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6c41d-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="6c41d-104">I följande avsnitt finns aktiviteter efter migrering för flera tjänster efter flytt från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.</span><span class="sxs-lookup"><span data-stu-id="6c41d-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="6c41d-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="6c41d-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="6c41d-106">Federerad Azure AD-autentisering med AD FS</span><span class="sxs-lookup"><span data-stu-id="6c41d-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="6c41d-107">**Gäller för:** Alla kunder som använder federerad autentisering med AD FS</span><span class="sxs-lookup"><span data-stu-id="6c41d-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="6c41d-108">Steg</span><span class="sxs-lookup"><span data-stu-id="6c41d-108">Step(s)</span></span> | <span data-ttu-id="6c41d-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c41d-109">Description</span></span> | <span data-ttu-id="6c41d-110">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6c41d-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6c41d-111">Ta bort förtroenden från en part i Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="6c41d-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="6c41d-112">Efter att användningen av Azure AD har slutförts använder organisationen alla tjänster Office 365 och är inte längre ansluten till Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="6c41d-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="6c41d-113">I det här läget behöver kunden ta bort det beroende tredjepartsförtroendet till Microsoft Cloud Deutschland-slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="6c41d-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="6c41d-114">Detta kan endast göras om ingen av kundens program pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som en identitetsprovider (IdP).</span><span class="sxs-lookup"><span data-stu-id="6c41d-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="6c41d-115">Organisationer med federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="6c41d-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="6c41d-116">Gruppgodkännanden</span><span class="sxs-lookup"><span data-stu-id="6c41d-116">Group approvals</span></span>
<span data-ttu-id="6c41d-117">**Gäller för:** Slutanvändare vars Azure AD-gruppgodkännandebegäranden inte godkänts under de senaste 30 dagarna före migreringen</span><span class="sxs-lookup"><span data-stu-id="6c41d-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="6c41d-118">Steg</span><span class="sxs-lookup"><span data-stu-id="6c41d-118">Step(s)</span></span> | <span data-ttu-id="6c41d-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c41d-119">Description</span></span> | <span data-ttu-id="6c41d-120">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6c41d-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6c41d-121">Förfrågningar om att gå med i en Azure AD-grupp de senaste 30 dagarna innan migreringen måste begäras igen om den ursprungliga begäran inte godkänts.</span><span class="sxs-lookup"><span data-stu-id="6c41d-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="6c41d-122">Slutanvändarkunder måste använda åtkomstpanelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa begäranden inte godkänts under de senaste 30 dagarna före migreringen.</span><span class="sxs-lookup"><span data-stu-id="6c41d-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="6c41d-123">Som slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="6c41d-123">As an end-user:</span></span> <ol><li><span data-ttu-id="6c41d-124">Gå till [åtkomstpanelen](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="6c41d-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="6c41d-125">Hitta en Azure AD-grupp för vilken godkännande av medlemskap väntar under 30 dagar före migreringen.</span><span class="sxs-lookup"><span data-stu-id="6c41d-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="6c41d-126">Begär att få gå med i Azure AD-gruppen igen.</span><span class="sxs-lookup"><span data-stu-id="6c41d-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="6c41d-127">Förfrågningar om att gå med i en grupp som är aktiv mindre än 30 dagar innan migreringen kan inte godkännas, såvida de inte begärs igen efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="6c41d-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="6c41d-128">Anpassade DNS-uppdateringar</span><span class="sxs-lookup"><span data-stu-id="6c41d-128">Custom DNS updates</span></span>
<span data-ttu-id="6c41d-129">**Gäller för:**  Alla kunder som hanterar sina egna DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="6c41d-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="6c41d-130">Steg</span><span class="sxs-lookup"><span data-stu-id="6c41d-130">Step(s)</span></span> | <span data-ttu-id="6c41d-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c41d-131">Description</span></span> | <span data-ttu-id="6c41d-132">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6c41d-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="6c41d-133">Uppdatera lokala DNS-tjänster för Office 365-tjänstens slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="6c41d-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="6c41d-134">Kund hanterade DNS-poster som pekar på Microsoft Cloud Deutschland måste uppdateras så att de pekar Office 365 slutpunkter för globala tjänster.</span><span class="sxs-lookup"><span data-stu-id="6c41d-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="6c41d-135">Se Domäner [i administrationscentret Microsoft 365 och](https://admin.microsoft.com/Adminportal/Home#/Domains) tillämpa ändringarna i DNS-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="6c41d-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="6c41d-136">Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="6c41d-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="6c41d-137">Tredjepartstjänster</span><span class="sxs-lookup"><span data-stu-id="6c41d-137">Third-party services</span></span>
<span data-ttu-id="6c41d-138">**Gäller för:** Kunder som använder tredjepartstjänster för Office 365 slutpunkter för tjänster</span><span class="sxs-lookup"><span data-stu-id="6c41d-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="6c41d-139">Steg</span><span class="sxs-lookup"><span data-stu-id="6c41d-139">Step(s)</span></span> | <span data-ttu-id="6c41d-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c41d-140">Description</span></span> | <span data-ttu-id="6c41d-141">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6c41d-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6c41d-142">Uppdatera partner och tredjepartstjänster för att Office 365 slutpunkter för tjänster.</span><span class="sxs-lookup"><span data-stu-id="6c41d-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="6c41d-143">Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar Office 365-tjänstslutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="6c41d-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="6c41d-144">Exempel: Registrera igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="6c41d-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="6c41d-145">Peka alla anpassade program som utnyttjar Graph API från `graph.microsoft.de` till `graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="6c41d-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="6c41d-146">Andra API:er med ändrade slutpunkter måste också uppdateras, om de används.</span><span class="sxs-lookup"><span data-stu-id="6c41d-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="6c41d-147">Ändra alla företagsprogram som inte är från första part så att de omdirigeras till de globala slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="6c41d-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="6c41d-148">Obligatorisk åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6c41d-148">Required action.</span></span> <span data-ttu-id="6c41d-149">Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="6c41d-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||