---
title: Välja domän som ska användas för att skapa Office 365-grupper
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
description: 'Lär dig att välja vilken domän du vill använda när du skapar Office 365-grupper genom att konfigurera e-postadressprinciper med PowerShell. '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808167"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="3b73d-103">Välja domän som ska användas för att skapa Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="3b73d-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="3b73d-p101">Vissa organisationer använder separata e-postdomäner för att dela upp olika delar av verksamheten. Du kan ange vilken domän som ska användas när användarna skapar Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="3b73d-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="3b73d-106">Om din organisation behöver användare för att skapa sina grupper i andra domäner än företagets standard accepterade domän kan du tillåta detta genom att konfigurera EPP-adresser (EAPs) med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b73d-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="3b73d-107">Innan du kan köra PowerShell-cmdlets kan du hämta och installera en modul där du kan prata med din Office 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="3b73d-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization.</span></span> <span data-ttu-id="3b73d-108">Läs [Anslut till Exchange Online med fjärr-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="3b73d-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="3b73d-109">Exempel på scenarier</span><span class="sxs-lookup"><span data-stu-id="3b73d-109">Example scenarios</span></span>

<span data-ttu-id="3b73d-110">Anta att ditt företags huvuddomän är Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="3b73d-111">Men organisationens standard accepterad domän är service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="3b73d-112">Det innebär att grupper skapas i service.contoso.com (till exempel jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3b73d-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="3b73d-113">Anta att du också har konfigurerat underdomäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3b73d-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="3b73d-114">Du vill också att grupper ska skapas i dessa domäner:</span><span class="sxs-lookup"><span data-stu-id="3b73d-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="3b73d-115">students.contoso.com för studenter</span><span class="sxs-lookup"><span data-stu-id="3b73d-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="3b73d-116">faculty.contoso.com för lärare och övrig personal</span><span class="sxs-lookup"><span data-stu-id="3b73d-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="3b73d-117">Följande två scenarier förklarar hur du skulle åstadkomma detta.</span><span class="sxs-lookup"><span data-stu-id="3b73d-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b73d-118">När du har flera EA:er utvärderas de i prioritetsordning.</span><span class="sxs-lookup"><span data-stu-id="3b73d-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="3b73d-119">Värdet 1 innebär högsta prioritet.</span><span class="sxs-lookup"><span data-stu-id="3b73d-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="3b73d-120">När en EAP matchar utvärderas ingen ytterligare EAP och adresser som stämplas i gruppen är enligt den matchade EAP.</span><span class="sxs-lookup"><span data-stu-id="3b73d-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="3b73d-121">> Om inga EAPs matchar de angivna villkoren etableras gruppen i organisationens standard accepterade domän.</span><span class="sxs-lookup"><span data-stu-id="3b73d-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="3b73d-122">Mer information om hur du lägger till en godkänd domän finns i [Hantera godkända domäner i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428).</span><span class="sxs-lookup"><span data-stu-id="3b73d-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="3b73d-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="3b73d-123">Scenario 1</span></span>

<span data-ttu-id="3b73d-124">Följande exempel visar hur du etablerar alla Office 365-grupper i organisationen i domänen groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="3b73d-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="3b73d-125">Scenario 2</span></span>

<span data-ttu-id="3b73d-126">Anta att du vill styra vilka underdomäner som Office 365-grupper skapas i.</span><span class="sxs-lookup"><span data-stu-id="3b73d-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="3b73d-127">Du vill ha:</span><span class="sxs-lookup"><span data-stu-id="3b73d-127">You want:</span></span>
  
- <span data-ttu-id="3b73d-128">Grupper som skapats av studenter (användare som har **institutionen** inställd **på Studenter)** i domänen students.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="3b73d-129">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="3b73d-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="3b73d-130">Grupper som skapats av fakultetsmedlemmar (användare som har **institutionen** inställd **på fakultet eller e-postadress innehåller faculty.contoso.com)**) i domänen faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="3b73d-131">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="3b73d-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="3b73d-132">Alla andra användare i domänen groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b73d-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="3b73d-133">Använd det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="3b73d-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="3b73d-134">Ändra principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="3b73d-134">Change email address policies</span></span>

<span data-ttu-id="3b73d-135">Använd cmdleten Set-EmailAddressPolicy för att ändra mallar för prioritet eller e-postadress för en befintlig princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="3b73d-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="3b73d-136">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="3b73d-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="3b73d-137">Ta bort principer för e-postadresser</span><span class="sxs-lookup"><span data-stu-id="3b73d-137">Delete email address policies</span></span>

<span data-ttu-id="3b73d-138">Använd cmdleten Remove-EmailAddressPolicy om du vill ta bort en princip för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="3b73d-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="3b73d-139">Om en princip för e-postadresser ändras påverkar det inte de grupper som redan har etablerats.</span><span class="sxs-lookup"><span data-stu-id="3b73d-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="3b73d-140">Hybridkrav</span><span class="sxs-lookup"><span data-stu-id="3b73d-140">Hybrid requirements</span></span>

<span data-ttu-id="3b73d-141">Om din organisation är konfigurerad i ett hybridscenario läser du [Konfigurera Office 365-grupper med lokal Exchange-hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) för att se till att organisationen uppfyller kraven för att skapa Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="3b73d-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="3b73d-142">Ytterligare information om hur du använder e-postadressprincipgrupper:</span><span class="sxs-lookup"><span data-stu-id="3b73d-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="3b73d-143">Det finns några fler saker att veta:</span><span class="sxs-lookup"><span data-stu-id="3b73d-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="3b73d-144">Hur snabbt grupper skapas beror på antalet EAPs som konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="3b73d-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="3b73d-145">Administratörer och användare kan också ändra domäner när de skapar grupper.</span><span class="sxs-lookup"><span data-stu-id="3b73d-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="3b73d-p110">Grupper av användare bestäms med standardfrågorna (Användaregenskaper) som redan finns tillgängliga. Information om filtrerbara egenskaper som stöds finns i [Filtrerbara egenskaper för parametern -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918).</span><span class="sxs-lookup"><span data-stu-id="3b73d-p110">Group of users is determined using the standard queries (User properties) that are already available. Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="3b73d-148">Om du inte konfigurerar några principer för e-postadresser för grupper väljs den godkända standarddomänen när en grupp skapas.</span><span class="sxs-lookup"><span data-stu-id="3b73d-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="3b73d-149">Om du tar bort en godkänd domän bör du uppdatera principerna för e-postadresser först - annars påverkas gruppetableringen.</span><span class="sxs-lookup"><span data-stu-id="3b73d-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="3b73d-150">Högst 100 principer för e-postadresser kan konfigureras för en organisation.</span><span class="sxs-lookup"><span data-stu-id="3b73d-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="3b73d-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="3b73d-151">Related articles</span></span>

[<span data-ttu-id="3b73d-152">Skapa en Office 365-grupp i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="3b73d-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
