---
title: Interaktioner i grupper
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
description: Interaktioner i grupper
ms.openlocfilehash: 235a897314a784ba3bb1ac50fe8bdfe9986a70d3
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377635"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="d79aa-103">Interaktioner i grupper</span><span class="sxs-lookup"><span data-stu-id="d79aa-103">Groups services interactions</span></span>

<span data-ttu-id="d79aa-104">Microsoft 365-grupper ger en gemensam infrastruktur för ett antal tjänster och arbets belastningar inom Microsofts 365-plattform för att tillhandahålla en uppkopplad upplevelse för slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="d79aa-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="d79aa-105">I sin kärna finns en Microsoft 365-grupp för att tillhandahålla:</span><span class="sxs-lookup"><span data-stu-id="d79aa-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="d79aa-106">Ett sätt att hantera medlemskap (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d79aa-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="d79aa-107">En plats för meddelanden och konversationer att genomföra (Exchange-postlåda, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="d79aa-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="d79aa-108">En plats där filer lagras (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="d79aa-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="d79aa-109">En kalender för schemaläggning (Exchange)</span><span class="sxs-lookup"><span data-stu-id="d79aa-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="d79aa-110">En antecknings bok för att fånga anteckningar (OneNote)</span><span class="sxs-lookup"><span data-stu-id="d79aa-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="d79aa-111">När du skapar en grupp skapas ett antal andra resurser, men de visas inte förrän de har åtkomst till den första gången från tjänsten:</span><span class="sxs-lookup"><span data-stu-id="d79aa-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="d79aa-112">En anslags tavla för att hantera grupp aktiviteter (Planner)</span><span class="sxs-lookup"><span data-stu-id="d79aa-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="d79aa-113">En arbets yta för rapportering (Power BI)</span><span class="sxs-lookup"><span data-stu-id="d79aa-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="d79aa-114">Ett område för delade videoklipp (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="d79aa-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="d79aa-115">Ett område för delade formulär (formulär)</span><span class="sxs-lookup"><span data-stu-id="d79aa-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="d79aa-116">I Microsoft 365 kan andra tjänster samverka med Microsoft 365-grupper för att tillhandahålla ytterligare funktioner och funktioner för grupp medlemmar.</span><span class="sxs-lookup"><span data-stu-id="d79aa-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="d79aa-117">Exempel på detta är:</span><span class="sxs-lookup"><span data-stu-id="d79aa-117">Examples of this include:</span></span>

- <span data-ttu-id="d79aa-118">Power app för appar</span><span class="sxs-lookup"><span data-stu-id="d79aa-118">Power Apps for apps</span></span>
- <span data-ttu-id="d79aa-119">Automatisera Power för arbets flöden</span><span class="sxs-lookup"><span data-stu-id="d79aa-119">Power Automate for workflows</span></span>
- <span data-ttu-id="d79aa-120">Project på webben och översikt för Vattenfalls projektledning</span><span class="sxs-lookup"><span data-stu-id="d79aa-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="d79aa-121">Teams för kanalbaserade konversationer</span><span class="sxs-lookup"><span data-stu-id="d79aa-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="d79aa-122">Yammer för intressanta grupper</span><span class="sxs-lookup"><span data-stu-id="d79aa-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="d79aa-123">Användar interaktion med grupper</span><span class="sxs-lookup"><span data-stu-id="d79aa-123">User interactions with groups</span></span>

<span data-ttu-id="d79aa-124">Microsoft 365-grupper kan skapas och hanteras av olika gränssnitt, både för administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="d79aa-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="d79aa-125">Administrativa upplevelser</span><span class="sxs-lookup"><span data-stu-id="d79aa-125">Administrative experiences</span></span>

<span data-ttu-id="d79aa-126">Administratörer kan skapa och hantera Microsoft 365-grupper från flera olika administrations Center för arbets belastning, kommando rads gränssnitt som stöder skript samt anpassade program som fungerar tillsammans med Graph API.</span><span class="sxs-lookup"><span data-stu-id="d79aa-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="d79aa-127">Det enda undantaget för detta är Yammer-grupper – som måste skapas från Yammer Web Interface.</span><span class="sxs-lookup"><span data-stu-id="d79aa-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="d79aa-128">**Relaterade inställningar**</span><span class="sxs-lookup"><span data-stu-id="d79aa-128">**Related settings**</span></span>

<span data-ttu-id="d79aa-129">Bland de olika administrativa gränssnitt som kan hantera grupp inställningar finns flera överlappande som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="d79aa-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="d79aa-130">**Administrationscenter för Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="d79aa-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="d79aa-131">I Microsoft 365 Admin Center är gäst åtkomst till grupper aktiverat som standard, vilket är möjligheten att tillåta ägare att lägga till gäster.</span><span class="sxs-lookup"><span data-stu-id="d79aa-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="d79aa-132">Det finns inga fler kontroller på organisations nivå i det här administrations centret.</span><span class="sxs-lookup"><span data-stu-id="d79aa-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="d79aa-133">**Administrations Center för Azure AD**</span><span class="sxs-lookup"><span data-stu-id="d79aa-133">**Azure AD admin center**</span></span>

<span data-ttu-id="d79aa-134">Administrations centret för Azure AD erbjuder kontroller om användare kan skapa grupper eller tilldela ägare i Azure-portaler, samt giltighets datum och princip inställningar.</span><span class="sxs-lookup"><span data-stu-id="d79aa-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="d79aa-135">Administrations Center innehåller också ett antal åtgärder för kontroll av gäst inbjudningar som går utöver det som ingår i Microsoft 365 Admin Center, till exempel möjligheten att begränsa huruvida icke-ägare kan bjuda in gäster</span><span class="sxs-lookup"><span data-stu-id="d79aa-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="d79aa-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="d79aa-136">**SharePoint**</span></span>

<span data-ttu-id="d79aa-137">SharePoint-webbplatser skapas med säkerhets grupper för ägare, medlem och besökare med de två första matchningarna till sina Microsoft 365-gruppmotparter.</span><span class="sxs-lookup"><span data-stu-id="d79aa-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="d79aa-138">När medlemskap för SharePoint Online-webbplatser hanteras vanligt vis av den associerade Microsoft 365-gruppen är det inte en dubbelriktad relation.</span><span class="sxs-lookup"><span data-stu-id="d79aa-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="d79aa-139">Alla ändringar av medlemskap på Microsoft 365-gruppnivån återspeglas i SharePoint, men om medlemskap ändras i SharePoint-gruppen visas inte detta i gruppen Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d79aa-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="d79aa-140">Användar upplevelser</span><span class="sxs-lookup"><span data-stu-id="d79aa-140">User experiences</span></span>

<span data-ttu-id="d79aa-141">Slutanvändare kan skapa grupper från flera tjänster i Microsoft 365, och i andra kan de bara dela med en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="d79aa-142">Följande tjänster gör det möjligt att skapa grupper för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="d79aa-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="d79aa-143">Outlook Planner-projekt för webben SharePoint-strömmar Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="d79aa-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="d79aa-144">**Begränsning av grupp skapande**</span><span class="sxs-lookup"><span data-stu-id="d79aa-144">**Restriction of group creation**</span></span>

<span data-ttu-id="d79aa-145">Ett gemensamt sätt att styra Sprawl är att begränsa vilka användare som kan skapa dem.</span><span class="sxs-lookup"><span data-stu-id="d79aa-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="d79aa-146">Detta kan bara göras om du begränsar skapandet av grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="d79aa-147">Detta påverkar möjligheten att skapa grupper från andra tjänster, där det kan vara nödvändigt för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="d79aa-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="d79aa-148">Microsoft 365-grupper stöder inte möjligheten att begränsa skapande av grupper från vissa appar eller tjänster medan de tillåts från andra.</span><span class="sxs-lookup"><span data-stu-id="d79aa-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="d79aa-149">Hur grupp skapande begränsas varierar mellan program och tjänster:</span><span class="sxs-lookup"><span data-stu-id="d79aa-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="d79aa-150">App eller tjänst</span><span class="sxs-lookup"><span data-stu-id="d79aa-150">App or service</span></span>|<span data-ttu-id="d79aa-151">Funktionerna</span><span class="sxs-lookup"><span data-stu-id="d79aa-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="d79aa-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="d79aa-152">Outlook</span></span>|<span data-ttu-id="d79aa-153">Alternativet **ny grupp** tas bort från menyn nytt på sidan kontakter</span><span class="sxs-lookup"><span data-stu-id="d79aa-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="d79aa-154">Planner</span><span class="sxs-lookup"><span data-stu-id="d79aa-154">Planner</span></span>|<span data-ttu-id="d79aa-155">I den **nya planen** förklaras att grupp skapandet har inaktiverats och att du kan lägga till planen i en befintlig grupp</span><span class="sxs-lookup"><span data-stu-id="d79aa-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="d79aa-156">Projekt för webben och översikt</span><span class="sxs-lookup"><span data-stu-id="d79aa-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="d79aa-157">**Skapa grupp** -menyn förklarar hur grupp skapande är begränsat och föreslår användning av en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="d79aa-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d79aa-158">SharePoint</span></span>|<span data-ttu-id="d79aa-159">Du kan fortfarande skapa en grupp webbplats som inte är kopplad till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="d79aa-160">Strömma</span><span class="sxs-lookup"><span data-stu-id="d79aa-160">Stream</span></span>|<span data-ttu-id="d79aa-161">Alternativet **gruppera** visas inte under **menyn skapa**.</span><span class="sxs-lookup"><span data-stu-id="d79aa-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="d79aa-162">Teams</span><span class="sxs-lookup"><span data-stu-id="d79aa-162">Teams</span></span>|<span data-ttu-id="d79aa-163">Användaren kan inte skapa ett team med en ny grupp, men du kan fortfarande skapa ett team som använder en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="d79aa-164">Knappen **skapa en grupp** ersätts med **Skapa team från en grupp**.</span><span class="sxs-lookup"><span data-stu-id="d79aa-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="d79aa-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="d79aa-165">Yammer</span></span>|<span data-ttu-id="d79aa-166">Alternativet **skapa ett grupp namn** tas bort från huvud grupper och grupp navigering.</span><span class="sxs-lookup"><span data-stu-id="d79aa-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="d79aa-167">Tjänst interaktioner med grupper</span><span class="sxs-lookup"><span data-stu-id="d79aa-167">Services interactions with groups</span></span>

<span data-ttu-id="d79aa-168">Se grupperna i Microsoft 365-affisch för information om olika typer av grupper, hur de skapas och hanteras och några få rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d79aa-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="d79aa-169">[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="d79aa-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="d79aa-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="d79aa-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="d79aa-171">Följande tabell innehåller en översikt över Microsoft 365-grupper interaktioner med olika tjänster:</span><span class="sxs-lookup"><span data-stu-id="d79aa-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="d79aa-172">Produkt</span><span class="sxs-lookup"><span data-stu-id="d79aa-172">Product</span></span>|<span data-ttu-id="d79aa-173">Funktioner</span><span class="sxs-lookup"><span data-stu-id="d79aa-173">Features</span></span>|<span data-ttu-id="d79aa-174">Fungerar tjänsten</span><span class="sxs-lookup"><span data-stu-id="d79aa-174">Does the service</span></span><br><span data-ttu-id="d79aa-175">finns utan en grupp?</span><span class="sxs-lookup"><span data-stu-id="d79aa-175">exist without a group?</span></span>|<span data-ttu-id="d79aa-176">Kan tjänsten</span><span class="sxs-lookup"><span data-stu-id="d79aa-176">Can the service</span></span><br><span data-ttu-id="d79aa-177">skapa en grupp?</span><span class="sxs-lookup"><span data-stu-id="d79aa-177">create a group?</span></span>|<span data-ttu-id="d79aa-178">Tar bort</span><span class="sxs-lookup"><span data-stu-id="d79aa-178">Does deleting the</span></span><br><span data-ttu-id="d79aa-179">instans ta bort gruppen?</span><span class="sxs-lookup"><span data-stu-id="d79aa-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="d79aa-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="d79aa-180">Azure AD</span></span>|<span data-ttu-id="d79aa-181">Medlemskap, grupp kontroller, gäster</span><span class="sxs-lookup"><span data-stu-id="d79aa-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="d79aa-182">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-182">Yes</span></span>|<span data-ttu-id="d79aa-183">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-183">Yes</span></span>|<span data-ttu-id="d79aa-184">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-184">Yes</span></span>|
|<span data-ttu-id="d79aa-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="d79aa-185">Exchange</span></span>|<span data-ttu-id="d79aa-186">Kalender, post låda</span><span class="sxs-lookup"><span data-stu-id="d79aa-186">Calendar, mailbox</span></span>|<span data-ttu-id="d79aa-187">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-187">Yes</span></span>|<span data-ttu-id="d79aa-188">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-188">Yes</span></span>|<span data-ttu-id="d79aa-189">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-189">Yes</span></span>|
|<span data-ttu-id="d79aa-190">Formulär</span><span class="sxs-lookup"><span data-stu-id="d79aa-190">Forms</span></span>|<span data-ttu-id="d79aa-191">Omformning</span><span class="sxs-lookup"><span data-stu-id="d79aa-191">Form</span></span>|<span data-ttu-id="d79aa-192">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-192">Yes</span></span>|<span data-ttu-id="d79aa-193">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-193">No</span></span>|<span data-ttu-id="d79aa-194">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-194">No</span></span>|
|<span data-ttu-id="d79aa-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="d79aa-195">OneNote</span></span>|<span data-ttu-id="d79aa-196">Antecknings bok</span><span class="sxs-lookup"><span data-stu-id="d79aa-196">Notebook</span></span>|<span data-ttu-id="d79aa-197">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-197">Yes</span></span>|<span data-ttu-id="d79aa-198">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-198">No</span></span>|<span data-ttu-id="d79aa-199">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-199">No</span></span>|
|<span data-ttu-id="d79aa-200">Planner</span><span class="sxs-lookup"><span data-stu-id="d79aa-200">Planner</span></span>|<span data-ttu-id="d79aa-201">Uppgifts tavla</span><span class="sxs-lookup"><span data-stu-id="d79aa-201">Task board</span></span>|<span data-ttu-id="d79aa-202">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-202">No</span></span>|<span data-ttu-id="d79aa-203">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-203">Yes</span></span>|<span data-ttu-id="d79aa-204">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-204">Yes</span></span>|
|<span data-ttu-id="d79aa-205">Power app-appen</span><span class="sxs-lookup"><span data-stu-id="d79aa-205">Power Apps app</span></span>|<span data-ttu-id="d79aa-206">Program</span><span class="sxs-lookup"><span data-stu-id="d79aa-206">App</span></span>|<span data-ttu-id="d79aa-207">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-207">Yes</span></span>|<span data-ttu-id="d79aa-208">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-208">No</span></span>|<span data-ttu-id="d79aa-209">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-209">No</span></span>|
|<span data-ttu-id="d79aa-210">Automatisk strömförsörjning</span><span class="sxs-lookup"><span data-stu-id="d79aa-210">Power Automate</span></span>|<span data-ttu-id="d79aa-211">Arbets</span><span class="sxs-lookup"><span data-stu-id="d79aa-211">Workflow</span></span>|<span data-ttu-id="d79aa-212">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-212">Yes</span></span>|<span data-ttu-id="d79aa-213">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-213">No</span></span>|<span data-ttu-id="d79aa-214">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-214">No</span></span>|
|<span data-ttu-id="d79aa-215">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="d79aa-215">Power BI (classic)</span></span>|<span data-ttu-id="d79aa-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="d79aa-216">Workspace</span></span>|<span data-ttu-id="d79aa-217">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-217">No</span></span>|<span data-ttu-id="d79aa-218">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-218">Yes</span></span>|<span data-ttu-id="d79aa-219">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-219">Yes</span></span>|
|<span data-ttu-id="d79aa-220">Power BI (ny)</span><span class="sxs-lookup"><span data-stu-id="d79aa-220">Power BI (new)</span></span>|<span data-ttu-id="d79aa-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="d79aa-221">Workspace</span></span>|<span data-ttu-id="d79aa-222">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-222">Yes</span></span>|<span data-ttu-id="d79aa-223">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-223">No</span></span>|<span data-ttu-id="d79aa-224">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-224">Yes</span></span>|
|<span data-ttu-id="d79aa-225">Project för webben</span><span class="sxs-lookup"><span data-stu-id="d79aa-225">Project for the web</span></span>|<span data-ttu-id="d79aa-226">Projektplan</span><span class="sxs-lookup"><span data-stu-id="d79aa-226">Project plan</span></span>|<span data-ttu-id="d79aa-227">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-227">Yes</span></span>|<span data-ttu-id="d79aa-228">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-228">Yes</span></span>|<span data-ttu-id="d79aa-229">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-229">No</span></span>|
|<span data-ttu-id="d79aa-230">Översikt</span><span class="sxs-lookup"><span data-stu-id="d79aa-230">Roadmap</span></span>|<span data-ttu-id="d79aa-231">Översikt</span><span class="sxs-lookup"><span data-stu-id="d79aa-231">Roadmap</span></span>|<span data-ttu-id="d79aa-232">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-232">Yes</span></span>|<span data-ttu-id="d79aa-233">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-233">Yes</span></span>|<span data-ttu-id="d79aa-234">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-234">No</span></span>|
|<span data-ttu-id="d79aa-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d79aa-235">SharePoint</span></span>|<span data-ttu-id="d79aa-236">Webbplatsmallar</span><span class="sxs-lookup"><span data-stu-id="d79aa-236">Site</span></span>|<span data-ttu-id="d79aa-237">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-237">Yes</span></span>|<span data-ttu-id="d79aa-238">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-238">Yes</span></span>|<span data-ttu-id="d79aa-239">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-239">Yes</span></span>|
|<span data-ttu-id="d79aa-240">Strömma</span><span class="sxs-lookup"><span data-stu-id="d79aa-240">Stream</span></span>|<span data-ttu-id="d79aa-241">Kanal, video</span><span class="sxs-lookup"><span data-stu-id="d79aa-241">Channel, video</span></span>|<span data-ttu-id="d79aa-242">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-242">Yes</span></span>|<span data-ttu-id="d79aa-243">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-243">Yes</span></span>|<span data-ttu-id="d79aa-244">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-244">Yes</span></span>|
|<span data-ttu-id="d79aa-245">Teams</span><span class="sxs-lookup"><span data-stu-id="d79aa-245">Teams</span></span>|<span data-ttu-id="d79aa-246">Grupp</span><span class="sxs-lookup"><span data-stu-id="d79aa-246">Team</span></span>|<span data-ttu-id="d79aa-247">Nej</span><span class="sxs-lookup"><span data-stu-id="d79aa-247">No</span></span>|<span data-ttu-id="d79aa-248">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-248">Yes</span></span>|<span data-ttu-id="d79aa-249">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-249">Yes</span></span>|
|<span data-ttu-id="d79aa-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="d79aa-250">Yammer</span></span>|<span data-ttu-id="d79aa-251">Grupp</span><span class="sxs-lookup"><span data-stu-id="d79aa-251">Group</span></span>|<span data-ttu-id="d79aa-252">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-252">Yes</span></span>|<span data-ttu-id="d79aa-253">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-253">Yes</span></span>|<span data-ttu-id="d79aa-254">Ja</span><span class="sxs-lookup"><span data-stu-id="d79aa-254">Yes</span></span>|

<span data-ttu-id="d79aa-255">Medan tabellen ovan tillhandahåller en översikt över grupp samverkan med Microsoft 365-tjänster finns det ett antal Nuances och tag som du bör förstå.</span><span class="sxs-lookup"><span data-stu-id="d79aa-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="d79aa-256">Följande avsnitt innehåller en mer ingående titt på de specifika arbets belastningarna och deras interaktioner med grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="d79aa-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="d79aa-257">Azure AD</span></span>

<span data-ttu-id="d79aa-258">Azure AD tillhandahåller de underliggande funktionerna för identitets hantering i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d79aa-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="d79aa-259">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-260">Grupp medlemskap</span><span class="sxs-lookup"><span data-stu-id="d79aa-260">Group membership</span></span>
- <span data-ttu-id="d79aa-261">Namngivnings princip</span><span class="sxs-lookup"><span data-stu-id="d79aa-261">Naming policy</span></span>
- <span data-ttu-id="d79aa-262">Förfalloprincip</span><span class="sxs-lookup"><span data-stu-id="d79aa-262">Expiration policy</span></span>
- <span data-ttu-id="d79aa-263">Gäst</span><span class="sxs-lookup"><span data-stu-id="d79aa-263">Guests</span></span>
- <span data-ttu-id="d79aa-264">Begränsning av grupp skapande</span><span class="sxs-lookup"><span data-stu-id="d79aa-264">Restriction of Group creation</span></span>

<span data-ttu-id="d79aa-265">**Kan Azure AD skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="d79aa-266">Ja, Microsoft 365-grupper kan skapas från Azure AD antingen via administrations webb portalen, via PowerShell eller Graph API.</span><span class="sxs-lookup"><span data-stu-id="d79aa-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="d79aa-267">**Existerar Azure AD utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="d79aa-268">Ja, Azure AD utför ett stort antal tjänster som inte har någon relation till Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="d79aa-269">Alla Microsoft 365-grupper representeras som ett objekt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d79aa-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="d79aa-270">**Kan det finnas flera instanser av Azure AD per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="d79aa-271">Nej, det finns bara en instans av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d79aa-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="d79aa-272">**Kan Azure AD associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="d79aa-273">Ja, eftersom Azure AD är den underliggande plattformen som tillhandahåller grupp medlems tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d79aa-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="d79aa-274">**Kan Azure ADs Association med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-275">Nej, Azure AD är den underliggande plattformen där det finns grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="d79aa-276">**Tar du bort instansen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="d79aa-277">Om du tar bort gruppen i Azure AD raderas relevanta grupprelaterade tjänster och innehåll.</span><span class="sxs-lookup"><span data-stu-id="d79aa-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="d79aa-278">Teams</span><span class="sxs-lookup"><span data-stu-id="d79aa-278">Teams</span></span>

<span data-ttu-id="d79aa-279">Teams är en chatt-centrerad arbets yta som syftar till att förbättra samarbetet genom att tillhandahålla ett interaktivt gränssnitt för att interagera med en mängd olika Microsoft-och tredje parts tjänster.</span><span class="sxs-lookup"><span data-stu-id="d79aa-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="d79aa-280">När ett team skapas döljs som standard den post låda och kalender som är kopplad till Microsoft 365-gruppen från både den globala adress listan i Exchange och Outlook.</span><span class="sxs-lookup"><span data-stu-id="d79aa-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="d79aa-281">Det här kan åsidosättas manuellt av en administratör om användaren vill använda både Outlook och Teams i samma Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="d79aa-282">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-283">Konversationer</span><span class="sxs-lookup"><span data-stu-id="d79aa-283">Conversations</span></span>
- <span data-ttu-id="d79aa-284">Kanaler & flikar</span><span class="sxs-lookup"><span data-stu-id="d79aa-284">Channels & tabs</span></span>
- <span data-ttu-id="d79aa-285">Tider</span><span class="sxs-lookup"><span data-stu-id="d79aa-285">Meetings</span></span>

<span data-ttu-id="d79aa-286">**Kan grupper skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="d79aa-287">Ja, skapa ett nytt team skapar en ny Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="d79aa-288">Det går också att skapa ett team för en befintlig grupp som för tillfället inte har någon.</span><span class="sxs-lookup"><span data-stu-id="d79aa-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="d79aa-289">**Existerar Teams utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="d79aa-290">Nej, det är inte möjligt för ett team att existera utan en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="d79aa-291">**Kan det finnas flera team per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="d79aa-292">Nej, relationen mellan ett team och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="d79aa-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="d79aa-293">**Kan ett team vara associerat med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-294">Nej, själva teamet kan bara kopplas till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="d79aa-295">**Kan teamets associering med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-296">Nej, teamet kan bara vara kopplade till den grupp som den ursprungligen var kopplad till.</span><span class="sxs-lookup"><span data-stu-id="d79aa-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="d79aa-297">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="d79aa-298">Ja, om du tar bort teamet i Microsoft Teams tas gruppen, de gruppassocierade tjänsterna och innehållet bort.</span><span class="sxs-lookup"><span data-stu-id="d79aa-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="d79aa-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="d79aa-299">Exchange</span></span>

<span data-ttu-id="d79aa-300">Exchange Online tillhandahåller meddelanden, kalender, kontakter och tillhör ande funktioner.</span><span class="sxs-lookup"><span data-stu-id="d79aa-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="d79aa-301">I kontexten för en grupp är det bara en enskild resurs som är kopplad – i motsats till en hel tjänst instans.</span><span class="sxs-lookup"><span data-stu-id="d79aa-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="d79aa-302">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-303">Post låda och kalender</span><span class="sxs-lookup"><span data-stu-id="d79aa-303">Mailbox and calendar</span></span>
- <span data-ttu-id="d79aa-304">Möjlighet att skicka e-post till alla grupp medlemmar</span><span class="sxs-lookup"><span data-stu-id="d79aa-304">Ability to email all Group members</span></span>
- <span data-ttu-id="d79aa-305">Lagring av Team kanal konversationer för eDiscovery-syften, Planner-kommentarer</span><span class="sxs-lookup"><span data-stu-id="d79aa-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="d79aa-306">**Kan Exchange skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="d79aa-307">Ja, det är möjligt att skapa en grupp från administrations centret för Exchange Online och från Outlook.</span><span class="sxs-lookup"><span data-stu-id="d79aa-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="d79aa-308">Du kan också konvertera distributions listor för Exchange till Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="d79aa-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="d79aa-309">**Finns det ingen grupp med Exchange?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="d79aa-310">Ja, Exchange Online erbjuder ett antal tjänster, inklusive delade post lådor och kalendrar, utan grupp koppling.</span><span class="sxs-lookup"><span data-stu-id="d79aa-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="d79aa-311">**Kan det finnas flera instanser av Exchange-postlådor eller-kalendrar per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="d79aa-312">Nej, det kan bara finnas en Exchange Online-postlåda och kalender för en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="d79aa-313">**Kan Exchange-postlådor och-kalendrar associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-314">Nej, post lådan och kalendern har en 1:1-relation med gruppen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="d79aa-315">Det går att dela post lådan med andra användare eller grupper, men detta utgör ingen form av tjänst koppling.</span><span class="sxs-lookup"><span data-stu-id="d79aa-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="d79aa-316">**Kan Exchange-postlådan eller kalenderns associering med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-317">Nej, post lådan och kalendern kan inte ändras till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="d79aa-318">Innehållet kan dock flyttas från en post låda till en annan i Outlook eller med hjälp av ett verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="d79aa-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="d79aa-319">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="d79aa-320">Ja, om du tar bort post lådan i Exchange tas gruppen bort samt gruppassocierade tjänster och innehåll.</span><span class="sxs-lookup"><span data-stu-id="d79aa-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="d79aa-321">Formulär</span><span class="sxs-lookup"><span data-stu-id="d79aa-321">Forms</span></span>

<span data-ttu-id="d79aa-322">Formulär ger webbaserade undersökningar och test.</span><span class="sxs-lookup"><span data-stu-id="d79aa-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="d79aa-323">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-324">Ägandes Kap för formulär</span><span class="sxs-lookup"><span data-stu-id="d79aa-324">Ownership of forms</span></span>

<span data-ttu-id="d79aa-325">**Kan formulär skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="d79aa-326">Nej, det går inte att skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="d79aa-327">**Finns det någon som inte är en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="d79aa-328">Ja, undersökningar och test kan skapas direkt i ett slutanvändares konto.</span><span class="sxs-lookup"><span data-stu-id="d79aa-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="d79aa-329">**Kan det finnas flera former per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="d79aa-330">Ja, det kan finnas flera formulär kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="d79aa-331">**Kan formulär vara kopplade till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-332">Nej, ett formulär kan bara kopplas till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="d79aa-333">**Kan ett formulärs koppling till en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-334">Nej, när ett formulär är associerat med en grupp (antingen direkt i eller ägarskap från en person) kan den inte flyttas till en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="d79aa-335">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="d79aa-336">Nej, det går inte att ta bort en grupp från formulär gränssnittet, endast enskilda formulär.</span><span class="sxs-lookup"><span data-stu-id="d79aa-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="d79aa-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="d79aa-337">OneNote</span></span>

<span data-ttu-id="d79aa-338">OneNote är en digital antecknings bok.</span><span class="sxs-lookup"><span data-stu-id="d79aa-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="d79aa-339">Den OneNote-anteckningsbok som har skapats med en grupp är en fil på den associerade SharePoint-webbplatsen och inte i en gruppansluten tjänst.</span><span class="sxs-lookup"><span data-stu-id="d79aa-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="d79aa-340">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-341">Delad antecknings bok (lagrad i det gruppassocierade SharePoint-biblioteket)</span><span class="sxs-lookup"><span data-stu-id="d79aa-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="d79aa-342">**Kan OneNote skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="d79aa-343">Nej, OneNote-programmet kan inte skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="d79aa-344">**Finns det ingen grupp med OneNote-anteckningsböcker?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="d79aa-345">Ja, antecknings böcker kan skapas direkt i OneDrive eller på andra delade platser.</span><span class="sxs-lookup"><span data-stu-id="d79aa-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="d79aa-346">**Kan det finnas flera OneNote-anteckningsböcker per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="d79aa-347">Ja, en antecknings bok skapas som standard och andra kan läggas till, men alla länkar till OneNote från gruppassocierade tjänster kommer alltid till standard antecknings boken.</span><span class="sxs-lookup"><span data-stu-id="d79aa-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="d79aa-348">**Kan en OneNote-anteckningsbok vara kopplad till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-349">Nej, antecknings boken är lagrad i det gruppassocierade SharePoint-biblioteket och länkad från olika gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="d79aa-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="d79aa-350">Den kan delas med andra grupper på samma sätt som den kan delas med enskilda personer.</span><span class="sxs-lookup"><span data-stu-id="d79aa-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="d79aa-351">**Kan antecknings bokens förening med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-352">Nej, antecknings boken är kopplad till gruppen och kan kommas åt direkt från andra grupp anslutna tjänster, men innehållet kan flyttas från en antecknings bok till en annan i OneNote-programmet.</span><span class="sxs-lookup"><span data-stu-id="d79aa-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="d79aa-353">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="d79aa-354">Nej, om du har tagit bort OneNote-anteckningsboken kan det finnas felaktiga länkar i vissa av de gruppassocierade tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="d79aa-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="d79aa-355">Planner</span><span class="sxs-lookup"><span data-stu-id="d79aa-355">Planner</span></span>

<span data-ttu-id="d79aa-356">Planner är en lättviktig tjänst för aktivitets hantering.</span><span class="sxs-lookup"><span data-stu-id="d79aa-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="d79aa-357">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-358">Anslags tavla för att hantera grupp aktiviteter</span><span class="sxs-lookup"><span data-stu-id="d79aa-358">Board for managing group tasks</span></span>

<span data-ttu-id="d79aa-359">**Kan Planner skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="d79aa-360">Ja, skapandet av en plan skapar en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="d79aa-361">**Finns det en Planner-tavla utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="d79aa-362">Nej, en plan måste kopplas till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="d79aa-363">**Kan det finnas flera planer per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="d79aa-364">Ja, det kan finnas flera planer per grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="d79aa-365">**Kan en plan associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-366">Nej, en plan är bara avsedd för grupp medlemskap för att fastställa åtkomst.</span><span class="sxs-lookup"><span data-stu-id="d79aa-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="d79aa-367">**Kan en plans förening med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-368">Nej, om du kopierar en plan skapas en ny grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="d79aa-369">En grupp som skapats i ett annat program visas inte i Planner automatiskt för en användare.</span><span class="sxs-lookup"><span data-stu-id="d79aa-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="d79aa-370">För att få åtkomst till anslags tavlan måste de öppna den från ett annat gruppbaserade gränssnitt, till exempel Outlook.</span><span class="sxs-lookup"><span data-stu-id="d79aa-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="d79aa-371">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="d79aa-372">Ja, om du tar bort planen raderas gruppen och tillhör ande gruppassocierade tjänster och innehåll.</span><span class="sxs-lookup"><span data-stu-id="d79aa-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="d79aa-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="d79aa-373">Power Apps</span></span>

<span data-ttu-id="d79aa-374">Power Apps ger en arbets yta för program utveckling utan kod.</span><span class="sxs-lookup"><span data-stu-id="d79aa-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="d79aa-375">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-376">Appar kan delas med en grupp som ska köras och ändras</span><span class="sxs-lookup"><span data-stu-id="d79aa-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="d79aa-377">**Kan Power Apps skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="d79aa-378">Nej, Power app kan inte skapa en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="d79aa-379">**Finns det några Power Apps utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="d79aa-380">Ja, appar kan skapas i Power app och lagras i det här kontot i Creator innan de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="d79aa-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="d79aa-381">**Kan det finnas flera program per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="d79aa-382">Ja, det kan finnas flera program som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="d79aa-383">**Kan appar vara kopplade till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-384">Ja, en app kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="d79aa-385">**Kan ett program associeras med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-386">Ja, eftersom kopplingen mellan Power Apps och en Microsoft 365-grupp endast är gemensam – programmet finns fortfarande kvar med skaparen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d79aa-387">[Grupper måste aktive ras innan appar kan delas med dem](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d79aa-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="d79aa-388">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="d79aa-389">Nej, programmen är inte anslutna till den andra gruppen än de som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="d79aa-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="d79aa-390">Automatisk strömförsörjning</span><span class="sxs-lookup"><span data-stu-id="d79aa-390">Power Automate</span></span>

<span data-ttu-id="d79aa-391">Power Automation (tidigare Microsoft-flöde) tillhandahåller arbets flöden och automatiserings tjänster.</span><span class="sxs-lookup"><span data-stu-id="d79aa-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="d79aa-392">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-393">Arbets flöden kan delas med en grupp för att köras och ändras.</span><span class="sxs-lookup"><span data-stu-id="d79aa-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="d79aa-394">**Kan automatisk start skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="d79aa-395">Nej, Power autoautomatisera kan inte skapa en Microsoft 365-grupp i kontexten för att vara associerad med en.</span><span class="sxs-lookup"><span data-stu-id="d79aa-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="d79aa-396">Det är möjligt att skapa ett flöde som utför olika operationer, till exempel att skapa en Azure AD-säkerhetsgrupp eller uppdatera medlemskap för en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="d79aa-397">**Finns det fler än en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="d79aa-398">Ja, flöden kan skapas i Power automatisering och lagras i det här kontot i Creator innan de delas eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="d79aa-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="d79aa-399">**Kan det finnas flera flöden per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="d79aa-400">Ja, det kan finnas flera flöden som delas med en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="d79aa-401">**Kan ett flöde kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-402">Ja, ett flöde kan delas med flera grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="d79aa-403">**Kan flödet kopplas till en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-404">Ja, eftersom kopplingen mellan Power automatisering och en Microsoft 365-grupp endast är gemensam – flödet finns fortfarande kvar med skaparen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="d79aa-405">**Tar du bort en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="d79aa-406">Nej, som Power app, är inte flödena anslutna till den andra gruppen än de som delas med dem.</span><span class="sxs-lookup"><span data-stu-id="d79aa-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="d79aa-407">Power BI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="d79aa-407">Power BI (classic)</span></span>

<span data-ttu-id="d79aa-408">Power BI tillhandahåller interaktiva data-drivna instrument paneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="d79aa-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="d79aa-409">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-410">Data rapportering</span><span class="sxs-lookup"><span data-stu-id="d79aa-410">Data reporting</span></span>

<span data-ttu-id="d79aa-411">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="d79aa-412">Om du skapar en klassisk arbets yta skapas en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="d79aa-413">**Finns det en klassisk Power BI-arbetsyta utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="d79aa-414">Nej, [en klassisk arbets yta i Power BI måste kopplas till en grupp](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="d79aa-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="d79aa-415">**Kan det finnas flera Power BI-arbetsytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="d79aa-416">Nej, relationen mellan en klassisk arbets yta och en grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="d79aa-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="d79aa-417">**Kan en arbets yta vara kopplad till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-418">Tekniskt Nej, när den klassiska arbets ytan skapas med gruppen kan innehållet delas utanför gruppen med användare och säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="d79aa-419">**Kan arbets ytans koppling till en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="d79aa-420">Nej, den klassiska arbets ytan är kopplad till gruppen, men innehållet kan flyttas från en arbets yta till en annan inom Power BI-gränssnittet eller genom att exportera innehåll lokalt.</span><span class="sxs-lookup"><span data-stu-id="d79aa-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="d79aa-421">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="d79aa-422">Ja, om du tar bort arbets ytan i Power BI tas grupp-och gruppassocierade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="d79aa-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="d79aa-423">Power BI (ny)</span><span class="sxs-lookup"><span data-stu-id="d79aa-423">Power BI (new)</span></span>

<span data-ttu-id="d79aa-424">Power BI tillhandahåller interaktiva data-drivna instrument paneler och rapporter.</span><span class="sxs-lookup"><span data-stu-id="d79aa-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="d79aa-425">När du skapar en ny arbets yta i Power BI skapar inte en Microsoft 365-grupp, vilket skapar en ny grupp (inte klassisk) i Power BI.</span><span class="sxs-lookup"><span data-stu-id="d79aa-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="d79aa-426">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="d79aa-427">Data rapportering</span><span class="sxs-lookup"><span data-stu-id="d79aa-427">Data reporting</span></span>

<span data-ttu-id="d79aa-428">**Kan Power BI skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="d79aa-429">Nej, det går inte att skapa en Microsoft 365-grupp från det nya Power BI-gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="d79aa-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="d79aa-430">**Finns den nya Power BI-arbetsytan utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="d79aa-431">Ja, det är möjligt att ha rapporter och arbets ytor som har skapats i Power BI och som inte är kopplade till Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="d79aa-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="d79aa-432">**Kan det finnas flera arbets ytor per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="d79aa-433">Ja, [flera arbets ytor som skapas av Power BI kan delas med en enda grupp](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="d79aa-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="d79aa-434">**Kan en arbets yta vara kopplad till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-435">Nej, en arbets yta som har skapats i Power BI kan bara kopplas till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="d79aa-436">**Kan en arbets yta ha en koppling till en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="d79aa-437">Ja och nej.</span><span class="sxs-lookup"><span data-stu-id="d79aa-437">Yes and no.</span></span> <span data-ttu-id="d79aa-438">En arbets yta som har skapats i Power BI kan bara kopplas till en enskild grupp åt gången men kan ändra associeringen när som helst.</span><span class="sxs-lookup"><span data-stu-id="d79aa-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="d79aa-439">En arbets yta som har skapats i Power BI av en grupp är permanent kopplad till gruppen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="d79aa-440">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="d79aa-441">Ja, om du tar bort arbets ytan i Power BI tas grupp-och gruppassocierade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="d79aa-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="d79aa-442">Project för webben</span><span class="sxs-lookup"><span data-stu-id="d79aa-442">Project for the web</span></span>

<span data-ttu-id="d79aa-443">Project för webben ger möjlighet att skapa projektplaner, Gantt-scheman och översikter.</span><span class="sxs-lookup"><span data-stu-id="d79aa-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="d79aa-444">Viktiga funktioner i grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-444">Key features provided to groups.</span></span>

- <span data-ttu-id="d79aa-445">Projektplaner</span><span class="sxs-lookup"><span data-stu-id="d79aa-445">Project plans</span></span>

<span data-ttu-id="d79aa-446">**Kan Project skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="d79aa-447">Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från Project för webben.</span><span class="sxs-lookup"><span data-stu-id="d79aa-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="d79aa-448">**Existerar projekt utan en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="d79aa-449">Ja, projekt kan existera utan att vara kopplade till en Microsoft 365-grupp, men tilldelning av uppgifter kräver grupp koppling.</span><span class="sxs-lookup"><span data-stu-id="d79aa-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="d79aa-450">**Kan det finnas flera projekt per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="d79aa-451">Ja, det går att koppla ihop flera projekt i en och samma grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="d79aa-452">**Kan Project associeras med flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-453">Nej, ett projekt kan bara kopplas till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="d79aa-454">**Kan ett projekts associering med en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-455">Nej, när kopplingen med en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="d79aa-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="d79aa-456">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="d79aa-457">Nej, om du tar bort projektet i Project för webben raderas inte gruppen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="d79aa-458">Översikt</span><span class="sxs-lookup"><span data-stu-id="d79aa-458">Roadmap</span></span>

<span data-ttu-id="d79aa-459">Med översikt kan du skapa projekt översikter med Project för webben och Project Online.</span><span class="sxs-lookup"><span data-stu-id="d79aa-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="d79aa-460">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-461">Projekt översikter</span><span class="sxs-lookup"><span data-stu-id="d79aa-461">Project roadmaps</span></span>

<span data-ttu-id="d79aa-462">**Kan du skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="d79aa-463">Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från översikten.</span><span class="sxs-lookup"><span data-stu-id="d79aa-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="d79aa-464">**Finns det ingen grupp i översikten?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="d79aa-465">Ja, planerna kan existera utan att vara kopplade till en Microsoft 365-grupp, men det krävs grupp koppling för att dela översikten.</span><span class="sxs-lookup"><span data-stu-id="d79aa-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="d79aa-466">**Kan det finnas flera översikter per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="d79aa-467">Ja, det går att ansluta flera översikter till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="d79aa-468">**Kan en översikt vara kopplad till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-469">Nej, en översikt kan bara kopplas till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="d79aa-470">**Går det att göra en översikt över en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="d79aa-471">Nej, när kopplingen med en grupp har upprättats kan den inte ändras.</span><span class="sxs-lookup"><span data-stu-id="d79aa-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="d79aa-472">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="d79aa-473">Nej, det tar inte bort gruppen om du tar bort översikten.</span><span class="sxs-lookup"><span data-stu-id="d79aa-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="d79aa-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d79aa-474">SharePoint</span></span>

<span data-ttu-id="d79aa-475">SharePoint är en webbaserad innehålls hanterings plattform som tillhandahåller bland annat lagrings tjänster för ett antal Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="d79aa-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="d79aa-476">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-477">Dokument bibliotek</span><span class="sxs-lookup"><span data-stu-id="d79aa-477">Document library</span></span>
- <span data-ttu-id="d79aa-478">Bibliotek för lagring av OneNote-anteckningsbok</span><span class="sxs-lookup"><span data-stu-id="d79aa-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="d79aa-479">Lagring av Teams-wiki-filer</span><span class="sxs-lookup"><span data-stu-id="d79aa-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="d79aa-480">**Kan SharePoint skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="d79aa-481">Ja, när du skapar en grupp webbplats i SharePoint skapas en Microsoft 365-grupp som standard.</span><span class="sxs-lookup"><span data-stu-id="d79aa-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="d79aa-482">Det går också att skapa en grupp och, om du vill, ett team för en befintlig webbplats.</span><span class="sxs-lookup"><span data-stu-id="d79aa-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="d79aa-483">**Finns det ingen grupp med SharePoint-webbplatser?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="d79aa-484">Ja, SharePoint erbjuder ett antal icke-gruppassocierade tjänster och webbplatser som kommunikations-och nav webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d79aa-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="d79aa-485">**Kan det finnas flera webbplatser per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="d79aa-486">Nej, det kan bara finnas en webbplats per grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="d79aa-487">Privata kanaler i Teams använder ytterligare webbplatser som inte är anslutna till gruppen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="d79aa-488">**Kan webbplatser vara kopplade till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-489">Tekniskt Nej, men när en webbplats skapas med en grupp kan innehållet delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="d79aa-490">**Kan en webbplats ha en koppling till en grupp ändring?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="d79aa-491">Nej, själva webbplatsen är kopplad till gruppen, men innehållet kan flyttas från en webbplats till en annan inom SharePoint-gränssnittet genom att exportera innehåll lokalt eller med hjälp av ett verktyg från tredje part.</span><span class="sxs-lookup"><span data-stu-id="d79aa-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="d79aa-492">**Tar du bort gruppen?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="d79aa-493">Ja, om du tar bort webbplatsen i SharePoint tas grupp-och gruppassocierade tjänster bort.</span><span class="sxs-lookup"><span data-stu-id="d79aa-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="d79aa-494">Strömma</span><span class="sxs-lookup"><span data-stu-id="d79aa-494">Stream</span></span>

<span data-ttu-id="d79aa-495">Microsoft Stream är en video värd-och delnings plattform.</span><span class="sxs-lookup"><span data-stu-id="d79aa-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="d79aa-496">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-497">Video lagring</span><span class="sxs-lookup"><span data-stu-id="d79aa-497">Video storage</span></span>
- <span data-ttu-id="d79aa-498">Inspelning av Teams-möte</span><span class="sxs-lookup"><span data-stu-id="d79aa-498">Teams meeting recording</span></span>
- <span data-ttu-id="d79aa-499">Video kanaler</span><span class="sxs-lookup"><span data-stu-id="d79aa-499">Video channels</span></span>

<span data-ttu-id="d79aa-500">**Kan strömmar skapa en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="d79aa-501">Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från strömmen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="d79aa-502">**Finns det en ström utan grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="d79aa-503">Ja, video kanaler och videor kan finnas i ström utan att vara kopplade till en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="d79aa-504">**Kan det finnas flera videor och kanaler per grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="d79aa-505">Ja, det kan finnas flera videor och kanaler i varje grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="d79aa-506">**Kan en video eller kanal kopplas till flera grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="d79aa-507">Ja, medan en video eller kanal skapas med en grupp kan den delas med andra grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="d79aa-508">**Kan kopplingen till en grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="d79aa-509">Ja och nej; videor i strömmen ägs av den ursprungliga avladdaren eller Mötes inspelningen och kan kopplas till alla grupper, men video kanaler kan bara kopplas till den grupp de ursprungligen skapades i.</span><span class="sxs-lookup"><span data-stu-id="d79aa-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="d79aa-510">**Tar du bort en grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="d79aa-511">Nej, det tar inte bort gruppen om du tar bort videoklipp eller kanaler.</span><span class="sxs-lookup"><span data-stu-id="d79aa-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="d79aa-512">Om du tar bort själva gruppen i strömmen tas gruppassocierade tjänster och innehåll bort, förutom själva videoklippen.</span><span class="sxs-lookup"><span data-stu-id="d79aa-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="d79aa-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="d79aa-513">Yammer</span></span>

<span data-ttu-id="d79aa-514">Yammer är en social plattform för företag som är utformad för att kunna främja community-engagemang inom och mellan organisationer.</span><span class="sxs-lookup"><span data-stu-id="d79aa-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="d79aa-515">Om du skapar en community (tidigare "grupp") i Yammer skapas en post låda, men för närvarande används inte detta.</span><span class="sxs-lookup"><span data-stu-id="d79aa-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="d79aa-516">En Microsoft 365-grupp som är kopplad till Yammer kan inte användas med ett team i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d79aa-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="d79aa-517">**Viktiga funktioner i grupper**</span><span class="sxs-lookup"><span data-stu-id="d79aa-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="d79aa-518">Konversations område</span><span class="sxs-lookup"><span data-stu-id="d79aa-518">Conversation area</span></span>

<span data-ttu-id="d79aa-519">**Kan Yammer skapa en Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="d79aa-520">Ja, om du skapar en ny grupp i Yammer skapas en ny Microsoft 365-grupp, om plattformarna är anslutna och användaren har möjlighet att skapa en grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="d79aa-521">Det går inte att skapa en Yammer-grupp med tillhör ande Microsoft 365-grupp i gränssnitt och tjänster som inte är i Yammer.</span><span class="sxs-lookup"><span data-stu-id="d79aa-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="d79aa-522">**Finns det en Yammer-grupp utan en Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="d79aa-523">Ja, det är möjligt att skapa en Yammer-grupp utan en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="d79aa-524">Om Yammer-plattformen inte är ansluten till Microsoft 365-grupper, eller om användare inte har möjlighet att skapa en Microsoft 365-grupp, skapas Yammer-grupper utan Microsoft 365-gruppkoppling.</span><span class="sxs-lookup"><span data-stu-id="d79aa-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="d79aa-525">**Kan det finnas flera Yammer-grupper per Microsoft 365-grupp?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="d79aa-526">Nej, relationen mellan en Yammer-grupp och en Microsoft 365-grupp är 1:1.</span><span class="sxs-lookup"><span data-stu-id="d79aa-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="d79aa-527">**Kan en Yammer-grupp associeras med flera Microsoft 365-grupper?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="d79aa-528">Nej, Yammer-gruppen kan bara kopplas till en enda Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d79aa-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="d79aa-529">Det är möjligt att inlägg delas med eller flyttas till andra Yammer-grupper.</span><span class="sxs-lookup"><span data-stu-id="d79aa-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="d79aa-530">**Kan en Yammer-grupps koppling till en Microsoft 365-grupp ändras?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="d79aa-531">Nej, Yammer-gruppen kan bara associeras med den Microsoft 365-grupp som den ursprungligen var kopplad till.</span><span class="sxs-lookup"><span data-stu-id="d79aa-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="d79aa-532">**Tar du bort Yammer-gruppen ta bort gruppen Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="d79aa-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="d79aa-533">Ja, om du tar bort gruppen i Yammer tas tillhör ande Microsoft-grupper och gruppassocierade tjänster och innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="d79aa-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

