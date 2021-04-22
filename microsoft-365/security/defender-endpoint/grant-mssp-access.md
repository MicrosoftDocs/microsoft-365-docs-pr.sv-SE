---
title: Bevilja åtkomst till hanterad säkerhetstjänstleverantör (MSSP)
description: Vidta nödvändiga åtgärder för att konfigurera MSSP-integrering med Microsoft Defender för slutpunkt
keywords: hanterad säkerhetstjänstleverantör, mssp, konfigurera, integrering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932757"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="3443f-104">Bevilja åtkomst för hanterad säkerhetstjänstleverantör (MSSP) (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="3443f-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3443f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3443f-105">**Applies to:**</span></span>
- [<span data-ttu-id="3443f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3443f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3443f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3443f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3443f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3443f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3443f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3443f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="3443f-110">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="3443f-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3443f-111">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="3443f-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3443f-112">Om du vill implementera en lösning med flera klientorganisationens delegerade åtkomst gör du följande:</span><span class="sxs-lookup"><span data-stu-id="3443f-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="3443f-113">Aktivera [rollbaserad åtkomstkontroll i](rbac.md) Defender för Endpoint och ansluta med Active Directory-grupper (AD).</span><span class="sxs-lookup"><span data-stu-id="3443f-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="3443f-114">Konfigurera [styrningsåtkomstpaket](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) för åtkomstbegäran och etablering.</span><span class="sxs-lookup"><span data-stu-id="3443f-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="3443f-115">Hantera åtkomstförfrågningar och granskningar i [Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="3443f-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3443f-116">Aktivera rollbaserade åtkomstkontroller i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3443f-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="3443f-117">**Skapa åtkomstgrupper för MSSP-resurser i Kund-AAD: Grupper**</span><span class="sxs-lookup"><span data-stu-id="3443f-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="3443f-118">De här grupperna länkas till de roller som du skapar i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="3443f-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="3443f-119">Det gör du genom att skapa tre grupper i kundens AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="3443f-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="3443f-120">Med den här metoden skapar vi följande grupper:</span><span class="sxs-lookup"><span data-stu-id="3443f-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="3443f-121">Analytiker på nivå 1</span><span class="sxs-lookup"><span data-stu-id="3443f-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="3443f-122">Analytiker på nivå 2</span><span class="sxs-lookup"><span data-stu-id="3443f-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="3443f-123">Mssp-analytikers godkännare</span><span class="sxs-lookup"><span data-stu-id="3443f-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="3443f-124">Skapa Defender för slutpunktsroller för lämpliga åtkomstnivåer i Customer Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3443f-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="3443f-125">Om du vill aktivera RBAC i kundens Microsoft Defender Säkerhetscenter öppnar du Inställningar > Behörigheter **>** Roller och "Aktivera roller" från ett användarkonto med rättigheter som global administratör eller säkerhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="3443f-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Bild av MSSP-åtkomst](images/mssp-access.png)

    <span data-ttu-id="3443f-127">Skapa sedan RBAC-roller för att uppfylla behoven på MSSP-nivån.</span><span class="sxs-lookup"><span data-stu-id="3443f-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="3443f-128">Länka de här rollerna till de skapade användargrupperna via "Tilldelade användargrupper".</span><span class="sxs-lookup"><span data-stu-id="3443f-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="3443f-129">Två möjliga roller:</span><span class="sxs-lookup"><span data-stu-id="3443f-129">Two possible roles:</span></span>

    - <span data-ttu-id="3443f-130">**Nivå 1-analytiker**</span><span class="sxs-lookup"><span data-stu-id="3443f-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="3443f-131">Utför alla åtgärder utom live-svar och hantera säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="3443f-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="3443f-132">**Nivå 2-analytiker**</span><span class="sxs-lookup"><span data-stu-id="3443f-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="3443f-133">Nivå 1-funktioner med tillägg till [live-svar](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="3443f-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="3443f-134">Mer information finns i Använda [rollbaserad åtkomstkontroll.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="3443f-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="3443f-135">Konfigurera styrningsåtkomstpaket</span><span class="sxs-lookup"><span data-stu-id="3443f-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="3443f-136">**Lägg till MSSP som ansluten organisation i kund AAD: identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="3443f-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="3443f-137">Om du lägger till MSSP som en ansluten organisation kan MSSP begära åtkomst och tillhandahålla åtkomst.</span><span class="sxs-lookup"><span data-stu-id="3443f-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="3443f-138">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Ansluten organisation.</span><span class="sxs-lookup"><span data-stu-id="3443f-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="3443f-139">Lägg till en ny organisation och sök efter din MSSP-analytiker via klientorganisations-ID eller domän.</span><span class="sxs-lookup"><span data-stu-id="3443f-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="3443f-140">Vi föreslår att du skapar en separat AD-klientorganisation för dina MSSP-analytiker.</span><span class="sxs-lookup"><span data-stu-id="3443f-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="3443f-141">**Skapa en resurskatalog i Kund AAD: Identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="3443f-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3443f-142">Resurskataloger är en logisk samling åtkomstpaket som skapats i kundens AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="3443f-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="3443f-143">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: kataloger och lägga till **ny katalog.**</span><span class="sxs-lookup"><span data-stu-id="3443f-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="3443f-144">I exemplet kallar vi det **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="3443f-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Bild av ny katalog](images/goverance-catalog.png)

    <span data-ttu-id="3443f-146">Mer information finns i [Skapa en resurskatalog.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="3443f-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="3443f-147">**Skapa åtkomstpaket för MSSP-resurser Kund AAD: Identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="3443f-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3443f-148">Åtkomstpaket är den samling av rättigheter och åtkomst som en begärare kommer att beviljas vid godkännande.</span><span class="sxs-lookup"><span data-stu-id="3443f-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="3443f-149">Det gör du genom att i kundens AD-klientorganisation få åtkomst till identitetsstyrning: Åtkomstpaket och lägga till **Nytt åtkomstpaket**.</span><span class="sxs-lookup"><span data-stu-id="3443f-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="3443f-150">Skapa ett åtkomstpaket för MSSP-godkännare och varje analytiker.</span><span class="sxs-lookup"><span data-stu-id="3443f-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="3443f-151">Följande analytikerkonfiguration på nivå 1 skapar till exempel ett åtkomstpaket som:</span><span class="sxs-lookup"><span data-stu-id="3443f-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="3443f-152">Kräver att en medlem i AD-gruppens **analytiker (MSSP) godkännare godkänner** nya begäranden</span><span class="sxs-lookup"><span data-stu-id="3443f-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="3443f-153">Har årliga åtkomstgranskningar, där SOC-analytiker kan begära ett åtkomsttillägg</span><span class="sxs-lookup"><span data-stu-id="3443f-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="3443f-154">Kan endast begäras av användare i MSSP-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="3443f-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="3443f-155">Access upphör automatiskt efter 365 dagar</span><span class="sxs-lookup"><span data-stu-id="3443f-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3443f-156">![Bild på nytt åtkomstpaket](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="3443f-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="3443f-157">Mer information finns i [Skapa ett nytt åtkomstpaket.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="3443f-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="3443f-158">**Länk för åtkomstbegäran till MSSP-resurser från kund AAD: identitetsstyrning**</span><span class="sxs-lookup"><span data-stu-id="3443f-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3443f-159">Länken Min åtkomstportal används av MSSP SOC-analytiker för att begära åtkomst via de åtkomstpaket som skapats.</span><span class="sxs-lookup"><span data-stu-id="3443f-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="3443f-160">Länken är beständiga, vilket innebär att samma länk kan användas med tiden för nya analytiker.</span><span class="sxs-lookup"><span data-stu-id="3443f-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="3443f-161">Analytikerbegäran går i en kö för godkännande av analytiker som godkänner **MSSP.**</span><span class="sxs-lookup"><span data-stu-id="3443f-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3443f-162">![Bild av åtkomstegenskaper](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="3443f-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="3443f-163">Länken finns på översiktssidan för varje åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="3443f-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="3443f-164">Hantera åtkomst</span><span class="sxs-lookup"><span data-stu-id="3443f-164">Manage access</span></span> 

1. <span data-ttu-id="3443f-165">Granska och auktorisera åtkomstförfrågningar i Customer and/or MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="3443f-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="3443f-166">Åtkomstförfrågningar hanteras i kundens My Access av medlemmar i gruppen Analysts godkännare för MSSP.</span><span class="sxs-lookup"><span data-stu-id="3443f-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="3443f-167">Det gör du genom att använda kundens myaccess med hjälp av:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="3443f-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="3443f-168">Exempel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="3443f-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="3443f-169">Godkänn eller neka förfrågningar i **avsnittet Godkännanden** i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="3443f-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="3443f-170">I det här läget har analytikernas åtkomst etablerats och varje analytiker ska kunna komma åt kundens Microsoft Defender Säkerhetscenter: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="3443f-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="3443f-171">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3443f-171">Related topics</span></span>
- [<span data-ttu-id="3443f-172">Få åtkomst till MSSP-kundportalen</span><span class="sxs-lookup"><span data-stu-id="3443f-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="3443f-173">Konfigurera varningsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3443f-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="3443f-174">Hämta varningar från kundens klientorganisation</span><span class="sxs-lookup"><span data-stu-id="3443f-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

