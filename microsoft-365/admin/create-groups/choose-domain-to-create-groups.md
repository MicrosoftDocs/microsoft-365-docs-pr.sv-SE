---
title: Välj vilken domän som ska användas när Microsoft 365-grupper skapas
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Lär dig att välja vilken domän du vill använda när du skapar Microsoft 365-grupper genom att konfigurera e-postadressprinciper med PowerShell. '
ms.openlocfilehash: 1bc8a160ffc368bc4c66a5ac17ffcb203dc678f5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630629"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="6d94c-103">Välj vilken domän som ska användas när Microsoft 365-grupper skapas</span><span class="sxs-lookup"><span data-stu-id="6d94c-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

 <span data-ttu-id="6d94c-104">Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten.</span><span class="sxs-lookup"><span data-stu-id="6d94c-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="6d94c-105">Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="6d94c-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="6d94c-106">Om din organisation behöver användare för att skapa sina grupper i andra domäner än företagets standard accepterade domän kan du tillåta detta genom att konfigurera EPP-adresser (EAPs) med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d94c-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="6d94c-107">Innan du kan köra PowerShell-cmdlets hämtar och installerar du en modul som låter dig prata med din organisation.</span><span class="sxs-lookup"><span data-stu-id="6d94c-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="6d94c-108">Läs [Anslut till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="6d94c-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="6d94c-109">Exempel på scenarier</span><span class="sxs-lookup"><span data-stu-id="6d94c-109">Example scenarios</span></span>

<span data-ttu-id="6d94c-110">Anta att ditt företags huvuddomän är Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="6d94c-111">Men organisationens standard accepterad domän är service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="6d94c-112">Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6d94c-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="6d94c-113">Anta att du också har konfigurerat underdomäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6d94c-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="6d94c-114">Du vill också att grupper ska skapas i dessa domäner:</span><span class="sxs-lookup"><span data-stu-id="6d94c-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="6d94c-115">students.contoso.com för studenter</span><span class="sxs-lookup"><span data-stu-id="6d94c-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="6d94c-116">faculty.contoso.com för lärare och övrig personal</span><span class="sxs-lookup"><span data-stu-id="6d94c-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="6d94c-117">Följande två scenarier förklarar hur du skulle åstadkomma detta.</span><span class="sxs-lookup"><span data-stu-id="6d94c-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d94c-118">När du har flera EA:er utvärderas de i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="6d94c-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="6d94c-119">Värdet 1 innebär högsta prioritet.</span><span class="sxs-lookup"><span data-stu-id="6d94c-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="6d94c-120">När en EAP matchar utvärderas ingen ytterligare EAP och adresser som stämplas i gruppen är enligt den matchade EAP.</span><span class="sxs-lookup"><span data-stu-id="6d94c-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="6d94c-121">> Om inga EAPs matchar de angivna villkoren etableras gruppen i organisationens standard accepterade domän.</span><span class="sxs-lookup"><span data-stu-id="6d94c-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="6d94c-122">Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).</span><span class="sxs-lookup"><span data-stu-id="6d94c-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="6d94c-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="6d94c-123">Scenario 1</span></span>

<span data-ttu-id="6d94c-124">I följande exempel visas hur du etablerar alla Microsoft 365-grupper i organisationen i domänen groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="6d94c-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="6d94c-125">Scenario 2</span></span>

<span data-ttu-id="6d94c-126">Anta att du vill styra vilka underdomäner som Microsoft 365-grupper skapas i.</span><span class="sxs-lookup"><span data-stu-id="6d94c-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="6d94c-127">Du vill ha:</span><span class="sxs-lookup"><span data-stu-id="6d94c-127">You want:</span></span>
  
- <span data-ttu-id="6d94c-128">Grupper som skapats av studenter (användare som har **institutionen** inställd **på Studenter)** i domänen students.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="6d94c-129">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="6d94c-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="6d94c-130">Grupper som skapats av fakultetsmedlemmar (användare som har **institutionen** inställd **på fakultet eller e-postadress innehåller faculty.contoso.com)**) i domänen faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="6d94c-131">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="6d94c-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="6d94c-132">Alla andra användare i domänen groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6d94c-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="6d94c-133">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="6d94c-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="6d94c-134">Ändra principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="6d94c-134">Change email address policies</span></span>

<span data-ttu-id="6d94c-135">Använd cmdleten Set-EmailAddressPolicy för att ändra mallar för prioritet eller e-postadress för en befintlig princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="6d94c-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="6d94c-136">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="6d94c-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="6d94c-137">Ta bort principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="6d94c-137">Delete email address policies</span></span>

<span data-ttu-id="6d94c-138">Använd cmdleten Remove-EmailAddressPolicy om du vill ta bort en princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="6d94c-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="6d94c-139">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="6d94c-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="6d94c-140">Hybridkrav</span><span class="sxs-lookup"><span data-stu-id="6d94c-140">Hybrid requirements</span></span>

<span data-ttu-id="6d94c-141">Om din organisation är konfigurerad i ett hybridscenario kan du läsa [Konfigurera Microsoft 365-grupper med lokal Exchange-hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) för att se till att din organisation uppfyller kraven för att skapa Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="6d94c-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="6d94c-142">Ytterligare information om hur du använder e-postadressprincipgrupper:</span><span class="sxs-lookup"><span data-stu-id="6d94c-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="6d94c-143">Det finns några fler saker att veta:</span><span class="sxs-lookup"><span data-stu-id="6d94c-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="6d94c-144">Hur snabbt grupper skapas beror på antalet EAPs som konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6d94c-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="6d94c-145">Administratörer och användare kan också ändra domäner när de skapar grupper.</span><span class="sxs-lookup"><span data-stu-id="6d94c-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="6d94c-146">Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="6d94c-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="6d94c-147">[Incheckning filterbara egenskaper för parametern -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) för filterbara egenskaper som stöds.</span><span class="sxs-lookup"><span data-stu-id="6d94c-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="6d94c-148">Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.</span><span class="sxs-lookup"><span data-stu-id="6d94c-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="6d94c-149">Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.</span><span class="sxs-lookup"><span data-stu-id="6d94c-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="6d94c-150">Högst 100 principer för e-postadresser kan konfigureras för en organisation.</span><span class="sxs-lookup"><span data-stu-id="6d94c-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="6d94c-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6d94c-151">Related articles</span></span>

[<span data-ttu-id="6d94c-152">Skapa en Microsoft 365-grupp i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="6d94c-152">Create an Microsoft 365 group in the admin center</span></span>](create-groups.md)
