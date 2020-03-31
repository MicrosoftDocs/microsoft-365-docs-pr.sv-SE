---
title: Distribuera Microsoft Teams för Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig steg för steg och lansera sedan Microsoft Teams i hela organisationen.
ms.openlocfilehash: 8220d06fe90bc4bc793ab33d6121e93bb855f973
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2019
ms.locfileid: "42812934"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="c9492-103">Distribuera Microsoft Teams för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9492-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c9492-104">*Den här arbetsbelastningen ingår i både version E3 och E5 av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c9492-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c9492-105">Microsoft Teams kombinerar chatt, konferenser, dokumentdelning och trådade konversationer på ett sätt som gör det enkelt att skapa och dela innehåll i grupper.</span><span class="sxs-lookup"><span data-stu-id="c9492-105">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups.</span></span> <span data-ttu-id="c9492-106">Teams är din metod för grupp- och samarbete med Microsoft 365 Enterprise och är en viktig del av konceptet Utvecklat för samarbete hos Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9492-106">Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="c9492-107">Om du aldrig har använt Teams tidigare kan du läsa mer i [Välkommen till Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span><span class="sxs-lookup"><span data-stu-id="c9492-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="c9492-108">Distribuera Teams i din organisation</span><span class="sxs-lookup"><span data-stu-id="c9492-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="c9492-109">Innan du börjar:</span><span class="sxs-lookup"><span data-stu-id="c9492-109">Before you begin:</span></span>

- <span data-ttu-id="c9492-110">Kontrollera att du har konfigurerat rätt faser för [grundinfrastrukturen](deploy-foundation-infrastructure.md) så att dina grupper har de användarkonton och säkerhetsfunktioner du behöver.</span><span class="sxs-lookup"><span data-stu-id="c9492-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="c9492-111">Faserna för identitets- och informationsskydd är viktigast för inloggning och för att kunna använda e-post och filer säkert med kvarhållnings- och känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="c9492-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="c9492-112">I [den här artikeln](https://docs.microsoft.com/microsoftteams/security-compliance-overview) kan du lära dig mer om säkerhet och efterlevnad i Teams.</span><span class="sxs-lookup"><span data-stu-id="c9492-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="c9492-113">I [den här artikeln](https://docs.microsoft.com/microsoftteams/office-365-licensing) kan du läsa mer om Office 365-licensiering för Teams.</span><span class="sxs-lookup"><span data-stu-id="c9492-113">Learn about Office 365 licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="c9492-114">Om du vill lansera Teams i din organisation läser du [Så lanserar du Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span><span class="sxs-lookup"><span data-stu-id="c9492-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="c9492-115">Du kan hitta mer information om din första uppsättning funktioner i Teams i [Chattar, grupper, kanaler och appar i Microsoft Teams
](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span><span class="sxs-lookup"><span data-stu-id="c9492-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="c9492-116">Information om mer avancerade funktioner i Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="c9492-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="c9492-117">Möten och konferenser</span><span class="sxs-lookup"><span data-stu-id="c9492-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="c9492-118">[Cloud Voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (kräver Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="c9492-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 E5)</span></span>

<span data-ttu-id="c9492-119">Information om hur du övervakar organisationens användning av Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="c9492-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="c9492-120">Analys av flera och enstaka grupper i Teams</span><span class="sxs-lookup"><span data-stu-id="c9492-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="c9492-121">Analyser och rapporter</span><span class="sxs-lookup"><span data-stu-id="c9492-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="c9492-122">Uppgradera till Teams</span><span class="sxs-lookup"><span data-stu-id="c9492-122">Upgrade to Teams</span></span>

<span data-ttu-id="c9492-123">Om du inte redan har gjort det kommer du snart att uppgradera från Skype för företag till Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9492-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="c9492-124">Oavsett om du precis har kommit igång med Teams, redan använder Teams parallellt med Skype för företag eller känner dig redo att uppgradera, vill vi se till att du har allt du behöver för att få en bra start med Teams.</span><span class="sxs-lookup"><span data-stu-id="c9492-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="c9492-125">Oavsett om du uppgraderar till Teams från Skype för företag – Online eller från en lokal Skype för företag-miljö till Teams ger uppgraderingsramverket en översikt över processen baserat på ditt företagsscenario.</span><span class="sxs-lookup"><span data-stu-id="c9492-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="c9492-126">Mer information finns i [Komma igång med uppgraderingen till Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="c9492-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c9492-127">Så här används Microsoft 365 Enterprise på Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9492-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c9492-128">Vill du se hur vi själva har distribuerat Teams på Microsoft och använder det för samarbete kan du läsa i:</span><span class="sxs-lookup"><span data-stu-id="c9492-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="c9492-129">Microsofts strategi för införande av Teams förbereder medarbetarna för en ny arbetskultur</span><span class="sxs-lookup"><span data-stu-id="c9492-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="c9492-130">Microsoft Teams Rum ger en globalt skalbar, modern mötesupplevelse</span><span class="sxs-lookup"><span data-stu-id="c9492-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="c9492-131">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c9492-131">Next steps</span></span>

- [<span data-ttu-id="c9492-132">Hantera Microsoft Teams-funktioner för din organisation</span><span class="sxs-lookup"><span data-stu-id="c9492-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="c9492-133">Administratörsutbildning för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9492-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

