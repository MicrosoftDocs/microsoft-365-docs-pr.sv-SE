---
title: Distribuera röst i Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Lär dig hur du väljer och distribuerar rätt Teams röst lösning för din organisation.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580917"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="9069e-103">Planera och distribuera en telefon lösning för Teams</span><span class="sxs-lookup"><span data-stu-id="9069e-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="9069e-104">Med en telefon lösning för team kan folk i organisationen ringa både inom och utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="9069e-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="9069e-105">En komplett röst lösning består av team, Microsoft Phone system och ett urval av alternativ för anslutning till det offentliga telefonnätet.</span><span class="sxs-lookup"><span data-stu-id="9069e-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Översikt över Teams Voice Solutions](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="9069e-107">Telefon systemet innehåller fullständiga PBX-funktioner (Private Branch Exchange) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="9069e-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="9069e-108">Samtal mellan användare i organisationen--oavsett deras geografiska plats – hanteras internt i telefon systemet och tar bort lång distans kostnader för dessa interna samtal.</span><span class="sxs-lookup"><span data-stu-id="9069e-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="9069e-109">Genom att ansluta telefon systemet till det offentliga telefonnät verket kan dina team användare även ringa samtal utanför din organisation.</span><span class="sxs-lookup"><span data-stu-id="9069e-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="9069e-110">Denna lösning hjälper dig att:</span><span class="sxs-lookup"><span data-stu-id="9069e-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="9069e-111">Välj den röst lösning som passar din organisation</span><span class="sxs-lookup"><span data-stu-id="9069e-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="9069e-112">Distribuera den valda röst lösningen</span><span class="sxs-lookup"><span data-stu-id="9069e-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="9069e-113">Följ de här stegen för att välja, planera och konfigurera din röst lösning:</span><span class="sxs-lookup"><span data-stu-id="9069e-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Välj din röst lösning](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="9069e-115">Välj din röst lösning</span><span class="sxs-lookup"><span data-stu-id="9069e-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="9069e-116">Konfigurera telefon system</span><span class="sxs-lookup"><span data-stu-id="9069e-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="9069e-117">Konfigurera PSTN-anslutning genom att välja en kombination av följande:</span><span class="sxs-lookup"><span data-stu-id="9069e-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="9069e-118">[Samtals plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) – Microsofts allt-i-moln-lösning med Microsoft som PSTN-bärvåg</span><span class="sxs-lookup"><span data-stu-id="9069e-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="9069e-119">[Direkt routning](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) – Använd dirigerad routning för att ansluta din egen PSTN-bärvåg till Teams</span><span class="sxs-lookup"><span data-stu-id="9069e-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="9069e-120">Dessutom kanske du vill veta mer om hur en stor, flerspråkig organisation migreras till en organisations Voice-lösning i den [contoso-fallstudien](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="9069e-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="9069e-121">Information om nödvändiga licenser finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="9069e-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="9069e-122">Team tilläggs licenser</span><span class="sxs-lookup"><span data-stu-id="9069e-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="9069e-123">Licensierings krav för Direct-routning</span><span class="sxs-lookup"><span data-stu-id="9069e-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
