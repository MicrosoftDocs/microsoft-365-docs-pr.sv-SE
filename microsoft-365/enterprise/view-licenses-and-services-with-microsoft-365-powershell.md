---
title: Visa Microsoft 365-licenser och -tjänster med PowerShell
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
description: Förklarar hur du använder PowerShell för att visa information om licensplaner, tjänster och licenser som är tillgängliga i din Microsoft 365-organisation.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924642"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="8dc51-103">Visa Microsoft 365-licenser och -tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dc51-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="8dc51-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8dc51-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8dc51-105">Varje Microsoft 365-prenumeration består av följande element:</span><span class="sxs-lookup"><span data-stu-id="8dc51-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="8dc51-106">**Licensplaner** Dessa kallas även licensplaner eller Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="8dc51-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="8dc51-107">Licensplaner definierar de Microsoft 365-tjänster som är tillgängliga för användare.</span><span class="sxs-lookup"><span data-stu-id="8dc51-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="8dc51-108">Din Microsoft 365-prenumeration kan innehålla flera licensabonnemang.</span><span class="sxs-lookup"><span data-stu-id="8dc51-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="8dc51-109">Ett exempel på en licensieringsplan är Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="8dc51-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="8dc51-110">**Tjänster** De kallas även tjänstplaner.</span><span class="sxs-lookup"><span data-stu-id="8dc51-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="8dc51-111">Tjänster är Microsoft 365-produkter, -funktioner och -funktioner som är tillgängliga i varje licensplan, till exempel Exchange Online och Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="8dc51-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="8dc51-112">Användare kan ha flera licenser tilldelade till sig från olika licensplaner som beviljar åtkomst till olika tjänster.</span><span class="sxs-lookup"><span data-stu-id="8dc51-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="8dc51-113">**Licenser** Varje licensplan innehåller antalet licenser som du har köpt.</span><span class="sxs-lookup"><span data-stu-id="8dc51-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="8dc51-114">Du tilldelar användare licenser så att de kan använda De Microsoft 365-tjänster som definieras av licensplanen.</span><span class="sxs-lookup"><span data-stu-id="8dc51-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="8dc51-115">Varje användarkonto kräver minst en licens från en licensplan så att de kan logga in på Microsoft 365 och använda tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="8dc51-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="8dc51-116">Du kan använda PowerShell för Microsoft 365 för att visa information om tillgängliga licensplaner, licenser och tjänster i Microsoft 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="8dc51-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="8dc51-117">Mer information om de produkter, funktioner och tjänster som är tillgängliga i olika Office 365-prenumerationer finns i [Alternativ för Office 365-abonnemang.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span><span class="sxs-lookup"><span data-stu-id="8dc51-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8dc51-118">Använda Azure Active Directory PowerShell för Graph-modulen</span><span class="sxs-lookup"><span data-stu-id="8dc51-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8dc51-119">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="8dc51-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="8dc51-120">Om du vill visa sammanfattningsinformation om dina aktuella licensabonnemang och tillgängliga licenser för varje abonnemang kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="8dc51-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="8dc51-121">Resultatet innehåller:</span><span class="sxs-lookup"><span data-stu-id="8dc51-121">The results contain:</span></span>
  
- <span data-ttu-id="8dc51-122">**SkuPartNumber:** Visar organisationens tillgängliga licensplaner.</span><span class="sxs-lookup"><span data-stu-id="8dc51-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="8dc51-123">`ENTERPRISEPACK`Licensabonnemangnamnet för Office 365 Enterprise, E3.</span><span class="sxs-lookup"><span data-stu-id="8dc51-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="8dc51-124">**Aktiverad:** Antalet licenser som du har köpt för ett visst licensabonnemang.</span><span class="sxs-lookup"><span data-stu-id="8dc51-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="8dc51-125">**ConsumedUnits:** Antalet licenser som du har tilldelat användare från en specifik licensplan.</span><span class="sxs-lookup"><span data-stu-id="8dc51-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="8dc51-126">Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licensplaner visar du först en lista över dina licensplaner.</span><span class="sxs-lookup"><span data-stu-id="8dc51-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="8dc51-127">Lagra sedan information om licensplaner i en variabel.</span><span class="sxs-lookup"><span data-stu-id="8dc51-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="8dc51-128">Visa sedan tjänsterna i ett visst licensabonnemang.</span><span class="sxs-lookup"><span data-stu-id="8dc51-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="8dc51-129">\<index> är ett heltal som anger radnumret för licensplanen från visningen av `Get-AzureADSubscribedSku | Select SkuPartNumber` kommandot, minus 1.</span><span class="sxs-lookup"><span data-stu-id="8dc51-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="8dc51-130">Om visningen av kommandot `Get-AzureADSubscribedSku | Select SkuPartNumber` till exempel är följande:</span><span class="sxs-lookup"><span data-stu-id="8dc51-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="8dc51-131">Kommandot för att visa tjänsterna för ENTERPRISEPREMIUM-licensplanen är följande:</span><span class="sxs-lookup"><span data-stu-id="8dc51-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="8dc51-132">ENTERPRISEPREMIUM är den tredje raden.</span><span class="sxs-lookup"><span data-stu-id="8dc51-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="8dc51-133">Därför är indexvärdet (3 –1) eller 2.</span><span class="sxs-lookup"><span data-stu-id="8dc51-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="8dc51-134">En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="8dc51-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8dc51-135">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dc51-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8dc51-136">Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="8dc51-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="8dc51-137">Det finns ett PowerShell-skript som automatiserar procedurerna som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8dc51-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="8dc51-138">Med skriptet kan du visa och inaktivera tjänster i din Microsoft 365-organisation, inklusive Sway.</span><span class="sxs-lookup"><span data-stu-id="8dc51-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="8dc51-139">Mer information finns i Inaktivera [åtkomst till Sway med PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8dc51-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="8dc51-140">Kör följande kommando om du vill visa sammanfattningsinformation om dina aktuella licensabonnemang och tillgängliga licenser för varje abonnemang:</span><span class="sxs-lookup"><span data-stu-id="8dc51-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="8dc51-141">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="8dc51-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="8dc51-142">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8dc51-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="8dc51-143">Resultatet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="8dc51-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="8dc51-144">**AccountSkuId:** Visa organisationens tillgängliga licensplaner med syntaxen `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="8dc51-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="8dc51-145">_\<CompanyName>_ är det värde som du angav när du registrerade dig i Microsoft 365 och är unikt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="8dc51-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="8dc51-146">Värdet _\<LicensingPlan>_ är detsamma för alla.</span><span class="sxs-lookup"><span data-stu-id="8dc51-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="8dc51-147">I värdet är till exempel företagsnamnet och licensplanens namn , som är systemnamnet för `litwareinc:ENTERPRISEPACK`  `litwareinc` Office  `ENTERPRISEPACK` 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="8dc51-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="8dc51-148">**ActiveUnits:** Antalet licenser som du har köpt för ett visst licensabonnemang.</span><span class="sxs-lookup"><span data-stu-id="8dc51-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="8dc51-149">**WarningUnits:** Antalet licenser i ett licensabonnemang som du inte har förnyat och som upphör efter respitperioden på 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="8dc51-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="8dc51-150">**ConsumedUnits:** Antalet licenser som du har tilldelat användare från en specifik licensplan.</span><span class="sxs-lookup"><span data-stu-id="8dc51-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="8dc51-151">Om du vill visa information om de Microsoft 365-tjänster som är tillgängliga i alla dina licensplaner kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8dc51-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="8dc51-152">I följande tabell visas Microsoft 365-tjänstplaner och deras eget namn för de vanligaste tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="8dc51-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="8dc51-153">Listan med tjänstplaner kan se annorlunda ut.</span><span class="sxs-lookup"><span data-stu-id="8dc51-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="8dc51-154">**Serviceplan**</span><span class="sxs-lookup"><span data-stu-id="8dc51-154">**Service plan**</span></span>|<span data-ttu-id="8dc51-155">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="8dc51-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="8dc51-156">Sway</span><span class="sxs-lookup"><span data-stu-id="8dc51-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="8dc51-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8dc51-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="8dc51-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="8dc51-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="8dc51-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="8dc51-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="8dc51-160">Microsoft 365-appar för företag *(kallades tidigare Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="8dc51-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="8dc51-161">Skype för företag online</span><span class="sxs-lookup"><span data-stu-id="8dc51-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="8dc51-162">Office</span><span class="sxs-lookup"><span data-stu-id="8dc51-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="8dc51-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8dc51-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="8dc51-164">Exchange Online-abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="8dc51-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="8dc51-165">En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="8dc51-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="8dc51-166">Använd följande syntax för att visa information om de Microsoft 365-tjänster som är tillgängliga i en specifik licensplan.</span><span class="sxs-lookup"><span data-stu-id="8dc51-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="8dc51-167">Det här exemplet visar de tjänster som är tillgängliga i licensplanen litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="8dc51-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="8dc51-168">Se även</span><span class="sxs-lookup"><span data-stu-id="8dc51-168">See also</span></span>

[<span data-ttu-id="8dc51-169">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dc51-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8dc51-170">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dc51-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8dc51-171">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8dc51-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)