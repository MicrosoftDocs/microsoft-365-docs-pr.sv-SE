---
title: Översikt över incidenter i Microsoft 365 Defender
description: Undersök incidenter som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
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
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068923"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="4db79-104">Översikt över incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4db79-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4db79-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4db79-105">**Applies to:**</span></span>
- <span data-ttu-id="4db79-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4db79-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="4db79-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4db79-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="4db79-108">Du kan [utvärdera den i en labbmiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller köra [pilotprojektet i produktion.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="4db79-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="4db79-109">Incidenterna baseras på relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="4db79-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="4db79-110">Aviseringar skapas när en skadlig händelse eller aktivitet visas i nätverket.</span><span class="sxs-lookup"><span data-stu-id="4db79-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="4db79-111">Enskilda aviseringar ger värdefulla ledtrådar om en 1:e attack.</span><span class="sxs-lookup"><span data-stu-id="4db79-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="4db79-112">Men attacker använder vanligtvis olika vektorer och tekniker för att utföra ett intrång.</span><span class="sxs-lookup"><span data-stu-id="4db79-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="4db79-113">Det kan vara svårt och tidskrävande att samla enskilda ledtrådar.</span><span class="sxs-lookup"><span data-stu-id="4db79-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="4db79-114">Den här korta videon ger en översikt över incidenter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4db79-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4db79-115">En incident är en samling korrelerade varningar som utgör berättelse om en attack.</span><span class="sxs-lookup"><span data-stu-id="4db79-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="4db79-116">Skadliga och misstänkta händelser som hittas på olika enheter, användare och postlådeenheter i nätverket aggregeras automatiskt av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4db79-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="4db79-117">Att gruppera relaterade aviseringar till en händelse ger säkerhetssäkerhet en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="4db79-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="4db79-118">Säkerhetsvakten kan till exempel se var attacken började, vilka taktiker som användes och hur långt attacken har varit i nätverket.</span><span class="sxs-lookup"><span data-stu-id="4db79-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="4db79-119">De kan också se attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades, hur allvarligt påverkan det var och annan information om berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="4db79-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="4db79-120">Om den är aktiverad kan Microsoft 365 Defender automatiskt undersöka och lösa enskilda aviseringar via automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="4db79-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4db79-121">Säkerhetshändelser kan också utföra ytterligare åtgärdsåtgärder för att lösa attacken direkt från händelsevyn.</span><span class="sxs-lookup"><span data-stu-id="4db79-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="4db79-122">Incidenter från de senaste 30 dagarna visas i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="4db79-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="4db79-123">Säkerhetsärenden kan direkt se vilka ärenden som ska prioriteras utifrån risknivå och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="4db79-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="4db79-124">Säkerhetsärenden kan också byta namn på incidenter, tilldela dem till enskilda analytiker, klassificera och lägga till taggar i incidenter för att få en bättre och mer anpassad upplevelse med incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="4db79-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="4db79-125">Se även</span><span class="sxs-lookup"><span data-stu-id="4db79-125">See also</span></span>
- [<span data-ttu-id="4db79-126">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="4db79-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="4db79-127">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="4db79-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4db79-128">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="4db79-128">Manage incidents</span></span>](manage-incidents.md)