---
title: Visa Microsoft 365-licenser och-tjänster med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Förklarar hur du använder PowerShell för att visa information om licens planer, tjänster och licenser som är tillgängliga i din Microsoft 365-organisation.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694560"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="91ecf-103">Visa Microsoft 365-licenser och-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="91ecf-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="91ecf-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="91ecf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="91ecf-105">Alla Microsoft 365-prenumerationer består av följande element:</span><span class="sxs-lookup"><span data-stu-id="91ecf-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="91ecf-106">**Licens planer** Dessa kallas även licens planer eller Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="91ecf-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="91ecf-107">Licens planer definierar vilka Microsoft 365-tjänster som är tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="91ecf-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="91ecf-108">Ditt Microsoft 365-abonnemang kan innehålla flera licens planer.</span><span class="sxs-lookup"><span data-stu-id="91ecf-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="91ecf-109">Ett exempel på en licens plan är Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="91ecf-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="91ecf-110">**Tjänster** De här kallas även för tjänste abonnemang.</span><span class="sxs-lookup"><span data-stu-id="91ecf-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="91ecf-111">Tjänster är Microsoft 365-produkter,-funktioner och-funktioner som är tillgängliga i varje licens plan, till exempel Exchange Online och Microsoft 365-appar för företag (tidigare kallat Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="91ecf-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="91ecf-112">Användare kan ha flera licenser tilldelade till dem från olika licens planer som beviljar åtkomst till olika tjänster.</span><span class="sxs-lookup"><span data-stu-id="91ecf-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="91ecf-113">**Licenser** Varje licens plan innehåller antalet licenser som du har köpt.</span><span class="sxs-lookup"><span data-stu-id="91ecf-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="91ecf-114">Du tilldelar licenser till användarna så att de kan använda Microsoft 365-tjänsterna som definieras av licens planen.</span><span class="sxs-lookup"><span data-stu-id="91ecf-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="91ecf-115">För varje användar konto krävs minst en licens från ett licens abonnemang så att de kan logga in på Microsoft 365 och använda tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="91ecf-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="91ecf-116">Du kan använda PowerShell för Microsoft 365 för att visa information om tillgängliga licens planer, licenser och tjänster i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="91ecf-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="91ecf-117">Mer information om produkter, funktioner och tjänster som är tillgängliga i olika Office 365-abonnemang finns i alternativ för [office 365-abonnemang](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span><span class="sxs-lookup"><span data-stu-id="91ecf-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="91ecf-118">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="91ecf-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="91ecf-119">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="91ecf-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="91ecf-120">Om du vill visa sammanfattnings information om dina aktuella licens planer och tillgängliga licenser för varje abonnemang kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="91ecf-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="91ecf-121">Resultatet innehåller:</span><span class="sxs-lookup"><span data-stu-id="91ecf-121">The results contain:</span></span>
  
- <span data-ttu-id="91ecf-122">**SkuPartNumber:** Visar tillgängliga licens planer för organisationen.</span><span class="sxs-lookup"><span data-stu-id="91ecf-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="91ecf-123">Till exempel `ENTERPRISEPACK` är licens Plans namnet för Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="91ecf-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="91ecf-124">**Aktive rad:** Antalet licenser som du har köpt för ett specifikt licens abonnemang.</span><span class="sxs-lookup"><span data-stu-id="91ecf-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="91ecf-125">**ConsumedUnits:** Antalet licenser som du har tilldelat användarna från en viss licens plan.</span><span class="sxs-lookup"><span data-stu-id="91ecf-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="91ecf-126">Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licens planer måste du först Visa en lista över dina licens planer.</span><span class="sxs-lookup"><span data-stu-id="91ecf-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="91ecf-127">Sedan lagrar du information om licens planer i en variabel.</span><span class="sxs-lookup"><span data-stu-id="91ecf-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="91ecf-128">Nästa steg är att Visa tjänsterna i en specifik licens plan.</span><span class="sxs-lookup"><span data-stu-id="91ecf-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="91ecf-129">\<index> är ett heltal som anger rad numret för licens planen från visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot, minus 1.</span><span class="sxs-lookup"><span data-stu-id="91ecf-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="91ecf-130">Till exempel om visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot är det här:</span><span class="sxs-lookup"><span data-stu-id="91ecf-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="91ecf-131">Då är kommandot för att Visa tjänsterna för ENTERPRISEPREMIUM-licens planen det här:</span><span class="sxs-lookup"><span data-stu-id="91ecf-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="91ecf-132">ENTERPRISEPREMIUM är den tredje raden.</span><span class="sxs-lookup"><span data-stu-id="91ecf-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="91ecf-133">Därför är indexvärdet (3-1) eller 2.</span><span class="sxs-lookup"><span data-stu-id="91ecf-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="91ecf-134">En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="91ecf-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="91ecf-135">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91ecf-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="91ecf-136">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="91ecf-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="91ecf-137">Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91ecf-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="91ecf-138">Du kan också använda skript för att visa och inaktivera tjänster i Microsoft 365-organisationen, inklusive Sway.</span><span class="sxs-lookup"><span data-stu-id="91ecf-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="91ecf-139">Mer information finns i [inaktivera åtkomst till Sway med PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="91ecf-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="91ecf-140">Om du vill visa sammanfattnings information om dina aktuella licens planer och tillgängliga licenser för varje abonnemang kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="91ecf-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="91ecf-141">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="91ecf-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="91ecf-142">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91ecf-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="91ecf-143">Resultatet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="91ecf-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="91ecf-144">**AccountSkuId:** Visa tillgängliga licens planer för organisationen med hjälp av syntaxen `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="91ecf-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="91ecf-145">_\<CompanyName>_ är värdet som du angav när du registrerade dig i Microsoft 365 och är unikt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="91ecf-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="91ecf-146">_\<LicensingPlan>_ Värdet är detsamma för alla.</span><span class="sxs-lookup"><span data-stu-id="91ecf-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="91ecf-147">Till exempel, i värdet `litwareinc:ENTERPRISEPACK` , företags namnet  `litwareinc` och namnet på licens planen  `ENTERPRISEPACK` , som är system namnet för Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="91ecf-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="91ecf-148">**ActiveUnits:** Antalet licenser som du har köpt för ett specifikt licens abonnemang.</span><span class="sxs-lookup"><span data-stu-id="91ecf-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="91ecf-149">**WarningUnits:** Antalet licenser i en licens plan som du inte har förnyat och som upphör att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="91ecf-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="91ecf-150">**ConsumedUnits:** Antalet licenser som du har tilldelat användarna från en viss licens plan.</span><span class="sxs-lookup"><span data-stu-id="91ecf-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="91ecf-151">Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licens planer kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="91ecf-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="91ecf-152">I följande tabell visas Microsoft 365-tjänstens abonnemang och deras egna namn för de vanligaste tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="91ecf-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="91ecf-153">Din lista över tjänste abonnemang kan skilja sig från varandra.</span><span class="sxs-lookup"><span data-stu-id="91ecf-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="91ecf-154">**Service plan**</span><span class="sxs-lookup"><span data-stu-id="91ecf-154">**Service plan**</span></span>|<span data-ttu-id="91ecf-155">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="91ecf-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="91ecf-156">Sway</span><span class="sxs-lookup"><span data-stu-id="91ecf-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="91ecf-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91ecf-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="91ecf-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="91ecf-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="91ecf-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="91ecf-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="91ecf-160">Microsoft 365-appar för företag *(tidigare kallat Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="91ecf-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="91ecf-161">Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="91ecf-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="91ecf-162">Office</span><span class="sxs-lookup"><span data-stu-id="91ecf-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="91ecf-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="91ecf-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="91ecf-164">Exchange Online-abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="91ecf-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="91ecf-165">En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="91ecf-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="91ecf-166">Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i ett specifikt licens abonnemang använder du följande syntax.</span><span class="sxs-lookup"><span data-stu-id="91ecf-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="91ecf-167">I det här exemplet visas de tjänster som är tillgängliga i licens planen litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="91ecf-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="91ecf-168">Se även</span><span class="sxs-lookup"><span data-stu-id="91ecf-168">See also</span></span>

[<span data-ttu-id="91ecf-169">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="91ecf-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="91ecf-170">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="91ecf-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="91ecf-171">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91ecf-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
