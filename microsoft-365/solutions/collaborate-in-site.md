---
title: Samarbeta med gäster på en webbplats
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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Läs mer om konfigurationsstegen för Microsoft 365 som krävs för att konfigurera en SharePoint-webbplats för samarbete med gäster.
ms.openlocfilehash: fd3cf55b3d95a5c79b9bd4d7c55855f7d73fc0d2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904654"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="555e8-103">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="555e8-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="555e8-104">Om du behöver samarbeta med gäster i dokument, data och listor kan du använda en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="555e8-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="555e8-105">Moderna SharePoint-webbplatser är anslutna till Microsoft 365-grupper och kan hantera webbplatsmedlemskapet och tillhandahålla ytterligare samarbetsverktyg, till exempel en delad postlåda och en kalender.</span><span class="sxs-lookup"><span data-stu-id="555e8-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="555e8-106">I den här artikeln går vi igenom konfigurationsstegen för Microsoft 365 som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="555e8-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="555e8-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="555e8-107">Video demonstration</span></span>

<span data-ttu-id="555e8-108">I den här videon visas konfigurationsstegen som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="555e8-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="555e8-109">Inställningar för externt Samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="555e8-109">Azure external collaboration settings</span></span>

<span data-ttu-id="555e8-110">Delning i Microsoft 365 styrs på sin högsta nivå av inställningarna för [B2B-externt samarbete i Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="555e8-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="555e8-111">Om gästdelning är inaktiverad eller begränsad i Azure Active Directory åsidosätter den här inställningen alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="555e8-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="555e8-112">Kontrollera inställningarna för B2B externt samarbete för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="555e8-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan Inställningar för externt samarbete i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="555e8-114">Inställningar för externt samarbete</span><span class="sxs-lookup"><span data-stu-id="555e8-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="555e8-115">Logga in till Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="555e8-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="555e8-116">I det vänstra navigeringsfönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="555e8-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="555e8-117">Klicka på **Externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="555e8-117">Click **External identities**.</span></span>
4. <span data-ttu-id="555e8-118">På skärmen **Kom igång** i det vänstra navigeringsfönstret klickar du på **inställningar för externt samarbete**.</span><span class="sxs-lookup"><span data-stu-id="555e8-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="555e8-119">Se till **administratörer och användare i gästens inbjudna roll kan bjuda in** och **Medlemmar kan bjuda in** är båda inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="555e8-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="555e8-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="555e8-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="555e8-121">Observera inställningarna i avsnittet **Begränsningar för samarbete**.</span><span class="sxs-lookup"><span data-stu-id="555e8-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="555e8-122">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="555e8-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="555e8-123">Om du arbetar med gäster från flera organisationer kanske du vill begränsa deras åtkomst till katalogdata.</span><span class="sxs-lookup"><span data-stu-id="555e8-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="555e8-124">Det gör att de inte kan se vem mer som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="555e8-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="555e8-125">**Under begränsningar för gästanvändaråtkomst** kan du göra det genom att välja **Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalogobjekt** eller **Gästanvändaråtkomst begränsas till egenskaper och medlemskap i sina egna katalogobjekt**.</span><span class="sxs-lookup"><span data-stu-id="555e8-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="555e8-126">Gästinställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="555e8-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="555e8-127">Moderna SharePoint-webbplatser använder Microsoft 365-grupper för att styra webbplatsåtkomsten.</span><span class="sxs-lookup"><span data-stu-id="555e8-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="555e8-128">Gästinställningarna för Microsoft 365-grupper måste vara aktiverat för att gäståtkomst i SharePoint-webbplatser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="555e8-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="555e8-130">Ange gästinställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="555e8-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="555e8-131">I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 expanderar du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="555e8-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="555e8-132">Klicka **organisationens inställningar**.</span><span class="sxs-lookup"><span data-stu-id="555e8-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="555e8-133">I listan klickar du på **Microsoft 365-grupper**.</span><span class="sxs-lookup"><span data-stu-id="555e8-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="555e8-134">Kontrollera att kryssrutorna **Låt gruppägare lägga till personer utanför organisationen i Microsoft 365-grupper som gäster** och **Låt gästgruppsmedlemmar få åtkomst till gruppinnehåll** är markerade.</span><span class="sxs-lookup"><span data-stu-id="555e8-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="555e8-135">Om du har gjort ändringar klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="555e8-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="555e8-136">Delningsinställningar på organisationsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="555e8-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="555e8-137">För att gäster ska ha åtkomst till SharePoint-webbplatser måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="555e8-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="555e8-138">Inställningarna på organisationsnivå avgör vilka inställningar som ska vara tillgängliga för enskilda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="555e8-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="555e8-139">Webbplatsinställningar får inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="555e8-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="555e8-140">Om du vill tillåta icke-autisk fil- och mappdelning väljer du **Alla**.</span><span class="sxs-lookup"><span data-stu-id="555e8-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="555e8-141">Om du vill säkerställa att alla personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="555e8-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="555e8-142">Välj den mest tillåtande inställning som behövs på alla webbplatser i din organisation.</span><span class="sxs-lookup"><span data-stu-id="555e8-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="555e8-144">För att ange delningsinställningar för SharePoint på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="555e8-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="555e8-145">I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 går du till **Administrationscenter** och klickar på **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="555e8-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="555e8-146">I det vänstra navigeringsfönstret i administrationscentret för SharePoint, under **Principer,** klickar du på **Delning.**</span><span class="sxs-lookup"><span data-stu-id="555e8-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="555e8-147">Se till att extern delning för SharePoint är inställd på **Alla** eller **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="555e8-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="555e8-148">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="555e8-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="555e8-149">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="555e8-149">Create a site</span></span>

<span data-ttu-id="555e8-150">Nästa steg är att skapa den webbplats som du planerar att använda för att samarbeta med gäster.</span><span class="sxs-lookup"><span data-stu-id="555e8-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="555e8-151">Så här skapar du en webbplats</span><span class="sxs-lookup"><span data-stu-id="555e8-151">To create a site</span></span>
1. <span data-ttu-id="555e8-152">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="555e8-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="555e8-153">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="555e8-153">Click **Create**.</span></span>
3. <span data-ttu-id="555e8-154">Klicka **på Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="555e8-154">Click **Team site**.</span></span>
4. <span data-ttu-id="555e8-155">Skriv ett webbplatsnamn och ange ett namn för gruppägaren (webbplatsägare).</span><span class="sxs-lookup"><span data-stu-id="555e8-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="555e8-156">Under **Avancerade inställningar** väljer du om du vill att den här webbplatsen ska vara offentlig eller privat.</span><span class="sxs-lookup"><span data-stu-id="555e8-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="555e8-157">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="555e8-157">Click **Next**.</span></span>
7. <span data-ttu-id="555e8-158">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="555e8-158">Click **Finish**.</span></span>

<span data-ttu-id="555e8-159">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="555e8-159">We'll invite users later.</span></span> <span data-ttu-id="555e8-160">Sedan är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="555e8-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="555e8-161">Delningsinställningar på webbplatsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="555e8-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="555e8-162">Kontrollera inställningarna för delning på webbplatsnivå för att säkerställa att de tillåter den typ av åtkomst som du vill använda för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="555e8-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="555e8-163">Om du till exempel har ställt in inställningarna på organisationsnivå till Alla **,** men du vill att alla gäster ska autentiseras för den här webbplatsen, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på Nya och **befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="555e8-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="555e8-164">Observera att webbplatsen inte kan delas med oauthenticerade personer **(inställningen** Alla), men enskilda filer och mappar kan.</span><span class="sxs-lookup"><span data-stu-id="555e8-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="555e8-165">Du kan också använda [känslighetsetiketter för att styra inställningar för extern delning för SharePoint-webbplatser.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="555e8-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="555e8-167">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="555e8-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="555e8-168">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="555e8-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="555e8-169">Välj den webbplats som du vill dela.</span><span class="sxs-lookup"><span data-stu-id="555e8-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="555e8-170">Klicka på ... och sedan på **Delning.**</span><span class="sxs-lookup"><span data-stu-id="555e8-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="555e8-171">Kontrollera att delning är inställt på **Alla** eller **Nya och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="555e8-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="555e8-172">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="555e8-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="555e8-173">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="555e8-173">Invite users</span></span>

<span data-ttu-id="555e8-174">Inställningarna för gästdelning är nu konfigurerade så att du kan börja lägga till interna användare och gäster på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="555e8-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="555e8-175">Webbplatsåtkomsten styrs via den associerade Microsoft 365-gruppen, så vi lägger till användare där.</span><span class="sxs-lookup"><span data-stu-id="555e8-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="555e8-176">Bjuda in interna användare till en grupp</span><span class="sxs-lookup"><span data-stu-id="555e8-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="555e8-177">Navigera till den webbplats där du vill lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="555e8-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="555e8-178">Klicka **på** länken Medlemmar uppe till höger vilket anger antalet medlemmar.</span><span class="sxs-lookup"><span data-stu-id="555e8-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="555e8-179">Klicka på **Lägg till medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="555e8-179">Click **Add members**.</span></span>
4. <span data-ttu-id="555e8-180">Skriv namnen eller e-postadresserna till de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="555e8-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="555e8-181">Gäster kan inte läggas till från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="555e8-181">Guests can't be added from the site.</span></span> <span data-ttu-id="555e8-182">Du måste lägga till dem med hjälp av Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="555e8-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="555e8-183">Som en förutsättning för att lägga till och bjuda in gäster till en grupp klickar du därför på webbplatsens URL i **URL-kolumnen**  för att navigera till den webbplatsspecifika sidan.</span><span class="sxs-lookup"><span data-stu-id="555e8-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="555e8-184">Klicka på ikonen för **appstartaren på den här** sidan och välj **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="555e8-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="555e8-185">Det här är skärmen där du kan bjuda in gäster till en grupp, som beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="555e8-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="555e8-186">Bjuda in gäster till en grupp</span><span class="sxs-lookup"><span data-stu-id="555e8-186">To invite guests to a group</span></span>
1. <span data-ttu-id="555e8-187">Under **Grupper** klickar du på den grupp som du vill bjuda in gäster till.</span><span class="sxs-lookup"><span data-stu-id="555e8-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="555e8-188">Öppna gruppens kontaktkort, klicka **på medlemslänken** längst upp till höger (länken som anger antalet medlemmar).</span><span class="sxs-lookup"><span data-stu-id="555e8-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="555e8-189">klickar du **på Lägg till medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="555e8-189">click **Add members**.</span></span>
4. <span data-ttu-id="555e8-190">Skriv e-postadresserna till de gäster som du vill bjuda in och klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="555e8-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="555e8-191">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="555e8-191">Click **Close**.</span></span>
<span data-ttu-id="555e8-192">Observera att du endast **behöver** klicka på Stäng om du inte är gruppens ägare och därför inte tillåts lägga till gästen i gruppen.</span><span class="sxs-lookup"><span data-stu-id="555e8-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="555e8-193">I sådana fall överförs begäran att lägga till gästen i gruppen till gruppägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="555e8-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="555e8-194">Se även</span><span class="sxs-lookup"><span data-stu-id="555e8-194">See also</span></span>

[<span data-ttu-id="555e8-195">Metodtips för att dela filer och mappar med overifierade användare</span><span class="sxs-lookup"><span data-stu-id="555e8-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="555e8-196">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="555e8-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="555e8-197">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="555e8-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="555e8-198">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="555e8-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="555e8-199">SharePoint- och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="555e8-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)