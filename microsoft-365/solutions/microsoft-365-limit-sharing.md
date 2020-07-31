---
title: Begränsa delning i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: Lär dig mer om olika alternativ för att begränsa eller inaktivera delning i Microsoft 365.
ms.openlocfilehash: 69a71d84f32316278353f8de392202f1a92dc22d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528188"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="2dea6-103">Begränsa delning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dea6-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="2dea6-104">Även om du inte kan inaktivera intern delning helt, eller ta bort knappen Dela från webbplatser, finns det flera olika sätt som du kan använda för att begränsa delning i Microsoft 365 för att uppfylla organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="2dea6-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="2dea6-105">Olika metoder för att dela filer visas i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="2dea6-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="2dea6-106">Klicka på länken i kolumnen **Delningsmetod** om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="2dea6-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="2dea6-107">Delningsmetod</span><span class="sxs-lookup"><span data-stu-id="2dea6-107">Sharing method</span></span>|<span data-ttu-id="2dea6-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2dea6-108">Description</span></span>|<span data-ttu-id="2dea6-109">Begränsningsalternativ</span><span class="sxs-lookup"><span data-stu-id="2dea6-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="2dea6-110">Microsoft 365-grupp eller team</span><span class="sxs-lookup"><span data-stu-id="2dea6-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="2dea6-111">Personer som beviljats åtkomst till ett team i Microsoft Teams eller en grupp i Microsoft 365 har redigeringsbehörighet för filer på den associerade SharePoint-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="2dea6-112">Om gruppen eller teamet är privat skickas delningsinbjudningar för att gå med i gruppen till ägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="2dea6-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="2dea6-113">Administratörer kan inaktivera gäståtkomst för att förhindra att personer utanför organisationen får åtkomst.</span><span class="sxs-lookup"><span data-stu-id="2dea6-113">Admins can disable guest access to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="2dea6-114">SharePoint-webbplats</span><span class="sxs-lookup"><span data-stu-id="2dea6-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="2dea6-115">Personer kan beviljas åtkomst som ägare, medlem eller besökare till en SharePoint-webbplats, och får samma åtkomstnivå till filer på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="2dea6-116">Webbplatsbehörigheter kan begränsas så att bara webbplatsägare kan dela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-116">Site permissions can be restricted so that only site owners can share the site.</span></span>|
|[<span data-ttu-id="2dea6-117">Dela med vissa personer</span><span class="sxs-lookup"><span data-stu-id="2dea6-117">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="2dea6-118">Webbplatsmedlemmar och personer med redigeringsbehörighet kan ge direkt behörighet till filer och mappar eller dela dem med hjälp av länkarna *Vissa personer*.</span><span class="sxs-lookup"><span data-stu-id="2dea6-118">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="2dea6-119">Webbplatsbehörigheter kan begränsas så att bara webbplatsägare kan dela filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="2dea6-119">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="2dea6-120">I det här fallet skickas direkt åtkomst och länkdelning för *Vissa personer* från webbplatsmedlemmar till webbplatsägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="2dea6-120">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="2dea6-121">Gästdelning i SharePoint</span><span class="sxs-lookup"><span data-stu-id="2dea6-121">SharePoint guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="2dea6-122">SharePoint-webbplatsägare och -medlemmar kan dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-122">SharePoint site owners and members can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="2dea6-123">Gästdelning kan inaktiveras för hela organisationen eller för enskilda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2dea6-123">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|[<span data-ttu-id="2dea6-124">Delningslänkarna *Personer i din organisation*</span><span class="sxs-lookup"><span data-stu-id="2dea6-124">*People in your organization* sharing links</span></span>](#people-in-your-organization-sharing-links)|<span data-ttu-id="2dea6-125">SharePoint-webbplatsägare och -medlemmar kan dela filer genom att använda länkarna *Personer i din organisation* som fungerar för alla inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-125">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="2dea6-126">Länkarna *Personer i din organisation* kan inaktiveras på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="2dea6-126">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="2dea6-127">E-post</span><span class="sxs-lookup"><span data-stu-id="2dea6-127">Email</span></span>](#email)|<span data-ttu-id="2dea6-128">Personer som har åtkomst till en fil kan skicka den till andra via e-post.</span><span class="sxs-lookup"><span data-stu-id="2dea6-128">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="2dea6-129">Administratörer kan kryptera filer med hjälp av känslighetsetiketter för att förhindra att de delas med obehöriga personer.</span><span class="sxs-lookup"><span data-stu-id="2dea6-129">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="2dea6-130">Nedladdning eller filkopia</span><span class="sxs-lookup"><span data-stu-id="2dea6-130">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="2dea6-131">Personer som har åtkomst till en fil kan ladda ned eller kopiera och dela den med andra som inte omfattas av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dea6-131">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="2dea6-132">Administratörer kan kryptera filer med hjälp av känslighetsetiketter för att förhindra att de delas med obehöriga personer.</span><span class="sxs-lookup"><span data-stu-id="2dea6-132">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="2dea6-133">Du kan använda de administratörskontroller som beskrivs i den här artikeln för att begränsa delning i organisationen, men vi rekommenderar att du använder de funktioner för säkerhet och efterlevnad som finns i Microsoft 365 för att skapa en säker delningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="2dea6-133">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="2dea6-134">Mer information finns i [Filsamarbete i SharePoint med Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) och [Teams för starkt reglerade data](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario).</span><span class="sxs-lookup"><span data-stu-id="2dea6-134">See [File collaboration in SharePoint with Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) and [Teams for highly regulated data](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario) for information.</span></span>

<span data-ttu-id="2dea6-135">Om du vill förstå hur delning används i organisationen [kör du en rapport om fil- och mappdelning](https://docs.microsoft.com/sharepoint/sharing-reports).</span><span class="sxs-lookup"><span data-stu-id="2dea6-135">To understand how sharing is being used in your organization, [run a report on file and folder sharing](https://docs.microsoft.com/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="2dea6-136">Microsoft 365-grupp eller team</span><span class="sxs-lookup"><span data-stu-id="2dea6-136">Microsoft 365 group or team</span></span>

<span data-ttu-id="2dea6-137">Om du vill begränsa delning i en Microsoft 365-grupp eller ett Microsoft Teams-team är det viktigt att du gör gruppen eller teamet privat.</span><span class="sxs-lookup"><span data-stu-id="2dea6-137">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="2dea6-138">Personer i din organisation kan gå med i en offentlig grupp eller ett team när som helst.</span><span class="sxs-lookup"><span data-stu-id="2dea6-138">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="2dea6-139">Om inte gruppen eller teamet är privat finns det inget sätt att begränsa delningen av gruppen eller dess filer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-139">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="2dea6-140">Gästdelning</span><span class="sxs-lookup"><span data-stu-id="2dea6-140">Guest sharing</span></span>

<span data-ttu-id="2dea6-141">Om du vill förhindra gäståtkomst i Teams kan du inaktivera gästdelning i administrationscentret för Teams.</span><span class="sxs-lookup"><span data-stu-id="2dea6-141">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="2dea6-142">Inaktivera gästdelning för Teams</span><span class="sxs-lookup"><span data-stu-id="2dea6-142">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="2dea6-143">I administrationscentret för Teams expanderar du **Organisationsomfattande inställningar** och klickar sedan på **Gäståtkomst**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-143">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="2dea6-144">Inaktivera **Tillåt gäståtkomst i Teams**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-144">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="2dea6-145">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-145">Click **Save**.</span></span>

<span data-ttu-id="2dea6-146">Om du vill förhindra gäståtkomst i Microsoft 365-grupper kan du inaktivera inställningarna för gäståtkomst för grupper i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2dea6-146">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2dea6-147">Inaktivera gästdelning i Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="2dea6-147">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="2dea6-148">I administrationscentret för Microsoft 365 klickar du på **Inställningar** och klickar sedan på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-148">In the Microsoft 365 admin center, click **Settings**, and then click **Settings**.</span></span>
2. <span data-ttu-id="2dea6-149">På fliken **Tjänster** klickar du på **Microsoft 365-grupper**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-149">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="2dea6-150">Avmarkera kryssrutorna **Låt gruppmedlemmar utanför organisationen få åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-150">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="2dea6-151">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-151">Click **Save changes**.</span></span>

    ![Skärmbild av delningsinställningarna för Microsoft 365-grupper i administrationscentret för Microsoft 365](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="2dea6-153">Om du vill förhindra gästdelning för en viss grupp eller ett team kan du göra det med Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dea6-153">If you want to prevent guest sharing for a particular group or team, you can do so by using Microsoft PowerShell.</span></span> <span data-ttu-id="2dea6-154">Mer information finns i [Blockera gästanvändare från en viss grupp](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group).</span><span class="sxs-lookup"><span data-stu-id="2dea6-154">See [Block guest users from a specific group](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group) for details.</span></span>

<span data-ttu-id="2dea6-155">Du kan begränsa gästdelning till användare från vissa domäner genom att tillåta eller blockera domäner i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2dea6-155">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="2dea6-156">Detta påverkar även gästdelning i SharePoint om du har aktiverat [SharePoint- och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span><span class="sxs-lookup"><span data-stu-id="2dea6-156">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="2dea6-157">Tillåta delningsinbjudningar endast från angivna domäner</span><span class="sxs-lookup"><span data-stu-id="2dea6-157">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="2dea6-158">Gå till sidan Översikt i Azure Active Directory och klicka på **Organisationsrelationer**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-158">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="2dea6-159">Klicka på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-159">Click **Settings**.</span></span>
3. <span data-ttu-id="2dea6-160">Under **Samarbetsbegränsningar** väljer du **Neka inbjudningar till de angivna domänerna** eller **Tillåt bara inbjudningar till de angivna domänerna**. Skriv sedan de domäner du vill använda.</span><span class="sxs-lookup"><span data-stu-id="2dea6-160">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="2dea6-161">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-161">Click **Save**.</span></span>

    ![Skärmbild av inställningar för samarbetsbegränsningar i Azure Active Directory](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="2dea6-163">SharePoint-webbplats</span><span class="sxs-lookup"><span data-stu-id="2dea6-163">SharePoint site</span></span>

<span data-ttu-id="2dea6-164">Du kan begränsa SharePoint-webbplatsdelning till enbart webbplatsägare.</span><span class="sxs-lookup"><span data-stu-id="2dea6-164">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="2dea6-165">Det förhindrar att webbplatsmedlemmar delar webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-165">This prevents site members from sharing the site.</span></span> <span data-ttu-id="2dea6-166">Kom ihåg att om webbplatsen är ansluten till en Microsoft 365-grupp kan gruppmedlemmar bjuda in andra till gruppen och dessa användare får åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-166">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="2dea6-167">Begränsa webbplatsdelning till ägare</span><span class="sxs-lookup"><span data-stu-id="2dea6-167">To limit site sharing to owners</span></span>
1. <span data-ttu-id="2dea6-168">Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-168">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2dea6-169">Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-169">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2dea6-170">Välj **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-170">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="2dea6-171">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-171">Click **Save**.</span></span>

    ![Skärmbild av inställningar för delningsbehörigheter på en SharePoint-webbplats](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="2dea6-173">Du kan förhindra användare som inte är medlemmar i webbplatsen från att begära åtkomst genom att inaktivera åtkomstbegäranden.</span><span class="sxs-lookup"><span data-stu-id="2dea6-173">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="2dea6-174">Inaktivera åtkomstbegäranden</span><span class="sxs-lookup"><span data-stu-id="2dea6-174">To turn off access requests</span></span>
1. <span data-ttu-id="2dea6-175">Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-175">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2dea6-176">Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-176">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2dea6-177">Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-177">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2dea6-178">Du kan begränsa delning av webbplatser till vissa domäner genom att tillåta eller blockera domäner för den webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-178">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="2dea6-179">Begränsa webbplatsdelning per domän</span><span class="sxs-lookup"><span data-stu-id="2dea6-179">To limit site sharing by domain</span></span>
1. <span data-ttu-id="2dea6-180">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-180">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="2dea6-181">Klicka på den webbplats du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="2dea6-181">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="2dea6-182">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-182">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="2dea6-183">Under **Avancerade inställningar för extern delning** väljer du **Begränsa delning per domän**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-183">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="2dea6-184">Lägg till de domäner du vill tillåta eller blockera och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-184">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="2dea6-185">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-185">Click **Save**.</span></span>

    ![Skärmbild av inställning för tillåtna domäner på webbplatsnivå](../media/limit-site-sharing-by-domain.png)

## <a name="sharing-with-specific-people"></a><span data-ttu-id="2dea6-187">Dela med vissa personer</span><span class="sxs-lookup"><span data-stu-id="2dea6-187">Sharing with specific people</span></span>

<span data-ttu-id="2dea6-188">Om du vill begränsa delningen av en webbplats eller dess innehåll, kan du konfigurera webbplatsen så att bara webbplatsägare kan dela filer, mappar och webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2dea6-188">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="2dea6-189">När det här är konfigurerat skickas webbplatsmedlemmars försök att dela filer eller mappar med hjälp av länkarna *Vissa personer* till webbplatsägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="2dea6-189">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="2dea6-190">Begränsa delning av webbplatser, filer och mappar till ägare</span><span class="sxs-lookup"><span data-stu-id="2dea6-190">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="2dea6-191">Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-191">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="2dea6-192">Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-192">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="2dea6-193">Välj **Endast webbplatsägare kan dela filer, mappar och webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-193">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="2dea6-194">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-194">Click **Save**.</span></span>

    ![Skärmbild av inställningar för delningsbehörigheter på en SharePoint-webbplats](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="2dea6-196">Gästdelning i SharePoint</span><span class="sxs-lookup"><span data-stu-id="2dea6-196">SharePoint guest sharing</span></span>

<span data-ttu-id="2dea6-197">Om du vill förhindra att SharePoint- eller OneDrive-filer och -mappar delas med personer utanför organisationen, kan du inaktivera gästdelning för hela organisationen eller för en enskild webbplats.</span><span class="sxs-lookup"><span data-stu-id="2dea6-197">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="2dea6-198">Inaktivera gästdelning i SharePoint för organisationen</span><span class="sxs-lookup"><span data-stu-id="2dea6-198">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="2dea6-199">I administrationscentret för SharePoint, under **Principer**, klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-199">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="2dea6-200">Under **Extern delning** drar du reglaget för SharePoint nedåt till **Endast personer i din organisation**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-200">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="2dea6-201">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-201">Click **Save**.</span></span>

    ![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="2dea6-203">Inaktivera gästdelning för en webbplats</span><span class="sxs-lookup"><span data-stu-id="2dea6-203">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="2dea6-204">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-204">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="2dea6-205">Klicka på den webbplats du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="2dea6-205">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="2dea6-206">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-206">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="2dea6-207">Under **Extern delning** väljer du **Endast personer i din organisation** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-207">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![Skärmbild av delningsinställningar för SharePoint på webbplatsnivå](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="2dea6-209">Om du vill tillåta delning med personer utanför organisationen, men du vill vara säker på att alla autentiseras, kan du inaktivera länkarna *Alla* (anonym delning) för hela organisationen eller för en enskild webbplats.</span><span class="sxs-lookup"><span data-stu-id="2dea6-209">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="2dea6-210">Inaktivera länkarna *Alla* på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="2dea6-210">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="2dea6-211">I administrationscentret för SharePoint, under **Principer**, klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-211">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="2dea6-212">Under **Extern delning** drar du reglaget för SharePoint nedåt till **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-212">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="2dea6-213">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-213">Click **Save**.</span></span>

    ![Skärmbild av delningsinställningar för SharePoint på webbplatsnivå](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="2dea6-215">Inaktivera länkarna *Alla* för en webbplats</span><span class="sxs-lookup"><span data-stu-id="2dea6-215">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="2dea6-216">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-216">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="2dea6-217">Klicka på den webbplats du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="2dea6-217">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="2dea6-218">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-218">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="2dea6-219">Under **Extern delning** väljer du **Nya och befintliga gäster** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2dea6-219">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![Skärmbild av delningsinställningar för SharePoint på webbplatsnivå](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="2dea6-221">Delningslänkarna *Personer i din organisation*</span><span class="sxs-lookup"><span data-stu-id="2dea6-221">*People in your organization* sharing links</span></span>

<span data-ttu-id="2dea6-222">Som standard kan medlemmar på en webbplats dela filer och mappar med andra personer i din organisation genom att använda länken *Personer i din organisation*.</span><span class="sxs-lookup"><span data-stu-id="2dea6-222">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="2dea6-223">Du kan inaktivera länkarna *Personer i din organisation* genom att använda PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2dea6-223">You can disable *People in your organization* links by using PowerShell:</span></span>

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

<span data-ttu-id="2dea6-224">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2dea6-224">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="email"></a><span data-ttu-id="2dea6-225">E-post</span><span class="sxs-lookup"><span data-stu-id="2dea6-225">Email</span></span>

<span data-ttu-id="2dea6-226">Du kan förhindra oönskad delning av e-postmeddelanden genom att använda kryptering.</span><span class="sxs-lookup"><span data-stu-id="2dea6-226">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="2dea6-227">Detta förhindrar att e-postmeddelanden vidarebefordras eller på annat sätt delas med obehöriga användare.</span><span class="sxs-lookup"><span data-stu-id="2dea6-227">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="2dea6-228">Du kan aktivera e-postkryptering genom att använda känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2dea6-228">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="2dea6-229">Mer information finns i [Begränsa åtkomst till innehåll med hjälp av kryptering i känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="2dea6-229">See [Restrict access to content by using encryption in sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="2dea6-230">Nedladdning eller filkopia</span><span class="sxs-lookup"><span data-stu-id="2dea6-230">Download or file copy</span></span>

<span data-ttu-id="2dea6-231">Användare som har åtkomst till filer och mappar i Microsoft 365 kan ladda ned filer och kopiera dem till externa medier.</span><span class="sxs-lookup"><span data-stu-id="2dea6-231">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="2dea6-232">Om du vill minska risken för oönskad fildelning kan du kryptera innehållet med hjälp av känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="2dea6-232">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dea6-233">Se även</span><span class="sxs-lookup"><span data-stu-id="2dea6-233">See also</span></span>

[<span data-ttu-id="2dea6-234">Inställningar för gästdelning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2dea6-234">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)
