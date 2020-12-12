---
title: Samar beta med gäster på en webbplats
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
description: Lär dig mer om de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663530"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="662bb-103">Samar beta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="662bb-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="662bb-104">Om du behöver samar beta med gäster mellan dokument, data och listor kan du använda en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="662bb-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="662bb-105">Moderna SharePoint-webbplatser är anslutna till Microsoft 365-grupper och kan hantera webbplats medlemskap och tillhandahålla ytterligare samarbets verktyg, till exempel en delad post låda och en kalender.</span><span class="sxs-lookup"><span data-stu-id="662bb-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="662bb-106">I den här artikeln går vi igenom de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="662bb-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="662bb-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="662bb-107">Video demonstration</span></span>

<span data-ttu-id="662bb-108">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="662bb-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="662bb-109">Inställningar för extern samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="662bb-109">Azure external collaboration settings</span></span>

<span data-ttu-id="662bb-110">Delning i Microsoft 365 regleras på högsta nivå av [B2B-inställningen för externt samarbete i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="662bb-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="662bb-111">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="662bb-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="662bb-112">Kontrol lera inställningarna för externt samarbete för B2B för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="662bb-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Skärm bild av sidan med inställningar för extern samarbets katalog i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="662bb-114">Så här anger du inställningar för extern samarbete</span><span class="sxs-lookup"><span data-stu-id="662bb-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="662bb-115">Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="662bb-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="662bb-116">I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="662bb-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="662bb-117">Klicka på **externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="662bb-117">Click **External identities**.</span></span>
4. <span data-ttu-id="662bb-118">Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .</span><span class="sxs-lookup"><span data-stu-id="662bb-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="662bb-119">Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="662bb-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="662bb-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="662bb-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="662bb-121">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="662bb-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="662bb-122">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="662bb-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="662bb-123">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="662bb-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="662bb-124">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="662bb-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="662bb-125">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="662bb-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="662bb-126">Inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="662bb-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="662bb-127">Moderna SharePoint-webbplatser använder Microsoft 365 Groups för att styra åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="662bb-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="662bb-128">Inställningarna för gruppen Microsoft 365-grupper måste aktive ras för att gäst åtkomsten på SharePoint-webbplatser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="662bb-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="662bb-130">Ange inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="662bb-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="662bb-131">Expandera **Inställningar** i det vänstra navigerings fönstret i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="662bb-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="662bb-132">Klicka på **org Settings**.</span><span class="sxs-lookup"><span data-stu-id="662bb-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="662bb-133">I listan klickar du på **Microsoft 365 Groups**.</span><span class="sxs-lookup"><span data-stu-id="662bb-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="662bb-134">Kontrol lera att **gruppen låt grupp ägarna lägger till personer utanför organisationen till Microsoft 365-grupper som gäster** och **Låt grupp medlemmarna i gruppen för gäst grupps medlemmar** vara markerade.</span><span class="sxs-lookup"><span data-stu-id="662bb-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="662bb-135">Om du har gjort ändringarna klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="662bb-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="662bb-136">Delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="662bb-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="662bb-137">För att gäster ska ha åtkomst till SharePoint-webbplatser måste delnings inställningarna för SharePoint-organisations nivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="662bb-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="662bb-138">Inställningarna på organisations nivå bestämmer vilka inställningar som ska vara tillgängliga för enskilda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="662bb-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="662bb-139">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="662bb-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="662bb-140">Om du vill tillåta overifierad fil-och mappdelning väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="662bb-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="662bb-141">Om du vill vara säker på att alla personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="662bb-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="662bb-142">Välj den mest tillåtna inställningen som behövs för en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="662bb-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="662bb-144">Så här anger du delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="662bb-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="662bb-145">Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="662bb-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="662bb-146">Klicka på **delning** **i det** vänstra navigerings fältet i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="662bb-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="662bb-147">Kontrol lera att extern delning för SharePoint är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="662bb-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="662bb-148">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="662bb-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="662bb-149">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="662bb-149">Create a site</span></span>

<span data-ttu-id="662bb-150">Nästa steg är att skapa den webbplats du planerar att använda för att samar beta med gäster.</span><span class="sxs-lookup"><span data-stu-id="662bb-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="662bb-151">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="662bb-151">To create a site</span></span>
1. <span data-ttu-id="662bb-152">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="662bb-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="662bb-153">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="662bb-153">Click **Create**.</span></span>
3. <span data-ttu-id="662bb-154">Klicka på **grupp webbplats**.</span><span class="sxs-lookup"><span data-stu-id="662bb-154">Click **Team site**.</span></span>
4. <span data-ttu-id="662bb-155">Ange ett namn på webbplatsen och ange gruppens ägare (webbplats ägare).</span><span class="sxs-lookup"><span data-stu-id="662bb-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="662bb-156">Under **Avancerade inställningar** väljer du om du vill att webbplatsen ska vara offentlig eller privat.</span><span class="sxs-lookup"><span data-stu-id="662bb-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="662bb-157">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="662bb-157">Click **Next**.</span></span>
7. <span data-ttu-id="662bb-158">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="662bb-158">Click **Finish**.</span></span>

<span data-ttu-id="662bb-159">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="662bb-159">We'll invite users later.</span></span> <span data-ttu-id="662bb-160">Sedan är det viktigt att kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="662bb-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="662bb-161">Delnings inställningar på SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="662bb-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="662bb-162">Kontrol lera inställningarna för delning av webbplats nivå för att se till att de tillåter åtkomst typen som du vill använda för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="662bb-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="662bb-163">Om du till exempel ställer in inställningar på organisations nivå till **vem som helst**, men vill att alla gäster ska autentiseras för webbplatsen, kontrollerar du att inställningarna för delning av webbplats nivå är inställda på **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="662bb-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="662bb-164">Observera att webbplatsen inte kan delas med overifierade personer (**alla** inställningar), men enskilda filer och mappar kan.</span><span class="sxs-lookup"><span data-stu-id="662bb-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="662bb-165">Du kan också använda [känslighets etiketter för att kontrol lera inställningar för extern delning för SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="662bb-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="662bb-167">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="662bb-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="662bb-168">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="662bb-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="662bb-169">Välj den webbplats du vill dela.</span><span class="sxs-lookup"><span data-stu-id="662bb-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="662bb-170">Klicka på... och klicka på **delning**.</span><span class="sxs-lookup"><span data-stu-id="662bb-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="662bb-171">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="662bb-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="662bb-172">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="662bb-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="662bb-173">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="662bb-173">Invite users</span></span>

<span data-ttu-id="662bb-174">Inställningar för gäst delning är nu konfigurerade så att du kan börja lägga till interna användare och gäster på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="662bb-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="662bb-175">Webbplats åtkomsten styrs via den associerade Microsoft 365-gruppen, så vi lägger till användare där.</span><span class="sxs-lookup"><span data-stu-id="662bb-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="662bb-176">Bjuda in interna användare till en grupp</span><span class="sxs-lookup"><span data-stu-id="662bb-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="662bb-177">Navigera till den webbplats där du vill lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="662bb-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="662bb-178">Klicka på **medlemmar** i det övre högra hörnet och anger antalet medlemmar.</span><span class="sxs-lookup"><span data-stu-id="662bb-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="662bb-179">Klicka på **Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="662bb-179">Click **Add members**.</span></span>
4. <span data-ttu-id="662bb-180">Skriv namnen eller e-postadresserna för de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="662bb-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="662bb-181">Det går inte att lägga till gäster från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="662bb-181">Guests can't be added from the site.</span></span> <span data-ttu-id="662bb-182">Du måste lägga till dem med hjälp av Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="662bb-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="662bb-183">För att du ska kunna lägga till och bjuda in gäster till en grupp klickar du därför på URL-adressen för webbplatsen i kolumnen **URL**  för att gå till den sitespecifika sidan.</span><span class="sxs-lookup"><span data-stu-id="662bb-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="662bb-184">Från den här sidan klickar du på ikonen för **Start programmet** och väljer **Outlook**.</span><span class="sxs-lookup"><span data-stu-id="662bb-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="662bb-185">Det här är den skärm där du kan bjuda in gäster till en grupp, för vilka procedurer beskrivs nedan.</span><span class="sxs-lookup"><span data-stu-id="662bb-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="662bb-186">Så här bjuder du in gäster till en grupp</span><span class="sxs-lookup"><span data-stu-id="662bb-186">To invite guests to a group</span></span>
1. <span data-ttu-id="662bb-187">Under **grupper** klickar du på den grupp som du vill bjuda in gäster till.</span><span class="sxs-lookup"><span data-stu-id="662bb-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="662bb-188">Öppna grupp kontakt kortet och klicka på länken **medlemmar** i det övre högra hörnet (länken som anger antalet medlemmar).</span><span class="sxs-lookup"><span data-stu-id="662bb-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="662bb-189">Klicka på **Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="662bb-189">click **Add members**.</span></span>
4. <span data-ttu-id="662bb-190">Skriv e-postadresserna för de gäster som du vill bjuda in och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="662bb-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="662bb-191">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="662bb-191">Click **Close**.</span></span>
<span data-ttu-id="662bb-192">Observera att du bara behöver klicka på **Stäng** om du inte är ägare till gruppen och att du inte kan lägga till gästen i gruppen.</span><span class="sxs-lookup"><span data-stu-id="662bb-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="662bb-193">I sådana fall överförs begäran om att lägga till gästen i gruppen till grupp ägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="662bb-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="662bb-194">Se även</span><span class="sxs-lookup"><span data-stu-id="662bb-194">See also</span></span>

[<span data-ttu-id="662bb-195">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="662bb-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="662bb-196">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="662bb-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="662bb-197">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="662bb-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="662bb-198">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="662bb-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="662bb-199">SharePoint och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="662bb-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
