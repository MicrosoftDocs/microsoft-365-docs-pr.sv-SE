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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Designa isolerade SharePoint Online-gruppwebbplatser, inklusive att ange behörighets nivåer, tilldela behörigheter till användare med åtkomst grupper och kapslade Azure AD-grupper.
ms.openlocfilehash: 035952c1921443d86602eb94e3965acee86ae3e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203125"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="0f2dd-103">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="0f2dd-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="0f2dd-104">**Sammanfattning:** Stega genom design processen för isolerade SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="0f2dd-105">I den här artikeln får du hjälp med de viktiga design beslut som du måste göra innan du skapar en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="0f2dd-106">Fas 1: Bestäm dina SharePoint-grupper och behörighets nivåer</span><span class="sxs-lookup"><span data-stu-id="0f2dd-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="0f2dd-107">Varje SharePoint Online-gruppwebbplats skapas som standard med följande SharePoint-grupper:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="0f2dd-108">\<site name> Gruppen</span><span class="sxs-lookup"><span data-stu-id="0f2dd-108">\<site name> Members</span></span>

- <span data-ttu-id="0f2dd-109">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="0f2dd-109">\<site name> Visitors</span></span>

- <span data-ttu-id="0f2dd-110">\<site name> Nmöjliga</span><span class="sxs-lookup"><span data-stu-id="0f2dd-110">\<site name> Owners</span></span>

<span data-ttu-id="0f2dd-111">Dessa grupper är åtskilda från Microsoft 365-och Azure Active Directory (AD)-grupper och är grunden för hur du tilldelar behörigheter för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="0f2dd-112">Uppsättningen med specifika behörigheter som avgör vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighets nivå.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-112">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="0f2dd-113">Det finns tre behörighets nivåer som standard för en SharePoint Online-grupp webbplats: redigera, läsa och fullständig behörighet.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-113">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="0f2dd-114">I följande tabell visas standard korrelationen för SharePoint-grupper och tilldelade behörighets nivåer:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-114">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="0f2dd-115">SharePoint-grupp</span><span class="sxs-lookup"><span data-stu-id="0f2dd-115">SharePoint group</span></span>|<span data-ttu-id="0f2dd-116">Behörighets nivå</span><span class="sxs-lookup"><span data-stu-id="0f2dd-116">Permission level</span></span>|
|---|---|
|<span data-ttu-id="0f2dd-117">\<site name> Gruppen</span><span class="sxs-lookup"><span data-stu-id="0f2dd-117">\<site name> Members</span></span>|<span data-ttu-id="0f2dd-118">Redigera</span><span class="sxs-lookup"><span data-stu-id="0f2dd-118">Edit</span></span>|
|<span data-ttu-id="0f2dd-119">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="0f2dd-119">\<site name> Visitors</span></span>|<span data-ttu-id="0f2dd-120">Läsa</span><span class="sxs-lookup"><span data-stu-id="0f2dd-120">Read</span></span>|
|<span data-ttu-id="0f2dd-121">\<site name> Nmöjliga</span><span class="sxs-lookup"><span data-stu-id="0f2dd-121">\<site name> Owners</span></span>|<span data-ttu-id="0f2dd-122">Fullständig behörighet</span><span class="sxs-lookup"><span data-stu-id="0f2dd-122">Full control</span></span>|
|

 <span data-ttu-id="0f2dd-123">**Metod tips:** Du kan skapa ytterligare SharePoint-grupper och behörighets nivåer.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-123">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="0f2dd-124">Vi rekommenderar att du använder de SharePoint-standardgrupper och behörighets nivåer som är en SharePoint Online-webbplats.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-124">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="0f2dd-125">Här är de SharePoint-standardgrupper och behörighets nivåer som är standard.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-125">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint-webbplatsens standard grupper och behörighets nivåer.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="0f2dd-127">Fas 2: tilldela behörigheter till användare med Access-grupper</span><span class="sxs-lookup"><span data-stu-id="0f2dd-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="0f2dd-128">Du kan tilldela behörigheter till användare genom att lägga till deras användar konto eller en Microsoft 365-eller Azure AD-grupp som användar kontot är medlem i, till SharePoint-grupperna.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-128">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="0f2dd-129">När du har lagt till, tilldelas användar kontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365-eller Azure AD-grupp, den behörighets nivå som är associerad med SharePoint-gruppen.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-129">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="0f2dd-130">Använda SharePoint-standardgrupper som exempel:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-130">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="0f2dd-131">Medlemmar i SharePoint-gruppen \*\* \<site name> medlemmar\*\* , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **Redigera**</span><span class="sxs-lookup"><span data-stu-id="0f2dd-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="0f2dd-132">Medlemmar i SharePoint-gruppen \*\* \<site name> besökare\*\* , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **läsa**</span><span class="sxs-lookup"><span data-stu-id="0f2dd-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="0f2dd-133">Medlemmar i SharePoint-gruppen \*\* \<site name> ägare\*\* , som kan inkludera både användar konton och grupper, tilldelas behörighets nivån **full kontroll**</span><span class="sxs-lookup"><span data-stu-id="0f2dd-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="0f2dd-134">**Metod tips:** Även om du kan hantera behörigheter med enskilda användar konton rekommenderar vi att du använder en enda Azure AD-grupp, som kallas åtkomst grupp, i stället.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-134">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="0f2dd-135">Det gör det enklare att hantera behörigheter genom medlemskap i åtkomst gruppen, i stället för att hantera listan över användar konton för varje SharePoint-grupp.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-135">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="0f2dd-136">Azure AD-grupper för Microsoft 365 är olika söker igenom med Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-136">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="0f2dd-137">Azure AD-grupper visas i administrations centret för Microsoft 365 med deras **typ** inställda på **säkerhet** och ingen e-postadress.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="0f2dd-138">Azure AD-grupper kan hanteras i:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-138">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="0f2dd-139">AD DS (Active Directory Domain Services)</span><span class="sxs-lookup"><span data-stu-id="0f2dd-139">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="0f2dd-140">Det här är grupper som har skapats i din lokala AD DS-infrastruktur och synkroniserats till din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="0f2dd-141">I administrations centret för Microsoft 365 har dessa grupper **statusen** **synkroniserad med Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="0f2dd-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="0f2dd-142">Office 365</span></span>

    <span data-ttu-id="0f2dd-143">Det här är grupper som har skapats med hjälp av administrations centret för Microsoft 365, Azure Portal eller Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="0f2dd-144">I administrations centret för Microsoft 365 har dessa grupper **statusen** **moln**.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="0f2dd-145">**Metod tips:** Om du använder AD DS lokalt och synkroniserar med ditt Microsoft 365-abonnemang, kan du utföra användar-och grupp hanteringen med AD DS.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="0f2dd-146">För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade grupp strukturen ut så här:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="0f2dd-147">SharePoint-grupp</span><span class="sxs-lookup"><span data-stu-id="0f2dd-147">SharePoint group</span></span>|<span data-ttu-id="0f2dd-148">Azure AD-baserad åtkomst grupp</span><span class="sxs-lookup"><span data-stu-id="0f2dd-148">Azure AD-based access group</span></span>|<span data-ttu-id="0f2dd-149">Behörighets nivå</span><span class="sxs-lookup"><span data-stu-id="0f2dd-149">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="0f2dd-150">\<site name> Gruppen</span><span class="sxs-lookup"><span data-stu-id="0f2dd-150">\<site name> Members</span></span>|<span data-ttu-id="0f2dd-151">\<site name> Gruppen</span><span class="sxs-lookup"><span data-stu-id="0f2dd-151">\<site name> Members</span></span>|<span data-ttu-id="0f2dd-152">Redigera</span><span class="sxs-lookup"><span data-stu-id="0f2dd-152">Edit</span></span>|
|<span data-ttu-id="0f2dd-153">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="0f2dd-153">\<site name> Visitors</span></span>|<span data-ttu-id="0f2dd-154">\<site name> Läsare</span><span class="sxs-lookup"><span data-stu-id="0f2dd-154">\<site name> Viewers</span></span>|<span data-ttu-id="0f2dd-155">Läsa</span><span class="sxs-lookup"><span data-stu-id="0f2dd-155">Read</span></span>|
|<span data-ttu-id="0f2dd-156">\<site name> Nmöjliga</span><span class="sxs-lookup"><span data-stu-id="0f2dd-156">\<site name> Owners</span></span>|<span data-ttu-id="0f2dd-157">\<site name> Administratörer</span><span class="sxs-lookup"><span data-stu-id="0f2dd-157">\<site name> Admins</span></span>|<span data-ttu-id="0f2dd-158">Fullständig behörighet</span><span class="sxs-lookup"><span data-stu-id="0f2dd-158">Full control</span></span>|
|

 <span data-ttu-id="0f2dd-159">**Metod tips:** Även om du kan använda Microsoft 365-eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD Groups.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="0f2dd-160">Azure AD-grupper, som hanteras antingen via AD DS eller Microsoft 365, ger dig större flexibilitet att använda kapslade grupper för att tilldela behörigheter.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="0f2dd-161">Här är de SharePoint-standardgrupper som är konfigurerade för användning av Azure AD-baserade åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Använda åtkomst grupper som medlemmar i standard webbplats grupper för SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="0f2dd-163">Tänk på följande när du utformar de tre åtkomst grupperna:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-163">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="0f2dd-164">Det bör bara finnas några medlemmar i gruppen \*\* \<site name> Administratörer\*\* , motsvarande ett litet antal SharePoint Online-administratörer som hanterar grupp webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="0f2dd-165">De flesta av dina webbplats medlemmar är i åtkomst grupperna \*\* \<site name> medlemmar\*\* eller \*\* \<site name> läsare\*\* .</span><span class="sxs-lookup"><span data-stu-id="0f2dd-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="0f2dd-166">Eftersom webbplats medlemmar i gruppen \*\* \<site name> medlemmar\*\* har möjlighet att ta bort eller ändra resurser på webbplatsen bör du noggrant överväga dess medlemskap.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="0f2dd-167">Om du är osäker kan du lägga till webbplats medlemmen i åtkomst gruppen \*\* \<site name> visnings program\*\* .</span><span class="sxs-lookup"><span data-stu-id="0f2dd-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="0f2dd-168">Här är ett exempel på SharePoint-grupper och åtkomst grupper för en isolerad webbplats med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Ett exempel på hur du använder åtkomst grupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="0f2dd-170">Fas 3: använda kapslade Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="0f2dd-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="0f2dd-171">Ett projekt som är begränsat till ett fåtal personer är att en enda nivå av Azure AD-baserade åtkomst grupper läggs till i SharePoint-grupperna på webbplatsen för att passa de flesta scenarier.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-171">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="0f2dd-172">Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enkelt tilldela SharePoint-behörigheter genom att använda kapslade grupper eller grupper som innehåller andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-172">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="0f2dd-173">Du vill till exempel skapa en isolerad SharePoint Online-gruppwebbplats för samarbete mellan cheferna för avdelningarna försäljning, marknadsföring, teknik, juridik och support samt de avdelningar som redan har sina egna grupper med användar konto medlemskap för chefer.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-173">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="0f2dd-174">I stället för att skapa en ny grupp för de nya webbplats medlemmarna och placera alla enskilda användar konton i den, placerar du de befintliga chefs grupperna för varje avdelning i gruppen nytt.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-174">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="0f2dd-175">Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan en enda grupp medlemskap för en isolerad webbplats för en organisation bli svår att hantera på grund av det skir antalet användar konton.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="0f2dd-176">I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupperna inom deras organisationer för att hantera behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="0f2dd-177">Så här använder du kapslade Azure AD-grupper:</span><span class="sxs-lookup"><span data-stu-id="0f2dd-177">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="0f2dd-178">Identifiera eller skapa de Azure AD-grupper som ska innehålla användar konton och lägga till lämpliga användar konton som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="0f2dd-179">Skapa en behållare för Azure AD-baserad åtkomst som kommer att innehålla de andra Azure AD-grupperna och lägga till dessa grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="0f2dd-180">För lämplig åtkomst nivå för gruppen behållar åtkomst identifierar du SharePoint-gruppen och motsvarande behörighets nivå.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="0f2dd-181">Du kan inte använda kapslade Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-181">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="0f2dd-182">Här är ett exempel på kapslade Azure AD-grupper för gruppen ProjectX member Access.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Ett exempel på hur kapslade åtkomst grupper används för gruppen medlemmar för ProjectX-webbplatsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="0f2dd-184">Eftersom alla användar konton i gruppen forsknings-, ingenjörs-och projekt ledare är avsedda att vara webbplats medlemmar är det enklare att lägga till deras Azure AD-grupper i ProjectX medlemmar.</span><span class="sxs-lookup"><span data-stu-id="0f2dd-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="0f2dd-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0f2dd-185">Next step</span></span>

<span data-ttu-id="0f2dd-186">När du är redo att skapa och konfigurera en isolerad webbplats i produktion kan du läsa [distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="0f2dd-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f2dd-187">Se även</span><span class="sxs-lookup"><span data-stu-id="0f2dd-187">See Also</span></span>

[<span data-ttu-id="0f2dd-188">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="0f2dd-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="0f2dd-189">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="0f2dd-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="0f2dd-190">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="0f2dd-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
