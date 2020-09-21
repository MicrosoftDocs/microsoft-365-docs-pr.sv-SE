---
title: Kör ditt pilot Microsoft Threat Protection Project
description: Kör ditt pilot Microsoft Threat Protection-projekt i produktionen för att effektivt fastställa fördelarna och antagandet av Microsoft Threat Protection (MTP).
keywords: Microsoft Threat Protection pilot, kör pilot Microsoft Threat Protection Project, utvärdera Microsoft Threat Protection i Production, Microsoft Threat Protection Pilot-projekt, cyberterrorism-säkerhet, Avancerat hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: bf080fddd7545c4397483c0eba7a010952922e7e
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956533"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="deee6-104">Kör ditt pilot Microsoft Threat Protection Project</span><span class="sxs-lookup"><span data-stu-id="deee6-104">Run your pilot Microsoft Threat Protection project</span></span> 

<span data-ttu-id="deee6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="deee6-105">**Applies to:**</span></span>
- <span data-ttu-id="deee6-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="deee6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="deee6-107">För att effektivt fastställa fördelarna och antagandet av Microsoft Threat Protection (MTP) kan du köra ett pilot projekt.</span><span class="sxs-lookup"><span data-stu-id="deee6-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="deee6-108">Innan du aktiverar Microsoft Threat Protection i produktions miljön och börjar med definierade användnings fall är det bäst att gå igenom en planerings process för att bestämma vilka uppgifter som måste utföras i det här pilot projektet och framgång.</span><span class="sxs-lookup"><span data-stu-id="deee6-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="deee6-109">Så här använder du pilot Playbook</span><span class="sxs-lookup"><span data-stu-id="deee6-109">How to use this pilot playbook</span></span>

<span data-ttu-id="deee6-110">I den här guiden får du en översikt över Microsoft Threat Protection och steg-för-steg-instruktioner om hur du konfigurerar pilot projektet.</span><span class="sxs-lookup"><span data-stu-id="deee6-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![Faser i en Microsoft Threat Protection pilot](../../media/pilotphases.png)

<span data-ttu-id="deee6-112">Följande exempel tids linje varierar beroende på om du har rätt resurser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="deee6-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="deee6-113">Vissa identifieringar och arbets flöden kan behöva mer inlärnings tid än de andra.</span><span class="sxs-lookup"><span data-stu-id="deee6-113">Some detections and workflows might need more learning time than the others.</span></span>

![Exempel på tids linje i att köra ett Microsoft Threat Protection pilot](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="deee6-115">För optimalt resultat följer du pilot instruktionerna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="deee6-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="deee6-116">Pilot Playbook faser</span><span class="sxs-lookup"><span data-stu-id="deee6-116">Pilot playbook phases</span></span> 

<span data-ttu-id="deee6-117">Det finns fyra faser för att köra ett Microsoft Threat Protection pilot:</span><span class="sxs-lookup"><span data-stu-id="deee6-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="deee6-118">Fas</span><span class="sxs-lookup"><span data-stu-id="deee6-118">Phase</span></span> | <span data-ttu-id="deee6-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="deee6-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="deee6-120">![Planering](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="deee6-121">Planering</span><span class="sxs-lookup"><span data-stu-id="deee6-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="deee6-122">Läs mer om vad du behöver tänka på innan du kör ett Microsoft Threat Protection Pilot-projekt:</span><span class="sxs-lookup"><span data-stu-id="deee6-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="deee6-123">-Omfattning</span><span class="sxs-lookup"><span data-stu-id="deee6-123">- Scope</span></span> <br> <span data-ttu-id="deee6-124">-Användnings fall</span><span class="sxs-lookup"><span data-stu-id="deee6-124">- Use cases</span></span> <br><span data-ttu-id="deee6-125">-Krav</span><span class="sxs-lookup"><span data-stu-id="deee6-125">- Requirements</span></span> <br><span data-ttu-id="deee6-126">-Test plan</span><span class="sxs-lookup"><span data-stu-id="deee6-126">- Test plan</span></span> <br> <span data-ttu-id="deee6-127">-Villkor</span><span class="sxs-lookup"><span data-stu-id="deee6-127">- Success criteria</span></span> <br> <span data-ttu-id="deee6-128">-Styrkort</span><span class="sxs-lookup"><span data-stu-id="deee6-128">- Scorecard</span></span> 
| <span data-ttu-id="deee6-129">![Förberedelse](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="deee6-130">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="deee6-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="deee6-131">Få åtkomst till Microsoft 365 säkerhets Center för att konfigurera pilot miljön för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="deee6-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="deee6-132">Du ska vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="deee6-132">You will be guided to:</span></span><br><br><span data-ttu-id="deee6-133">-Identifiera intressenter och inhämta en uppsägning för din pilot</span><span class="sxs-lookup"><span data-stu-id="deee6-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="deee6-134">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="deee6-134">- Environment considerations</span></span> <br><span data-ttu-id="deee6-135">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="deee6-135">- Access</span></span> <br><span data-ttu-id="deee6-136">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="deee6-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="deee6-137">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="deee6-137">- Configuration order</span></span> <br> <span data-ttu-id="deee6-138">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="deee6-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="deee6-139">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="deee6-139">- Configure domain</span></span> <br><span data-ttu-id="deee6-140">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="deee6-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="deee6-141">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="deee6-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="deee6-142">![Simulering av attacker](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="deee6-143">Simulering av attacker</span><span class="sxs-lookup"><span data-stu-id="deee6-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="deee6-144">För att simulera en attack ska du vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="deee6-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="deee6-145">-Kontrol lera test miljö kraven</span><span class="sxs-lookup"><span data-stu-id="deee6-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="deee6-146">-Kör simuleringen</span><span class="sxs-lookup"><span data-stu-id="deee6-146">-  Run the simulation</span></span> <br><span data-ttu-id="deee6-147">-Undersök en olycka</span><span class="sxs-lookup"><span data-stu-id="deee6-147">- Investigate an incident</span></span> <br><span data-ttu-id="deee6-148">-Lös problemet</span><span class="sxs-lookup"><span data-stu-id="deee6-148">- resolve the incident</span></span> 
| <span data-ttu-id="deee6-149">![Stänga och sammanfatta](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="deee6-150">Stänga och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="deee6-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="deee6-151">När du har nått slutet av processen kommer du att vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="deee6-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="deee6-152">-Gå igenom dina slutliga utdata</span><span class="sxs-lookup"><span data-stu-id="deee6-152">- Go through your final output</span></span><br><span data-ttu-id="deee6-153">-Presentera dina synpunkter för dina intressenter</span><span class="sxs-lookup"><span data-stu-id="deee6-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="deee6-154">-Ge feedback</span><span class="sxs-lookup"><span data-stu-id="deee6-154">- Provide feedback</span></span> <br><span data-ttu-id="deee6-155">-Ta nästa steg</span><span class="sxs-lookup"><span data-stu-id="deee6-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="deee6-156">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="deee6-156">Next step</span></span>
|<span data-ttu-id="deee6-157">![Planerings fas](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="deee6-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="deee6-158">Planerings fas</span><span class="sxs-lookup"><span data-stu-id="deee6-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="deee6-159">Planera ditt Microsoft Threat Protection Pilot projekt</span><span class="sxs-lookup"><span data-stu-id="deee6-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
