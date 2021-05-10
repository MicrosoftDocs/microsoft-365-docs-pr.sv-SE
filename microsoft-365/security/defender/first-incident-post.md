---
title: Steg 3. Granska ditt första incident efter incidenten
description: Så här utför du en granskning av din första incident i Microsoft 365 Defender.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 44f583d32de166fe3d68a182406eb3a2ee814084
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297158"
---
# <a name="step-3-perform-a-post-incident-review-of-your-first-incident"></a><span data-ttu-id="0d146-105">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="0d146-105">Step 3.</span></span> <span data-ttu-id="0d146-106">Granska ditt första incident efter incidenten</span><span class="sxs-lookup"><span data-stu-id="0d146-106">Perform a post-incident review of your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0d146-107">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0d146-107">**Applies to:**</span></span>
- <span data-ttu-id="0d146-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d146-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="0d146-109">National Institute of Standards and Technology (NIST) rekommenderar att organisationer måste granska incidenten för att kunna lära sig av den och lära sig och förbättra säkerheten, när alla åtgärder har vidtagits för att återställa attackerna.</span><span class="sxs-lookup"><span data-stu-id="0d146-109">National Institute of Standards and Technology (NIST) recommends that once all steps have been taken to recover from the attack, organizations must review the incident to learn from it and learn and improve security posture or processes.</span></span> <span data-ttu-id="0d146-110">Att utvärdera olika aspekter av incidenthantering är viktigt i förberedelsen för nästa incident.</span><span class="sxs-lookup"><span data-stu-id="0d146-110">Assessing the different aspects of incident-handling becomes important in preparing for the next incident.</span></span>

<span data-ttu-id="0d146-111">Microsoft 365 Defender kan hjälpa till med att utföra aktiviteter efter incidenter genom att skicka ett meddelande till organisationen med aviseringar som stämmer överens med [MITRE ATT&CK Framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="0d146-111">Microsoft 365 Defender can assist in performing post-incident activities by providing an organization with alerts that align with [MITRE ATT&CK Framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="0d146-112">Alla etikettattacker på Microsoft Defender-lösningar i enlighet med en ATT&CK-taktik eller -teknik.</span><span class="sxs-lookup"><span data-stu-id="0d146-112">All Microsoft Defender solutions label attacks in accordance with an ATT&CK tactic or technique.</span></span> 

<span data-ttu-id="0d146-113">Genom att mappa aviseringar till det här branschramverket kan du:</span><span class="sxs-lookup"><span data-stu-id="0d146-113">By mapping alerts to this industry framework, you can:</span></span>

- <span data-ttu-id="0d146-114">Genomför en analys av luckor i säkerhetstäckningen.</span><span class="sxs-lookup"><span data-stu-id="0d146-114">Conduct an analysis of gaps in security coverage.</span></span>
- <span data-ttu-id="0d146-115">Fastställa adversary- och kampanjattribution.</span><span class="sxs-lookup"><span data-stu-id="0d146-115">Determine adversary and campaign attribution.</span></span>
- <span data-ttu-id="0d146-116">Utföra trendanalyser.</span><span class="sxs-lookup"><span data-stu-id="0d146-116">Perform trend analysis.</span></span>
- <span data-ttu-id="0d146-117">Identifiera kompetensbrister i information om attackmetoden.</span><span class="sxs-lookup"><span data-stu-id="0d146-117">Identify skill gaps in attack method awareness.</span></span>
- <span data-ttu-id="0d146-118">Skapa en Power Automate Playbook för snabbare åtgärd.</span><span class="sxs-lookup"><span data-stu-id="0d146-118">Create a Power Automate Playbook for faster remediation.</span></span> 

<span data-ttu-id="0d146-119">Granskningsaktivitet efter incidenter kan också resultera i finjustering av din säkerhetskonfiguration och säkerhetsteamets processer, och förbättra organisationens svarsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="0d146-119">Post-incident review activity can also result in fine-tuning your security configuration and security team's processes, enhancing your organization’s response capabilities.</span></span>

## <a name="next-step"></a><span data-ttu-id="0d146-120">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0d146-120">Next step</span></span>

<span data-ttu-id="0d146-121">Se följande ytterligare undersökningssökvägar:</span><span class="sxs-lookup"><span data-stu-id="0d146-121">See these additional investigation paths:</span></span>

- [<span data-ttu-id="0d146-122">Nätfiske-e-post</span><span class="sxs-lookup"><span data-stu-id="0d146-122">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="0d146-123">Identitetsbaserad attack</span><span class="sxs-lookup"><span data-stu-id="0d146-123">Identity-based attack</span></span>](first-incident-path-identity.md)


## <a name="see-also"></a><span data-ttu-id="0d146-124">Se även</span><span class="sxs-lookup"><span data-stu-id="0d146-124">See also</span></span>

- [<span data-ttu-id="0d146-125">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="0d146-125">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0d146-126">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="0d146-126">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="0d146-127">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="0d146-127">Manage incidents</span></span>](manage-incidents.md)
