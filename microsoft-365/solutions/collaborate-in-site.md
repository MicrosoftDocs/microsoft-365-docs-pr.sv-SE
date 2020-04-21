---
title: Samarbeta med gäster på en webbplats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Läs om hur du samarbetar med gäster på en SharePoint-webbplats.
ms.openlocfilehash: 5a8bc5da55f3582a7e298dab97ec4d6b3d147b60
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630743"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="466fc-103">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="466fc-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="466fc-104">Om du behöver samarbeta med gäster över dokument, data och listor kan du använda en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="466fc-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="466fc-105">Moderna SharePoint-webbplatser är anslutna till Microsoft 365-grupper och kan hantera webbplatsmedlemskapet och tillhandahålla ytterligare samarbetsverktyg som en delad postlåda och kalender.</span><span class="sxs-lookup"><span data-stu-id="466fc-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="466fc-106">I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera en SharePoint-webbplats för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="466fc-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="466fc-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="466fc-107">Video demonstration</span></span>

<span data-ttu-id="466fc-108">I det här videoklippet visas de konfigurationssteg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="466fc-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="466fc-109">Inställningar för Azure-organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="466fc-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="466fc-110">Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="466fc-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="466fc-111">Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="466fc-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="466fc-112">Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="466fc-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="466fc-114">Så här anger du inställningar för organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="466fc-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="466fc-115">Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .</span><span class="sxs-lookup"><span data-stu-id="466fc-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="466fc-116">Klicka på Azure **Active Directory**i den vänstra navigeringen .</span><span class="sxs-lookup"><span data-stu-id="466fc-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="466fc-117">Klicka på **Organisationsrelationer**i **fönstret Översikt.**</span><span class="sxs-lookup"><span data-stu-id="466fc-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="466fc-118">Klicka på **Inställningar**i fönstret **Organisationsrelationer** .</span><span class="sxs-lookup"><span data-stu-id="466fc-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="466fc-119">Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="466fc-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="466fc-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="466fc-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="466fc-121">Observera inställningarna i avsnittet **Samarbetsbegränsningar.**</span><span class="sxs-lookup"><span data-stu-id="466fc-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="466fc-122">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="466fc-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="466fc-123">Gästinställningar för Microsoft 365 Grupper</span><span class="sxs-lookup"><span data-stu-id="466fc-123">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="466fc-124">Moderna SharePoint-webbplatser använder Microsoft 365-grupper för att styra webbplatsåtkomsten.</span><span class="sxs-lookup"><span data-stu-id="466fc-124">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="466fc-125">Gästinställningarna för Microsoft 365 Grupper måste vara aktiverade för att gäståtkomsten på SharePoint-webbplatser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="466fc-125">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Skärmbild av gästinställningar för Microsoft 365 Grupper i Microsoft 365-administrationscentret](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="466fc-127">Så här anger du gästinställningar för Microsoft 365 Grupper</span><span class="sxs-lookup"><span data-stu-id="466fc-127">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="466fc-128">Expandera **Inställningar**i det vänstra navigeringsfältet i Microsoft 365 i det vänstra navigeringscentret .</span><span class="sxs-lookup"><span data-stu-id="466fc-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="466fc-129">Klicka på **Tjänster & tillägg**.</span><span class="sxs-lookup"><span data-stu-id="466fc-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="466fc-130">Klicka på **Microsoft 365 Grupper**i listan .</span><span class="sxs-lookup"><span data-stu-id="466fc-130">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="466fc-131">Kontrollera att kryssrutorna **Låt gruppmedlemmar utanför organisationen får åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper** är markerade.</span><span class="sxs-lookup"><span data-stu-id="466fc-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="466fc-132">Om du har gjort ändringar klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="466fc-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="466fc-133">Delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="466fc-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="466fc-134">För att gästerna ska få tillgång till SharePoint-webbplatser måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="466fc-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="466fc-135">Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="466fc-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="466fc-136">Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="466fc-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="466fc-137">Om du vill tillåta oautentiserade fil- och mappdelning väljer du **Alla**.</span><span class="sxs-lookup"><span data-stu-id="466fc-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="466fc-138">Om du vill vara säkra på att alla personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="466fc-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="466fc-139">Välj den mest tillåtande inställningen som behövs av en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="466fc-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="466fc-141">Så här anger du delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="466fc-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="466fc-142">Klicka på **SharePoint**under **Administrationscenter i administrationscentret**för Microsoft 365, i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="466fc-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="466fc-143">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="466fc-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="466fc-144">Kontrollera att extern delning för SharePoint är inställt **på Alla** eller Nya och **befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="466fc-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="466fc-145">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="466fc-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="466fc-146">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="466fc-146">Create a site</span></span>

<span data-ttu-id="466fc-147">Nästa steg är att skapa den webbplats som du planerar att använda för att samarbeta med gäster.</span><span class="sxs-lookup"><span data-stu-id="466fc-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="466fc-148">Så här skapar du en webbplats</span><span class="sxs-lookup"><span data-stu-id="466fc-148">To create a site</span></span>
1. <span data-ttu-id="466fc-149">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="466fc-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="466fc-150">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="466fc-150">Click **Create**.</span></span>
3. <span data-ttu-id="466fc-151">Klicka på **Gruppwebbplats**.</span><span class="sxs-lookup"><span data-stu-id="466fc-151">Click **Team site**.</span></span>
4. <span data-ttu-id="466fc-152">Skriv ett webbplatsnamn och ange ett namn för gruppägaren (webbplatsägaren).</span><span class="sxs-lookup"><span data-stu-id="466fc-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="466fc-153">Under **Avancerade inställningar**väljer du om du vill att det ska vara en offentlig eller privat webbplats.</span><span class="sxs-lookup"><span data-stu-id="466fc-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="466fc-154">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="466fc-154">Click **Next**.</span></span>
7. <span data-ttu-id="466fc-155">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="466fc-155">Click **Finish**.</span></span>

<span data-ttu-id="466fc-156">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="466fc-156">We'll invite users later.</span></span> <span data-ttu-id="466fc-157">Därefter är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="466fc-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="466fc-158">Delningsinställningar för SharePoint-webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="466fc-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="466fc-159">Kontrollera delningsinställningarna på webbplatsnivå för att se till att de tillåter den typ av åtkomst som du vill ha för den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="466fc-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="466fc-160">Om du till exempel anger inställningarna på organisationsnivå till **Alla**, men vill att alla gäster ska autentisera för den här webbplatsen, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="466fc-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="466fc-161">Observera att webbplatsen inte kan delas med oautentiserade personer (**Någon** inställning), men enskilda filer och mappar kan.</span><span class="sxs-lookup"><span data-stu-id="466fc-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="466fc-163">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="466fc-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="466fc-164">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="466fc-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="466fc-165">Välj den webbplats som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="466fc-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="466fc-166">Klicka på **Delning** i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="466fc-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="466fc-167">Se till att delning är inställt **på Vem som helst** eller Nya och befintliga **gäster**.</span><span class="sxs-lookup"><span data-stu-id="466fc-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="466fc-168">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="466fc-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="466fc-169">Bjud in användare</span><span class="sxs-lookup"><span data-stu-id="466fc-169">Invite users</span></span>

<span data-ttu-id="466fc-170">Gästdelningsinställningarna är nu konfigurerade, så att du kan börja lägga till interna användare och gäster på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="466fc-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="466fc-171">Webbplatsåtkomsten styrs via den associerade Microsoft 365-gruppen, så vi lägger till användare där.</span><span class="sxs-lookup"><span data-stu-id="466fc-171">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="466fc-172">Så här bjuder du in interna användare till en grupp</span><span class="sxs-lookup"><span data-stu-id="466fc-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="466fc-173">Navigera till den webbplats där du vill lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="466fc-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="466fc-174">Klicka på **Medlemmar** längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="466fc-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="466fc-175">Klicka på **Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="466fc-175">Click **Add members**.</span></span>
4. <span data-ttu-id="466fc-176">Skriv namnen eller e-postadresserna till de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="466fc-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="466fc-177">Gästanvändare kan inte läggas till från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="466fc-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="466fc-178">Du måste lägga till dem med Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="466fc-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="466fc-179">Så här bjuder du in gäster till en grupp</span><span class="sxs-lookup"><span data-stu-id="466fc-179">To invite guests to a group</span></span>
1. <span data-ttu-id="466fc-180">Klicka på den grupp där du vill lägga till medlemmar under **Grupper**i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="466fc-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="466fc-181">Öppna gruppkontaktkortet och klicka sedan på Lägg **till medlemmar**under **Fler alternativ** (...).</span><span class="sxs-lookup"><span data-stu-id="466fc-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="466fc-182">Skriv e-postadresserna till de gäster som du vill bjuda in och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="466fc-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="466fc-183">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="466fc-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="466fc-184">Se även</span><span class="sxs-lookup"><span data-stu-id="466fc-184">See Also</span></span>

[<span data-ttu-id="466fc-185">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="466fc-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="466fc-186">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="466fc-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="466fc-187">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="466fc-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="466fc-188">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="466fc-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

