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
recommendations: false
description: Interaktion mellan grupptjänster
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539209"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="10b31-103">Interaktion mellan grupptjänster</span><span class="sxs-lookup"><span data-stu-id="10b31-103">Groups services interactions</span></span>

<span data-ttu-id="10b31-104">Microsoft 365 Grupper är ett vanligt material för flera tjänster och arbetsbelastningar på Microsoft 365-plattformen för att ge slutanvändarna en uppkopplad upplevelse.</span><span class="sxs-lookup"><span data-stu-id="10b31-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="10b31-105">Det finns en grupp Microsoft 365 tillhandahåller följande:</span><span class="sxs-lookup"><span data-stu-id="10b31-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="10b31-106">Ett sätt att hantera medlemskapet (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="10b31-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="10b31-107">En plats där meddelanden och konversationer äger rum (Exchange postlåda, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="10b31-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="10b31-108">En plats där filer ska lagras (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="10b31-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="10b31-109">En kalender för schemaläggning (Exchange)</span><span class="sxs-lookup"><span data-stu-id="10b31-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="10b31-110">En anteckningsbok för att spara anteckningar (OneNote)</span><span class="sxs-lookup"><span data-stu-id="10b31-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="10b31-111">När grupper skapas etableras även ett antal andra resurser, men de visas inte förrän första gången nås från tjänsten:</span><span class="sxs-lookup"><span data-stu-id="10b31-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="10b31-112">En tavla för hantering av gruppuppgifter (Planner)</span><span class="sxs-lookup"><span data-stu-id="10b31-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="10b31-113">En arbetsyta för rapportering (Power BI)</span><span class="sxs-lookup"><span data-stu-id="10b31-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="10b31-114">Ett område för delade videor (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="10b31-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="10b31-115">Ett område för delade formulär (formulär)</span><span class="sxs-lookup"><span data-stu-id="10b31-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="10b31-116">I Microsoft 365 funktioner kan andra tjänster interagera med Microsoft 365 grupper för att ge ytterligare funktioner till gruppmedlemmarna.</span><span class="sxs-lookup"><span data-stu-id="10b31-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="10b31-117">Exempel på detta är:</span><span class="sxs-lookup"><span data-stu-id="10b31-117">Examples of this include:</span></span>

- <span data-ttu-id="10b31-118">Power Apps för appar</span><span class="sxs-lookup"><span data-stu-id="10b31-118">Power Apps for apps</span></span>
- <span data-ttu-id="10b31-119">Power Automate för arbetsflöden</span><span class="sxs-lookup"><span data-stu-id="10b31-119">Power Automate for workflows</span></span>
- <span data-ttu-id="10b31-120">Project på webben och Översikt över vattenfallsbaserad projekthantering</span><span class="sxs-lookup"><span data-stu-id="10b31-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="10b31-121">Teams för kanalbaserade konversationer</span><span class="sxs-lookup"><span data-stu-id="10b31-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="10b31-122">Yammer för intressegrupper</span><span class="sxs-lookup"><span data-stu-id="10b31-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="10b31-123">Användarinteraktion med grupper</span><span class="sxs-lookup"><span data-stu-id="10b31-123">User interactions with groups</span></span>

<span data-ttu-id="10b31-124">Microsoft 365 Grupper kan skapas och hanteras från en mängd olika gränssnitt, både av administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="10b31-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="10b31-125">Administrativa funktioner</span><span class="sxs-lookup"><span data-stu-id="10b31-125">Administrative experiences</span></span>

<span data-ttu-id="10b31-126">Administratörer kan skapa och hantera Microsoft 365 grupper från flera av administrationscentret för arbetsbelastningen, kommandoradsgränssnitt som stöder skript samt egna appar som interagerar med Graph API.</span><span class="sxs-lookup"><span data-stu-id="10b31-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="10b31-127">Det enda undantaget är Yammer grupper – som måste skapas från Yammer webbgränssnittet.</span><span class="sxs-lookup"><span data-stu-id="10b31-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="10b31-128">**Relaterade inställningar**</span><span class="sxs-lookup"><span data-stu-id="10b31-128">**Related settings**</span></span>

<span data-ttu-id="10b31-129">I de olika administrativa gränssnitten som kan hantera gruppinställningar finns det flera överlappningar som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="10b31-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="10b31-130">**Administrationscentret för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="10b31-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="10b31-131">I Microsoft 365 är gäståtkomst i grupper aktiverad som standard, vilket är möjligheten att låta ägare lägga till gäster.</span><span class="sxs-lookup"><span data-stu-id="10b31-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="10b31-132">Det finns inga ytterligare kontroller på organisationsnivå för grupper i det här administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="10b31-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="10b31-133">**Administrationscenter för Azure AD**</span><span class="sxs-lookup"><span data-stu-id="10b31-133">**Azure AD admin center**</span></span>

<span data-ttu-id="10b31-134">I administrationscentret för Azure AD finns kontroller för huruvida användare kan skapa grupper eller tilldela ägare i Azure-portaler, samt inställningar för förfallo- och namnprinciper.</span><span class="sxs-lookup"><span data-stu-id="10b31-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="10b31-135">Administrationscentret innehåller också ett antal åtgärder för gästinbjudan som går utöver de som finns i Microsoft 365-administrationscentret, till exempel möjlighet att begränsa huruvida icke-ägare också kan bjuda in gäster</span><span class="sxs-lookup"><span data-stu-id="10b31-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="10b31-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="10b31-136">**SharePoint**</span></span>

<span data-ttu-id="10b31-137">SharePoint skapas med säkerhetsgrupper som ägare, medlemmar och besökare, med de två första som matchar deras Microsoft 365-gruppmotsvarsvarumer.</span><span class="sxs-lookup"><span data-stu-id="10b31-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="10b31-138">Medlemskap för SharePoint onlinewebbplatser hanteras i allmänhet av den associerade Microsoft 365-gruppen, men det är inte en dubbelriktad relation.</span><span class="sxs-lookup"><span data-stu-id="10b31-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="10b31-139">Ändringar av medlemskap på Microsoft 365-gruppnivå återspeglas i SharePoint, men om medlemskapet ändras i SharePoint-gruppen återspeglas inte detta i Microsoft 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="10b31-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="10b31-140">Användarupplevelser</span><span class="sxs-lookup"><span data-stu-id="10b31-140">User experiences</span></span>

<span data-ttu-id="10b31-141">Slutanvändarna kan skapa grupper från flera av tjänsterna Microsoft 365 och i andra kan de bara dela med en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="10b31-142">Följande tjänster gör det möjligt att skapa grupper av slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="10b31-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="10b31-143">Outlook Planner Project för webben SharePoint Streama Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="10b31-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="10b31-144">**Begränsning när grupper skapas**</span><span class="sxs-lookup"><span data-stu-id="10b31-144">**Restriction of group creation**</span></span>

<span data-ttu-id="10b31-145">En vanlig metod för att styra utstråningen av team är att begränsa vilka användare som kan skapa dem.</span><span class="sxs-lookup"><span data-stu-id="10b31-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="10b31-146">Det kan bara göras genom att begränsa skapandet av grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="10b31-147">Det här påverkar möjligheten att skapa grupper från andra tjänster där det kan vara nödvändigt för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="10b31-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="10b31-148">Microsoft 365 Grupper stöder inte möjligheten att begränsa skapandet av grupper från vissa appar eller tjänster samtidigt som det är tillåtet från andra.</span><span class="sxs-lookup"><span data-stu-id="10b31-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="10b31-149">Upplevelsen av att skapa gruppbegränsningar varierar mellan program och tjänster:</span><span class="sxs-lookup"><span data-stu-id="10b31-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="10b31-150">App eller tjänst</span><span class="sxs-lookup"><span data-stu-id="10b31-150">App or service</span></span>|<span data-ttu-id="10b31-151">Upplevelse</span><span class="sxs-lookup"><span data-stu-id="10b31-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="10b31-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="10b31-152">Outlook</span></span>|<span data-ttu-id="10b31-153">**Alternativet Ny** grupp tas bort från menyn Nytt på sidan Personer</span><span class="sxs-lookup"><span data-stu-id="10b31-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="10b31-154">Planner</span><span class="sxs-lookup"><span data-stu-id="10b31-154">Planner</span></span>|<span data-ttu-id="10b31-155">**Ny plan** förklarar att skapande av grupper har inaktiverats och ger möjlighet att lägga till planen i en befintlig grupp</span><span class="sxs-lookup"><span data-stu-id="10b31-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="10b31-156">Project för webben och Översikt</span><span class="sxs-lookup"><span data-stu-id="10b31-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="10b31-157">**På menyn Skapa** grupp förklaras att skapandet av grupper är begränsat och föreslår att en befintlig grupp används.</span><span class="sxs-lookup"><span data-stu-id="10b31-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="10b31-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="10b31-158">SharePoint</span></span>|<span data-ttu-id="10b31-159">Det går fortfarande att skapa en gruppwebbplats som inte är ansluten till en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="10b31-160">Stream</span><span class="sxs-lookup"><span data-stu-id="10b31-160">Stream</span></span>|<span data-ttu-id="10b31-161">**Gruppalternativet** visas inte under **menyn Skapa.**</span><span class="sxs-lookup"><span data-stu-id="10b31-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="10b31-162">Teams</span><span class="sxs-lookup"><span data-stu-id="10b31-162">Teams</span></span>|<span data-ttu-id="10b31-163">Användaren kan inte skapa ett team med en ny grupp men kan fortfarande skapa ett team som använder en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="10b31-164">**Knappen Skapa ett team** ersätts med **Skapa team från en grupp.**</span><span class="sxs-lookup"><span data-stu-id="10b31-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="10b31-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="10b31-165">Yammer</span></span>|<span data-ttu-id="10b31-166">**Alternativet Skapa en grupp** tas bort från huvudnavigeringen för grupper/communities.</span><span class="sxs-lookup"><span data-stu-id="10b31-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="10b31-167">Interaktion mellan tjänster med grupper</span><span class="sxs-lookup"><span data-stu-id="10b31-167">Services interactions with groups</span></span>

<span data-ttu-id="10b31-168">I postern Grupper Microsoft 365 du information om olika typer av grupper, hur de skapas och hanteras samt några rekommendationer om styrning.</span><span class="sxs-lookup"><span data-stu-id="10b31-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="10b31-169">[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="10b31-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="10b31-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="10b31-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="10b31-171">Följande tabell innehåller en översikt över hur Microsoft 365 grupper interagerar med olika tjänster:</span><span class="sxs-lookup"><span data-stu-id="10b31-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="10b31-172">Produkt</span><span class="sxs-lookup"><span data-stu-id="10b31-172">Product</span></span>|<span data-ttu-id="10b31-173">Funktioner</span><span class="sxs-lookup"><span data-stu-id="10b31-173">Features</span></span>|<span data-ttu-id="10b31-174">Gör tjänsten</span><span class="sxs-lookup"><span data-stu-id="10b31-174">Does the service</span></span><br><span data-ttu-id="10b31-175">finns det ingen grupp?</span><span class="sxs-lookup"><span data-stu-id="10b31-175">exist without a group?</span></span>|<span data-ttu-id="10b31-176">Kan tjänsten</span><span class="sxs-lookup"><span data-stu-id="10b31-176">Can the service</span></span><br><span data-ttu-id="10b31-177">skapa en grupp?</span><span class="sxs-lookup"><span data-stu-id="10b31-177">create a group?</span></span>|<span data-ttu-id="10b31-178">Tar bort</span><span class="sxs-lookup"><span data-stu-id="10b31-178">Does deleting the</span></span><br><span data-ttu-id="10b31-179">instans ta bort gruppen?</span><span class="sxs-lookup"><span data-stu-id="10b31-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="10b31-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="10b31-180">Azure AD</span></span>|<span data-ttu-id="10b31-181">Medlemskap, gruppkontroller, gäster</span><span class="sxs-lookup"><span data-stu-id="10b31-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="10b31-182">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-182">Yes</span></span>|<span data-ttu-id="10b31-183">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-183">Yes</span></span>|<span data-ttu-id="10b31-184">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-184">Yes</span></span>|
|<span data-ttu-id="10b31-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="10b31-185">Exchange</span></span>|<span data-ttu-id="10b31-186">Kalender, postlåda</span><span class="sxs-lookup"><span data-stu-id="10b31-186">Calendar, mailbox</span></span>|<span data-ttu-id="10b31-187">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-187">Yes</span></span>|<span data-ttu-id="10b31-188">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-188">Yes</span></span>|<span data-ttu-id="10b31-189">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-189">Yes</span></span>|
|<span data-ttu-id="10b31-190">Forms</span><span class="sxs-lookup"><span data-stu-id="10b31-190">Forms</span></span>|<span data-ttu-id="10b31-191">Formulär</span><span class="sxs-lookup"><span data-stu-id="10b31-191">Form</span></span>|<span data-ttu-id="10b31-192">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-192">Yes</span></span>|<span data-ttu-id="10b31-193">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-193">No</span></span>|<span data-ttu-id="10b31-194">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-194">No</span></span>|
|<span data-ttu-id="10b31-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="10b31-195">OneNote</span></span>|<span data-ttu-id="10b31-196">Anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="10b31-196">Notebook</span></span>|<span data-ttu-id="10b31-197">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-197">Yes</span></span>|<span data-ttu-id="10b31-198">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-198">No</span></span>|<span data-ttu-id="10b31-199">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-199">No</span></span>|
|<span data-ttu-id="10b31-200">Planner</span><span class="sxs-lookup"><span data-stu-id="10b31-200">Planner</span></span>|<span data-ttu-id="10b31-201">Uppgiftstavla</span><span class="sxs-lookup"><span data-stu-id="10b31-201">Task board</span></span>|<span data-ttu-id="10b31-202">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-202">No</span></span>|<span data-ttu-id="10b31-203">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-203">Yes</span></span>|<span data-ttu-id="10b31-204">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-204">Yes</span></span>|
|<span data-ttu-id="10b31-205">Power Apps appen</span><span class="sxs-lookup"><span data-stu-id="10b31-205">Power Apps app</span></span>|<span data-ttu-id="10b31-206">Program</span><span class="sxs-lookup"><span data-stu-id="10b31-206">App</span></span>|<span data-ttu-id="10b31-207">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-207">Yes</span></span>|<span data-ttu-id="10b31-208">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-208">No</span></span>|<span data-ttu-id="10b31-209">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-209">No</span></span>|
|<span data-ttu-id="10b31-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="10b31-210">Power Automate</span></span>|<span data-ttu-id="10b31-211">Arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="10b31-211">Workflow</span></span>|<span data-ttu-id="10b31-212">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-212">Yes</span></span>|<span data-ttu-id="10b31-213">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-213">No</span></span>|<span data-ttu-id="10b31-214">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-214">No</span></span>|
|<span data-ttu-id="10b31-215">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="10b31-215">Power BI (classic)</span></span>|<span data-ttu-id="10b31-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="10b31-216">Workspace</span></span>|<span data-ttu-id="10b31-217">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-217">No</span></span>|<span data-ttu-id="10b31-218">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-218">Yes</span></span>|<span data-ttu-id="10b31-219">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-219">Yes</span></span>|
|<span data-ttu-id="10b31-220">Power BI (nytt)</span><span class="sxs-lookup"><span data-stu-id="10b31-220">Power BI (new)</span></span>|<span data-ttu-id="10b31-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="10b31-221">Workspace</span></span>|<span data-ttu-id="10b31-222">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-222">Yes</span></span>|<span data-ttu-id="10b31-223">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-223">No</span></span>|<span data-ttu-id="10b31-224">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-224">Yes</span></span>|
|<span data-ttu-id="10b31-225">Project för webben</span><span class="sxs-lookup"><span data-stu-id="10b31-225">Project for the web</span></span>|<span data-ttu-id="10b31-226">Project abonnemang</span><span class="sxs-lookup"><span data-stu-id="10b31-226">Project plan</span></span>|<span data-ttu-id="10b31-227">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-227">Yes</span></span>|<span data-ttu-id="10b31-228">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-228">Yes</span></span>|<span data-ttu-id="10b31-229">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-229">No</span></span>|
|<span data-ttu-id="10b31-230">Översikt</span><span class="sxs-lookup"><span data-stu-id="10b31-230">Roadmap</span></span>|<span data-ttu-id="10b31-231">Översikt</span><span class="sxs-lookup"><span data-stu-id="10b31-231">Roadmap</span></span>|<span data-ttu-id="10b31-232">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-232">Yes</span></span>|<span data-ttu-id="10b31-233">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-233">Yes</span></span>|<span data-ttu-id="10b31-234">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-234">No</span></span>|
|<span data-ttu-id="10b31-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="10b31-235">SharePoint</span></span>|<span data-ttu-id="10b31-236">Webbplats</span><span class="sxs-lookup"><span data-stu-id="10b31-236">Site</span></span>|<span data-ttu-id="10b31-237">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-237">Yes</span></span>|<span data-ttu-id="10b31-238">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-238">Yes</span></span>|<span data-ttu-id="10b31-239">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-239">Yes</span></span>|
|<span data-ttu-id="10b31-240">Stream</span><span class="sxs-lookup"><span data-stu-id="10b31-240">Stream</span></span>|<span data-ttu-id="10b31-241">Kanal, video</span><span class="sxs-lookup"><span data-stu-id="10b31-241">Channel, video</span></span>|<span data-ttu-id="10b31-242">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-242">Yes</span></span>|<span data-ttu-id="10b31-243">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-243">Yes</span></span>|<span data-ttu-id="10b31-244">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-244">Yes</span></span>|
|<span data-ttu-id="10b31-245">Teams</span><span class="sxs-lookup"><span data-stu-id="10b31-245">Teams</span></span>|<span data-ttu-id="10b31-246">Team</span><span class="sxs-lookup"><span data-stu-id="10b31-246">Team</span></span>|<span data-ttu-id="10b31-247">Nej</span><span class="sxs-lookup"><span data-stu-id="10b31-247">No</span></span>|<span data-ttu-id="10b31-248">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-248">Yes</span></span>|<span data-ttu-id="10b31-249">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-249">Yes</span></span>|
|<span data-ttu-id="10b31-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="10b31-250">Yammer</span></span>|<span data-ttu-id="10b31-251">Grupp</span><span class="sxs-lookup"><span data-stu-id="10b31-251">Group</span></span>|<span data-ttu-id="10b31-252">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-252">Yes</span></span>|<span data-ttu-id="10b31-253">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-253">Yes</span></span>|<span data-ttu-id="10b31-254">Ja</span><span class="sxs-lookup"><span data-stu-id="10b31-254">Yes</span></span>|

<span data-ttu-id="10b31-255">Även om tabellen ovan ger en översikt över gruppinteraktion med Microsoft 365 tjänster, finns det ett antal nyanser och inveckligheter som du bör förstå.</span><span class="sxs-lookup"><span data-stu-id="10b31-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="10b31-256">I följande avsnitt får du en mer detaljerad bild av de specifika arbetsbelastningara och deras interaktioner med grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="10b31-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="10b31-257">Azure AD</span></span>

<span data-ttu-id="10b31-258">Azure AD tillhandahåller underliggande identitetshanteringsfunktioner i hela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10b31-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="10b31-259">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-260">Gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="10b31-260">Group membership</span></span>
- <span data-ttu-id="10b31-261">Namnprincip</span><span class="sxs-lookup"><span data-stu-id="10b31-261">Naming policy</span></span>
- <span data-ttu-id="10b31-262">Förfalloprincip</span><span class="sxs-lookup"><span data-stu-id="10b31-262">Expiration policy</span></span>
- <span data-ttu-id="10b31-263">Gäster</span><span class="sxs-lookup"><span data-stu-id="10b31-263">Guests</span></span>
- <span data-ttu-id="10b31-264">Begränsning av skapande av grupp</span><span class="sxs-lookup"><span data-stu-id="10b31-264">Restriction of Group creation</span></span>

<span data-ttu-id="10b31-265">**Kan Azure AD skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="10b31-266">Ja, Microsoft 365 grupper kan skapas från Azure AD via administrationswebbportalen, via PowerShell eller via Graph API.</span><span class="sxs-lookup"><span data-stu-id="10b31-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="10b31-267">**Finns Azure AD utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="10b31-268">Ja, Azure AD utför ett stort antal tjänster som inte har någon relation till Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="10b31-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="10b31-269">Varje Microsoft 365 representeras som ett objekt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10b31-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="10b31-270">**Kan det finnas flera instanser av Azure AD per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="10b31-271">Nej, det finns bara en instans av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10b31-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="10b31-272">**Kan Azure AD associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="10b31-273">Ja, eftersom Azure AD är den underliggande plattform som tillhandahåller tjänsten för gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="10b31-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="10b31-274">**Kan Azure AD:s koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="10b31-275">Nej, Azure AD är den underliggande plattformen där grupper finns.</span><span class="sxs-lookup"><span data-stu-id="10b31-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="10b31-276">**Raderas gruppen om instansen tas bort?**</span><span class="sxs-lookup"><span data-stu-id="10b31-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="10b31-277">Om du tar bort gruppen i Azure AD tas relevanta grupprelaterade tjänster och relevant innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="10b31-278">Teams</span><span class="sxs-lookup"><span data-stu-id="10b31-278">Teams</span></span>

<span data-ttu-id="10b31-279">Teams är en chattcentreerad arbetsyta som försöker förbättra samarbetet genom att tillhandahålla ett enda gränssnitt som interagerar med olika Microsoft- och tredjepartstjänster.</span><span class="sxs-lookup"><span data-stu-id="10b31-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="10b31-280">Som standard döljs postlådan och kalendern som är kopplad till Microsoft 365-gruppen från både den globala adresslistan i Exchange och Outlook.</span><span class="sxs-lookup"><span data-stu-id="10b31-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="10b31-281">Administratören kan manuellt åsidosätta detta om användaren vill använda både Outlook och Teams i samma Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="10b31-282">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-283">Konversationer</span><span class="sxs-lookup"><span data-stu-id="10b31-283">Conversations</span></span>
- <span data-ttu-id="10b31-284">Kanaler & flikar</span><span class="sxs-lookup"><span data-stu-id="10b31-284">Channels & tabs</span></span>
- <span data-ttu-id="10b31-285">Möten</span><span class="sxs-lookup"><span data-stu-id="10b31-285">Meetings</span></span>

<span data-ttu-id="10b31-286">**Kan Teams skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="10b31-287">Ja, när du skapar ett nytt team skapas en ny Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="10b31-288">Det går även att skapa ett team för en befintlig grupp som inte har någon för närvarande.</span><span class="sxs-lookup"><span data-stu-id="10b31-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="10b31-289">**Finns grupper utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="10b31-290">Nej, det går inte att ha ett team utan en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="10b31-291">**Kan det finnas flera team per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="10b31-292">Nej, relationen mellan ett team och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="10b31-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="10b31-293">**Kan ett team associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-294">Nej, själva teamet kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="10b31-295">**Kan ett teams koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="10b31-296">Nej, teamet kan aldrig bara associeras med gruppen som det ursprungligen var kopplat till.</span><span class="sxs-lookup"><span data-stu-id="10b31-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="10b31-297">**Raderas gruppen om du tar bort teamet?**</span><span class="sxs-lookup"><span data-stu-id="10b31-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="10b31-298">Ja, om du tar Microsoft Teams gruppen i gruppen tas gruppen, grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="10b31-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="10b31-299">Exchange</span></span>

<span data-ttu-id="10b31-300">Exchange Online får meddelandefunktioner, kalenderfunktioner, kontakter och tillhörande funktioner.</span><span class="sxs-lookup"><span data-stu-id="10b31-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="10b31-301">Inom en grupp är endast en enda resurs associerad – i motsats till en hel tjänstinstans.</span><span class="sxs-lookup"><span data-stu-id="10b31-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="10b31-302">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-303">Postlåda och kalender</span><span class="sxs-lookup"><span data-stu-id="10b31-303">Mailbox and calendar</span></span>
- <span data-ttu-id="10b31-304">Möjlighet att skicka e-post till alla gruppmedlemmar</span><span class="sxs-lookup"><span data-stu-id="10b31-304">Ability to email all Group members</span></span>
- <span data-ttu-id="10b31-305">Storage av Teams kanalkonversationer i eDiscovery-syfte, Planner-kommentarer</span><span class="sxs-lookup"><span data-stu-id="10b31-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="10b31-306">**Kan Exchange skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="10b31-307">Ja, det går att skapa en grupp Exchange Online administrationscentret och från Outlook.</span><span class="sxs-lookup"><span data-stu-id="10b31-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="10b31-308">Du kan också konvertera Exchange distributionslistor till Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="10b31-309">**Finns Exchange någon grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="10b31-310">Ja, Exchange Online tillhandahåller ett antal tjänster, inklusive delade postlådor och kalendrar, utan någon gruppassociatorganisation.</span><span class="sxs-lookup"><span data-stu-id="10b31-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="10b31-311">**Kan det finnas flera instanser Exchange postlådor eller kalendrar per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="10b31-312">Nej, det kan bara finnas Exchange Online postlåda och kalender för en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="10b31-313">**Kan Exchange postlådor och kalendrar associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-314">Nej, postlådan och kalendern har en 1:1-relation med gruppen.</span><span class="sxs-lookup"><span data-stu-id="10b31-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="10b31-315">Det går att dela postlådan med andra användare eller grupper, men det skapar ingen form av tjänstassociating.</span><span class="sxs-lookup"><span data-stu-id="10b31-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="10b31-316">**Kan Exchange postlådans eller kalenderns koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="10b31-317">Nej, postlådan och kalendern kan inte ändras till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="10b31-318">Innehållet kan dock flyttas från en postlåda till en annan inom Outlook eller med hjälp av ett verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="10b31-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="10b31-319">**Tas gruppen bort när du tar bort postlådan?**</span><span class="sxs-lookup"><span data-stu-id="10b31-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="10b31-320">Ja, om du tar Exchange postlådan i ett e-postkonto tas gruppen samt grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="10b31-321">Forms</span><span class="sxs-lookup"><span data-stu-id="10b31-321">Forms</span></span>

<span data-ttu-id="10b31-322">Forms tillhandahåller webbaserade undersökningar och test.</span><span class="sxs-lookup"><span data-stu-id="10b31-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="10b31-323">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-324">Äganderätt till formulär</span><span class="sxs-lookup"><span data-stu-id="10b31-324">Ownership of forms</span></span>

<span data-ttu-id="10b31-325">**Kan formulär skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="10b31-326">Nej, Formulär kan inte skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="10b31-327">**Finns formulär utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="10b31-328">Ja, undersökningar och test kan skapas direkt i en slutanvändares konto.</span><span class="sxs-lookup"><span data-stu-id="10b31-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="10b31-329">**Kan det finnas flera formulär per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="10b31-330">Ja, det kan finnas flera formulär kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="10b31-331">**Kan formulär kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-332">Nej, ett formulär kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="10b31-333">**Kan ett formulärs koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="10b31-334">Nej, när ett formulär är kopplat till en grupp (skapas direkt i, eller ägarskap som överförs från en enskild person) kan det inte flyttas till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="10b31-335">**Tas gruppen bort när du tar bort formuläret?**</span><span class="sxs-lookup"><span data-stu-id="10b31-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="10b31-336">Nej, det går inte att ta bort en grupp från Forms-gränssnittet, bara enskilda formulär.</span><span class="sxs-lookup"><span data-stu-id="10b31-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="10b31-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="10b31-337">OneNote</span></span>

<span data-ttu-id="10b31-338">OneNote är ett digitalt anteckningsboksprogram.</span><span class="sxs-lookup"><span data-stu-id="10b31-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="10b31-339">Den OneNote som skapats med en grupp är en fil på den associerade SharePoint-webbplatsen i stället för en gruppansluten tjänst.</span><span class="sxs-lookup"><span data-stu-id="10b31-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="10b31-340">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-341">Delad anteckningsbok (lagrad i det grupprelaterade SharePoint anteckningsboksbiblioteket)</span><span class="sxs-lookup"><span data-stu-id="10b31-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="10b31-342">**Kan OneNote skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="10b31-343">Nej, OneNote kan inte skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="10b31-344">**Finns OneNote utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="10b31-345">Ja, anteckningsböcker kan skapas direkt i OneDrive eller på andra delade platser.</span><span class="sxs-lookup"><span data-stu-id="10b31-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="10b31-346">**Kan det finnas flera OneNote anteckningsböcker per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="10b31-347">Ja, en anteckningsbok skapas som standard och andra kan läggas till, men alla länkar till OneNote från grupprelaterade tjänster går alltid till standardanteckningsboken.</span><span class="sxs-lookup"><span data-stu-id="10b31-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="10b31-348">**Kan en OneNote associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-349">Nej, anteckningsboken lagras i det grupprelaterade SharePoint och länkas från olika gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="10b31-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="10b31-350">Men den kan delas med andra grupper på samma sätt som den kan delas med enskilda personer.</span><span class="sxs-lookup"><span data-stu-id="10b31-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="10b31-351">**Kan anteckningsbokens koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="10b31-352">Nej, själva anteckningsboken är kopplad till gruppen och kan kommas åt direkt från andra gruppanslutna tjänster, men innehållet kan flyttas från en anteckningsbok till en annan i OneNote program.</span><span class="sxs-lookup"><span data-stu-id="10b31-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="10b31-353">**Tas gruppen bort när du tar bort anteckningsboken?**</span><span class="sxs-lookup"><span data-stu-id="10b31-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="10b31-354">Nej, men om anteckningsboken OneNote bort kan det finnas brutna länkar i vissa grupprelaterade tjänster.</span><span class="sxs-lookup"><span data-stu-id="10b31-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="10b31-355">Planner</span><span class="sxs-lookup"><span data-stu-id="10b31-355">Planner</span></span>

<span data-ttu-id="10b31-356">Planner är en enkel tjänst för uppgiftshantering för grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="10b31-357">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-358">Tavla för hantering av gruppuppgifter</span><span class="sxs-lookup"><span data-stu-id="10b31-358">Board for managing group tasks</span></span>

<span data-ttu-id="10b31-359">**Kan Planner skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="10b31-360">Ja, när du skapar en plan skapas en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="10b31-361">**Finns det en Planner-tavla utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="10b31-362">Nej, en plan måste vara kopplad till en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="10b31-363">**Kan det finnas flera planer per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="10b31-364">Ja, det kan finnas flera planer per grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="10b31-365">**Kan en plan associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-366">Nej, en plan förlitar sig enbart på gruppmedlemskapet för att avgöra åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="10b31-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="10b31-367">**Kan en plans koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="10b31-368">Nej, men när en plan kopieras skapas en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="10b31-369">En grupp som har skapats av ett annat program visas inte automatiskt i Planner för en användare.</span><span class="sxs-lookup"><span data-stu-id="10b31-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="10b31-370">För att komma åt tavlan först måste de öppna den från ett annat gruppbaserat gränssnitt, till exempel från Outlook.</span><span class="sxs-lookup"><span data-stu-id="10b31-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="10b31-371">**Tas gruppen bort när planen tas bort?**</span><span class="sxs-lookup"><span data-stu-id="10b31-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="10b31-372">Ja, om du tar bort planen tas gruppen och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="10b31-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="10b31-373">Power Apps</span></span>

<span data-ttu-id="10b31-374">Power Apps en arbetsyta för apputveckling utan kod.</span><span class="sxs-lookup"><span data-stu-id="10b31-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="10b31-375">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-376">Appar kan delas med en grupp som ska köras och ändras</span><span class="sxs-lookup"><span data-stu-id="10b31-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="10b31-377">**Kan Power Apps skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="10b31-378">Nej, Power Apps inte skapa en Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="10b31-379">**Finns Power Apps utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="10b31-380">Ja, appar kan skapas i Power Apps och finnas i creators-kontot tills de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="10b31-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="10b31-381">**Kan det finnas flera appar per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="10b31-382">Ja, det kan finnas flera program som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="10b31-383">**Kan appar kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-384">Ja, en app kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="10b31-385">**Kan en apps koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="10b31-386">Ja, eftersom kopplingen mellan Power Apps och en Microsoft 365 bara delas – appen finns fortfarande kvar hos skaparen.</span><span class="sxs-lookup"><span data-stu-id="10b31-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b31-387">[Grupper måste vara säkerhetsaktiverade innan appar kan delas med dem.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="10b31-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="10b31-388">**Raderas gruppen om du tar bort programmet?**</span><span class="sxs-lookup"><span data-stu-id="10b31-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="10b31-389">Nej, apparna är inte kopplade till den andra gruppen än den som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="10b31-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="10b31-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="10b31-390">Power Automate</span></span>

<span data-ttu-id="10b31-391">Power Automate (kallades tidigare för Microsoft Flow) innehåller arbetsflöden och automatiseringstjänster.</span><span class="sxs-lookup"><span data-stu-id="10b31-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="10b31-392">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-393">Arbetsflöden kan delas med en grupp som ska köras och ändras.</span><span class="sxs-lookup"><span data-stu-id="10b31-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="10b31-394">**Kan Power Automate skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="10b31-395">Nej, Power Automate kan inte skapa Microsoft 365 grupp i samband med att den kopplas till en.</span><span class="sxs-lookup"><span data-stu-id="10b31-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="10b31-396">Det går dock att skapa ett flöde som utför olika åtgärder, till exempel skapa en Azure AD-säkerhetsgrupp eller uppdatera medlemskap i en Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="10b31-397">**Finns flöden utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="10b31-398">Ja, flöden kan skapas inom Power Automate och finnas i creators-kontot tills de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="10b31-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="10b31-399">**Kan det finnas flera flöden per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="10b31-400">Ja, det kan finnas flera flöden som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="10b31-401">**Kan ett flöde associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-402">Ja, ett flöde kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="10b31-403">**Kan ett flödes koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="10b31-404">Ja, eftersom kopplingen mellan Power Automate och en Microsoft 365 bara delas – finns flödet fortfarande kvar hos skaparen.</span><span class="sxs-lookup"><span data-stu-id="10b31-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="10b31-405">**Tas gruppen bort när du tar bort ett flöde?**</span><span class="sxs-lookup"><span data-stu-id="10b31-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="10b31-406">Nej, Power Apps inte direkt till den andra gruppen än den som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="10b31-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="10b31-407">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="10b31-407">Power BI (classic)</span></span>

<span data-ttu-id="10b31-408">Power BI interaktiva datadrivna instrumentpaneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="10b31-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="10b31-409">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-410">Datarapportering</span><span class="sxs-lookup"><span data-stu-id="10b31-410">Data reporting</span></span>

<span data-ttu-id="10b31-411">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="10b31-412">Ja, när du skapar en klassisk arbetsyta skapas Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="10b31-413">**Finns det Power BI klassiska arbetsytan utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="10b31-414">Nej, [en klassisk arbetsyta i Power BI måste associeras med en grupp](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="10b31-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="10b31-415">**Kan det finnas Power BI arbetsytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="10b31-416">Nej, relationen mellan en klassisk arbetsyta och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="10b31-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="10b31-417">**Kan en arbetsyta kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-418">Tekniskt sett är det inget, men när den klassiska arbetsytan skapas med gruppen kan innehållet delas utanför gruppen med användare och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="10b31-419">**Kan arbetsytans koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="10b31-420">Nej, den klassiska arbetsytan är kopplad till gruppen, men innehållet kan flyttas från en arbetsyta till en annan i Power BI gränssnittet eller genom att exportera innehåll lokalt.</span><span class="sxs-lookup"><span data-stu-id="10b31-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="10b31-421">**Tas gruppen bort när du tar bort arbetsytan?**</span><span class="sxs-lookup"><span data-stu-id="10b31-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="10b31-422">Ja, om du tar bort arbetsytan Power BI grupp- och grupprelaterade tjänster och innehåll.</span><span class="sxs-lookup"><span data-stu-id="10b31-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="10b31-423">Power BI (nytt)</span><span class="sxs-lookup"><span data-stu-id="10b31-423">Power BI (new)</span></span>

<span data-ttu-id="10b31-424">Power BI interaktiva datadrivna instrumentpaneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="10b31-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="10b31-425">När du skapar en ny arbetsyta i Power BI skapas inte en Microsoft 365-grupp, och om du skapar en grupp på något annat sätt skapas en ny (inte klassisk) arbetsyta i Power BI.</span><span class="sxs-lookup"><span data-stu-id="10b31-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="10b31-426">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="10b31-427">Datarapportering</span><span class="sxs-lookup"><span data-stu-id="10b31-427">Data reporting</span></span>

<span data-ttu-id="10b31-428">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="10b31-429">Nej, det går inte att skapa en Microsoft 365 från det nya Power BI gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="10b31-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="10b31-430">**Finns den nya Power BI arbetsytan utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="10b31-431">Ja, det går att skapa rapporter och arbetsytor i Power BI som inte är kopplade Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="10b31-432">**Kan det finnas flera arbetsytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="10b31-433">Ja, [flera arbetsytor som skapas Power BI kan delas med en enda grupp](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="10b31-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="10b31-434">**Kan en arbetsyta kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-435">Nej, en arbetsyta som skapats Power BI bara kan kopplas till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="10b31-436">**Kan en arbetsytas koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="10b31-437">Ja och nej.</span><span class="sxs-lookup"><span data-stu-id="10b31-437">Yes and no.</span></span> <span data-ttu-id="10b31-438">En arbetsyta som Power BI kan bara associeras med en enskild grupp i taget, men du kan när som helst ändra kopplingen.</span><span class="sxs-lookup"><span data-stu-id="10b31-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="10b31-439">En arbetsyta som Power BI av en grupp är permanent kopplad till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="10b31-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="10b31-440">**Tas gruppen bort när du tar bort arbetsytan?**</span><span class="sxs-lookup"><span data-stu-id="10b31-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="10b31-441">Ja, om du tar bort arbetsytan Power BI gruppen och grupprelaterade tjänster och innehåll tas bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="10b31-442">Project för webben</span><span class="sxs-lookup"><span data-stu-id="10b31-442">Project for the web</span></span>

<span data-ttu-id="10b31-443">Project för webben har möjlighet att skapa projektplaner, Gantt-diagram och översikter.</span><span class="sxs-lookup"><span data-stu-id="10b31-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="10b31-444">Huvudfunktioner för grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-444">Key features provided to groups.</span></span>

- <span data-ttu-id="10b31-445">Project abonnemang</span><span class="sxs-lookup"><span data-stu-id="10b31-445">Project plans</span></span>

<span data-ttu-id="10b31-446">**Kan Project för webben skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="10b31-447">Ja, det går att skapa en ny Microsoft 365 direkt från Project för webben.</span><span class="sxs-lookup"><span data-stu-id="10b31-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="10b31-448">**Finns det projekt utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="10b31-449">Ja, det kan finnas projekt utan att vara kopplade Microsoft 365 en grupp, men tilldelning av aktiviteter kräver gruppassociat koppling.</span><span class="sxs-lookup"><span data-stu-id="10b31-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="10b31-450">**Kan det finnas flera projekt per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="10b31-451">Ja, det går att ansluta flera projekt i en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="10b31-452">**Kan projektet associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-453">Nej, ett projekt kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="10b31-454">**Kan ett projekts koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="10b31-455">Nej, när kopplingen till en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="10b31-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="10b31-456">**Tas gruppen bort när du tar bort projektet?**</span><span class="sxs-lookup"><span data-stu-id="10b31-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="10b31-457">Nej, gruppen tas inte bort om Project för webben tas bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="10b31-458">Översikt</span><span class="sxs-lookup"><span data-stu-id="10b31-458">Roadmap</span></span>

<span data-ttu-id="10b31-459">Översikt ger möjlighet att skapa projektöversikter med Project för webben och Project Online.</span><span class="sxs-lookup"><span data-stu-id="10b31-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="10b31-460">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-461">Project översikter</span><span class="sxs-lookup"><span data-stu-id="10b31-461">Project roadmaps</span></span>

<span data-ttu-id="10b31-462">**Kan Översikt skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="10b31-463">Ja, det går att skapa en ny Microsoft 365 direkt från översikten.</span><span class="sxs-lookup"><span data-stu-id="10b31-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="10b31-464">**Finns Översikt utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="10b31-465">Ja, översikter kan finnas utan att vara kopplade till Microsoft 365 grupp, men för delning av översikten krävs gruppassociat koppling.</span><span class="sxs-lookup"><span data-stu-id="10b31-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="10b31-466">**Kan det finnas flera översikter per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="10b31-467">Ja, det går att ansluta flera översikter till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="10b31-468">**Kan en översikt associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-469">Nej, en översikt kan bara associeras med en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="10b31-470">**Kan en översiktsorganisation med en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="10b31-471">Nej, när kopplingen till en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="10b31-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="10b31-472">**Tas gruppen bort när du tar bort översikten?**</span><span class="sxs-lookup"><span data-stu-id="10b31-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="10b31-473">Nej, gruppen tas inte bort när du tar bort översikten.</span><span class="sxs-lookup"><span data-stu-id="10b31-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="10b31-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="10b31-474">SharePoint</span></span>

<span data-ttu-id="10b31-475">SharePoint är en webbaserad innehållshanteringsplattform som bland annat tillhandahåller lagringstjänster för ett antal Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="10b31-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="10b31-476">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-477">Dokumentbibliotek</span><span class="sxs-lookup"><span data-stu-id="10b31-477">Document library</span></span>
- <span data-ttu-id="10b31-478">Bibliotek för lagring av OneNote anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="10b31-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="10b31-479">Storage av Teams wiki-filer</span><span class="sxs-lookup"><span data-stu-id="10b31-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="10b31-480">**Kan SharePoint skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="10b31-481">Ja, när du skapar en gruppwebbplats i SharePoint skapas en Microsoft 365 grupp som standard.</span><span class="sxs-lookup"><span data-stu-id="10b31-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="10b31-482">Det går även att skapa en grupp och, om du vill, ett team för en befintlig webbplats.</span><span class="sxs-lookup"><span data-stu-id="10b31-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="10b31-483">**Finns SharePoint webbplatser utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="10b31-484">Ja, SharePoint erbjuder ett antal icke-grupprelaterade tjänster och webbplatser, till exempel kommunikations- och navplatser.</span><span class="sxs-lookup"><span data-stu-id="10b31-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="10b31-485">**Kan det finnas flera webbplatser per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="10b31-486">Nej, det kan bara finnas en webbplats per grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="10b31-487">Privata kanaler i Teams använder ytterligare webbplatser som inte är kopplade till gruppen.</span><span class="sxs-lookup"><span data-stu-id="10b31-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="10b31-488">**Kan webbplatser kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-489">Tekniskt sett är det inget, men när en webbplats skapas med en grupp kan innehållet delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="10b31-490">**Kan en webbplats koppling till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="10b31-491">Nej, själva webbplatsen är kopplad till gruppen, men innehållet kan flyttas från en webbplats till en annan i SharePoint-gränssnittet, genom att exportera innehåll lokalt eller med hjälp av ett tredjepartsverktyg.</span><span class="sxs-lookup"><span data-stu-id="10b31-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="10b31-492">**Raderas gruppen om du tar bort webbplatsen?**</span><span class="sxs-lookup"><span data-stu-id="10b31-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="10b31-493">Ja, om du tar bort SharePoint gruppwebbplatser tas grupp- och grupprelaterade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="10b31-494">Stream</span><span class="sxs-lookup"><span data-stu-id="10b31-494">Stream</span></span>

<span data-ttu-id="10b31-495">Microsoft Stream är en videovärd och delningsplattform.</span><span class="sxs-lookup"><span data-stu-id="10b31-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="10b31-496">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-497">Videolagring</span><span class="sxs-lookup"><span data-stu-id="10b31-497">Video storage</span></span>
- <span data-ttu-id="10b31-498">Teams mötesinspelning</span><span class="sxs-lookup"><span data-stu-id="10b31-498">Teams meeting recording</span></span>
- <span data-ttu-id="10b31-499">Videokanaler</span><span class="sxs-lookup"><span data-stu-id="10b31-499">Video channels</span></span>

<span data-ttu-id="10b31-500">**Kan Stream skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="10b31-501">Ja, det går att skapa en ny Microsoft 365 direkt från Stream.</span><span class="sxs-lookup"><span data-stu-id="10b31-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="10b31-502">**Finns Stream utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="10b31-503">Ja, videokanaler och videor kan finnas i Stream utan att vara kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="10b31-504">**Kan det finnas flera videor och kanaler per grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="10b31-505">Ja, det kan finnas flera videor och kanaler i varje grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="10b31-506">**Kan en video eller kanal associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="10b31-507">Ja, medan en video eller kanal skapas med en grupp kan den delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="10b31-508">**Kan kopplingen till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="10b31-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="10b31-509">Ja och nej. Videor i Stream ägs av den ursprungliga uppladdaren eller mötesinspelaren och kan därför kopplas till valfri grupp, men videokanaler kan bara kopplas till gruppen de ursprungligen skapades i.</span><span class="sxs-lookup"><span data-stu-id="10b31-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="10b31-510">**Tas gruppen bort när du tar bort videor eller kanaler?**</span><span class="sxs-lookup"><span data-stu-id="10b31-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="10b31-511">Nej, gruppen tas inte bort när du tar bort videor eller kanaler.</span><span class="sxs-lookup"><span data-stu-id="10b31-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="10b31-512">Men om du tar bort själva gruppen i Stream tas grupprelaterade tjänster och innehåll bort, förutom själva videoklippen.</span><span class="sxs-lookup"><span data-stu-id="10b31-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="10b31-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="10b31-513">Yammer</span></span>

<span data-ttu-id="10b31-514">Yammer är en social plattform för företag som utformats för att främja community-engagemang inom och mellan organisationer.</span><span class="sxs-lookup"><span data-stu-id="10b31-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="10b31-515">När du skapar en community (kallades tidigare "grupp") i Yammer en postlåda, men detta används för närvarande inte.</span><span class="sxs-lookup"><span data-stu-id="10b31-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="10b31-516">En Microsoft 365 grupp som är associerad med Yammer kan inte användas med ett team i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10b31-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="10b31-517">**Huvudfunktioner för grupper**</span><span class="sxs-lookup"><span data-stu-id="10b31-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="10b31-518">Konversationsområdet</span><span class="sxs-lookup"><span data-stu-id="10b31-518">Conversation area</span></span>

<span data-ttu-id="10b31-519">**Kan Yammer skapa en Microsoft 365 grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="10b31-520">Ja, om du skapar en ny grupp i Yammer skapas en ny Microsoft 365-grupp, om plattformarna är anslutna och användaren har möjlighet att skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="10b31-521">En Yammer grupp med associerad Microsoft 365 kan inte skapas i något gränssnitt eller någon annan tjänst än Yammer sig.</span><span class="sxs-lookup"><span data-stu-id="10b31-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="10b31-522">**Finns det Yammer grupp utan en Microsoft 365 grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="10b31-523">Ja, det går att skapa en Yammer grupp utan en Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="10b31-524">Om Yammer-plattformen inte är ansluten till Microsoft 365-grupper eller om användarna inte kan skapa en Microsoft 365-grupp skapas Yammer-grupper utan någon Microsoft 365-gruppassociatorganisation.</span><span class="sxs-lookup"><span data-stu-id="10b31-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="10b31-525">**Kan det finnas flera Yammer per Microsoft 365 grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="10b31-526">Nej, förhållandet mellan en Yammer och en Microsoft 365 är 1:1.</span><span class="sxs-lookup"><span data-stu-id="10b31-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="10b31-527">**Kan en Yammer associeras med flera Microsoft 365 grupper?**</span><span class="sxs-lookup"><span data-stu-id="10b31-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="10b31-528">Nej, gruppen Yammer bara associeras med en enda Microsoft 365 grupp.</span><span class="sxs-lookup"><span data-stu-id="10b31-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="10b31-529">Inlägg kan delas med eller flyttas till andra Yammer grupper.</span><span class="sxs-lookup"><span data-stu-id="10b31-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="10b31-530">**Kan en Yammer grupps koppling till en grupp Microsoft 365 gruppändring?**</span><span class="sxs-lookup"><span data-stu-id="10b31-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="10b31-531">Nej, gruppen Yammer någonsin bara associeras med den Microsoft 365 gruppen som den ursprungligen var associerad med.</span><span class="sxs-lookup"><span data-stu-id="10b31-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="10b31-532">**Tas gruppen Yammer bort en Microsoft 365 grupp?**</span><span class="sxs-lookup"><span data-stu-id="10b31-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="10b31-533">Ja, om du tar bort gruppen Yammer microsoft-relaterade grupper och grupprelaterade tjänster och innehåll tas bort.</span><span class="sxs-lookup"><span data-stu-id="10b31-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10b31-534">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="10b31-534">Related topics</span></span>

[<span data-ttu-id="10b31-535">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="10b31-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="10b31-536">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="10b31-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)