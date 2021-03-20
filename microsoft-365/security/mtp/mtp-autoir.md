---
title: Automatiserad undersökning och svar i Microsoft 365 Defender
description: Få en översikt över automatiska undersöknings- och svarsfunktioner, även kallat självbetjäning, i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd, självbetjäning
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 199bc72e7a8e1e5783105b44de150368a41b872c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917088"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="19481-104">Automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19481-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="19481-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="19481-105">**Applies to:**</span></span>
- <span data-ttu-id="19481-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19481-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="19481-107">Om din organisation använder [Microsoft 365 Defender](microsoft-threat-protection.md)får teamet för säkerhetsåtgärder en avisering när en skadlig eller misstänkt artefakt hittas.</span><span class="sxs-lookup"><span data-stu-id="19481-107">If your organization is using [Microsoft 365 Defender](microsoft-threat-protection.md), your security operations team receives an alert whenever a malicious or suspicious artifact is detected.</span></span> <span data-ttu-id="19481-108">Med den till synes oändliga flödet av hot som kommer in ställs säkerhetsteam ofta inför utmaningar med att hantera den stora mängden aviseringar.</span><span class="sxs-lookup"><span data-stu-id="19481-108">Given the seemingly never-ending flow of threats that come in, security teams often face challenges in addressing the high volume of alerts.</span></span> <span data-ttu-id="19481-109">Som tur är innehåller Microsoft 365 Defender funktioner för automatisk undersökning och åtgärder (AIR) som kan hjälpa din säkerhetsgrupp att hantera hot mer effektivt och effektivare.</span><span class="sxs-lookup"><span data-stu-id="19481-109">Fortunately, Microsoft 365 Defender includes automated investigation and remediation (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="19481-110">Den här artikeln innehåller en översikt över AIR med länkar till nästa steg och ytterligare resurser.</span><span class="sxs-lookup"><span data-stu-id="19481-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="19481-111">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="19481-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="19481-112">Du kan [utvärdera den i en labbmiljö](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) eller köra [pilotprojektet i produktion.](./mtp-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="19481-112">You can [evaluate it in a lab environment](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](./mtp-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="19481-113">Så här fungerar automatisk undersökning och självbetjäning</span><span class="sxs-lookup"><span data-stu-id="19481-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="19481-114">När säkerhetsvarningar utlöses är det upp till ditt säkerhetsteam att titta på varningarna och vidta åtgärder för att skydda din organisation.</span><span class="sxs-lookup"><span data-stu-id="19481-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="19481-115">Det kan ta mycket tid att prioritera och undersöka aviseringar, särskilt när nya aviseringar kommer in medan en undersökning pågår.</span><span class="sxs-lookup"><span data-stu-id="19481-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="19481-116">Säkerhetsåtgärder grupper kan känna sig överhopad av mängden hot de måste övervaka och skydda mot.</span><span class="sxs-lookup"><span data-stu-id="19481-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="19481-117">Med hjälp av automatiska undersöknings- och svarsfunktioner kan Microsoft 365 Defender vara till hjälp.</span><span class="sxs-lookup"><span data-stu-id="19481-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="19481-118">Titta på följande video för att se hur självbetjäning fungerar:</span><span class="sxs-lookup"><span data-stu-id="19481-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="19481-119">I Microsoft 365 Defender fungerar automatisk undersökning och svar med självöverlåtande funktioner på dina enheter, e-& och innehåll och identiteter.</span><span class="sxs-lookup"><span data-stu-id="19481-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="19481-120">I den här artikeln beskrivs hur automatisk undersökning och svar fungerar.</span><span class="sxs-lookup"><span data-stu-id="19481-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="19481-121">Information om hur du konfigurerar dessa funktioner [finns i Konfigurera funktioner för automatisk undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="19481-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="19481-122">Din egen virtuella analytiker</span><span class="sxs-lookup"><span data-stu-id="19481-122">Your own virtual analyst</span></span>

<span data-ttu-id="19481-123">Tänk dig att du har en virtuell analytiker i ditt team för säkerhet på nivå 1 eller nivå 2.</span><span class="sxs-lookup"><span data-stu-id="19481-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="19481-124">Den virtuella analytikern efterliknar de bästa stegen som säkerhetsåtgärder kan vidta för att undersöka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="19481-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="19481-125">Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet, och ta på sig en stor belastning av undersökningar och hotreparation.</span><span class="sxs-lookup"><span data-stu-id="19481-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="19481-126">En sådan virtuell assistent kan avsevärt minska tiden för att svara, vilket frigör din säkerhetsgrupp för andra viktiga strategiska projekt.</span><span class="sxs-lookup"><span data-stu-id="19481-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="19481-127">Om det här scenariot låter som science fiction är det inte det!</span><span class="sxs-lookup"><span data-stu-id="19481-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="19481-128">En sådan virtuell analytiker är en del av din Microsoft 365 Defender-programsvit, och namnet är *en automatiserad undersökning och svar.*</span><span class="sxs-lookup"><span data-stu-id="19481-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="19481-129">Med funktionerna för automatiserad undersökning och svar kan ditt säkerhetsteam avsevärt öka organisationens kapacitet för att hantera säkerhetsvarningar och incidenter.</span><span class="sxs-lookup"><span data-stu-id="19481-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="19481-130">Med automatiserad undersökning och svar kan du minska kostnaderna för hantering av undersökning och åtgärder och få ut mesta mesta av din säkerhetssvit för hot.</span><span class="sxs-lookup"><span data-stu-id="19481-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="19481-131">Automatiska undersöknings- och svarsfunktioner hjälper teamet med säkerhetsåtgärder genom att:</span><span class="sxs-lookup"><span data-stu-id="19481-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="19481-132">Avgöra om ett hot kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="19481-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="19481-133">Vidta (eller rekommendera) alla nödvändiga åtgärder;</span><span class="sxs-lookup"><span data-stu-id="19481-133">Taking (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="19481-134">Avgöra om och vilka andra undersökningar som ska ske; och</span><span class="sxs-lookup"><span data-stu-id="19481-134">Determining whether and what other investigations should occur; and</span></span>
4. <span data-ttu-id="19481-135">Upprepa processen om det behövs för andra aviseringar.</span><span class="sxs-lookup"><span data-stu-id="19481-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="19481-136">Automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="19481-136">The automated investigation process</span></span>

<span data-ttu-id="19481-137">En avisering skapar en händelse, som kan påbörja en automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="19481-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="19481-138">Den automatiska undersökningen resulterar i en bedömning för varje bevis.</span><span class="sxs-lookup"><span data-stu-id="19481-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="19481-139">Olika beslut kan vara:</span><span class="sxs-lookup"><span data-stu-id="19481-139">Verdicts can be:</span></span>
- <span data-ttu-id="19481-140">*Skadlig*;</span><span class="sxs-lookup"><span data-stu-id="19481-140">*Malicious*;</span></span>
- <span data-ttu-id="19481-141">*Misstänkt –* om du har en misstänkt e eller</span><span class="sxs-lookup"><span data-stu-id="19481-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="19481-142">*Inga hot hittades*.</span><span class="sxs-lookup"><span data-stu-id="19481-142">*No threats found*.</span></span> 

<span data-ttu-id="19481-143">Åtgärdsåtgärder för skadliga eller misstänkta enheter identifieras.</span><span class="sxs-lookup"><span data-stu-id="19481-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="19481-144">Några exempel på åtgärder:</span><span class="sxs-lookup"><span data-stu-id="19481-144">Examples of remediation actions include:</span></span>
- <span data-ttu-id="19481-145">Skicka en fil till karantän.</span><span class="sxs-lookup"><span data-stu-id="19481-145">Sending a file to quarantine;</span></span>
- <span data-ttu-id="19481-146">Stoppar en process.</span><span class="sxs-lookup"><span data-stu-id="19481-146">Stopping a process;</span></span>
- <span data-ttu-id="19481-147">Isolera en enhet</span><span class="sxs-lookup"><span data-stu-id="19481-147">Isolating a device;</span></span>
- <span data-ttu-id="19481-148">Blockera en URL och</span><span class="sxs-lookup"><span data-stu-id="19481-148">Blocking a URL; and</span></span> 
- <span data-ttu-id="19481-149">andra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="19481-149">other actions.</span></span> <span data-ttu-id="19481-150">(Se [Åtgärder för åtgärder i Microsoft 365 Defender](mtp-remediation-actions.md).)</span><span class="sxs-lookup"><span data-stu-id="19481-150">(See [Remediation actions in Microsoft 365 Defender](mtp-remediation-actions.md).)</span></span>

<span data-ttu-id="19481-151">Beroende på [hur automatiska undersöknings-](mtp-configure-auto-investigation-response.md) och svarsfunktioner har konfigurerats för organisationen utförs åtgärder automatiskt eller bara om säkerhetsgruppen har godkänt det.</span><span class="sxs-lookup"><span data-stu-id="19481-151">Depending on [how automated investigation and response capabilities are configured](mtp-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="19481-152">Alla åtgärder, väntande eller slutförda, visas i [Åtgärdscenter.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="19481-152">All actions, whether pending or completed, are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="19481-153">Medan en undersökning körs läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den slutförs.</span><span class="sxs-lookup"><span data-stu-id="19481-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="19481-154">Om en okritisk enhet visas någon annanstans utökar den automatiska undersökningen dess omfattning så att den omfattar den enheten, och undersökningen upprepas.</span><span class="sxs-lookup"><span data-stu-id="19481-154">If an incriminated entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="19481-155">I Microsoft 365 Defender korrelerar varje automatisk undersökning signaler i Microsoft Defender för identitet, Microsoft Defender för slutpunkt och Defender för Office 365, enligt sammanfattningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="19481-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="19481-156">Enheter</span><span class="sxs-lookup"><span data-stu-id="19481-156">Entities</span></span> |<span data-ttu-id="19481-157">Skyddstjänster för hot</span><span class="sxs-lookup"><span data-stu-id="19481-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="19481-158">Enheter (kallas även slutpunkter, och kallas ibland för datorer)</span><span class="sxs-lookup"><span data-stu-id="19481-158">Devices (also referred to as endpoints, and sometimes referred to as machines)</span></span>     |[<span data-ttu-id="19481-159">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="19481-159">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="19481-160">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="19481-160">Microsoft Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="19481-161">E-postinnehåll (e-postmeddelanden som kan innehålla filer och URL:er)</span><span class="sxs-lookup"><span data-stu-id="19481-161">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="19481-162">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="19481-162">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)         |

> [!NOTE]
> <span data-ttu-id="19481-163">Inte alla aviseringar utlöser en automatiserad undersökning och inte alla undersökningsresultat i automatiserade åtgärdsåtgärder. Det beror på hur automatisk undersökning och svar har konfigurerats för organisationen.</span><span class="sxs-lookup"><span data-stu-id="19481-163">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; it depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="19481-164">Se [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="19481-164">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="19481-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="19481-165">Next steps</span></span>

- [<span data-ttu-id="19481-166">Se förutsättningarna för automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19481-166">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="19481-167">Konfigurera automatisk undersökning och svar för organisationen</span><span class="sxs-lookup"><span data-stu-id="19481-167">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="19481-168">Läs mer om Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="19481-168">Learn more about the Action center</span></span>](mtp-action-center.md)