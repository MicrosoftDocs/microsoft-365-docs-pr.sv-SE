---
title: Samarbeta med gäster i ett team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Läs om hur du samarbetar med gäster i Teams.
ms.openlocfilehash: 54bf52eebc77e1cce8e1c05a708572d7d1e7fdae
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42811620"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="b45ef-103">Samarbeta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="b45ef-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="b45ef-104">Om du behöver samarbeta med gäster över dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b45ef-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="b45ef-105">Teams tillhandahåller alla samarbetsfunktioner som är tillgängliga i Office och SharePoint med beständig chatt och en anpassningsbar och utökningsbar uppsättning samarbetsverktyg i en enhetlig användarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="b45ef-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="b45ef-106">I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera ett team för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="b45ef-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b45ef-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="b45ef-107">Video demonstration</span></span>

<span data-ttu-id="b45ef-108">I det här videoklippet visas de konfigurationssteg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="b45ef-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="b45ef-109">Inställningar för Azure-organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="b45ef-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="b45ef-110">Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b45ef-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="b45ef-111">Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b45ef-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="b45ef-112">Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="b45ef-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan Inställningar för Azure Active Directory-organisationsrelationer](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="b45ef-114">Så här anger du inställningar för organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="b45ef-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="b45ef-115">Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .</span><span class="sxs-lookup"><span data-stu-id="b45ef-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b45ef-116">Klicka på Azure **Active Directory**i den vänstra navigeringen .</span><span class="sxs-lookup"><span data-stu-id="b45ef-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b45ef-117">Klicka på **Organisationsrelationer**i **fönstret Översikt.**</span><span class="sxs-lookup"><span data-stu-id="b45ef-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="b45ef-118">Klicka på **Inställningar**i fönstret **Organisationsrelationer** .</span><span class="sxs-lookup"><span data-stu-id="b45ef-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="b45ef-119">Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="b45ef-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b45ef-121">Observera inställningarna i avsnittet **Samarbetsbegränsningar.**</span><span class="sxs-lookup"><span data-stu-id="b45ef-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="b45ef-122">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="b45ef-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="b45ef-123">Inställningar för gäståtkomst till team</span><span class="sxs-lookup"><span data-stu-id="b45ef-123">Teams guest access settings</span></span>

<span data-ttu-id="b45ef-124">Lagen har en master on/off-knapp för gäståtkomst och en mängd olika inställningar som är tillgängliga för att styra vad gästerna kan göra i ett team.</span><span class="sxs-lookup"><span data-stu-id="b45ef-124">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="b45ef-125">Huvudväxeln, **Tillåt gäståtkomst i Teams** måste vara **på** för gäståtkomst till arbete i Teams.</span><span class="sxs-lookup"><span data-stu-id="b45ef-125">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="b45ef-126">Kontrollera att gäståtkomst är aktiverat i Teams och gör eventuella justeringar av gästinställningarna baserat på dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="b45ef-126">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="b45ef-127">Tänk på att dessa inställningar påverkar alla team.</span><span class="sxs-lookup"><span data-stu-id="b45ef-127">Keep in mind that these settings affect all teams.</span></span>

![Skärmbild av Teams gäståtkomst växla](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="b45ef-129">Så här anger du inställningar för Teams gäståtkomst</span><span class="sxs-lookup"><span data-stu-id="b45ef-129">To set Teams guest access settings</span></span>

1. <span data-ttu-id="b45ef-130">Logga in på Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com)admin center på .</span><span class="sxs-lookup"><span data-stu-id="b45ef-130">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="b45ef-131">I den vänstra navigeringen klickar du på **Visa alla**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-131">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="b45ef-132">Klicka på **Teams** **under Administrationscenter**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-132">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="b45ef-133">Expandera inställningar för hela Organisationen för hela Organisationen i administrationscentret för Team i den vänstra **navigeringen** och klicka på **Gäståtkomst**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-133">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="b45ef-134">Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-134">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="b45ef-135">Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-135">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b45ef-136">Det kan ta upp till 24 timmar innan Teams gästinställning blir aktiv när du har aktiverat den.</span><span class="sxs-lookup"><span data-stu-id="b45ef-136">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="office-365-groups-guest-settings"></a><span data-ttu-id="b45ef-137">Gästinställningar för Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="b45ef-137">Office 365 Groups guest settings</span></span>

<span data-ttu-id="b45ef-138">Teams använder Office 365-grupper för gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="b45ef-138">Teams uses Office 365 Groups for team membership.</span></span> <span data-ttu-id="b45ef-139">Gästinställningarna för Office 365-grupper måste vara aktiverade för att gäståtkomsten i Teams ska fungera.</span><span class="sxs-lookup"><span data-stu-id="b45ef-139">The Office 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Skärmbild av gästinställningar för Office 365 Grupper i microsoft 365-administrationscentret](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="b45ef-141">Så här anger du gästinställningar för Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="b45ef-141">To set Office 365 Groups guest settings</span></span>

1. <span data-ttu-id="b45ef-142">Expandera **Inställningar**i det vänstra navigeringsfältet i Microsoft 365 i det vänstra navigeringscentret .</span><span class="sxs-lookup"><span data-stu-id="b45ef-142">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="b45ef-143">Klicka på **Tjänster & tillägg**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-143">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="b45ef-144">Klicka på **Office 365 Grupper**i listan .</span><span class="sxs-lookup"><span data-stu-id="b45ef-144">In the list, click **Office 365 Groups**.</span></span>
4. <span data-ttu-id="b45ef-145">Kontrollera att kryssrutorna **Låt gruppmedlemmar utanför organisationen får åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper** är markerade.</span><span class="sxs-lookup"><span data-stu-id="b45ef-145">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="b45ef-146">Om du har gjort ändringar klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-146">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="b45ef-147">Delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-147">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="b45ef-148">Teams-innehåll som filer, mappar och listor lagras alla i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b45ef-148">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="b45ef-149">För att gästerna ska få tillgång till dessa objekt i Teams måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="b45ef-149">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="b45ef-150">Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser, inklusive webbplatser som är associerade med team.</span><span class="sxs-lookup"><span data-stu-id="b45ef-150">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="b45ef-151">Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="b45ef-151">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="b45ef-152">Om du vill tillåta fil- och mappdelning med oautentiserade personer väljer du **Alla**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-152">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="b45ef-153">Om du vill se till att alla gäster måste autentisera, välj **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="b45ef-153">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="b45ef-154">Välj den mest tillåtande inställningen som behövs av en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b45ef-154">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar på SharePoint-organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="b45ef-156">Så här anger du delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-156">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="b45ef-157">Klicka på **SharePoint**under **Administrationscenter i administrationscentret**för Microsoft 365, i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="b45ef-157">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="b45ef-158">Klicka på **Dela**i administrationscentret för SharePoint i det vänstra navigeringscentret.</span><span class="sxs-lookup"><span data-stu-id="b45ef-158">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="b45ef-159">Kontrollera att extern delning för SharePoint är inställt **på Alla** eller Nya och **befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-159">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="b45ef-160">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-160">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="b45ef-161">Standardlänkinställningar för sharepoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-161">SharePoint organization level default link settings</span></span>

<span data-ttu-id="b45ef-162">Standardinställningarna för fil- och mapplänk avgör vilket länkalternativ som visas för användaren som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="b45ef-162">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="b45ef-163">Användare kan ändra länktypen till ett av de andra alternativen innan de delar om så önskas.</span><span class="sxs-lookup"><span data-stu-id="b45ef-163">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="b45ef-164">Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b45ef-164">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="b45ef-165">Välj den typ av länk som är markerad som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="b45ef-165">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="b45ef-166">**Alla med länken** - Välj det här alternativet om du förväntar dig att göra en hel del oautentiserade delning av filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="b45ef-166">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="b45ef-167">Om du vill tillåta *någon* länkar men är oroliga för oavsiktlig oautentiserade delning, överväga ett av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="b45ef-167">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="b45ef-168">Den här länktypen är bara tillgänglig om du har aktiverat **Alla delar.**</span><span class="sxs-lookup"><span data-stu-id="b45ef-168">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="b45ef-169">**Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelning ska vara med personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b45ef-169">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="b45ef-170">**Specifika personer** - Tänk på det här alternativet om du förväntar dig att göra en hel del fil- och mappdelning med gäster.</span><span class="sxs-lookup"><span data-stu-id="b45ef-170">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="b45ef-171">Denna typ av länk fungerar med gäster och kräver att de autentisera.</span><span class="sxs-lookup"><span data-stu-id="b45ef-171">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av inställningar för delning på SharePoint-organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="b45ef-173">Så här anger du standardlänkinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-173">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="b45ef-174">Navigera till sidan Delning i administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b45ef-174">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="b45ef-175">Under **Fil- och mapplänkar**väljer du den standarddelningslänk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="b45ef-175">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="b45ef-176">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-176">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="b45ef-177">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="b45ef-177">Create a team</span></span>

<span data-ttu-id="b45ef-178">Nästa steg är att skapa det team som du planerar att använda för att samarbeta med gäster.</span><span class="sxs-lookup"><span data-stu-id="b45ef-178">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="b45ef-179">Så här skapar du ett team</span><span class="sxs-lookup"><span data-stu-id="b45ef-179">To create a team</span></span>
1. <span data-ttu-id="b45ef-180">På fliken **Teams** i Teams klickar du på **Gå med i eller skapa ett lag** längst ned i den vänstra rutan.</span><span class="sxs-lookup"><span data-stu-id="b45ef-180">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="b45ef-181">Klicka på **Skapa ett team**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-181">Click **Create a team**.</span></span>
3. <span data-ttu-id="b45ef-182">Klicka på **Bygg ett team från grunden**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-182">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b45ef-183">Välj **Privat** eller **Offentlig**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-183">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="b45ef-184">Skriv ett namn och en beskrivning för teamet och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-184">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="b45ef-185">Klicka på **Hoppa över**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-185">Click **Skip**.</span></span>

<span data-ttu-id="b45ef-186">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="b45ef-186">We'll invite users later.</span></span> <span data-ttu-id="b45ef-187">Därefter är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för SharePoint-webbplatsen som är kopplad till teamet.</span><span class="sxs-lookup"><span data-stu-id="b45ef-187">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="b45ef-188">Delningsinställningar för SharePoint-webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-188">SharePoint site level sharing settings</span></span>

<span data-ttu-id="b45ef-189">Kontrollera delningsinställningarna på webbplatsnivå för att se till att de tillåter den typ av åtkomst som du vill ha för det här teamet.</span><span class="sxs-lookup"><span data-stu-id="b45ef-189">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="b45ef-190">Om du till exempel anger inställningarna på organisationsnivå till **Alla**, men vill att alla gäster ska autentisera för det här teamet, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-190">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Skärmbild av externa delningsinställningar för SharePoint-webbplatsen](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="b45ef-192">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="b45ef-192">To set site-level sharing settings</span></span>
1. <span data-ttu-id="b45ef-193">Expandera **Platser** i det vänstra navigeringscentret i administrationscentret för SharePoint och klicka på **Aktiva webbplatser.**</span><span class="sxs-lookup"><span data-stu-id="b45ef-193">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b45ef-194">Välj plats för det team som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="b45ef-194">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="b45ef-195">Klicka på **Dela**i menyfliksområdet .</span><span class="sxs-lookup"><span data-stu-id="b45ef-195">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="b45ef-196">Se till att delning är inställt **på Vem som helst** eller Nya och befintliga **gäster**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-196">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="b45ef-197">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-197">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="b45ef-198">Bjud in användare</span><span class="sxs-lookup"><span data-stu-id="b45ef-198">Invite users</span></span>

<span data-ttu-id="b45ef-199">Gästdelningsinställningarna är nu konfigurerade, så att du kan börja lägga till interna användare och gäster i ditt team.</span><span class="sxs-lookup"><span data-stu-id="b45ef-199">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="b45ef-200">Så här bjuder du in interna användare till ett team</span><span class="sxs-lookup"><span data-stu-id="b45ef-200">To invite internal users to a team</span></span>
1. <span data-ttu-id="b45ef-201">Klicka på **Fler alternativ** **\*\***( ) i gruppen och klicka sedan på **Lägg till medlem**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-201">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b45ef-202">Skriv namnet på den person som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="b45ef-202">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="b45ef-203">Klicka på **Lägg till**och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-203">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="b45ef-204">Så här bjuder du in gäster till ett team</span><span class="sxs-lookup"><span data-stu-id="b45ef-204">To invite guests to a team</span></span>
1. <span data-ttu-id="b45ef-205">Klicka på **Fler alternativ** **\*\***( ) i gruppen och klicka sedan på **Lägg till medlem**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-205">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b45ef-206">Skriv e-postadressen till den gäst som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="b45ef-206">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="b45ef-207">Klicka på **Redigera gästinformation**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-207">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="b45ef-208">Skriv gästens fullständiga namn och klicka på bocken.</span><span class="sxs-lookup"><span data-stu-id="b45ef-208">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="b45ef-209">Klicka på **Lägg till**och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="b45ef-209">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b45ef-210">Se även</span><span class="sxs-lookup"><span data-stu-id="b45ef-210">See Also</span></span>

[<span data-ttu-id="b45ef-211">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="b45ef-211">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="b45ef-212">Begränsa oavsiktlig exponering för filer när du delar med gäster</span><span class="sxs-lookup"><span data-stu-id="b45ef-212">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="b45ef-213">Skapa en säker gästdelningsmiljö</span><span class="sxs-lookup"><span data-stu-id="b45ef-213">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="b45ef-214">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="b45ef-214">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
