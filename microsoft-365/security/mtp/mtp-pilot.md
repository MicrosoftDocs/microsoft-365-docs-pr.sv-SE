---
title: Kör ditt pilot Microsoft 365 Defender Project
description: Kör piloten Microsoft 365 Defender Project in the Production för att effektivt fastställa fördelarna och antagandet av Microsoft 365 Defender.
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659327"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="37fc1-104">Kör ditt pilot Microsoft 365 Defender Project</span><span class="sxs-lookup"><span data-stu-id="37fc1-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="37fc1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="37fc1-105">**Applies to:**</span></span>
- <span data-ttu-id="37fc1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37fc1-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="37fc1-107">Med den här guiden får du hjälp att köra ett pilot projekt genom att ange att du har ett välstrukturerat abonnemang och du kan använda funktionen för att hantera anslags verktyget och slutligen ingå piloten med de viktiga anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="37fc1-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Faser i en Microsoft 365 Defender pilot](../../media/pilotphases.png)


<span data-ttu-id="37fc1-109">Genom att använda en pilot kan du effektivt bestämma fördelarna med adoptiing Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="37fc1-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="37fc1-110">Innan du aktiverar Microsoft 365 Defender i produktions miljön och startar dina användnings fall är det bäst att planera för att bestämma vilka uppgifter som ska utföras för pilot projektet och hur du ställer in framgång.</span><span class="sxs-lookup"><span data-stu-id="37fc1-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="37fc1-111">Så här använder du pilot Playbook</span><span class="sxs-lookup"><span data-stu-id="37fc1-111">How to use this pilot playbook</span></span>

<span data-ttu-id="37fc1-112">I den här guiden får du en översikt över Microsoft 365 Defender och stegvisa instruktioner för hur du konfigurerar pilot projektet.</span><span class="sxs-lookup"><span data-stu-id="37fc1-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="37fc1-113">Microsoft 365 Defender är ett enhetligt för hands versions paket med för-och efter intrång som enhetligt koordinerar skydd, identifiering, förebyggande, undersökning och svar för slut punkter, identiteter, e-postmeddelanden och program för att ge ett integrerat skydd mot sofistikerade attacker.</span><span class="sxs-lookup"><span data-stu-id="37fc1-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="37fc1-114">Det gör det genom att kombinera och dirigera följande funktioner till en enda säkerhets lösning:</span><span class="sxs-lookup"><span data-stu-id="37fc1-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="37fc1-115">Microsoft Defender för slut punkt, det nya namnet på Microsoft Defender Avancerat skydd (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="37fc1-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="37fc1-116">Microsoft Defender för Office 365, det nya namnet på Office 365 ATP (e-post)</span><span class="sxs-lookup"><span data-stu-id="37fc1-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="37fc1-117">Microsoft Defender för identitet, det nya namnet på Azure ATP (identitet)</span><span class="sxs-lookup"><span data-stu-id="37fc1-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="37fc1-118">Säkerhet för Microsoft Cloud App (appar)</span><span class="sxs-lookup"><span data-stu-id="37fc1-118">Microsoft Cloud App Security (apps)</span></span>

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet för slut punkter Microsoft Defender för slut punkter, moln program, Microsoft Cloud App-säkerhet och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="37fc1-120">Med den integrerade Microsoft 365 Defender-lösningen kan säkerhets experter koppla ihop hotet om att Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App Security tar emot och fastställer det fulla scopet och effekten av hotet, hur det kommer att påverkas och hur det påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="37fc1-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="37fc1-121">Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv läka berörda post lådor, slut punkter och användar identiteter.</span><span class="sxs-lookup"><span data-stu-id="37fc1-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="37fc1-122">Mer information finns i [Microsoft 365 Defender-översikten](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .</span><span class="sxs-lookup"><span data-stu-id="37fc1-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="37fc1-123">Följande exempel tids linje varierar beroende på om du har rätt resurser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="37fc1-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="37fc1-124">Vissa identifieringar och arbets flöden kan behöva mer inlärnings tid än de andra.</span><span class="sxs-lookup"><span data-stu-id="37fc1-124">Some detections and workflows might need more learning time than the others.</span></span>

![Exempel på tids linje i en Microsoft 365 Defender pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="37fc1-126">För optimalt resultat följer du pilot instruktionerna så nära som möjligt.</span><span class="sxs-lookup"><span data-stu-id="37fc1-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="37fc1-127">Pilot Playbook faser</span><span class="sxs-lookup"><span data-stu-id="37fc1-127">Pilot playbook phases</span></span> 

<span data-ttu-id="37fc1-128">Det finns fyra faser i en Microsoft 365 Defender pilot:</span><span class="sxs-lookup"><span data-stu-id="37fc1-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="37fc1-129">Fas</span><span class="sxs-lookup"><span data-stu-id="37fc1-129">Phase</span></span> | <span data-ttu-id="37fc1-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="37fc1-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="37fc1-131">Planering</span><span class="sxs-lookup"><span data-stu-id="37fc1-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="37fc1-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="37fc1-132">~ 1 day</span></span>| <span data-ttu-id="37fc1-133">Läs mer om vad du behöver tänka på innan du kör Microsoft 365 Defender pilot-projektet:</span><span class="sxs-lookup"><span data-stu-id="37fc1-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="37fc1-134">-Omfattning</span><span class="sxs-lookup"><span data-stu-id="37fc1-134">- Scope</span></span> <br> <span data-ttu-id="37fc1-135">-Användnings fall</span><span class="sxs-lookup"><span data-stu-id="37fc1-135">- Use cases</span></span> <br><span data-ttu-id="37fc1-136">-Krav</span><span class="sxs-lookup"><span data-stu-id="37fc1-136">- Requirements</span></span> <br><span data-ttu-id="37fc1-137">-Test plan</span><span class="sxs-lookup"><span data-stu-id="37fc1-137">- Test plan</span></span> <br> <span data-ttu-id="37fc1-138">-Villkor</span><span class="sxs-lookup"><span data-stu-id="37fc1-138">- Success criteria</span></span> <br> <span data-ttu-id="37fc1-139">-Styrkort</span><span class="sxs-lookup"><span data-stu-id="37fc1-139">- Scorecard</span></span> 
| [<span data-ttu-id="37fc1-140">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="37fc1-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="37fc1-141">~ 2 dagar</span><span class="sxs-lookup"><span data-stu-id="37fc1-141">~2 days</span></span>|  <span data-ttu-id="37fc1-142">Få åtkomst till Microsoft 365 säkerhets Center för att konfigurera pilot miljön för Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="37fc1-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="37fc1-143">Du är guidad att:</span><span class="sxs-lookup"><span data-stu-id="37fc1-143">You'll be guided to:</span></span><br><br><span data-ttu-id="37fc1-144">-Identifiera intressenter och inhämta en uppsägning för din pilot</span><span class="sxs-lookup"><span data-stu-id="37fc1-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="37fc1-145">-Miljö överväganden</span><span class="sxs-lookup"><span data-stu-id="37fc1-145">- Environment considerations</span></span> <br><span data-ttu-id="37fc1-146">-Åtkomst</span><span class="sxs-lookup"><span data-stu-id="37fc1-146">- Access</span></span> <br><span data-ttu-id="37fc1-147">-Konfigurera Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="37fc1-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="37fc1-148">-Konfigurations beställning</span><span class="sxs-lookup"><span data-stu-id="37fc1-148">- Configuration order</span></span> <br> <span data-ttu-id="37fc1-149">-Registrera dig för Microsoft 365 E5-utvärderings version</span><span class="sxs-lookup"><span data-stu-id="37fc1-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="37fc1-150">-Konfigurera domän</span><span class="sxs-lookup"><span data-stu-id="37fc1-150">- Configure domain</span></span> <br><span data-ttu-id="37fc1-151">-Tilldela Microsoft 365 E5-licenser</span><span class="sxs-lookup"><span data-stu-id="37fc1-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="37fc1-152">-Slutför installations guiden i portalen</span><span class="sxs-lookup"><span data-stu-id="37fc1-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="37fc1-153">Simulering av attacker</span><span class="sxs-lookup"><span data-stu-id="37fc1-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="37fc1-154">~ 2 dagar</span><span class="sxs-lookup"><span data-stu-id="37fc1-154">~2 days</span></span>| <span data-ttu-id="37fc1-155">För att simulera en attack ska du vägleda dig till:</span><span class="sxs-lookup"><span data-stu-id="37fc1-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="37fc1-156">-Kontrol lera test miljö kraven</span><span class="sxs-lookup"><span data-stu-id="37fc1-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="37fc1-157">-Kör simuleringen</span><span class="sxs-lookup"><span data-stu-id="37fc1-157">-  Run the simulation</span></span> <br><span data-ttu-id="37fc1-158">-Undersök en olycka</span><span class="sxs-lookup"><span data-stu-id="37fc1-158">- Investigate an incident</span></span> <br><span data-ttu-id="37fc1-159">-Lös problemet</span><span class="sxs-lookup"><span data-stu-id="37fc1-159">- resolve the incident</span></span> 
| [<span data-ttu-id="37fc1-160">Stänga och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="37fc1-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="37fc1-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="37fc1-161">~ 1 day</span></span>| <span data-ttu-id="37fc1-162">När du har nått slutet av processen är du guidad att:</span><span class="sxs-lookup"><span data-stu-id="37fc1-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="37fc1-163">-Gå igenom dina slutliga utdata</span><span class="sxs-lookup"><span data-stu-id="37fc1-163">- Go through your final output</span></span><br><span data-ttu-id="37fc1-164">-Presentera dina synpunkter för dina intressenter</span><span class="sxs-lookup"><span data-stu-id="37fc1-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="37fc1-165">-Ge feedback</span><span class="sxs-lookup"><span data-stu-id="37fc1-165">- Provide feedback</span></span> <br><span data-ttu-id="37fc1-166">-Ta nästa steg</span><span class="sxs-lookup"><span data-stu-id="37fc1-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="37fc1-167">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="37fc1-167">Next step</span></span>
|[<span data-ttu-id="37fc1-168">Planerings fas</span><span class="sxs-lookup"><span data-stu-id="37fc1-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="37fc1-169">Planera ditt Microsoft 365 Defender Pilot projekt</span><span class="sxs-lookup"><span data-stu-id="37fc1-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
