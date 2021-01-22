---
title: Översikt över incidenter i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929288"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="30862-104">Översikt över incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30862-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30862-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="30862-105">**Applies to:**</span></span>
- <span data-ttu-id="30862-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30862-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="30862-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="30862-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="30862-108">Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="30862-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="30862-109">Incidenter baseras på relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="30862-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="30862-110">Aviseringar skapas när en skadlig händelse eller aktivitet visas på nätverket.</span><span class="sxs-lookup"><span data-stu-id="30862-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="30862-111">Enskilda varningar ger värdefulla ledtrådar om en going attack.</span><span class="sxs-lookup"><span data-stu-id="30862-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="30862-112">Attacker använder emellertid vanligtvis olika vektorer och tekniker för att utföra ett intrång.</span><span class="sxs-lookup"><span data-stu-id="30862-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="30862-113">Det kan vara svårt och tidskrävande att skapa cirkeldiagram för enskilda ledtrådar tillsammans.</span><span class="sxs-lookup"><span data-stu-id="30862-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="30862-114">Den här korta videon ger en översikt över incidenter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="30862-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="30862-115">En incident är en samling korrelerade varningar som utgör en berättelse om en attack.</span><span class="sxs-lookup"><span data-stu-id="30862-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="30862-116">Skadliga och misstänkta händelser som hittas på olika enheter, användare och postlådeenheter i nätverket aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="30862-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="30862-117">Om du grupperar relaterade aviseringar till en händelse får säkerhetsvarningen en omfattande översikt över en attack.</span><span class="sxs-lookup"><span data-stu-id="30862-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="30862-118">Säkerhetssäkerhet kan till exempel se var attacken började, vilka taktiker som användes och hur långt attacken har varit i nätverket.</span><span class="sxs-lookup"><span data-stu-id="30862-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="30862-119">De kan också se attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades, hur allvarligt påverkan det var och annan information om berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="30862-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="30862-120">Om den är aktiverad kan Microsoft 365 Defender automatiskt undersöka och lösa enskilda varningar genom automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="30862-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="30862-121">Säkerhetsärenden kan också vidta ytterligare åtgärder för att lösa attacken direkt från händelsevyn.</span><span class="sxs-lookup"><span data-stu-id="30862-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="30862-122">Incidenter från de senaste 30 dagarna visas i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="30862-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="30862-123">Härifrån kan säkerhetsärenden se vilka ärenden som ska prioriteras baserat på risknivå och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="30862-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="30862-124">Säkerhetsärenden kan också byta namn på incidenter, tilldela dem till enskilda analytiker, klassificera och lägga till taggar i incidenter för att få en bättre och mer anpassad upplevelse för incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="30862-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="30862-125">Se även</span><span class="sxs-lookup"><span data-stu-id="30862-125">See also</span></span>
- [<span data-ttu-id="30862-126">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="30862-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="30862-127">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="30862-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="30862-128">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="30862-128">Manage incidents</span></span>](manage-incidents.md)
