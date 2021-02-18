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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Utforma isolerade SharePoint Online-gruppwebbplatser, inklusive att fastställa behörighetsnivåer, tilldela behörigheter till användare med åtkomstgrupper och kapslade Azure AD-grupper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288341"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="00041-103">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="00041-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="00041-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="00041-104">**Applies to**</span></span>
- [<span data-ttu-id="00041-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="00041-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="00041-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00041-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


 <span data-ttu-id="00041-107">**Sammanfattning:** Stega igenom designprocessen för isolerade SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="00041-107">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="00041-108">Den här artikeln tar dig genom de viktigaste designbesluten du måste fatta innan du skapar en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="00041-108">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="00041-109">Fas 1: Ta reda på dina SharePoint-grupper och behörighetsnivåer</span><span class="sxs-lookup"><span data-stu-id="00041-109">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="00041-110">Alla SharePoint Online-gruppwebbplatser skapas som standard med följande SharePoint-grupper:</span><span class="sxs-lookup"><span data-stu-id="00041-110">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="00041-111">\<site name> Medlemmar</span><span class="sxs-lookup"><span data-stu-id="00041-111">\<site name> Members</span></span>

- <span data-ttu-id="00041-112">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="00041-112">\<site name> Visitors</span></span>

- <span data-ttu-id="00041-113">\<site name> Ägare</span><span class="sxs-lookup"><span data-stu-id="00041-113">\<site name> Owners</span></span>

<span data-ttu-id="00041-114">De här grupperna är separata från Microsoft 365- och Azure Active Directory-grupper (AD) och utgör grunden för tilldelning av behörigheter för webbplatsens resurser.</span><span class="sxs-lookup"><span data-stu-id="00041-114">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="00041-115">Den uppsättning specifika behörigheter som bestämmer vad en medlem i en SharePoint-grupp kan göra på en webbplats är en behörighetsnivå.</span><span class="sxs-lookup"><span data-stu-id="00041-115">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level.</span></span> <span data-ttu-id="00041-116">Det finns tre behörighetsnivåer som standard för en SharePoint Online-gruppwebbplats: Redigera, Läsa och Fullständig behörighet.</span><span class="sxs-lookup"><span data-stu-id="00041-116">There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control.</span></span> <span data-ttu-id="00041-117">I följande tabell visas standardkorrelationen för SharePoint-grupper och tilldelade behörighetsnivåer:</span><span class="sxs-lookup"><span data-stu-id="00041-117">The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="00041-118">SharePoint-grupp</span><span class="sxs-lookup"><span data-stu-id="00041-118">SharePoint group</span></span>|<span data-ttu-id="00041-119">Behörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="00041-119">Permission level</span></span>|
|---|---|
|<span data-ttu-id="00041-120">\<site name> Medlemmar</span><span class="sxs-lookup"><span data-stu-id="00041-120">\<site name> Members</span></span>|<span data-ttu-id="00041-121">Redigera</span><span class="sxs-lookup"><span data-stu-id="00041-121">Edit</span></span>|
|<span data-ttu-id="00041-122">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="00041-122">\<site name> Visitors</span></span>|<span data-ttu-id="00041-123">Läsa</span><span class="sxs-lookup"><span data-stu-id="00041-123">Read</span></span>|
|<span data-ttu-id="00041-124">\<site name> Ägare</span><span class="sxs-lookup"><span data-stu-id="00041-124">\<site name> Owners</span></span>|<span data-ttu-id="00041-125">Fullständig kontroll</span><span class="sxs-lookup"><span data-stu-id="00041-125">Full control</span></span>|
|

 <span data-ttu-id="00041-126">**Metod bäst:** Du kan skapa ytterligare SharePoint-grupper och behörighetsnivåer.</span><span class="sxs-lookup"><span data-stu-id="00041-126">**Best practice:** You can create additional SharePoint groups and permission levels.</span></span> <span data-ttu-id="00041-127">Vi rekommenderar dock att du använder standardgrupperna och behörighetsnivåerna för SharePoint Online-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="00041-127">However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="00041-128">Här är standardgrupperna och behörighetsnivåerna i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="00041-128">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint-standardgrupper och behörighetsnivåer för en SharePoint Online-webbplats.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="00041-130">Steg 2: Tilldela behörigheter till användare med åtkomstgrupper</span><span class="sxs-lookup"><span data-stu-id="00041-130">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="00041-131">Du kan tilldela behörigheter till användare genom att lägga till deras användarkonto, eller en Microsoft 365- eller Azure AD-grupp där användarkontot är medlem, till SharePoint-grupperna.</span><span class="sxs-lookup"><span data-stu-id="00041-131">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="00041-132">När användarkontona har lagts till tilldelas användarkontona, antingen direkt eller indirekt via medlemskap i en Microsoft 365- eller Azure AD-grupp, den behörighetsnivå som är kopplad till SharePoint-gruppen.</span><span class="sxs-lookup"><span data-stu-id="00041-132">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="00041-133">Använda SharePoint-standardgrupper som exempel:</span><span class="sxs-lookup"><span data-stu-id="00041-133">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="00041-134">Medlemmar i **\<site name> SharePoint-gruppen** Medlemmar, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån** Redigera</span><span class="sxs-lookup"><span data-stu-id="00041-134">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="00041-135">Medlemmar i **\<site name> SharePoint-gruppen** Besökare, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån** Läsa</span><span class="sxs-lookup"><span data-stu-id="00041-135">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="00041-136">Medlemmar i **\<site name> SharePoint-gruppen** Ägare, som kan innehålla både användarkonton och grupper, tilldelas **behörighetsnivån Fullständig** behörighet</span><span class="sxs-lookup"><span data-stu-id="00041-136">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="00041-137">**Metod bäst:** Även om du kan hantera behörigheter via enskilda användarkonton rekommenderar vi att du använder en enda Azure AD-grupp, en så kallad åtkomstgrupp, i stället.</span><span class="sxs-lookup"><span data-stu-id="00041-137">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead.</span></span> <span data-ttu-id="00041-138">Det gör det enklare att hantera behörigheter genom medlemskap i åtkomstgruppen, i stället för att hantera listan med användarkonton för varje SharePoint-grupp.</span><span class="sxs-lookup"><span data-stu-id="00041-138">This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="00041-139">Azure AD-grupper för Microsoft 365 skiljer sig åt mellan Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="00041-139">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="00041-140">Azure AD-grupper visas i administrationscentret för  Microsoft 365 med säkerhetstypen inställd på **säkerhet** och har ingen e-postadress.</span><span class="sxs-lookup"><span data-stu-id="00041-140">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="00041-141">Azure AD-grupper kan hanteras i:</span><span class="sxs-lookup"><span data-stu-id="00041-141">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="00041-142">Active Directory DS (AD DS)</span><span class="sxs-lookup"><span data-stu-id="00041-142">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="00041-143">Det här är grupper som har skapats i din lokala AD DS infrastruktur och synkroniserats med din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="00041-143">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="00041-144">I administrationscentret för Microsoft 365 har de här grupperna **statusen Synkroniserad** **med Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="00041-144">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="00041-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="00041-145">Office 365</span></span>

    <span data-ttu-id="00041-146">Det här är grupper som har skapats med hjälp av antingen Administrationscenter för Microsoft 365, Azure-portalen eller Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00041-146">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="00041-147">I administrationscentret för Microsoft 365 har de här grupperna **molnstatus.** </span><span class="sxs-lookup"><span data-stu-id="00041-147">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="00041-148">**Metod bäst:** Om du använder AD DS och synkroniserar med Microsoft 365-prenumerationen utför du användar- och grupphanteringen med AD DS.</span><span class="sxs-lookup"><span data-stu-id="00041-148">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="00041-149">För isolerade SharePoint Online-gruppwebbplatser ser den rekommenderade gruppstrukturen ut så här:</span><span class="sxs-lookup"><span data-stu-id="00041-149">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="00041-150">SharePoint-grupp</span><span class="sxs-lookup"><span data-stu-id="00041-150">SharePoint group</span></span>|<span data-ttu-id="00041-151">Azure AD-baserad åtkomstgrupp</span><span class="sxs-lookup"><span data-stu-id="00041-151">Azure AD-based access group</span></span>|<span data-ttu-id="00041-152">Behörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="00041-152">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="00041-153">\<site name> Medlemmar</span><span class="sxs-lookup"><span data-stu-id="00041-153">\<site name> Members</span></span>|<span data-ttu-id="00041-154">\<site name> Medlemmar</span><span class="sxs-lookup"><span data-stu-id="00041-154">\<site name> Members</span></span>|<span data-ttu-id="00041-155">Redigera</span><span class="sxs-lookup"><span data-stu-id="00041-155">Edit</span></span>|
|<span data-ttu-id="00041-156">\<site name> Besökare</span><span class="sxs-lookup"><span data-stu-id="00041-156">\<site name> Visitors</span></span>|<span data-ttu-id="00041-157">\<site name> Läsare</span><span class="sxs-lookup"><span data-stu-id="00041-157">\<site name> Viewers</span></span>|<span data-ttu-id="00041-158">Läsa</span><span class="sxs-lookup"><span data-stu-id="00041-158">Read</span></span>|
|<span data-ttu-id="00041-159">\<site name> Ägare</span><span class="sxs-lookup"><span data-stu-id="00041-159">\<site name> Owners</span></span>|<span data-ttu-id="00041-160">\<site name> Administratörer</span><span class="sxs-lookup"><span data-stu-id="00041-160">\<site name> Admins</span></span>|<span data-ttu-id="00041-161">Fullständig kontroll</span><span class="sxs-lookup"><span data-stu-id="00041-161">Full control</span></span>|
|

 <span data-ttu-id="00041-162">**Metod bäst:** Även om du kan använda antingen Microsoft 365 eller Azure AD-grupper som medlemmar i SharePoint-grupper rekommenderar vi att du använder Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="00041-162">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="00041-163">Azure AD-grupper som hanteras antingen via AD DS eller Microsoft 365 ger dig mer flexibilitet att använda kapslade grupper för att tilldela behörigheter.</span><span class="sxs-lookup"><span data-stu-id="00041-163">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="00041-164">Här är de SharePoint-standardgrupper som konfigurerats för att använda Azure AD-baserade åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="00041-164">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Använda åtkomstgrupper som medlemmar i standardwebbplatsgrupper i SharePoint Online.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="00041-166">När du skapar de tre åtkomstgrupperna bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="00041-166">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="00041-167">Det bör bara finnas ett **\<site name>** fåtal medlemmar i åtkomstgruppen Administratörer, vilket motsvarar ett litet antal SharePoint Online-administratörer som hanterar gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="00041-167">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="00041-168">De flesta av webbplatsmedlemmarna finns i **\<site name> åtkomstgrupperna Medlemmar** **eller \<site name>** Läsare.</span><span class="sxs-lookup"><span data-stu-id="00041-168">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="00041-169">Eftersom medlemmar i gruppen **\<site name> Medlemmar har** möjlighet att ta bort eller ändra resurser på webbplatsen ska du noga överväga medlemskapet.</span><span class="sxs-lookup"><span data-stu-id="00041-169">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="00041-170">Om du är osäker kan du lägga till webbplatsmedlemmen i **\<site name> åtkomstgruppen** Läsare.</span><span class="sxs-lookup"><span data-stu-id="00041-170">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="00041-171">Här är ett exempel på SharePoint-grupperna och åtkomstgrupperna för en isolerad webbplats med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="00041-171">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![Ett exempel på hur du använder åtkomstgrupper för en SharePoint Online-webbplats med namnet ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="00041-173">Fas 3: Använd kapslade Azure AD-grupper</span><span class="sxs-lookup"><span data-stu-id="00041-173">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="00041-174">För ett projekt som begränsas till ett litet antal personer kommer en enda nivå av Azure AD-baserade åtkomstgrupper som lagts till i SharePoint-grupperna på webbplatsen att passa de flesta scenarier.</span><span class="sxs-lookup"><span data-stu-id="00041-174">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios.</span></span> <span data-ttu-id="00041-175">Men om du har ett stort antal personer och dessa personer redan är medlemmar i etablerade Azure AD-grupper kan du enklare tilldela SharePoint-behörigheter genom att använda kapslade grupper eller grupper som innehåller andra grupper som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="00041-175">However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="00041-176">Du vill till exempel skapa en isolerad SharePoint Online-gruppwebbplats för samarbete mellan chefer för sälj-, marknadsförings-, teknik-, juridik- och supportavdelningar och de avdelningarna har redan egna grupper med användarkontomedlemskap i ledningen.</span><span class="sxs-lookup"><span data-stu-id="00041-176">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership.</span></span> <span data-ttu-id="00041-177">I stället för att skapa en ny grupp för de nya webbplatsmedlemmarna och placera alla enskilda chefers användarkonton i den, kan du placera befintliga ledningsgrupper för varje avdelning i den nya gruppen.</span><span class="sxs-lookup"><span data-stu-id="00041-177">Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="00041-178">Om du delar en Microsoft 365-prenumeration mellan flera organisationer kan det bli svårt att hantera en enstaka nivå av gruppmedlemskap för en isolerad webbplats på grund av det stora antalet användarkonton.</span><span class="sxs-lookup"><span data-stu-id="00041-178">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="00041-179">I det här fallet kan du använda kapslade Azure AD-grupper för varje organisation som innehåller grupperna i deras organisationer för att hantera behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="00041-179">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="00041-180">Så här använder du kapslade Azure AD-grupper:</span><span class="sxs-lookup"><span data-stu-id="00041-180">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="00041-181">Identifiera eller skapa Azure AD-grupperna som kommer att innehålla användarkonton och lägg till lämpliga användarkonton som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="00041-181">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="00041-182">Skapa den Azure AD-baserade åtkomstgrupp för behållaren som innehåller de andra Azure AD-grupperna och lägg till de grupperna som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="00041-182">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="00041-183">Identifiera SharePoint-gruppen och motsvarande behörighetsnivå för lämplig åtkomstnivå för behållarens åtkomstgrupp.</span><span class="sxs-lookup"><span data-stu-id="00041-183">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="00041-184">Du kan inte använda kapslade Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="00041-184">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="00041-185">Här är ett exempel på kapslade Azure AD-grupper för projectX-medlemsåtkomstgruppen.</span><span class="sxs-lookup"><span data-stu-id="00041-185">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![Ett exempel på hur du använder kapslade åtkomstgrupper för medlemmars åtkomstgrupp för ProjectX-webbplatsen.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="00041-187">Eftersom alla användarkonton i grupperna Forskning, Teknik och Project är avsedda att vara webbplatsmedlemmar är det enklare att lägga till deras Azure AD-grupper i åtkomstgruppen ProjectX-medlemmar.</span><span class="sxs-lookup"><span data-stu-id="00041-187">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="00041-188">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="00041-188">Next step</span></span>

<span data-ttu-id="00041-189">När du är redo att skapa och konfigurera en isolerad webbplats i produktionen kan du gå till [Distribuera en isolerad SharePoint Online-gruppwebbplats.](deploy-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="00041-189">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00041-190">Se även</span><span class="sxs-lookup"><span data-stu-id="00041-190">See Also</span></span>

[<span data-ttu-id="00041-191">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="00041-191">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="00041-192">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="00041-192">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="00041-193">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="00041-193">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
