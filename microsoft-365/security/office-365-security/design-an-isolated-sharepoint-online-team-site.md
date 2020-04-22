---
title: Utforma en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sammanfattning: Steg genom designprocessen för isolerade SharePoint Online-gruppwebbplatser.'
ms.openlocfilehash: 5efd5fb0501d88fda37f1530ef62e4c5110e4da2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638518"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c0b5e-103">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c0b5e-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="c0b5e-104">**Sammanfattning:** Stega igenom designprocessen för isolerade SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="c0b5e-105">Den här artikeln tar dig igenom de viktiga designbeslut du måste fatta innan du skapar en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="c0b5e-106">Fas 1: Bestäm dina SharePoint-grupper och behörighetsnivåer</span><span class="sxs-lookup"><span data-stu-id="c0b5e-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="c0b5e-107">Varje SharePoint Online-gruppwebbplats skapas som standard med följande SharePoint-grupper:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="c0b5e-108">\<webbplatsnamn> medlemmar</span><span class="sxs-lookup"><span data-stu-id="c0b5e-108">\<site name> Members</span></span>
    
- <span data-ttu-id="c0b5e-109">\<webbplatsnamn> besökare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="c0b5e-110">\<webbplatsnamn> ägare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-110">\<site name> Owners</span></span>
    
<span data-ttu-id="c0b5e-111">Dessa grupper är separata från Microsoft 365- och Azure Active Directory-grupper (AD) och ligger till grund för tilldelning av behörigheter för resurserna på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="c0b5e-112">Den uppsättning specifika behörigheter som avgör vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighetsnivå.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="c0b5e-113">Det finns tre behörighetsnivåer som standard för en SharePoint Online-gruppwebbplats: Redigera, Läsa och Fullständig kontroll.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="c0b5e-114">I följande tabell visas standardkorrelationen för SharePoint-grupper och tilldelade behörighetsnivåer:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="c0b5e-115">**SharePoint-grupp**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-115">**SharePoint group**</span></span>|<span data-ttu-id="c0b5e-116">**Behörighetsnivå**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0b5e-117">\<webbplatsnamn> medlemmar</span><span class="sxs-lookup"><span data-stu-id="c0b5e-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c0b5e-118">Redigera</span><span class="sxs-lookup"><span data-stu-id="c0b5e-118">Edit</span></span>  <br/> |
|<span data-ttu-id="c0b5e-119">\<webbplatsnamn> besökare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c0b5e-120">Läsa</span><span class="sxs-lookup"><span data-stu-id="c0b5e-120">Read</span></span>  <br/> |
|<span data-ttu-id="c0b5e-121">\<webbplatsnamn> ägare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c0b5e-122">Fullständig kontroll</span><span class="sxs-lookup"><span data-stu-id="c0b5e-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c0b5e-123">**Bästa praxis:** Du kan skapa ytterligare SharePoint-grupper och behörighetsnivåer.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="c0b5e-124">Vi rekommenderar dock att du använder standarddelningsgrupperna och behörighetsnivåerna för din isolerade SharePoint Online-webbplats.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="c0b5e-125">Här är standardgrupperna och behörighetsnivåerna för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![Standardgrupperna och behörighetsnivåerna för en SharePoint Online-webbplats.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="c0b5e-127">Fas 2: Tilldela behörigheter till användare med åtkomstgrupper</span><span class="sxs-lookup"><span data-stu-id="c0b5e-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="c0b5e-128">Du kan tilldela behörigheter till användare genom att lägga till deras användarkonto, eller en Microsoft 365- eller Azure AD-grupp som användarkontot är medlem i, till SharePoint-grupperna.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-128">You can assign permissions to users by adding their user account, or an Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="c0b5e-129">När användarkontona har lagts till tilldelas användarkontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365- eller Azure AD-grupp, behörighetsnivån som är associerad med SharePoint-gruppen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-129">Once added, the user accounts, either directly or indirectly via membership in an Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="c0b5e-130">Använda standard-SharePoint-grupper som ett exempel:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="c0b5e-131">Medlemmar i \*\* \<webbplatsnamnet> Medlemmar\*\* SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Redigera**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="c0b5e-132">Medlemmar i \*\* \<webbplatsnamnet> Visitors\*\* SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Läs**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="c0b5e-133">Medlemmar i \*\* \<webbplatsnamnet> Ägare\*\* SharePoint-grupp, som kan innehålla både användarkonton och grupper, tilldelas behörighetsnivån **Fullständig kontroll**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="c0b5e-134">**Bästa praxis:** Även om du kan hantera behörigheter via enskilda användarkonton rekommenderar vi att du använder en enda Azure AD-grupp, en så kallad åtkomstgrupp, i stället.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="c0b5e-135">Detta förenklar hanteringen av behörigheter via medlemskap i åtkomstgruppen, i stället för att hantera listan över användarkonton för varje SharePoint-grupp.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="c0b5e-136">Azure AD-grupper för Microsoft 365 skiljer sig från Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-136">Azure AD groups for Microsoft 365 are different than Microsoft 365 groups.</span></span> <span data-ttu-id="c0b5e-137">Azure AD-grupper visas i Microsoft 365-administrationscentret med deras **typ** inställd på **Säkerhet** och har ingen e-postadress.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="c0b5e-138">Azure AD-grupper kan hanteras inom:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-138">Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="c0b5e-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="c0b5e-139">Active Directory Domain Services (AD DS)</span></span>
    
    <span data-ttu-id="c0b5e-140">Det här är grupper som har skapats i din lokala AD DS-infrastruktur och synkroniserats med din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="c0b5e-141">I administrationscentret för Microsoft 365 har dessa grupper **status** **för synkroniserad med active directory**.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="c0b5e-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="c0b5e-142">Office 365</span></span>
    
    <span data-ttu-id="c0b5e-143">Det här är grupper som har skapats med hjälp av microsoft 365-administrationscentret, Azure-portalen eller Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="c0b5e-144">I administrationscentret för Microsoft 365 har dessa grupper status **för** **molnet**.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="c0b5e-145">**Bästa praxis:** Om du använder AD DS lokalt och synkroniserar med din Microsoft 365-prenumeration kan du utföra din användar- och grupphantering med AD DS.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>
  
<span data-ttu-id="c0b5e-146">För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade gruppstrukturen ut så här:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="c0b5e-147">**SharePoint-grupp**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-147">**SharePoint group**</span></span>|<span data-ttu-id="c0b5e-148">**Azure AD-baserad åtkomstgrupp**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="c0b5e-149">**Behörighetsnivå**</span><span class="sxs-lookup"><span data-stu-id="c0b5e-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0b5e-150">\<webbplatsnamn> medlemmar</span><span class="sxs-lookup"><span data-stu-id="c0b5e-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c0b5e-151">\<webbplatsnamn> medlemmar</span><span class="sxs-lookup"><span data-stu-id="c0b5e-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c0b5e-152">Redigera</span><span class="sxs-lookup"><span data-stu-id="c0b5e-152">Edit</span></span>  <br/> |
|<span data-ttu-id="c0b5e-153">\<webbplatsnamn> besökare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c0b5e-154">\<webbplatsnamn> Tittare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="c0b5e-155">Läsa</span><span class="sxs-lookup"><span data-stu-id="c0b5e-155">Read</span></span>  <br/> |
|<span data-ttu-id="c0b5e-156">\<webbplatsnamn> ägare</span><span class="sxs-lookup"><span data-stu-id="c0b5e-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c0b5e-157">\<webbplatsnamn> administratörer</span><span class="sxs-lookup"><span data-stu-id="c0b5e-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="c0b5e-158">Fullständig kontroll</span><span class="sxs-lookup"><span data-stu-id="c0b5e-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c0b5e-159">**Bästa praxis:** Även om du kan använda microsoft 365- eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="c0b5e-160">Azure AD-grupper, som hanteras antingen via AD DS eller Microsoft 365, ger dig större flexibilitet att använda kapslade grupper för att tilldela behörigheter.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="c0b5e-161">Här är standard-SharePoint-grupper som konfigurerats för att använda Azure AD-baserade åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Använda åtkomstgrupper som medlemmar i standardwebbplatsgrupper för SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="c0b5e-163">När du utformar de tre åtkomstgrupperna bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="c0b5e-164">Det bör bara finnas ett fåtal medlemmar i \*\* \<webbplatsnamnet> åtkomstgruppen administratörer,\*\* vilket motsvarar ett litet antal SharePoint Online-administratörer som hanterar gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="c0b5e-165">De flesta av dina webbplatsmedlemmar finns i \*\* \<webbplatsnamnet> medlemmar\*\* eller \*\* \<webbplatsnamn> Tittare\*\* åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="c0b5e-166">Eftersom webbplatsmedlemmar i \*\* \<webbplatsnamnet> medlemmars\*\* åtkomstgrupp har möjlighet att ta bort eller ändra resurser på webbplatsen bör du noga överväga medlemskapet.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="c0b5e-167">När du är osäker lägger du till webbplatsmedlemmen i \*\* \<webbplatsnamnet>\*\* tittaråtkomstgruppen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="c0b5e-168">Här är ett exempel på SharePoint-grupper och åtkomstgrupper för en isolerad webbplats med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Ett exempel på hur du använder åtkomstgrupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="c0b5e-170">Fas 3: Använd kapslade Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="c0b5e-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="c0b5e-171">För ett projekt som är begränsat till ett litet antal personer passar en enda nivå av Azure AD-baserade åtkomstgrupper som läggs till i SharePoint-grupperna på webbplatsen de flesta scenarier.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="c0b5e-172">Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enklare tilldela SharePoint-behörigheter med hjälp av kapslade grupper eller grupper som innehåller andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="c0b5e-173">Du vill till exempel skapa en isolerad SharePoint-onlinegruppwebbplats för samarbete mellan cheferna för försäljnings-, marknadsförings-, teknik-, juridiska och supportavdelningar och de avdelningar som redan är deras egna grupper med ett antal företagsprofiler.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="c0b5e-174">I stället för att skapa en ny grupp för de nya webbplatsmedlemmarna och placera alla enskilda verkställande användarkonton i den, placera de befintliga ledningsgrupperna för varje avdelning i den nya gruppen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="c0b5e-175">Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan det bli svårt att hantera en enda gruppmedlemskap för en isolerad webbplats för en organisation på grund av det stora antalet användarkonton.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="c0b5e-176">I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupperna inom deras organisationer för att hantera behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="c0b5e-177">Så här använder du kapslade Azure AD-grupper:</span><span class="sxs-lookup"><span data-stu-id="c0b5e-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="c0b5e-178">Identifiera eller skapa Azure AD-grupper som ska innehålla användarkonton och lägga till lämpliga användarkonton som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="c0b5e-179">Skapa behållaren Azure AD-baserad åtkomstgrupp som ska innehålla de andra Azure AD-grupperna och lägga till dessa grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="c0b5e-180">Om du vill ha rätt åtkomstnivå för behållaråtkomstgruppen identifierar du SharePoint-gruppen och motsvarande behörighetsnivå.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c0b5e-181">Du kan inte använda kapslade Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-181">You cannot use nested Microsoft 365 groups.</span></span> 
  
<span data-ttu-id="c0b5e-182">Här är ett exempel på kapslade Azure AD-grupper för projectx-medlemsåtkomstgruppen.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Ett exempel på hur du använder kapslade åtkomstgrupper för medlemsåtkomstgruppen för ProjectX-platsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="c0b5e-184">Eftersom alla användarkonton i teamen För forskning, teknik och projekt är avsedda att vara platsmedlemmar är det enklare att lägga till sina Azure AD-grupper i åtkomstgruppen För ProjectX-medlemmar.</span><span class="sxs-lookup"><span data-stu-id="c0b5e-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c0b5e-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c0b5e-185">Next step</span></span>

<span data-ttu-id="c0b5e-186">När du är redo att skapa och konfigurera en isolerad plats i produktion läser [du Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="c0b5e-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0b5e-187">Se även</span><span class="sxs-lookup"><span data-stu-id="c0b5e-187">See Also</span></span>

[<span data-ttu-id="c0b5e-188">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="c0b5e-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="c0b5e-189">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c0b5e-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="c0b5e-190">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c0b5e-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



