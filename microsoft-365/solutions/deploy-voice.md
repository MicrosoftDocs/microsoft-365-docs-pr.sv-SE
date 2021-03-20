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
description: Lär dig hur du väljer och distribuerar rätt Röstlösning för Teams för din organisation.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918388"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="69213-103">Planera och distribuera en Teams röstlösning</span><span class="sxs-lookup"><span data-stu-id="69213-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="69213-104">Med en röstlösning i Teams kan personer i organisationen ringa samtal både inom och utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="69213-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="69213-105">En fullständig röstlösning består av Teams, Microsoft Phone System och ett urval av alternativ för anslutning till det publika telenätet (PSTN).</span><span class="sxs-lookup"><span data-stu-id="69213-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Översikt över röstlösningar för Teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="69213-107">Telefonsystemet tillhandahåller kompletta PBX-funktioner (Private Branch Exchange) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="69213-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="69213-108">Samtal mellan användare i din organisation – oavsett deras geografiska plats – hanteras internt i telefonsystemet, vilket tar bort kostnader för långa avstånd för dessa interna samtal.</span><span class="sxs-lookup"><span data-stu-id="69213-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="69213-109">Genom att ansluta telefonsystemet till PSTN-nätverket (Public Switched Telephone Network) kan dina Teams-användare även ringa samtal utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="69213-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="69213-110">Med hjälp av den här lösningsvägledning kan du:</span><span class="sxs-lookup"><span data-stu-id="69213-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="69213-111">Välj den röstlösning som är rätt för din organisation</span><span class="sxs-lookup"><span data-stu-id="69213-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="69213-112">Distribuera den röstlösning du valt</span><span class="sxs-lookup"><span data-stu-id="69213-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="69213-113">Följ de här anvisningarna för att välja, planera och konfigurera din röstlösning:</span><span class="sxs-lookup"><span data-stu-id="69213-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Välj din röstlösning](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="69213-115">Välj din röstlösning</span><span class="sxs-lookup"><span data-stu-id="69213-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="69213-116">Konfigurera telefonsystem</span><span class="sxs-lookup"><span data-stu-id="69213-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="69213-117">Konfigurera PSTN-anslutning genom att välja en eller en kombination av följande:</span><span class="sxs-lookup"><span data-stu-id="69213-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="69213-118">[Samtalsabonnemang](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) – Microsofts lösning för hela molnet med Microsoft som PSTN-operatör</span><span class="sxs-lookup"><span data-stu-id="69213-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="69213-119">[Direkt routning](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) – Använd direkt routning för att ansluta din egen PSTN-operatör till Teams</span><span class="sxs-lookup"><span data-stu-id="69213-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="69213-120">Dessutom kanske du vill läsa om hur ett stort, multinationellt företag migrerat till en Röstlösning för Teams i [Contoso-fallstudien.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="69213-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="69213-121">Mer information om obligatoriska licenser finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="69213-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="69213-122">Tilläggslicenser för Teams</span><span class="sxs-lookup"><span data-stu-id="69213-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="69213-123">Licenskrav för direktdirigering</span><span class="sxs-lookup"><span data-stu-id="69213-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)