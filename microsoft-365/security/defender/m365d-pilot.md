---
title: Kör ditt pilotprojekt i Microsoft 365 Defender
description: Kör ditt pilotprojekt i Microsoft 365 Defender i produktionen för att effektivt avgöra vilka fördelar och införande av Microsoft 365 Defender är.
keywords: Microsoft Threat Protection-pilot, kör pilotprojekt för Microsoft Threat Protection, utvärderar Microsoft Threat Protection i produktionen, Microsoft Threat Protection-pilotprojekt, cybersäkerhet, avancerade fortlöpande hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1dd310d962cbce2b339cf09d5be6317c227d3f13
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076289"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="952ca-104">Kör ditt pilotprojekt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="952ca-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="952ca-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="952ca-105">**Applies to:**</span></span>
- <span data-ttu-id="952ca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="952ca-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="952ca-107">Den här guiden hjälper dig att köra ett pilotprojekt genom att lägga till pekare för att säkerställa att du har en välstrukturerad plan så att du kan vägleda dig genom att använda attack simuleringsfunktionen och slutligen göra en avslutande beräkning av piloten med viktiga take-aways så att du kan reflektera över och dokumentera resultaten.</span><span class="sxs-lookup"><span data-stu-id="952ca-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Faser i körning av en Microsoft 365 Defender-pilot](../../media/pilotphases.png)


<span data-ttu-id="952ca-109">Genom att köra ett pilottest kan du effektivt avgöra fördelarna med att använda Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="952ca-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="952ca-110">Innan du aktiverar Microsoft 365 Defender i produktionsmiljön och startar dina användningsfall är det bäst att planera för att fastställa vilka uppgifter som ska utföras för ditt pilotprojekt och ange framgångskriterier.</span><span class="sxs-lookup"><span data-stu-id="952ca-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="952ca-111">Så här använder du den här pilotspelboken</span><span class="sxs-lookup"><span data-stu-id="952ca-111">How to use this pilot playbook</span></span>

<span data-ttu-id="952ca-112">Den här guiden innehåller en översikt över Microsoft 365 Defender och stegvisa instruktioner om hur du ställer in ditt pilotprojekt.</span><span class="sxs-lookup"><span data-stu-id="952ca-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="952ca-113">Microsoft 365 Defender är en enhetlig företagsskyddssvit före och efter intrång som inbyggt koordinerar skydd, identifiering, skydd, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att tillhandahålla integrerat skydd mot avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="952ca-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="952ca-114">Det gör det genom att kombinera och lösa följande funktioner till en enda säkerhetslösning:</span><span class="sxs-lookup"><span data-stu-id="952ca-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="952ca-115">Microsoft Defender för Slutpunkt, det nya namnet för Microsoft Defender Avancerat skydd (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="952ca-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="952ca-116">Microsoft Defender för Office 365, det nya namnet för Office 365 ATP (e-post)</span><span class="sxs-lookup"><span data-stu-id="952ca-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="952ca-117">Microsoft Defender för identitet, det nya namnet för Azure ATP (identitet)</span><span class="sxs-lookup"><span data-stu-id="952ca-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="952ca-118">Microsoft Cloud App Security (appar)</span><span class="sxs-lookup"><span data-stu-id="952ca-118">Microsoft Cloud App Security (apps)</span></span>

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="952ca-120">Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperter hantera hoten som Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet tar emot och fastställa hotens fullständiga omfattning och påverkan, hur det kommit in i miljön, vad det påverkas och hur det för närvarande påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="952ca-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="952ca-121">Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och självutmanade postlådor, slutpunkter och användaridentiteter.</span><span class="sxs-lookup"><span data-stu-id="952ca-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="952ca-122">Mer information [finns i Översikt över Microsoft 365 Defender.](microsoft-365-defender.md)</span><span class="sxs-lookup"><span data-stu-id="952ca-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="952ca-123">Följande exempel på tidslinjen varierar beroende på rätt resurser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="952ca-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="952ca-124">Vissa identifieringar och arbetsflöden kan behöva mer utbildningstid än de andra.</span><span class="sxs-lookup"><span data-stu-id="952ca-124">Some detections and workflows might need more learning time than the others.</span></span>

![Exempel på tidslinje i en Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="952ca-126">För bästa resultat bör du följa pilotinstruktionerna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="952ca-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="952ca-127">Pilotspelboksfaser</span><span class="sxs-lookup"><span data-stu-id="952ca-127">Pilot playbook phases</span></span> 

<span data-ttu-id="952ca-128">Det finns fyra faser i ett Microsoft 365 Defender-pilottest:</span><span class="sxs-lookup"><span data-stu-id="952ca-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="952ca-129">Fas</span><span class="sxs-lookup"><span data-stu-id="952ca-129">Phase</span></span> | <span data-ttu-id="952ca-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="952ca-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="952ca-131">Planering</span><span class="sxs-lookup"><span data-stu-id="952ca-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="952ca-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="952ca-132">~ 1 day</span></span>| <span data-ttu-id="952ca-133">Läs om vad du behöver tänka på innan du kör pilotprojektet i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="952ca-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="952ca-134">- Omfattning</span><span class="sxs-lookup"><span data-stu-id="952ca-134">- Scope</span></span> <br> <span data-ttu-id="952ca-135">- Användningsfall</span><span class="sxs-lookup"><span data-stu-id="952ca-135">- Use cases</span></span> <br><span data-ttu-id="952ca-136">- Krav</span><span class="sxs-lookup"><span data-stu-id="952ca-136">- Requirements</span></span> <br><span data-ttu-id="952ca-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="952ca-137">- Test plan</span></span> <br> <span data-ttu-id="952ca-138">- Kriterier för framgång</span><span class="sxs-lookup"><span data-stu-id="952ca-138">- Success criteria</span></span> <br> <span data-ttu-id="952ca-139">- Styrkort</span><span class="sxs-lookup"><span data-stu-id="952ca-139">- Scorecard</span></span> 
| [<span data-ttu-id="952ca-140">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="952ca-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="952ca-141">~2 dagar</span><span class="sxs-lookup"><span data-stu-id="952ca-141">~2 days</span></span>|  <span data-ttu-id="952ca-142">Access Microsoft 365 Säkerhetscenter för att konfigurera din Microsoft 365 Defender-pilotmiljö.</span><span class="sxs-lookup"><span data-stu-id="952ca-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="952ca-143">Du vägleds till:</span><span class="sxs-lookup"><span data-stu-id="952ca-143">You'll be guided to:</span></span><br><br><span data-ttu-id="952ca-144">– Identifiera intressenter och be om att få ett pilottecken</span><span class="sxs-lookup"><span data-stu-id="952ca-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="952ca-145">- Att tänka på när det gäller miljön</span><span class="sxs-lookup"><span data-stu-id="952ca-145">- Environment considerations</span></span> <br><span data-ttu-id="952ca-146">- Access</span><span class="sxs-lookup"><span data-stu-id="952ca-146">- Access</span></span> <br><span data-ttu-id="952ca-147">- Azure Active Directory-konfiguration</span><span class="sxs-lookup"><span data-stu-id="952ca-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="952ca-148">- Konfigurationsordning</span><span class="sxs-lookup"><span data-stu-id="952ca-148">- Configuration order</span></span> <br> <span data-ttu-id="952ca-149">- Registrera dig för utvärderingsversionen av Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="952ca-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="952ca-150">- Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="952ca-150">- Configure domain</span></span> <br><span data-ttu-id="952ca-151">- Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="952ca-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="952ca-152">- Slutför installationsguiden i portalen</span><span class="sxs-lookup"><span data-stu-id="952ca-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="952ca-153">Attack simulering</span><span class="sxs-lookup"><span data-stu-id="952ca-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="952ca-154">~2 dagar</span><span class="sxs-lookup"><span data-stu-id="952ca-154">~2 days</span></span>| <span data-ttu-id="952ca-155">Om du vill simulera en attack får du vägledning genom att:</span><span class="sxs-lookup"><span data-stu-id="952ca-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="952ca-156">- Kontrollera testmiljökraven</span><span class="sxs-lookup"><span data-stu-id="952ca-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="952ca-157">- Kör simuleringen</span><span class="sxs-lookup"><span data-stu-id="952ca-157">-  Run the simulation</span></span> <br><span data-ttu-id="952ca-158">- Undersöka en händelse</span><span class="sxs-lookup"><span data-stu-id="952ca-158">- Investigate an incident</span></span> <br><span data-ttu-id="952ca-159">- lösa problemet</span><span class="sxs-lookup"><span data-stu-id="952ca-159">- resolve the incident</span></span> 
| [<span data-ttu-id="952ca-160">Avslutande och sammanfattande</span><span class="sxs-lookup"><span data-stu-id="952ca-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="952ca-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="952ca-161">~ 1 day</span></span>| <span data-ttu-id="952ca-162">När du har kommit till slutet av processen vägleds du till:</span><span class="sxs-lookup"><span data-stu-id="952ca-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="952ca-163">- Gå igenom dina slutliga utdata</span><span class="sxs-lookup"><span data-stu-id="952ca-163">- Go through your final output</span></span><br><span data-ttu-id="952ca-164">- Presentera dina utdata för dina intressenter</span><span class="sxs-lookup"><span data-stu-id="952ca-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="952ca-165">- Ge feedback</span><span class="sxs-lookup"><span data-stu-id="952ca-165">- Provide feedback</span></span> <br><span data-ttu-id="952ca-166">- Gör nästa steg</span><span class="sxs-lookup"><span data-stu-id="952ca-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="952ca-167">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="952ca-167">Next step</span></span>
|[<span data-ttu-id="952ca-168">Planeringsfas</span><span class="sxs-lookup"><span data-stu-id="952ca-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="952ca-169">Planera ditt pilotprojekt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="952ca-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
