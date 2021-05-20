---
title: Välj den domän som ska användas när du skapar Microsoft 365 grupper
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
recommendations: false
description: Lär dig att välja den domän som ska användas när du Microsoft 365 grupper genom att konfigurera principer för e-postadresser med PowerShell.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583154"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="78bb6-103">Välj den domän som ska användas när du skapar Microsoft 365 grupper</span><span class="sxs-lookup"><span data-stu-id="78bb6-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="78bb6-104">Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten.</span><span class="sxs-lookup"><span data-stu-id="78bb6-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="78bb6-105">Du kan ange vilken domän som ska användas när användarna skapar Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="78bb6-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="78bb6-106">Om din organisation kräver att användare skapar sina grupper i andra domäner än den godkända standarddomänen för ditt företag kan du tillåta det genom att konfigurera principer för e-postadresser med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78bb6-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="78bb6-107">Innan du kan köra PowerShell-cmdlets laddar du ned och installerar en modul som gör att du kan prata med din organisation.</span><span class="sxs-lookup"><span data-stu-id="78bb6-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="78bb6-108">Läs [Anslut till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="78bb6-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="78bb6-109">Exempelscenarier</span><span class="sxs-lookup"><span data-stu-id="78bb6-109">Example scenarios</span></span>

<span data-ttu-id="78bb6-110">Anta att företagets huvuddomän är en Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="78bb6-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="78bb6-111">Men din organisations godkända standarddomän är service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="78bb6-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="78bb6-112">Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78bb6-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="78bb6-113">Anta att du även har underdomäner konfigurerade i din organisation.</span><span class="sxs-lookup"><span data-stu-id="78bb6-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="78bb6-114">Du vill också att grupper ska skapas i dessa domäner:</span><span class="sxs-lookup"><span data-stu-id="78bb6-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="78bb6-115">students.contoso.com för studenter</span><span class="sxs-lookup"><span data-stu-id="78bb6-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="78bb6-116">faculty.contoso.com för lärare och övrig personal</span><span class="sxs-lookup"><span data-stu-id="78bb6-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="78bb6-117">I följande två scenarier förklaras hur du ska göra detta.</span><span class="sxs-lookup"><span data-stu-id="78bb6-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="78bb6-118">Om du har flera EP:er utvärderas de i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="78bb6-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="78bb6-119">Värdet 1 innebär högsta prioritet.</span><span class="sxs-lookup"><span data-stu-id="78bb6-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="78bb6-120">När en e-postadresser matchar utvärderas inte några ytterligare e-postadresser och adresser som märks i gruppen godkänns enligt den matchande e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="78bb6-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="78bb6-121">> om inga e-postprogram matchar de angivna villkoren får gruppen etableras i organisationens godkända standarddomän.</span><span class="sxs-lookup"><span data-stu-id="78bb6-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="78bb6-122">Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="78bb6-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="78bb6-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="78bb6-123">Scenario 1</span></span>

<span data-ttu-id="78bb6-124">Följande exempel visar hur du etablerar alla Microsoft 365 grupper i organisationen i groups.contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="78bb6-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="78bb6-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="78bb6-125">Scenario 2</span></span>

<span data-ttu-id="78bb6-126">Anta att du vill styra vilka underdomäner Microsoft 365 grupper skapas i.</span><span class="sxs-lookup"><span data-stu-id="78bb6-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="78bb6-127">Du vill ha:</span><span class="sxs-lookup"><span data-stu-id="78bb6-127">You want:</span></span>
  
- <span data-ttu-id="78bb6-128">Grupper som skapas av elever (användare där **Avdelning har** **angetts till Studenter**) i students.groups.contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="78bb6-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="78bb6-129">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="78bb6-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="78bb6-130">Grupper som skapas av lärare  och andra (användare där Avdelning har angetts till Lärare eller E-postadress **innehåller faculty.contoso.com)** i faculty.groups.contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="78bb6-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="78bb6-131">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="78bb6-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="78bb6-132">Grupper som har skapats av någon annan skapas i groups.contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="78bb6-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="78bb6-133">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="78bb6-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="78bb6-134">Ändra principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="78bb6-134">Change email address policies</span></span>

<span data-ttu-id="78bb6-135">Använd cmdleten Set-EmailAddressPolicy för att ändra mallar för prioritet eller e-postadress för en befintlig princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="78bb6-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="78bb6-136">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="78bb6-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="78bb6-137">Ta bort principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="78bb6-137">Delete email address policies</span></span>

<span data-ttu-id="78bb6-138">Använd cmdleten Remove-EmailAddressPolicy om du vill ta bort en princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="78bb6-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="78bb6-139">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="78bb6-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="78bb6-140">Hybridkrav</span><span class="sxs-lookup"><span data-stu-id="78bb6-140">Hybrid requirements</span></span>

<span data-ttu-id="78bb6-141">Om organisationen är konfigurerad i ett hybridscenario kan du läsa Konfigurera Microsoft 365-grupper med en lokal [Exchange-hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) för att kontrollera att organisationen uppfyller kraven för att Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="78bb6-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="78bb6-142">Mer information om hur du använder principer för e-postadresser:</span><span class="sxs-lookup"><span data-stu-id="78bb6-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="78bb6-143">Det finns några fler saker att veta:</span><span class="sxs-lookup"><span data-stu-id="78bb6-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="78bb6-144">Hur snabbt grupper skapas beror på hur många e-skaps som konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="78bb6-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="78bb6-145">Administratörer och användare kan också ändra domäner när de skapar grupper.</span><span class="sxs-lookup"><span data-stu-id="78bb6-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="78bb6-146">Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="78bb6-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="78bb6-147">Information om [filtrerbara egenskaper som stöds finns i Filtrerbara egenskaper för parametern -RecipientFilter.](/powershell/exchange/recipientfilter-properties)</span><span class="sxs-lookup"><span data-stu-id="78bb6-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="78bb6-148">Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.</span><span class="sxs-lookup"><span data-stu-id="78bb6-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="78bb6-149">Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.</span><span class="sxs-lookup"><span data-stu-id="78bb6-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="78bb6-150">Högst 100 principer för e-postadresser kan konfigureras för en organisation.</span><span class="sxs-lookup"><span data-stu-id="78bb6-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="78bb6-151">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="78bb6-151">Related content</span></span>

<span data-ttu-id="78bb6-152">[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (artikel)</span><span class="sxs-lookup"><span data-stu-id="78bb6-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="78bb6-153">[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="78bb6-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="78bb6-154">[Skapa en Microsoft 365 grupp i administrationscentret](../admin/create-groups/create-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="78bb6-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>