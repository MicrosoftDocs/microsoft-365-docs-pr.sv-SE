---
title: Välj den domän som ska användas när du skapar Microsoft 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Lär dig hur du väljer den domän som ska användas när du skapar Microsoft 365 Groups genom att konfigurera principer för e-postadresser med PowerShell.
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612946"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="403ae-103">Välj den domän som ska användas när du skapar Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="403ae-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="403ae-104">Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten.</span><span class="sxs-lookup"><span data-stu-id="403ae-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="403ae-105">Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="403ae-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="403ae-106">Om din organisation behöver användare för att skapa grupper i andra domäner än den godkända domänen för ditt företag kan du tillåta detta genom att konfigurera e-postadress principer (principer) med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="403ae-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="403ae-107">Innan du kan köra PowerShell-cmdlets laddar du ned och installerar en modul som låter dig prata med din organisation.</span><span class="sxs-lookup"><span data-stu-id="403ae-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="403ae-108">Läs [Anslut till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="403ae-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="403ae-109">Exempel scenarier</span><span class="sxs-lookup"><span data-stu-id="403ae-109">Example scenarios</span></span>

<span data-ttu-id="403ae-110">Låt oss säga att företagets huvudsakliga domän är Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="403ae-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="403ae-111">Men organisationens standard domän är service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="403ae-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="403ae-112">Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="403ae-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="403ae-113">Låt oss säga att du också har konfigurerade under domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="403ae-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="403ae-114">Du vill att grupper ska skapas i dessa domäner också:</span><span class="sxs-lookup"><span data-stu-id="403ae-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="403ae-115">students.contoso.com för studenter</span><span class="sxs-lookup"><span data-stu-id="403ae-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="403ae-116">faculty.contoso.com för lärare och övrig personal</span><span class="sxs-lookup"><span data-stu-id="403ae-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="403ae-117">I följande två scenarier förklaras hur du gör det.</span><span class="sxs-lookup"><span data-stu-id="403ae-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="403ae-118">När du har flera principer utvärderas de i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="403ae-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="403ae-119">Värdet 1 innebär högsta prioritet.</span><span class="sxs-lookup"><span data-stu-id="403ae-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="403ae-120">När ett EAP-nummer matchar har ingen ytterligare EAP utvärderats och adresser som har stämplats i gruppen är som följer den matchade EAP.</span><span class="sxs-lookup"><span data-stu-id="403ae-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="403ae-121">> om ingen principer matchar de angivna villkoren får gruppen etableringen i organisationens standard domän.</span><span class="sxs-lookup"><span data-stu-id="403ae-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="403ae-122">Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).</span><span class="sxs-lookup"><span data-stu-id="403ae-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="403ae-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="403ae-123">Scenario 1</span></span>

<span data-ttu-id="403ae-124">I följande exempel visas hur du kan etablera alla Microsoft 365-grupper i din organisation i groups.contoso.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="403ae-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="403ae-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="403ae-125">Scenario 2</span></span>

<span data-ttu-id="403ae-126">Låt oss säga att du vill kontrol lera vilka under domäner Microsoft 365-grupper skapas i.</span><span class="sxs-lookup"><span data-stu-id="403ae-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="403ae-127">Du vill ha:</span><span class="sxs-lookup"><span data-stu-id="403ae-127">You want:</span></span>
  
- <span data-ttu-id="403ae-128">Grupper som skapas av elever (användare som har en **avdelning** som är inställt på **studenter**) i students.Groups.contoso.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="403ae-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="403ae-129">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="403ae-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="403ae-130">Grupper som skapas av lärare (användare som har en **avdelning** inställd på **lärare eller e-postadress innehåller Faculty.contoso.com)**) i Faculty.Groups.contoso.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="403ae-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="403ae-131">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="403ae-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="403ae-132">Grupper som skapas av någon annan skapas i domänen groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="403ae-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="403ae-133">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="403ae-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="403ae-134">Ändra principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="403ae-134">Change email address policies</span></span>

<span data-ttu-id="403ae-135">Använd cmdleten Set-EmailAddressPolicy för att ändra mallar för prioritet eller e-postadress för en befintlig princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="403ae-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="403ae-136">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="403ae-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="403ae-137">Ta bort principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="403ae-137">Delete email address policies</span></span>

<span data-ttu-id="403ae-138">Använd cmdleten Remove-EmailAddressPolicy om du vill ta bort en princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="403ae-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="403ae-139">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="403ae-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="403ae-140">Hybridkrav</span><span class="sxs-lookup"><span data-stu-id="403ae-140">Hybrid requirements</span></span>

<span data-ttu-id="403ae-141">Om organisationen har kon figurer ATS i ett hybrid scenario kan du läsa [Konfigurera Microsoft 365-grupper med lokal Exchange-hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) för att kontrol lera att din organisation uppfyller kraven för att skapa Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="403ae-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="403ae-142">Ytterligare information om hur du använder principer för e-postadresser:</span><span class="sxs-lookup"><span data-stu-id="403ae-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="403ae-143">Det finns några saker du bör känna till:</span><span class="sxs-lookup"><span data-stu-id="403ae-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="403ae-144">Hur snabbt grupper skapas beror på hur många principer som är konfigurerade i organisationen.</span><span class="sxs-lookup"><span data-stu-id="403ae-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="403ae-145">Administratörer och användare kan också ändra domäner när de skapar grupper.</span><span class="sxs-lookup"><span data-stu-id="403ae-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="403ae-146">Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="403ae-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="403ae-147">Läs filter bara [Egenskaper för parametern-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) för filter bara egenskaper som stöds.</span><span class="sxs-lookup"><span data-stu-id="403ae-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="403ae-148">Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.</span><span class="sxs-lookup"><span data-stu-id="403ae-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="403ae-149">Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.</span><span class="sxs-lookup"><span data-stu-id="403ae-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="403ae-150">Högst 100 principer för e-postadresser kan konfigureras för en organisation.</span><span class="sxs-lookup"><span data-stu-id="403ae-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="403ae-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="403ae-151">Related articles</span></span>

[<span data-ttu-id="403ae-152">Planerings steg-för-steg-samarbete för samarbets styrning</span><span class="sxs-lookup"><span data-stu-id="403ae-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="403ae-153">Skapa en plan för hantering av samarbete</span><span class="sxs-lookup"><span data-stu-id="403ae-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="403ae-154">Skapa en Microsoft 365-grupp i administrations centret</span><span class="sxs-lookup"><span data-stu-id="403ae-154">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
