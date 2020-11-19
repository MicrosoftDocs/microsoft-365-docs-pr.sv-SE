---
title: Incidenter översikt i Microsoft 365 Defender
description: Undersök tillbud som visas på enheter, användare och post lådor.
keywords: incidenter, varningar, undersöka, korrelation, attacker, datorer, enheter, användare, identiteter, identitet, post låda, e-post, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357617"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="9ad14-104">Incidenter översikt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ad14-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9ad14-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9ad14-105">**Applies to:**</span></span>
- <span data-ttu-id="9ad14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ad14-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="9ad14-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9ad14-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9ad14-108">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="9ad14-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="9ad14-109">Händelser är baserade på relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="9ad14-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="9ad14-110">Aviseringar skapas när en illvillig händelse eller aktivitet visas i nätverket.</span><span class="sxs-lookup"><span data-stu-id="9ad14-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="9ad14-111">Enskilda meddelanden ger värdefulla LED trådar om pågående attacker.</span><span class="sxs-lookup"><span data-stu-id="9ad14-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="9ad14-112">Däremot använder angrepp olika vektorer och teknik för att genomföra en överträdelse.</span><span class="sxs-lookup"><span data-stu-id="9ad14-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="9ad14-113">Piecing enskilda LED trådar kan vara utmanande och tids krävande.</span><span class="sxs-lookup"><span data-stu-id="9ad14-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="9ad14-114">I den här korta videon får du en översikt över händelser i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9ad14-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="9ad14-115">En olycka är en samling med korrelerade aviseringar som utgör artikeln om en attack.</span><span class="sxs-lookup"><span data-stu-id="9ad14-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="9ad14-116">Skadliga och misstänkta händelser som hittas i olika enheter, användare och post lådor i nätverket aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9ad14-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="9ad14-117">Om du grupprelaterade notifieringar till en olycka får säkerhets försvararna en omfattande översikt över en attack.</span><span class="sxs-lookup"><span data-stu-id="9ad14-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="9ad14-118">Säkerhets försvarare kan till exempel se var angreppet startade, vilken taktiker som användes och hur långt angreppet har gått till nätverket.</span><span class="sxs-lookup"><span data-stu-id="9ad14-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="9ad14-119">De kan också se omfattningen av angreppet, till exempel hur många enheter, användare och post lådor som påverkades, hur allvarligt det var och andra detaljer om berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="9ad14-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="9ad14-120">Om den är aktive rad kan Microsoft 365 Defender automatiskt undersöka och lösa enskilda aviseringar via automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="9ad14-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="9ad14-121">Säkerhets försvarare kan även utföra ytterligare åtgärder för att lösa angreppen direkt från vyn incidenter.</span><span class="sxs-lookup"><span data-stu-id="9ad14-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="9ad14-122">Incidenter från de senaste 30 dagarna visas i incident kön.</span><span class="sxs-lookup"><span data-stu-id="9ad14-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="9ad14-123">Härifrån kan säkerhets försvarare se vilka händelser som ska prioriteras baserat på risk nivå och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="9ad14-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="9ad14-124">Säkerhets försvarare kan även byta namn på incidenter, tilldela dem enskilda analyser, klassificera och lägga till taggar i tillbud för att få en bättre och mer anpassningsbar upplevelse för problem hantering.</span><span class="sxs-lookup"><span data-stu-id="9ad14-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="9ad14-125">Se även</span><span class="sxs-lookup"><span data-stu-id="9ad14-125">See also</span></span>
- [<span data-ttu-id="9ad14-126">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="9ad14-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="9ad14-127">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="9ad14-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="9ad14-128">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="9ad14-128">Manage incidents</span></span>](manage-incidents.md)
