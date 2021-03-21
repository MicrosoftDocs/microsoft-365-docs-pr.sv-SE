---
title: Interaktion mellan grupptjänster
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interaktion mellan grupptjänster
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921030"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="c2627-103">Interaktion mellan grupptjänster</span><span class="sxs-lookup"><span data-stu-id="c2627-103">Groups services interactions</span></span>

<span data-ttu-id="c2627-104">Microsoft 365 Groups är ett vanligt material för flera tjänster och arbetsbelastningar på Microsoft 365-plattformen för att ge slutanvändarna anslutna upplevelser.</span><span class="sxs-lookup"><span data-stu-id="c2627-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="c2627-105">Det finns en Microsoft 365-grupp som tillhandahåller följande:</span><span class="sxs-lookup"><span data-stu-id="c2627-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="c2627-106">Ett sätt att hantera medlemskapet (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c2627-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="c2627-107">En plats där meddelanden och konversationer äger rum (Exchange-postlåda, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="c2627-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="c2627-108">En plats där filer ska lagras (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c2627-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="c2627-109">En kalender för schemaläggning (Exchange)</span><span class="sxs-lookup"><span data-stu-id="c2627-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="c2627-110">En anteckningsbok för att spara anteckningar (OneNote)</span><span class="sxs-lookup"><span data-stu-id="c2627-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="c2627-111">När grupper skapas etableras även ett antal andra resurser, men de visas inte förrän första gången nås från tjänsten:</span><span class="sxs-lookup"><span data-stu-id="c2627-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="c2627-112">En tavla för hantering av gruppuppgifter (Planner)</span><span class="sxs-lookup"><span data-stu-id="c2627-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="c2627-113">En arbetsyta för rapportering (Power BI)</span><span class="sxs-lookup"><span data-stu-id="c2627-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="c2627-114">Ett område för delade videor (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="c2627-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="c2627-115">Ett område för delade formulär (formulär)</span><span class="sxs-lookup"><span data-stu-id="c2627-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="c2627-116">I Microsoft 365 kan andra tjänster interagera med Microsoft 365-grupper för att ge gruppmedlemmar ytterligare funktioner.</span><span class="sxs-lookup"><span data-stu-id="c2627-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="c2627-117">Exempel på detta är:</span><span class="sxs-lookup"><span data-stu-id="c2627-117">Examples of this include:</span></span>

- <span data-ttu-id="c2627-118">Power-appar för appar</span><span class="sxs-lookup"><span data-stu-id="c2627-118">Power Apps for apps</span></span>
- <span data-ttu-id="c2627-119">Power Automate för arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="c2627-119">Power Automate for workflows</span></span>
- <span data-ttu-id="c2627-120">Project på webben och Översikt över vattenfallsbaserad projekthantering</span><span class="sxs-lookup"><span data-stu-id="c2627-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="c2627-121">Team för kanalbaserade konversationer</span><span class="sxs-lookup"><span data-stu-id="c2627-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="c2627-122">Yammer för intressegrupper</span><span class="sxs-lookup"><span data-stu-id="c2627-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="c2627-123">Användarinteraktion med grupper</span><span class="sxs-lookup"><span data-stu-id="c2627-123">User interactions with groups</span></span>

<span data-ttu-id="c2627-124">Microsoft 365-grupper kan skapas och hanteras från en mängd olika gränssnitt, både av administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="c2627-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="c2627-125">Administrativa funktioner</span><span class="sxs-lookup"><span data-stu-id="c2627-125">Administrative experiences</span></span>

<span data-ttu-id="c2627-126">Administratörer kan skapa och hantera Microsoft 365-grupper från flera av administrationscentret för arbetsbelastningen, kommandoradsgränssnitt som stöder skript samt anpassade appar som interagerar med Graph API.</span><span class="sxs-lookup"><span data-stu-id="c2627-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="c2627-127">Det enda undantaget är Yammer-grupper – som måste skapas från Yammer-webbgränssnittet.</span><span class="sxs-lookup"><span data-stu-id="c2627-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="c2627-128">**Relaterade inställningar**</span><span class="sxs-lookup"><span data-stu-id="c2627-128">**Related settings**</span></span>

<span data-ttu-id="c2627-129">I de olika administrativa gränssnitten som kan hantera gruppinställningar finns det flera överlappningar som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="c2627-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="c2627-130">**Administrationscenter för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="c2627-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="c2627-131">I administrationscentret för Microsoft 365 är gäståtkomst i grupper aktiverad som standard, eftersom ägare kan lägga till gäster.</span><span class="sxs-lookup"><span data-stu-id="c2627-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="c2627-132">Det finns inga ytterligare kontroller på organisationsnivå för grupper i det här administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="c2627-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="c2627-133">**Administrationscenter för Azure AD**</span><span class="sxs-lookup"><span data-stu-id="c2627-133">**Azure AD admin center**</span></span>

<span data-ttu-id="c2627-134">I administrationscentret för Azure AD finns kontroller för huruvida användare kan skapa grupper eller tilldela ägare i Azure-portaler, samt inställningar för förfallo- och namnprinciper.</span><span class="sxs-lookup"><span data-stu-id="c2627-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="c2627-135">I administrationscentret finns också ett antal åtgärder för att styra gästinbjudningar som går utöver de som finns i administrationscentret för Microsoft 365, till exempel möjlighet att begränsa huruvida personer som inte är ägare också kan bjuda in gäster.</span><span class="sxs-lookup"><span data-stu-id="c2627-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="c2627-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="c2627-136">**SharePoint**</span></span>

<span data-ttu-id="c2627-137">SharePoint-webbplatser skapas med säkerhetsgrupper som ägare, medlemmar och besökare, med de två första som matchar deras Microsoft 365-gruppmotsvarsvarumer.</span><span class="sxs-lookup"><span data-stu-id="c2627-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="c2627-138">Medlemskap för SharePoint Online-webbplatser hanteras i allmänhet av den associerade Microsoft 365-gruppen, men det är inte en dubbelriktad relation.</span><span class="sxs-lookup"><span data-stu-id="c2627-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="c2627-139">Ändringar av medlemskap på Microsoft 365-gruppnivå återspeglas i SharePoint, men om medlemskapet ändras i SharePoint-gruppen återspeglas inte detta i Microsoft 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2627-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="c2627-140">Användarupplevelser</span><span class="sxs-lookup"><span data-stu-id="c2627-140">User experiences</span></span>

<span data-ttu-id="c2627-141">Slutanvändarna kan skapa grupper från flera av tjänsterna i Microsoft 365 och i andra kan de bara dela med en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="c2627-142">Följande tjänster gör det möjligt att skapa grupper av slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="c2627-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="c2627-143">Outlook Planner-projekt för webben SharePoint Streama Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="c2627-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="c2627-144">**Begränsning när grupper skapas**</span><span class="sxs-lookup"><span data-stu-id="c2627-144">**Restriction of group creation**</span></span>

<span data-ttu-id="c2627-145">En vanlig metod för att styra utstråningen av team är att begränsa vilka användare som kan skapa dem.</span><span class="sxs-lookup"><span data-stu-id="c2627-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="c2627-146">Det kan bara göras genom att begränsa skapandet av grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="c2627-147">Det här påverkar möjligheten att skapa grupper från andra tjänster där det kan vara nödvändigt för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="c2627-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="c2627-148">Microsoft 365 Groups stöder inte möjligheten att begränsa skapandet av grupper från vissa appar eller tjänster och samtidigt tillåta det från andra.</span><span class="sxs-lookup"><span data-stu-id="c2627-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="c2627-149">Upplevelsen av att skapa gruppbegränsningar varierar mellan program och tjänster:</span><span class="sxs-lookup"><span data-stu-id="c2627-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="c2627-150">App eller tjänst</span><span class="sxs-lookup"><span data-stu-id="c2627-150">App or service</span></span>|<span data-ttu-id="c2627-151">Upplevelse</span><span class="sxs-lookup"><span data-stu-id="c2627-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="c2627-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="c2627-152">Outlook</span></span>|<span data-ttu-id="c2627-153">**Alternativet Ny** grupp tas bort från menyn Nytt på sidan Personer</span><span class="sxs-lookup"><span data-stu-id="c2627-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="c2627-154">Planner</span><span class="sxs-lookup"><span data-stu-id="c2627-154">Planner</span></span>|<span data-ttu-id="c2627-155">**Ny plan** förklarar att skapande av grupper har inaktiverats och ger möjlighet att lägga till planen i en befintlig grupp</span><span class="sxs-lookup"><span data-stu-id="c2627-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="c2627-156">Project för webben och Översikt</span><span class="sxs-lookup"><span data-stu-id="c2627-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="c2627-157">**På menyn Skapa** grupp förklaras att skapandet av grupper är begränsat och föreslår att en befintlig grupp används.</span><span class="sxs-lookup"><span data-stu-id="c2627-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="c2627-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2627-158">SharePoint</span></span>|<span data-ttu-id="c2627-159">Det går fortfarande att skapa en gruppwebbplats som inte är ansluten till en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="c2627-160">Strömma</span><span class="sxs-lookup"><span data-stu-id="c2627-160">Stream</span></span>|<span data-ttu-id="c2627-161">**Gruppalternativet** visas inte under **menyn Skapa.**</span><span class="sxs-lookup"><span data-stu-id="c2627-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="c2627-162">Teams</span><span class="sxs-lookup"><span data-stu-id="c2627-162">Teams</span></span>|<span data-ttu-id="c2627-163">Användaren kan inte skapa ett team med en ny grupp men kan fortfarande skapa ett team som använder en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="c2627-164">**Knappen Skapa ett team** ersätts med **Skapa team från en grupp.**</span><span class="sxs-lookup"><span data-stu-id="c2627-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="c2627-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="c2627-165">Yammer</span></span>|<span data-ttu-id="c2627-166">**Alternativet Skapa en grupp** tas bort från huvudnavigeringen för grupper/communities.</span><span class="sxs-lookup"><span data-stu-id="c2627-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="c2627-167">Interaktion mellan tjänster med grupper</span><span class="sxs-lookup"><span data-stu-id="c2627-167">Services interactions with groups</span></span>

<span data-ttu-id="c2627-168">Gå till groups i Microsoft 365-affischen för information om olika typer av grupper, hur de skapas och hanteras och några rekommendationer för styrning.</span><span class="sxs-lookup"><span data-stu-id="c2627-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="c2627-169">[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="c2627-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="c2627-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c2627-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="c2627-171">Följande tabell innehåller en översikt över hur Microsoft 365 Groups interagerar med olika tjänster:</span><span class="sxs-lookup"><span data-stu-id="c2627-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="c2627-172">Produkt</span><span class="sxs-lookup"><span data-stu-id="c2627-172">Product</span></span>|<span data-ttu-id="c2627-173">Funktioner</span><span class="sxs-lookup"><span data-stu-id="c2627-173">Features</span></span>|<span data-ttu-id="c2627-174">Gör tjänsten</span><span class="sxs-lookup"><span data-stu-id="c2627-174">Does the service</span></span><br><span data-ttu-id="c2627-175">finns det ingen grupp?</span><span class="sxs-lookup"><span data-stu-id="c2627-175">exist without a group?</span></span>|<span data-ttu-id="c2627-176">Kan tjänsten</span><span class="sxs-lookup"><span data-stu-id="c2627-176">Can the service</span></span><br><span data-ttu-id="c2627-177">skapa en grupp?</span><span class="sxs-lookup"><span data-stu-id="c2627-177">create a group?</span></span>|<span data-ttu-id="c2627-178">Tar bort</span><span class="sxs-lookup"><span data-stu-id="c2627-178">Does deleting the</span></span><br><span data-ttu-id="c2627-179">instans ta bort gruppen?</span><span class="sxs-lookup"><span data-stu-id="c2627-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="c2627-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="c2627-180">Azure AD</span></span>|<span data-ttu-id="c2627-181">Medlemskap, gruppkontroller, gäster</span><span class="sxs-lookup"><span data-stu-id="c2627-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="c2627-182">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-182">Yes</span></span>|<span data-ttu-id="c2627-183">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-183">Yes</span></span>|<span data-ttu-id="c2627-184">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-184">Yes</span></span>|
|<span data-ttu-id="c2627-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="c2627-185">Exchange</span></span>|<span data-ttu-id="c2627-186">Kalender, postlåda</span><span class="sxs-lookup"><span data-stu-id="c2627-186">Calendar, mailbox</span></span>|<span data-ttu-id="c2627-187">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-187">Yes</span></span>|<span data-ttu-id="c2627-188">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-188">Yes</span></span>|<span data-ttu-id="c2627-189">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-189">Yes</span></span>|
|<span data-ttu-id="c2627-190">Formulär</span><span class="sxs-lookup"><span data-stu-id="c2627-190">Forms</span></span>|<span data-ttu-id="c2627-191">Formulär</span><span class="sxs-lookup"><span data-stu-id="c2627-191">Form</span></span>|<span data-ttu-id="c2627-192">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-192">Yes</span></span>|<span data-ttu-id="c2627-193">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-193">No</span></span>|<span data-ttu-id="c2627-194">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-194">No</span></span>|
|<span data-ttu-id="c2627-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="c2627-195">OneNote</span></span>|<span data-ttu-id="c2627-196">Anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="c2627-196">Notebook</span></span>|<span data-ttu-id="c2627-197">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-197">Yes</span></span>|<span data-ttu-id="c2627-198">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-198">No</span></span>|<span data-ttu-id="c2627-199">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-199">No</span></span>|
|<span data-ttu-id="c2627-200">Planner</span><span class="sxs-lookup"><span data-stu-id="c2627-200">Planner</span></span>|<span data-ttu-id="c2627-201">Uppgiftstavla</span><span class="sxs-lookup"><span data-stu-id="c2627-201">Task board</span></span>|<span data-ttu-id="c2627-202">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-202">No</span></span>|<span data-ttu-id="c2627-203">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-203">Yes</span></span>|<span data-ttu-id="c2627-204">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-204">Yes</span></span>|
|<span data-ttu-id="c2627-205">Appen Power Apps</span><span class="sxs-lookup"><span data-stu-id="c2627-205">Power Apps app</span></span>|<span data-ttu-id="c2627-206">Program</span><span class="sxs-lookup"><span data-stu-id="c2627-206">App</span></span>|<span data-ttu-id="c2627-207">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-207">Yes</span></span>|<span data-ttu-id="c2627-208">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-208">No</span></span>|<span data-ttu-id="c2627-209">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-209">No</span></span>|
|<span data-ttu-id="c2627-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="c2627-210">Power Automate</span></span>|<span data-ttu-id="c2627-211">Arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c2627-211">Workflow</span></span>|<span data-ttu-id="c2627-212">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-212">Yes</span></span>|<span data-ttu-id="c2627-213">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-213">No</span></span>|<span data-ttu-id="c2627-214">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-214">No</span></span>|
|<span data-ttu-id="c2627-215">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="c2627-215">Power BI (classic)</span></span>|<span data-ttu-id="c2627-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="c2627-216">Workspace</span></span>|<span data-ttu-id="c2627-217">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-217">No</span></span>|<span data-ttu-id="c2627-218">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-218">Yes</span></span>|<span data-ttu-id="c2627-219">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-219">Yes</span></span>|
|<span data-ttu-id="c2627-220">Power BI (nytt)</span><span class="sxs-lookup"><span data-stu-id="c2627-220">Power BI (new)</span></span>|<span data-ttu-id="c2627-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="c2627-221">Workspace</span></span>|<span data-ttu-id="c2627-222">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-222">Yes</span></span>|<span data-ttu-id="c2627-223">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-223">No</span></span>|<span data-ttu-id="c2627-224">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-224">Yes</span></span>|
|<span data-ttu-id="c2627-225">Project för webben</span><span class="sxs-lookup"><span data-stu-id="c2627-225">Project for the web</span></span>|<span data-ttu-id="c2627-226">Projektplan</span><span class="sxs-lookup"><span data-stu-id="c2627-226">Project plan</span></span>|<span data-ttu-id="c2627-227">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-227">Yes</span></span>|<span data-ttu-id="c2627-228">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-228">Yes</span></span>|<span data-ttu-id="c2627-229">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-229">No</span></span>|
|<span data-ttu-id="c2627-230">Översikt</span><span class="sxs-lookup"><span data-stu-id="c2627-230">Roadmap</span></span>|<span data-ttu-id="c2627-231">Översikt</span><span class="sxs-lookup"><span data-stu-id="c2627-231">Roadmap</span></span>|<span data-ttu-id="c2627-232">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-232">Yes</span></span>|<span data-ttu-id="c2627-233">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-233">Yes</span></span>|<span data-ttu-id="c2627-234">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-234">No</span></span>|
|<span data-ttu-id="c2627-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2627-235">SharePoint</span></span>|<span data-ttu-id="c2627-236">Webbplats</span><span class="sxs-lookup"><span data-stu-id="c2627-236">Site</span></span>|<span data-ttu-id="c2627-237">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-237">Yes</span></span>|<span data-ttu-id="c2627-238">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-238">Yes</span></span>|<span data-ttu-id="c2627-239">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-239">Yes</span></span>|
|<span data-ttu-id="c2627-240">Strömma</span><span class="sxs-lookup"><span data-stu-id="c2627-240">Stream</span></span>|<span data-ttu-id="c2627-241">Kanal, video</span><span class="sxs-lookup"><span data-stu-id="c2627-241">Channel, video</span></span>|<span data-ttu-id="c2627-242">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-242">Yes</span></span>|<span data-ttu-id="c2627-243">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-243">Yes</span></span>|<span data-ttu-id="c2627-244">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-244">Yes</span></span>|
|<span data-ttu-id="c2627-245">Teams</span><span class="sxs-lookup"><span data-stu-id="c2627-245">Teams</span></span>|<span data-ttu-id="c2627-246">Team</span><span class="sxs-lookup"><span data-stu-id="c2627-246">Team</span></span>|<span data-ttu-id="c2627-247">Nej</span><span class="sxs-lookup"><span data-stu-id="c2627-247">No</span></span>|<span data-ttu-id="c2627-248">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-248">Yes</span></span>|<span data-ttu-id="c2627-249">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-249">Yes</span></span>|
|<span data-ttu-id="c2627-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="c2627-250">Yammer</span></span>|<span data-ttu-id="c2627-251">Grupp</span><span class="sxs-lookup"><span data-stu-id="c2627-251">Group</span></span>|<span data-ttu-id="c2627-252">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-252">Yes</span></span>|<span data-ttu-id="c2627-253">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-253">Yes</span></span>|<span data-ttu-id="c2627-254">Ja</span><span class="sxs-lookup"><span data-stu-id="c2627-254">Yes</span></span>|

<span data-ttu-id="c2627-255">I tabellen ovan ges en översikt över gruppinteraktion med Microsoft 365-tjänster, men det finns ett antal nyanser och felaktigheter som du bör förstå.</span><span class="sxs-lookup"><span data-stu-id="c2627-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="c2627-256">I följande avsnitt får du en mer detaljerad bild av de specifika arbetsbelastningara och deras interaktioner med grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="c2627-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="c2627-257">Azure AD</span></span>

<span data-ttu-id="c2627-258">Azure AD innehåller de underliggande identitetshanteringsfunktionerna i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2627-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="c2627-259">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-260">Gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="c2627-260">Group membership</span></span>
- <span data-ttu-id="c2627-261">Namnprincip</span><span class="sxs-lookup"><span data-stu-id="c2627-261">Naming policy</span></span>
- <span data-ttu-id="c2627-262">Förfalloprincip</span><span class="sxs-lookup"><span data-stu-id="c2627-262">Expiration policy</span></span>
- <span data-ttu-id="c2627-263">Gäster</span><span class="sxs-lookup"><span data-stu-id="c2627-263">Guests</span></span>
- <span data-ttu-id="c2627-264">Begränsning av skapande av grupp</span><span class="sxs-lookup"><span data-stu-id="c2627-264">Restriction of Group creation</span></span>

<span data-ttu-id="c2627-265">**Kan Azure AD skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="c2627-266">Ja, Microsoft 365-grupper kan skapas från Azure AD antingen via administrationswebbportalen, via PowerShell eller Graph API.</span><span class="sxs-lookup"><span data-stu-id="c2627-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="c2627-267">**Finns Azure AD utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="c2627-268">Ja, Azure AD utför ett stort antal tjänster som inte har någon relation till Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="c2627-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="c2627-269">Varje Microsoft 365-grupp representeras som ett objekt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2627-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="c2627-270">**Kan det finnas flera instanser av Azure AD per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="c2627-271">Nej, det finns bara en instans av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2627-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="c2627-272">**Kan Azure AD associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="c2627-273">Ja, eftersom Azure AD är den underliggande plattform som tillhandahåller tjänsten för gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="c2627-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="c2627-274">**Kan Azure AD:s koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="c2627-275">Nej, Azure AD är den underliggande plattformen där grupper finns.</span><span class="sxs-lookup"><span data-stu-id="c2627-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="c2627-276">**Raderas gruppen om instansen tas bort?**</span><span class="sxs-lookup"><span data-stu-id="c2627-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="c2627-277">Om du tar bort gruppen i Azure AD tas relevanta grupprelaterade tjänster och relevant innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="c2627-278">Teams</span><span class="sxs-lookup"><span data-stu-id="c2627-278">Teams</span></span>

<span data-ttu-id="c2627-279">Teams är en chattcentreerad arbetsyta som förbättrar samarbetet genom att ge ett enda gränssnitt för att interagera med olika Microsoft- och tredjepartstjänster.</span><span class="sxs-lookup"><span data-stu-id="c2627-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="c2627-280">När ett team skapas döljs som standard postlådan och kalendern som är kopplad till Microsoft 365-gruppen från både den globala adresslistan i Exchange och Outlook.</span><span class="sxs-lookup"><span data-stu-id="c2627-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="c2627-281">En administratör kan manuellt åsidosätta detta om användaren vill använda både Outlook och Teams i samma Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="c2627-282">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-283">Konversationer</span><span class="sxs-lookup"><span data-stu-id="c2627-283">Conversations</span></span>
- <span data-ttu-id="c2627-284">Kanaler & flikar</span><span class="sxs-lookup"><span data-stu-id="c2627-284">Channels & tabs</span></span>
- <span data-ttu-id="c2627-285">Möten</span><span class="sxs-lookup"><span data-stu-id="c2627-285">Meetings</span></span>

<span data-ttu-id="c2627-286">**Kan Teams skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="c2627-287">Ja, när du skapar ett nytt team skapas en ny Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="c2627-288">Det går även att skapa ett team för en befintlig grupp som inte har någon för närvarande.</span><span class="sxs-lookup"><span data-stu-id="c2627-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="c2627-289">**Finns grupper utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="c2627-290">Nej, det går inte att ha ett team utan en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="c2627-291">**Kan det finnas flera team per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="c2627-292">Nej, relationen mellan ett team och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="c2627-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="c2627-293">**Kan ett team associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-294">Nej, själva teamet kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="c2627-295">**Kan ett teams koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="c2627-296">Nej, teamet kan aldrig bara associeras med gruppen som det ursprungligen var kopplat till.</span><span class="sxs-lookup"><span data-stu-id="c2627-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="c2627-297">**Raderas gruppen om du tar bort teamet?**</span><span class="sxs-lookup"><span data-stu-id="c2627-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="c2627-298">Ja, om du tar bort teamet i Microsoft Teams tas gruppen, grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="c2627-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="c2627-299">Exchange</span></span>

<span data-ttu-id="c2627-300">Med Exchange Online får du meddelanden, kalender, kontakter och tillhörande funktioner.</span><span class="sxs-lookup"><span data-stu-id="c2627-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="c2627-301">Inom en grupp är endast en enda resurs associerad – i motsats till en hel tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="c2627-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="c2627-302">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-303">Postlåda och kalender</span><span class="sxs-lookup"><span data-stu-id="c2627-303">Mailbox and calendar</span></span>
- <span data-ttu-id="c2627-304">Möjlighet att skicka e-post till alla gruppmedlemmar</span><span class="sxs-lookup"><span data-stu-id="c2627-304">Ability to email all Group members</span></span>
- <span data-ttu-id="c2627-305">Lagring av Teams-kanalkonversationer i eDiscovery-syfte, Planner-kommentarer</span><span class="sxs-lookup"><span data-stu-id="c2627-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="c2627-306">**Kan Exchange skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="c2627-307">Ja, det går att skapa en grupp från administrationscentret för Exchange Online och från Outlook.</span><span class="sxs-lookup"><span data-stu-id="c2627-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="c2627-308">Du kan också konvertera Exchange-distributionslistor till Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="c2627-309">**Finns Exchange utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="c2627-310">Ja, Exchange Online tillhandahåller ett antal tjänster, inklusive delade postlådor och kalendrar, utan någon gruppassociatorganisation.</span><span class="sxs-lookup"><span data-stu-id="c2627-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="c2627-311">**Kan det finnas flera instanser av Exchange-postlådor eller -kalendrar per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="c2627-312">Nej, det kan bara finnas en enda Exchange Online-postlåda och kalender för en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="c2627-313">**Kan Exchange-postlådor och -kalendrar associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-314">Nej, postlådan och kalendern har en 1:1-relation med gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2627-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="c2627-315">Det går att dela postlådan med andra användare eller grupper, men det skapar ingen form av tjänstassociating.</span><span class="sxs-lookup"><span data-stu-id="c2627-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="c2627-316">**Kan Exchange-postlådan eller kalenderns koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="c2627-317">Nej, postlådan och kalendern kan inte ändras till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="c2627-318">Innehållet kan dock flyttas från en postlåda till en annan i Outlook eller med hjälp av ett verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="c2627-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="c2627-319">**Tas gruppen bort när du tar bort postlådan?**</span><span class="sxs-lookup"><span data-stu-id="c2627-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="c2627-320">Ja, om du tar bort postlådan i Exchange tas gruppen samt grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="c2627-321">Formulär</span><span class="sxs-lookup"><span data-stu-id="c2627-321">Forms</span></span>

<span data-ttu-id="c2627-322">Forms tillhandahåller webbaserade undersökningar och test.</span><span class="sxs-lookup"><span data-stu-id="c2627-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="c2627-323">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-324">Äganderätt till formulär</span><span class="sxs-lookup"><span data-stu-id="c2627-324">Ownership of forms</span></span>

<span data-ttu-id="c2627-325">**Kan formulär skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="c2627-326">Nej, Formulär kan inte skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="c2627-327">**Finns formulär utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="c2627-328">Ja, undersökningar och test kan skapas direkt i en slutanvändares konto.</span><span class="sxs-lookup"><span data-stu-id="c2627-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="c2627-329">**Kan det finnas flera formulär per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="c2627-330">Ja, det kan finnas flera formulär kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="c2627-331">**Kan formulär kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-332">Nej, ett formulär kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="c2627-333">**Kan ett formulärs koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="c2627-334">Nej, när ett formulär är kopplat till en grupp (skapas direkt i, eller ägarskap som överförs från en enskild person) kan det inte flyttas till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="c2627-335">**Tas gruppen bort när du tar bort formuläret?**</span><span class="sxs-lookup"><span data-stu-id="c2627-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="c2627-336">Nej, det går inte att ta bort en grupp från Forms-gränssnittet, bara enskilda formulär.</span><span class="sxs-lookup"><span data-stu-id="c2627-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="c2627-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="c2627-337">OneNote</span></span>

<span data-ttu-id="c2627-338">OneNote är ett digitalt anteckningsboksprogram.</span><span class="sxs-lookup"><span data-stu-id="c2627-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="c2627-339">OneNote-anteckningsboken som skapats med en grupp är en fil på den associerade SharePoint-webbplatsen i stället för en gruppansluten tjänst.</span><span class="sxs-lookup"><span data-stu-id="c2627-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="c2627-340">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-341">Delad anteckningsbok (lagrad i det grupprelaterade SharePoint-biblioteket)</span><span class="sxs-lookup"><span data-stu-id="c2627-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="c2627-342">**Kan OneNote skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="c2627-343">Nej, OneNote-programmet kan inte skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="c2627-344">**Finns OneNote-anteckningsböcker utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="c2627-345">Ja, anteckningsböcker kan skapas direkt på OneDrive eller på andra delade platser.</span><span class="sxs-lookup"><span data-stu-id="c2627-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="c2627-346">**Kan det finnas flera OneNote-anteckningsböcker per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="c2627-347">Ja, en anteckningsbok skapas som standard och andra kan läggas till, men länkar till OneNote från grupprelaterade tjänster går alltid till standardanteckningsboken.</span><span class="sxs-lookup"><span data-stu-id="c2627-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="c2627-348">**Kan en OneNote-anteckningsbok associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-349">Nej, anteckningsboken lagras i det grupprelaterade SharePoint-webbplatsbiblioteket och länkas från olika gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="c2627-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="c2627-350">Men den kan delas med andra grupper på samma sätt som den kan delas med enskilda personer.</span><span class="sxs-lookup"><span data-stu-id="c2627-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="c2627-351">**Kan anteckningsbokens koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="c2627-352">Nej, själva anteckningsboken är kopplad till gruppen och kan kommas åt direkt från andra gruppanslutna tjänster, men innehållet kan flyttas från en anteckningsbok till en annan i OneNote-programmet.</span><span class="sxs-lookup"><span data-stu-id="c2627-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="c2627-353">**Tas gruppen bort när du tar bort anteckningsboken?**</span><span class="sxs-lookup"><span data-stu-id="c2627-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="c2627-354">Nej, men om OneNote-anteckningsboken tas bort kan det finnas brutna länkar i vissa grupprelaterade tjänster.</span><span class="sxs-lookup"><span data-stu-id="c2627-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="c2627-355">Planner</span><span class="sxs-lookup"><span data-stu-id="c2627-355">Planner</span></span>

<span data-ttu-id="c2627-356">Planner är en enkel tjänst för uppgiftshantering för grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="c2627-357">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-358">Tavla för hantering av gruppuppgifter</span><span class="sxs-lookup"><span data-stu-id="c2627-358">Board for managing group tasks</span></span>

<span data-ttu-id="c2627-359">**Kan Planner skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="c2627-360">Ja, när du skapar en plan skapas en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="c2627-361">**Finns det en Planner-tavla utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="c2627-362">Nej, en plan måste vara kopplad till en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="c2627-363">**Kan det finnas flera planer per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="c2627-364">Ja, det kan finnas flera planer per grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="c2627-365">**Kan en plan associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-366">Nej, en plan förlitar sig enbart på gruppmedlemskapet för att avgöra åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="c2627-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="c2627-367">**Kan en plans koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="c2627-368">Nej, men när en plan kopieras skapas en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="c2627-369">En grupp som har skapats av ett annat program visas inte automatiskt i Planner för en användare.</span><span class="sxs-lookup"><span data-stu-id="c2627-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="c2627-370">För att komma åt tavlan först måste de öppna den från ett annat gruppbaserat gränssnitt, till exempel Outlook.</span><span class="sxs-lookup"><span data-stu-id="c2627-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="c2627-371">**Tas gruppen bort när planen tas bort?**</span><span class="sxs-lookup"><span data-stu-id="c2627-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="c2627-372">Ja, om du tar bort planen tas gruppen och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="c2627-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="c2627-373">Power Apps</span></span>

<span data-ttu-id="c2627-374">Med Power Apps finns en arbetsyta för programutveckling utan kod.</span><span class="sxs-lookup"><span data-stu-id="c2627-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="c2627-375">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-376">Appar kan delas med en grupp som ska köras och ändras</span><span class="sxs-lookup"><span data-stu-id="c2627-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="c2627-377">**Kan Power-appar skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="c2627-378">Nej, Power Apps kan inte skapa en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="c2627-379">**Finns Power Apps utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="c2627-380">Ja, appar kan skapas i Power-appar och finnas i creators-kontot tills de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="c2627-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="c2627-381">**Kan det finnas flera appar per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="c2627-382">Ja, det kan finnas flera program som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="c2627-383">**Kan appar kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-384">Ja, en app kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="c2627-385">**Kan en apps koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="c2627-386">Ja, eftersom kopplingen mellan Power Apps och en Microsoft 365-grupp bara delas – appen finns fortfarande kvar hos skaparen.</span><span class="sxs-lookup"><span data-stu-id="c2627-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2627-387">[Grupper måste vara säkerhetsaktiverade innan appar kan delas med dem.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="c2627-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="c2627-388">**Raderas gruppen om du tar bort programmet?**</span><span class="sxs-lookup"><span data-stu-id="c2627-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="c2627-389">Nej, apparna är inte kopplade till den andra gruppen än den som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="c2627-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="c2627-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="c2627-390">Power Automate</span></span>

<span data-ttu-id="c2627-391">Med Power Automate (tidigare Microsoft Flow) får du arbetsflöden och automatiseringstjänster.</span><span class="sxs-lookup"><span data-stu-id="c2627-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="c2627-392">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-393">Arbetsflöden kan delas med en grupp som ska köras och ändras.</span><span class="sxs-lookup"><span data-stu-id="c2627-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="c2627-394">**Kan Power Automate skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="c2627-395">Nej, Power Automate kan inte skapa en Microsoft 365-grupp när den är kopplad till en.</span><span class="sxs-lookup"><span data-stu-id="c2627-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="c2627-396">Det går dock att skapa ett flöde som utför olika åtgärder, till exempel skapa en Azure AD-säkerhetsgrupp eller uppdatera medlemskap i en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="c2627-397">**Finns flöden utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="c2627-398">Ja, flöden kan skapas i Power Automate och finnas i creators-kontot tills de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="c2627-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="c2627-399">**Kan det finnas flera flöden per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="c2627-400">Ja, det kan finnas flera flöden som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="c2627-401">**Kan ett flöde associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-402">Ja, ett flöde kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="c2627-403">**Kan ett flödes koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="c2627-404">Ja, eftersom kopplingen mellan Power Automate och en Microsoft 365-grupp bara delas , finns flödet fortfarande kvar hos skaparen.</span><span class="sxs-lookup"><span data-stu-id="c2627-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="c2627-405">**Tas gruppen bort när du tar bort ett flöde?**</span><span class="sxs-lookup"><span data-stu-id="c2627-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="c2627-406">Nej, precis som i Power Apps är flödena inte anslutna till den andra gruppen än den som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="c2627-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="c2627-407">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="c2627-407">Power BI (classic)</span></span>

<span data-ttu-id="c2627-408">Power BI tillhandahåller interaktiva datadrivna instrumentpaneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="c2627-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="c2627-409">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-410">Datarapportering</span><span class="sxs-lookup"><span data-stu-id="c2627-410">Data reporting</span></span>

<span data-ttu-id="c2627-411">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="c2627-412">Ja, när du skapar en klassisk arbetsyta skapas en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="c2627-413">**Finns det en klassisk arbetsyta i Power BI utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="c2627-414">Nej, [en klassisk arbetsyta i Power BI måste vara kopplad till en grupp](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="c2627-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="c2627-415">**Kan det finnas flera Power BI-arbetsytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="c2627-416">Nej, relationen mellan en klassisk arbetsyta och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="c2627-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="c2627-417">**Kan en arbetsyta kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-418">Tekniskt sett är det inget, men när den klassiska arbetsytan skapas med gruppen kan innehållet delas utanför gruppen med användare och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="c2627-419">**Kan arbetsytans koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="c2627-420">Nej, den klassiska arbetsytan är kopplad till gruppen, men innehållet kan flyttas från en arbetsyta till en annan i Power BI-gränssnittet eller genom att exportera innehåll lokalt.</span><span class="sxs-lookup"><span data-stu-id="c2627-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="c2627-421">**Tas gruppen bort när du tar bort arbetsytan?**</span><span class="sxs-lookup"><span data-stu-id="c2627-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="c2627-422">Ja, om du tar bort arbetsytan i Power BI tas grupp- och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="c2627-423">Power BI (nytt)</span><span class="sxs-lookup"><span data-stu-id="c2627-423">Power BI (new)</span></span>

<span data-ttu-id="c2627-424">Power BI tillhandahåller interaktiva datadrivna instrumentpaneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="c2627-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="c2627-425">När du skapar en ny arbetsyta i Power BI skapas inte en Microsoft 365-grupp, och om du skapar en grupp på något annat sätt skapas en ny (inte klassisk) arbetsyta i Power BI.</span><span class="sxs-lookup"><span data-stu-id="c2627-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="c2627-426">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="c2627-427">Datarapportering</span><span class="sxs-lookup"><span data-stu-id="c2627-427">Data reporting</span></span>

<span data-ttu-id="c2627-428">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="c2627-429">Nej, det går inte att skapa en Microsoft 365-grupp från det nya Power BI-gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="c2627-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="c2627-430">**Finns den nya Power BI-arbetsytan utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="c2627-431">Ja, det går att skapa rapporter och arbetsytor i Power BI som inte är kopplade till Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="c2627-432">**Kan det finnas flera arbetsytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="c2627-433">Ja, [flera arbetsytor som skapas av Power BI kan delas med en enda grupp](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="c2627-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="c2627-434">**Kan en arbetsyta kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-435">Nej, en arbetsyta som skapas av Power BI kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="c2627-436">**Kan en arbetsytas koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="c2627-437">Ja och nej.</span><span class="sxs-lookup"><span data-stu-id="c2627-437">Yes and no.</span></span> <span data-ttu-id="c2627-438">Arbetsytor som skapas i Power BI kan bara associeras med en enda grupp åt gången, men du kan när som helst ändra kopplingen.</span><span class="sxs-lookup"><span data-stu-id="c2627-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="c2627-439">En arbetsyta som skapats i Power BI av en grupp är permanent kopplad till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2627-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="c2627-440">**Tas gruppen bort när du tar bort arbetsytan?**</span><span class="sxs-lookup"><span data-stu-id="c2627-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="c2627-441">Ja, om du tar bort arbetsytan i Power BI tas gruppen och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="c2627-442">Project för webben</span><span class="sxs-lookup"><span data-stu-id="c2627-442">Project for the web</span></span>

<span data-ttu-id="c2627-443">Med Project för webben kan du skapa projektplaner, Gantt-diagram och översikter.</span><span class="sxs-lookup"><span data-stu-id="c2627-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="c2627-444">Huvudfunktioner för grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-444">Key features provided to groups.</span></span>

- <span data-ttu-id="c2627-445">Projektplaner</span><span class="sxs-lookup"><span data-stu-id="c2627-445">Project plans</span></span>

<span data-ttu-id="c2627-446">**Kan Project för webben skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="c2627-447">Ja, det går att skapa en ny Microsoft 365-grupp direkt från Project för webben.</span><span class="sxs-lookup"><span data-stu-id="c2627-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="c2627-448">**Finns det projekt utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="c2627-449">Ja, projekt kan finnas utan att vara kopplade till en Microsoft 365-grupp, men tilldelning av uppgifter kräver gruppassociat koppling.</span><span class="sxs-lookup"><span data-stu-id="c2627-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="c2627-450">**Kan det finnas flera projekt per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="c2627-451">Ja, det går att ansluta flera projekt i en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="c2627-452">**Kan projektet associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-453">Nej, ett projekt kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="c2627-454">**Kan ett projekts koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="c2627-455">Nej, när kopplingen till en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="c2627-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="c2627-456">**Tas gruppen bort när du tar bort projektet?**</span><span class="sxs-lookup"><span data-stu-id="c2627-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="c2627-457">Nej, gruppen tas inte bort om du tar bort projektet i Project för webben.</span><span class="sxs-lookup"><span data-stu-id="c2627-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="c2627-458">Översikt</span><span class="sxs-lookup"><span data-stu-id="c2627-458">Roadmap</span></span>

<span data-ttu-id="c2627-459">Översikt ger möjlighet att skapa projektöversikter med Project för webben och Project Online.</span><span class="sxs-lookup"><span data-stu-id="c2627-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="c2627-460">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-461">Project-översikter</span><span class="sxs-lookup"><span data-stu-id="c2627-461">Project roadmaps</span></span>

<span data-ttu-id="c2627-462">**Kan Översikt skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="c2627-463">Ja, det går att skapa en ny Microsoft 365-grupp direkt från översikten.</span><span class="sxs-lookup"><span data-stu-id="c2627-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="c2627-464">**Finns Översikt utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="c2627-465">Ja, det kan finnas översikter utan att vara kopplade till en Microsoft 365-grupp, men delning av översikten kräver gruppanslutning.</span><span class="sxs-lookup"><span data-stu-id="c2627-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="c2627-466">**Kan det finnas flera översikter per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="c2627-467">Ja, det går att ansluta flera översikter till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="c2627-468">**Kan en översikt associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-469">Nej, en översikt kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="c2627-470">**Kan en översiktsorganisation med en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="c2627-471">Nej, när kopplingen till en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="c2627-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="c2627-472">**Tas gruppen bort när du tar bort översikten?**</span><span class="sxs-lookup"><span data-stu-id="c2627-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="c2627-473">Nej, gruppen tas inte bort när du tar bort översikten.</span><span class="sxs-lookup"><span data-stu-id="c2627-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="c2627-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c2627-474">SharePoint</span></span>

<span data-ttu-id="c2627-475">SharePoint är en webbaserad innehållshanteringsplattform som tillhandahåller bland annat lagringstjänster för ett antal Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="c2627-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="c2627-476">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-477">Dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="c2627-477">Document library</span></span>
- <span data-ttu-id="c2627-478">Bibliotek för lagring av OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="c2627-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="c2627-479">Lagring av Wiki-filer i Teams</span><span class="sxs-lookup"><span data-stu-id="c2627-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="c2627-480">**Kan SharePoint skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="c2627-481">Ja, en Microsoft 365-grupp skapas som standard när du skapar en gruppwebbplats i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c2627-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="c2627-482">Det går även att skapa en grupp och, om du vill, ett team för en befintlig webbplats.</span><span class="sxs-lookup"><span data-stu-id="c2627-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="c2627-483">**Finns SharePoint-webbplatser utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="c2627-484">Ja, SharePoint erbjuder ett antal icke-grupprelaterade tjänster och webbplatser, till exempel kommunikations- och navplatser.</span><span class="sxs-lookup"><span data-stu-id="c2627-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="c2627-485">**Kan det finnas flera webbplatser per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="c2627-486">Nej, det kan bara finnas en webbplats per grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="c2627-487">Privata kanaler i Teams använder ytterligare webbplatser som inte är kopplade till gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2627-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="c2627-488">**Kan webbplatser kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-489">Tekniskt sett är det inget, men när en webbplats skapas med en grupp kan innehållet delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="c2627-490">**Kan en webbplats koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="c2627-491">Nej, själva webbplatsen är kopplad till gruppen, men innehållet kan flyttas från en webbplats till en annan i SharePoint-gränssnittet, genom att exportera innehåll lokalt eller med hjälp av ett verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="c2627-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="c2627-492">**Raderas gruppen om du tar bort webbplatsen?**</span><span class="sxs-lookup"><span data-stu-id="c2627-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="c2627-493">Ja, om du tar bort webbplatsen i SharePoint tas grupp- och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="c2627-494">Strömma</span><span class="sxs-lookup"><span data-stu-id="c2627-494">Stream</span></span>

<span data-ttu-id="c2627-495">Microsoft Stream är en videovärd och delningsplattform.</span><span class="sxs-lookup"><span data-stu-id="c2627-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="c2627-496">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-497">Videolagring</span><span class="sxs-lookup"><span data-stu-id="c2627-497">Video storage</span></span>
- <span data-ttu-id="c2627-498">Inspelning av Teams-möte</span><span class="sxs-lookup"><span data-stu-id="c2627-498">Teams meeting recording</span></span>
- <span data-ttu-id="c2627-499">Videokanaler</span><span class="sxs-lookup"><span data-stu-id="c2627-499">Video channels</span></span>

<span data-ttu-id="c2627-500">**Kan Stream skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="c2627-501">Ja, det går att skapa en ny Microsoft 365-grupp direkt från Stream.</span><span class="sxs-lookup"><span data-stu-id="c2627-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="c2627-502">**Finns Stream utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="c2627-503">Ja, videokanaler och videor kan finnas i Stream utan att vara kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="c2627-504">**Kan det finnas flera videor och kanaler per grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="c2627-505">Ja, det kan finnas flera videor och kanaler i varje grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="c2627-506">**Kan en video eller kanal associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="c2627-507">Ja, medan en video eller kanal skapas med en grupp kan den delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="c2627-508">**Kan kopplingen till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="c2627-509">Ja och nej. Videor i Stream ägs av den ursprungliga uppladdaren eller mötesinspelaren och kan därför kopplas till valfri grupp, men videokanaler kan bara kopplas till gruppen de ursprungligen skapades i.</span><span class="sxs-lookup"><span data-stu-id="c2627-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="c2627-510">**Tas gruppen bort när du tar bort videor eller kanaler?**</span><span class="sxs-lookup"><span data-stu-id="c2627-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="c2627-511">Nej, gruppen tas inte bort när du tar bort videor eller kanaler.</span><span class="sxs-lookup"><span data-stu-id="c2627-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="c2627-512">Men om du tar bort själva gruppen i Stream tas grupprelaterade tjänster och innehåll bort, förutom själva videoklippen.</span><span class="sxs-lookup"><span data-stu-id="c2627-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="c2627-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="c2627-513">Yammer</span></span>

<span data-ttu-id="c2627-514">Yammer är en social plattform för företag som utformats för att främja community-engagemang inom och mellan organisationer.</span><span class="sxs-lookup"><span data-stu-id="c2627-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="c2627-515">När du skapar en community (kallades tidigare "grupp") i Yammer skapas en postlåda, men detta används för närvarande inte.</span><span class="sxs-lookup"><span data-stu-id="c2627-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="c2627-516">En Microsoft 365-grupp som är associerad med Yammer kan inte användas med ett team i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2627-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="c2627-517">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="c2627-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="c2627-518">Konversationsområdet</span><span class="sxs-lookup"><span data-stu-id="c2627-518">Conversation area</span></span>

<span data-ttu-id="c2627-519">**Kan Yammer skapa en Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="c2627-520">Ja, om du skapar en ny grupp i Yammer skapas en ny Microsoft 365-grupp, om plattformarna är anslutna och användaren har möjlighet att skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="c2627-521">Du kan inte skapa en Yammer-grupp med tillhörande Microsoft 365-grupp i något gränssnitt eller någon annan tjänst än själva Yammer.</span><span class="sxs-lookup"><span data-stu-id="c2627-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="c2627-522">**Finns det en Yammer-grupp utan Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="c2627-523">Ja, det går att skapa en Yammer-grupp utan en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="c2627-524">Om Yammer-plattformen inte är ansluten till Microsoft 365-grupper eller om användarna inte kan skapa en Microsoft 365-grupp skapas Yammer-grupper utan någon Microsoft 365-gruppassociatorganisation.</span><span class="sxs-lookup"><span data-stu-id="c2627-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="c2627-525">**Kan det finnas flera Yammer-grupper per Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="c2627-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="c2627-526">Nej, relationen mellan en Yammer-grupp och en Microsoft 365-grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="c2627-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="c2627-527">**Kan en Yammer-grupp associeras med flera Microsoft 365-grupper?**</span><span class="sxs-lookup"><span data-stu-id="c2627-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="c2627-528">Nej, Yammer-gruppen kan bara associeras med en enda Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c2627-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="c2627-529">Inlägg kan delas med eller flyttas till andra Yammer-grupper.</span><span class="sxs-lookup"><span data-stu-id="c2627-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="c2627-530">**Kan en Yammer-grupps koppling till en Microsoft 365-grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="c2627-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="c2627-531">Nej, Yammer-gruppen kan aldrig associeras med den Microsoft 365-grupp den ursprungligen var kopplad till.</span><span class="sxs-lookup"><span data-stu-id="c2627-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="c2627-532">**Tas Microsoft 365-gruppen bort när du tar bort Yammer-gruppen?**</span><span class="sxs-lookup"><span data-stu-id="c2627-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="c2627-533">Ja, om du tar bort gruppen i Yammer tas relaterade Microsoft-grupper och grupprelaterade tjänster och tillhörande innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="c2627-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2627-534">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c2627-534">Related topics</span></span>

[<span data-ttu-id="c2627-535">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="c2627-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="c2627-536">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="c2627-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)