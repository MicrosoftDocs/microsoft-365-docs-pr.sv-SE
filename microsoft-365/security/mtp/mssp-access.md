---
title: Tillhandahålla åtkomst för hanterad säkerhetstjänstleverantör (MSSP)
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Säkerhetscenter för Microsoft 365
keywords: Komma igång med Microsoft 365 Säkerhetscenter, OATP, MDATP, MDO, MDE, enda fönsterruta av glas, konvergerad portal, säkerhetsportal, Defender-säkerhetsportalen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: db9279ba1bc5fe11f3a31884a05b4403f0cb67f3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906706"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="43e13-104">Tillhandahålla åtkomst för hanterad säkerhetstjänstleverantör (MSSP)</span><span class="sxs-lookup"><span data-stu-id="43e13-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="43e13-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="43e13-105">**Applies to:**</span></span>

- [<span data-ttu-id="43e13-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43e13-106">Microsoft 365 Defender</span></span>](./microsoft-threat-protection.md)
- [<span data-ttu-id="43e13-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="43e13-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="43e13-108">Om du vill implementera en lösning med flera klientorganisationens delegerade åtkomst gör du följande:</span><span class="sxs-lookup"><span data-stu-id="43e13-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="43e13-109">Aktivera [rollbaserad åtkomstkontroll i](/windows/security/threat-protection/microsoft-defender-atp/rbac) Defender för slutpunkt i Microsoft 365 säkerhetscenter och anslut med Azure Active Directory-grupper (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="43e13-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="43e13-110">Konfigurera [styrningsåtkomstpaket](/azure/active-directory/governance/identity-governance-overview) för åtkomstbegäran och etablering.</span><span class="sxs-lookup"><span data-stu-id="43e13-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="43e13-111">Hantera åtkomstförfrågningar och granskningar i [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="43e13-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="43e13-112">Aktivera rollbaserade åtkomstkontroller i Microsoft Defender för Slutpunkt i Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="43e13-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="43e13-113">**Skapa åtkomstgrupper för MSSP-resurser i Kund-AAD: Grupper**</span><span class="sxs-lookup"><span data-stu-id="43e13-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="43e13-114">De här grupperna länkas till de roller som du skapar i Defender för Slutpunkt i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="43e13-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="43e13-115">Det gör du genom att skapa tre grupper i kundens AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="43e13-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="43e13-116">Med den här metoden skapar vi följande grupper:</span><span class="sxs-lookup"><span data-stu-id="43e13-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="43e13-117">Analytiker på nivå 1</span><span class="sxs-lookup"><span data-stu-id="43e13-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="43e13-118">Analytiker på nivå 2</span><span class="sxs-lookup"><span data-stu-id="43e13-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="43e13-119">Mssp-analytikers godkännare</span><span class="sxs-lookup"><span data-stu-id="43e13-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="43e13-120">Skapa Defender för slutpunktsroller för lämpliga åtkomstnivåer i Customer Defender för Endpoint i Roller och grupper i Säkerhetscenter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43e13-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="43e13-121">Åtkomstbehörigheter **> Slutpunktsroller &** grupper > Roller med ett användarkonto med behörigheten Global administratör eller Säkerhetsadministratör för att aktivera RBAC i Kundens Microsoft 365-säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="43e13-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Bild av MSSP-åtkomst](../../media/mssp-access.png)

    <span data-ttu-id="43e13-123">Skapa sedan RBAC-roller för att uppfylla behoven på MSSP-nivån.</span><span class="sxs-lookup"><span data-stu-id="43e13-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="43e13-124">Länka de här rollerna till de skapade användargrupperna via "Tilldelade användargrupper".</span><span class="sxs-lookup"><span data-stu-id="43e13-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="43e13-125">Två möjliga roller:</span><span class="sxs-lookup"><span data-stu-id="43e13-125">Two possible roles:</span></span>

    - <span data-ttu-id="43e13-126">**Nivå 1-analytiker**</span><span class="sxs-lookup"><span data-stu-id="43e13-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="43e13-127">Utför alla åtgärder utom live-svar och hantera säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="43e13-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="43e13-128">**Nivå 2-analytiker**</span><span class="sxs-lookup"><span data-stu-id="43e13-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="43e13-129">Nivå 1-funktioner med tillägg till [live-svar](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="43e13-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="43e13-130">Mer information finns i Använda [rollbaserad åtkomstkontroll.](/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="43e13-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="43e13-131">Konfigurera styrningsåtkomstpaket</span><span class="sxs-lookup"><span data-stu-id="43e13-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="43e13-132">**Lägg till MSSP som ansluten organisation i kund AAD: identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="43e13-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="43e13-133">Om du lägger till MSSP som en ansluten organisation kan MSSP begära åtkomst och tillhandahålla åtkomst.</span><span class="sxs-lookup"><span data-stu-id="43e13-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="43e13-134">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Ansluten organisation.</span><span class="sxs-lookup"><span data-stu-id="43e13-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="43e13-135">Lägg till en ny organisation och sök efter din MSSP-analytiker via klientorganisations-ID eller domän.</span><span class="sxs-lookup"><span data-stu-id="43e13-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="43e13-136">Vi föreslår att du skapar en separat AD-klientorganisation för dina MSSP-analytiker.</span><span class="sxs-lookup"><span data-stu-id="43e13-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="43e13-137">**Skapa en resurskatalog i Kund AAD: Identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="43e13-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43e13-138">Resurskataloger är en logisk samling åtkomstpaket som skapats i kundens AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="43e13-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="43e13-139">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: kataloger och lägga till **ny katalog.**</span><span class="sxs-lookup"><span data-stu-id="43e13-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="43e13-140">I exemplet kallar vi det **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="43e13-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Bild av ny katalog](../../media/goverance-catalog.png)

    <span data-ttu-id="43e13-142">Mer information finns i [Skapa en resurskatalog.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="43e13-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="43e13-143">**Skapa åtkomstpaket för MSSP-resurser Kund AAD: Identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="43e13-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43e13-144">Åtkomstpaket är den samling av rättigheter och åtkomst som en begärare kommer att beviljas vid godkännande.</span><span class="sxs-lookup"><span data-stu-id="43e13-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="43e13-145">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Åtkomstpaket och lägga till **Nytt åtkomstpaket**.</span><span class="sxs-lookup"><span data-stu-id="43e13-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="43e13-146">Skapa ett åtkomstpaket för MSSP-godkännare och varje analytiker.</span><span class="sxs-lookup"><span data-stu-id="43e13-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="43e13-147">Följande analytikerkonfiguration på nivå 1 skapar till exempel ett åtkomstpaket som:</span><span class="sxs-lookup"><span data-stu-id="43e13-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="43e13-148">Kräver att en medlem i AD-gruppens **analytiker (MSSP) godkännare godkänner** nya begäranden</span><span class="sxs-lookup"><span data-stu-id="43e13-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="43e13-149">Har årliga åtkomstgranskningar, där SOC-analytiker kan begära ett åtkomsttillägg</span><span class="sxs-lookup"><span data-stu-id="43e13-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="43e13-150">Kan endast begäras av användare i MSSP-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="43e13-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="43e13-151">Access upphör automatiskt efter 365 dagar</span><span class="sxs-lookup"><span data-stu-id="43e13-151">Access auto expires after 365 days</span></span>

    ![Bild på nytt åtkomstpaket](../../media/new-access-package.png)

    <span data-ttu-id="43e13-153">Mer information finns i [Skapa ett nytt åtkomstpaket.](/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="43e13-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="43e13-154">**Länk för åtkomstbegäran till MSSP-resurser från kund AAD: identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="43e13-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43e13-155">Länken Min åtkomstportal används av MSSP SOC-analytiker för att begära åtkomst via de åtkomstpaket som skapats.</span><span class="sxs-lookup"><span data-stu-id="43e13-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="43e13-156">Länken är beständiga, vilket innebär att samma länk kan användas med tiden för nya analytiker.</span><span class="sxs-lookup"><span data-stu-id="43e13-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="43e13-157">Analytikerbegäran går i en kö för godkännande av analytiker som godkänner **MSSP.**</span><span class="sxs-lookup"><span data-stu-id="43e13-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Bild av åtkomstegenskaper](../../media/access-properties.png)

    <span data-ttu-id="43e13-159">Länken finns på översiktssidan för varje åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="43e13-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="43e13-160">Hantera åtkomst</span><span class="sxs-lookup"><span data-stu-id="43e13-160">Manage access</span></span> 

1. <span data-ttu-id="43e13-161">Granska och auktorisera åtkomstförfrågningar i Customer and/or MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="43e13-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="43e13-162">Åtkomstförfrågningar hanteras i kundens My Access av medlemmar i gruppen Analysts godkännare för MSSP.</span><span class="sxs-lookup"><span data-stu-id="43e13-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="43e13-163">Det gör du genom att använda kundens myaccess med hjälp av:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="43e13-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="43e13-164">Exempel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="43e13-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="43e13-165">Godkänn eller neka förfrågningar i **avsnittet Godkännanden** i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="43e13-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="43e13-166">I det här läget har analytiker åtkomst till företaget etablerats och varje analytiker ska kunna komma åt kundens Microsoft 365 Säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="43e13-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="43e13-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` med de behörigheter och roller som de har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="43e13-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43e13-168">Delegerad åtkomst till Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365 ger för närvarande tillgång till en enda innehavare per webbläsarfönster.</span><span class="sxs-lookup"><span data-stu-id="43e13-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>