---
title: Introduktion till att svara på din första incident
description: Grundläggande information om hur du svarar på din första incident i Microsoft 365 Defender.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
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
ms.openlocfilehash: 6e65a12f42b9f5f75c1a19cb9c4a261c94feaf31
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841720"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="61490-104">Introduktion till att svara på din första incident</span><span class="sxs-lookup"><span data-stu-id="61490-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="61490-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="61490-105">**Applies to:**</span></span>
- <span data-ttu-id="61490-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61490-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="61490-107">Organisationens strategi för incidentåtgärder avgör om organisationen kan hantera allt störande säkerhetstillbud och cyberbrott.</span><span class="sxs-lookup"><span data-stu-id="61490-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="61490-108">Att vidta preventativa åtgärder är viktigt, men möjligheten att agera snabbt för att begränsa, radera och återställa efter identifierade incidenter kan minimera skador och affärsförluster.</span><span class="sxs-lookup"><span data-stu-id="61490-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="61490-109">Den här genomgången av incidentåtgärder visar hur du som en del av ett team för säkerhetsåtgärder kan utföra de flesta viktiga åtgärder för incidenter i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="61490-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="61490-110">Här är stegen:</span><span class="sxs-lookup"><span data-stu-id="61490-110">Here are the steps:</span></span>

- <span data-ttu-id="61490-111">Förberedelse av din säkerhetsstatus</span><span class="sxs-lookup"><span data-stu-id="61490-111">Preparation of your security posture</span></span>
- <span data-ttu-id="61490-112">För varje incident:</span><span class="sxs-lookup"><span data-stu-id="61490-112">For each incident:</span></span>
  - <span data-ttu-id="61490-113">Steg 1: Triage och analys</span><span class="sxs-lookup"><span data-stu-id="61490-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="61490-114">Steg 2: Åtgärd (inneslutning, överläggning och återställning)</span><span class="sxs-lookup"><span data-stu-id="61490-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="61490-115">Steg 3: Granskning efter incident</span><span class="sxs-lookup"><span data-stu-id="61490-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="61490-116">Ett säkerhetsincident definieras av National Institute of Standards and Technology (NIST) som "en förekomst som faktiskt eller potentiellt uppfyller sekretess, integritet eller tillgänglighet för ett informationssystem. eller den information som systemet bearbetar, lagrar eller överför; eller som utgör en överträdelse eller omedelbart hot om brott mot säkerhetsprinciper, säkerhetsmetoder eller principer för acceptabel användning."</span><span class="sxs-lookup"><span data-stu-id="61490-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="61490-117">Incidenter i Microsoft 365 Defender är den logiska utgångspunkten för analys och incidentsvar.</span><span class="sxs-lookup"><span data-stu-id="61490-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="61490-118">Att analysera och åtgärda incidenter utgör vanligtvis de flesta av ett säkerhetsoperationsteams uppgifter.</span><span class="sxs-lookup"><span data-stu-id="61490-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="61490-119">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="61490-119">Next step</span></span>

<span data-ttu-id="61490-120">[![Förbereda organisationen och Microsoft 365 klientorganisation](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="61490-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="61490-121">Se till att din organisation Microsoft 365 klientorganisationen är [förberedda för incidenthantering.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="61490-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61490-122">Se även</span><span class="sxs-lookup"><span data-stu-id="61490-122">See also</span></span>

<span data-ttu-id="61490-123">Vägledning om incidentsvar för Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="61490-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="61490-124">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="61490-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="61490-125">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="61490-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="61490-126">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="61490-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="61490-127">Ytterligare exempel på svar på första incidenter:</span><span class="sxs-lookup"><span data-stu-id="61490-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="61490-128">Nätfiske-e-post</span><span class="sxs-lookup"><span data-stu-id="61490-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="61490-129">Identitetsbasattack</span><span class="sxs-lookup"><span data-stu-id="61490-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="61490-130">Detaljerade spelböcker för incidentsvar</span><span class="sxs-lookup"><span data-stu-id="61490-130">Detailed incident response playbooks</span></span>](/security/compass/incident-response-playbooks)


