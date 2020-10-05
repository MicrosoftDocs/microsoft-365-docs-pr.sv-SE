---
title: Incidenter översikt i Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c9b495b70c8b61188b4db3175b54e406feb87fc8
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357848"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="3a8a7-104">Incidenter översikt i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3a8a7-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3a8a7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3a8a7-105">**Applies to:**</span></span>
- <span data-ttu-id="3a8a7-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3a8a7-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3a8a7-107">Händelser är baserade på relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="3a8a7-108">Aviseringar skapas när en illvillig händelse eller aktivitet visas i nätverket.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="3a8a7-109">Enskilda meddelanden ger värdefulla LED trådar om pågående attacker.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="3a8a7-110">Däremot använder angrepp olika vektorer och teknik för att genomföra en överträdelse.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="3a8a7-111">Piecing enskilda LED trådar kan vara utmanande och tids krävande.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="3a8a7-112">Den här korta videon ger en översikt över incidenter i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="3a8a7-113">En olycka är en samling med korrelerade aviseringar som utgör artikeln om en attack.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="3a8a7-114">Illvilliga och misstänkta händelser som finns i olika enheter, användare och post lådor i nätverket aggregeras automatiskt efter Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="3a8a7-115">Om du grupprelaterade notifieringar till en olycka får säkerhets försvararna en omfattande översikt över en attack.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="3a8a7-116">Säkerhets försvarare kan till exempel se var angreppet startade, vilken taktiker som användes och hur långt angreppet har gått till nätverket.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="3a8a7-117">De kan också se omfattningen av angreppet, till exempel hur många enheter, användare och post lådor som påverkades, hur allvarligt det var och andra detaljer om berörda enheter.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="3a8a7-118">Om den är aktive rad kan Microsoft Threat Protection automatiskt undersöka och lösa enskilda aviseringar via automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="3a8a7-119">Säkerhets försvarare kan även utföra ytterligare åtgärder för att lösa angreppen direkt från vyn incidenter.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="3a8a7-120">Incidenter från de senaste 30 dagarna visas i incident kön.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="3a8a7-121">Härifrån kan säkerhets försvarare se vilka händelser som ska prioriteras baserat på risk nivå och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="3a8a7-122">Säkerhets försvarare kan även byta namn på incidenter, tilldela dem enskilda analyser, klassificera och lägga till taggar i tillbud för att få en bättre och mer anpassningsbar upplevelse för problem hantering.</span><span class="sxs-lookup"><span data-stu-id="3a8a7-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="3a8a7-123">Se även</span><span class="sxs-lookup"><span data-stu-id="3a8a7-123">See also</span></span>
- [<span data-ttu-id="3a8a7-124">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="3a8a7-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="3a8a7-125">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="3a8a7-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="3a8a7-126">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="3a8a7-126">Manage incidents</span></span>](manage-incidents.md)
