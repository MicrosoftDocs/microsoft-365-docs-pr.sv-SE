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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig mer om de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.
ms.openlocfilehash: cb3cfc52191be4bacfb9d84672131149082ee80e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277574"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="ec845-103">Samar beta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="ec845-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="ec845-104">Om du behöver samar beta med gäster mellan dokument, data och listor kan du använda en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="ec845-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="ec845-105">Moderna SharePoint-webbplatser är anslutna till Microsoft 365-grupper och kan hantera webbplats medlemskap och tillhandahålla ytterligare samarbets verktyg, till exempel en delad post låda och kalender.</span><span class="sxs-lookup"><span data-stu-id="ec845-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="ec845-106">I den här artikeln går vi igenom de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="ec845-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="ec845-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="ec845-107">Video demonstration</span></span>

<span data-ttu-id="ec845-108">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="ec845-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="ec845-109">Inställningar för extern samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="ec845-109">Azure external collaboration settings</span></span>

<span data-ttu-id="ec845-110">Delning i Microsoft 365 regleras på högsta nivå av [organisations Relations inställningarna i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="ec845-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="ec845-111">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter detta eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec845-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="ec845-112">Kontrol lera inställningarna för extern samarbete för att se till att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="ec845-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Skärm bild av sidan med inställningar för extern samarbets katalog i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="ec845-114">Så här anger du inställningar för extern samarbete:</span><span class="sxs-lookup"><span data-stu-id="ec845-114">To set external collaboration settings:</span></span>


1. <span data-ttu-id="ec845-115">Logga in på Microsoft Azure på [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ec845-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ec845-116">I det vänstra navigerings fältet klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ec845-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="ec845-117">Välj **externa identiteter** och klicka på **Inställningar för externt samarbete**.</span><span class="sxs-lookup"><span data-stu-id="ec845-117">Select **External Identities** and click on **External collaboration settings**.</span></span>
4. <span data-ttu-id="ec845-118">I fönstret **Inställningar för gäst inbjudningar** kontrollerar du att **Administratörer och användare i rollen som inbjudan gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ec845-118">In the **Guest invite settings** pane, ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
5. <span data-ttu-id="ec845-119">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec845-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="ec845-120">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="ec845-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="ec845-121">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="ec845-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="ec845-122">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="ec845-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="ec845-123">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="ec845-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="ec845-124">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="ec845-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="ec845-125">Inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="ec845-125">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="ec845-126">Moderna SharePoint-webbplatser använder Microsoft 365 Groups för att styra åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ec845-126">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="ec845-127">Inställningarna för gruppen Microsoft 365-grupper måste aktive ras för att gäst åtkomsten på SharePoint-webbplatser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="ec845-127">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="ec845-129">Ange inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="ec845-129">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="ec845-130">I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ec845-130">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="ec845-131">Klicka på **tjänster & tillägg**.</span><span class="sxs-lookup"><span data-stu-id="ec845-131">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="ec845-132">I listan klickar du på **Microsoft 365 Groups**.</span><span class="sxs-lookup"><span data-stu-id="ec845-132">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="ec845-133">Kontrol lera att **grupp medlemmarna utanför din organisation får grupp innehållet** och **låta grupp ägarna lägga till personer utanför organisationen för grupper** markerar båda kryss rutorna.</span><span class="sxs-lookup"><span data-stu-id="ec845-133">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="ec845-134">Om du har gjort ändringarna klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ec845-134">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="ec845-135">Delnings inställningar för SharePoint-organisationnivå</span><span class="sxs-lookup"><span data-stu-id="ec845-135">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="ec845-136">För att gäster ska ha åtkomst till SharePoint-webbplatser måste delnings inställningarna för SharePoint-organisations nivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="ec845-136">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="ec845-137">Inställningarna på organisations nivå bestämmer vilka inställningar som är tillgängliga för enskilda webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ec845-137">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="ec845-138">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="ec845-138">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="ec845-139">Om du vill tillåta overifierad fil-och mappdelning väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="ec845-139">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="ec845-140">Om du vill vara säker på att alla personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="ec845-140">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="ec845-141">Välj den mest tillåtna inställningen som behövs för en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ec845-141">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="ec845-143">Så här anger du delnings inställningar för SharePoint-organisationnivå</span><span class="sxs-lookup"><span data-stu-id="ec845-143">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="ec845-144">Klicka på **SharePoint**i det vänstra navigerings fältet **i administrations**centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec845-144">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="ec845-145">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="ec845-145">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="ec845-146">Kontrol lera att extern delning för SharePoint är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="ec845-146">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="ec845-147">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec845-147">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="ec845-148">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="ec845-148">Create a site</span></span>

<span data-ttu-id="ec845-149">Nästa steg är att skapa den webbplats du planerar att använda för att samar beta med gäster.</span><span class="sxs-lookup"><span data-stu-id="ec845-149">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="ec845-150">Skapa en webbplats</span><span class="sxs-lookup"><span data-stu-id="ec845-150">To create a site</span></span>
1. <span data-ttu-id="ec845-151">I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="ec845-151">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="ec845-152">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ec845-152">Click **Create**.</span></span>
3. <span data-ttu-id="ec845-153">Klicka på **grupp webbplats**.</span><span class="sxs-lookup"><span data-stu-id="ec845-153">Click **Team site**.</span></span>
4. <span data-ttu-id="ec845-154">Ange ett namn på webbplatsen och ange gruppens ägare (webbplats ägare).</span><span class="sxs-lookup"><span data-stu-id="ec845-154">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="ec845-155">Under **Avancerade inställningar**väljer du om du vill att det ska vara en offentlig eller privat webbplats.</span><span class="sxs-lookup"><span data-stu-id="ec845-155">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="ec845-156">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ec845-156">Click **Next**.</span></span>
7. <span data-ttu-id="ec845-157">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="ec845-157">Click **Finish**.</span></span>

<span data-ttu-id="ec845-158">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="ec845-158">We'll invite users later.</span></span> <span data-ttu-id="ec845-159">Sedan är det viktigt att kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="ec845-159">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="ec845-160">Delnings inställningar för SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="ec845-160">SharePoint site level sharing settings</span></span>

<span data-ttu-id="ec845-161">Kontrol lera inställningarna för delning av webbplats nivå för att se till att de tillåter åtkomst typen som du vill använda för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ec845-161">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="ec845-162">Om du till exempel ställer in inställningar på organisations nivå till **vem som helst**, men vill att alla gäster ska autentiseras för webbplatsen, kontrollerar du att inställningarna för delning av webbplats nivå är inställda på **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="ec845-162">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="ec845-163">Observera att webbplatsen inte kan delas med overifierade personer (**alla** inställningar), men enskilda filer och mappar kan.</span><span class="sxs-lookup"><span data-stu-id="ec845-163">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="ec845-165">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="ec845-165">To set site-level sharing settings</span></span>
1. <span data-ttu-id="ec845-166">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="ec845-166">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ec845-167">Välj den webbplats du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="ec845-167">Select the site that you just created.</span></span>
3. <span data-ttu-id="ec845-168">Klicka på **Delning** i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="ec845-168">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="ec845-169">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="ec845-169">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="ec845-170">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec845-170">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="ec845-171">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="ec845-171">Invite users</span></span>

<span data-ttu-id="ec845-172">Inställningar för gäst delning är nu konfigurerade så att du kan börja lägga till interna användare och gäster på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="ec845-172">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="ec845-173">Webbplats åtkomsten styrs via den associerade Microsoft 365-gruppen, så vi lägger till användare där.</span><span class="sxs-lookup"><span data-stu-id="ec845-173">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="ec845-174">Bjuda in interna användare till en grupp</span><span class="sxs-lookup"><span data-stu-id="ec845-174">To invite internal users to a group</span></span>
1. <span data-ttu-id="ec845-175">Navigera till den webbplats där du vill lägga till användare.</span><span class="sxs-lookup"><span data-stu-id="ec845-175">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="ec845-176">Klicka på **medlemmar** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="ec845-176">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="ec845-177">Klicka på **Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="ec845-177">Click **Add members**.</span></span>
4. <span data-ttu-id="ec845-178">Skriv namnen eller e-postadresserna för de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ec845-178">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="ec845-179">Gäst användare kan inte läggas till från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ec845-179">Guest users can't be added from the site.</span></span> <span data-ttu-id="ec845-180">Du måste lägga till dem med hjälp av Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="ec845-180">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="ec845-181">Så här bjuder du in gäster till en grupp</span><span class="sxs-lookup"><span data-stu-id="ec845-181">To invite guests to a group</span></span>
1. <span data-ttu-id="ec845-182">I Outlook på webben klickar du under **grupper**på den grupp där du vill lägga till medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ec845-182">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="ec845-183">Öppna grupp kontakt kortet och klicka på **Lägg till medlemmar**under **fler alternativ** (...).</span><span class="sxs-lookup"><span data-stu-id="ec845-183">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="ec845-184">Skriv e-postadresserna för de gäster som du vill bjuda in och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ec845-184">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="ec845-185">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ec845-185">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec845-186">Se även</span><span class="sxs-lookup"><span data-stu-id="ec845-186">See Also</span></span>

[<span data-ttu-id="ec845-187">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="ec845-187">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="ec845-188">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="ec845-188">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="ec845-189">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="ec845-189">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="ec845-190">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="ec845-190">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
