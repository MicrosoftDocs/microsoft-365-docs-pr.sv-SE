---
title: Automatiserad undersökning och svar i Microsoft 365 Defender
description: Få en översikt över automatisk undersökning och svarsfunktioner i Microsoft 365 Defender
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930336"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="8b1c0-104">Automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1c0-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b1c0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b1c0-105">**Applies to:**</span></span>
- <span data-ttu-id="8b1c0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1c0-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="8b1c0-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="8b1c0-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="8b1c0-108">Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="8b1c0-109">Så här fungerar automatisk undersökning och självbetjäning</span><span class="sxs-lookup"><span data-stu-id="8b1c0-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="8b1c0-110">När säkerhetsvarningar utlöses är det upp till teamet för säkerhetsåtgärder att titta på dessa aviseringar och vidta åtgärder för att skydda organisationen.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="8b1c0-111">Det kan ta mycket tid att prioritera och undersöka aviseringar, särskilt när nya aviseringar kommer in medan en undersökning pågår.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="8b1c0-112">Säkerhetsteam kan känna sig överhopade av mängden hot de måste övervaka och skydda mot.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="8b1c0-113">Automatisk undersökning och svarsfunktioner i Microsoft 365 Defender kan vara till hjälp.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="8b1c0-114">Titta på följande video för att se hur självbetjäning fungerar:</span><span class="sxs-lookup"><span data-stu-id="8b1c0-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="8b1c0-115">I Microsoft 365 Defender fungerar automatisk undersökning och svar med funktioner för självutskick på dina enheter, e-& och identiteter.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="8b1c0-116">I den här artikeln beskrivs hur automatisk undersökning och svar fungerar.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="8b1c0-117">Information om hur du konfigurerar de här funktionerna finns i Konfigurera funktioner för [automatisk undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="8b1c0-118">Din egen virtuella analytiker</span><span class="sxs-lookup"><span data-stu-id="8b1c0-118">Your own virtual analyst</span></span>

<span data-ttu-id="8b1c0-119">Tänk dig att du har en virtuell analytiker i ditt team för säkerhetsåtgärder på nivå 1/nivå 2.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="8b1c0-120">Den virtuella analytikern efterliknar de idealiska steg som säkerhetsåtgärder kan vidta för att undersöka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="8b1c0-121">Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet, och ta på sig en stor belastning på undersökningar och hotreparation.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="8b1c0-122">En sådan virtuell assistent kan minska tiden för att svara, vilket frigör din säkerhetsgrupp för andra viktiga strategiska projekt.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="8b1c0-123">Om det här scenariot låter som science fiction är det inte det!</span><span class="sxs-lookup"><span data-stu-id="8b1c0-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="8b1c0-124">En sådan virtuell analytiker är en del av Microsoft 365 Defender-programsviten och namnet är *automatisk undersökning och svar.*</span><span class="sxs-lookup"><span data-stu-id="8b1c0-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="8b1c0-125">Med automatiserad undersökning och svar kan teamet för säkerhetsåtgärder avsevärt öka organisationens kapacitet för att hantera säkerhetsvarningar och incidenter.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="8b1c0-126">Med automatiserad undersökning och svar kan du minska kostnaderna för hantering av undersöknings- och åtgärdsaktiviteter och få ut det mesta av din programsvit för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="8b1c0-127">automatiserad undersökning och svar hjälper din grupp med säkerhetsåtgärder genom att:</span><span class="sxs-lookup"><span data-stu-id="8b1c0-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="8b1c0-128">Avgöra om ett hot kräver åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="8b1c0-129">Utföra (eller rekommendera) nödvändiga åtgärdsåtgärder;</span><span class="sxs-lookup"><span data-stu-id="8b1c0-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="8b1c0-130">Fastställa vilka ytterligare undersökningar som ska ske. och</span><span class="sxs-lookup"><span data-stu-id="8b1c0-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="8b1c0-131">Upprepa processen om det behövs för andra aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="8b1c0-132">Den automatiska undersökningen</span><span class="sxs-lookup"><span data-stu-id="8b1c0-132">The automated investigation process</span></span>

<span data-ttu-id="8b1c0-133">**Avisering**  >  **incident**  >  **automatiserad undersökning**  >  **bedömning**  >  **åtgärdsåtgärd**</span><span class="sxs-lookup"><span data-stu-id="8b1c0-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="8b1c0-134">En utlöst avisering skapar en händelse, som kan starta en automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="8b1c0-135">Undersökningen kan resultera i en eller flera åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="8b1c0-136">I Microsoft 365 Defender korrelerar varje automatiserad undersökning signaler till Microsoft Defender för identitet, Microsoft Defender för Endpoint och Defender för Office 365, enligt sammanfattningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="8b1c0-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="8b1c0-137">Enheter</span><span class="sxs-lookup"><span data-stu-id="8b1c0-137">Entities</span></span> |<span data-ttu-id="8b1c0-138">Skyddstjänster för hot</span><span class="sxs-lookup"><span data-stu-id="8b1c0-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="8b1c0-139">Enheter (kallas även slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="8b1c0-140">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b1c0-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="8b1c0-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8b1c0-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="8b1c0-142">E-postinnehåll (filer och meddelanden i postlådor)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="8b1c0-143">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1c0-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="8b1c0-144">Varje undersökning genererar en bedömning *(skadlig,* *misstänkt* eller inga hot hittades) för varje bevis som *undersöks.*</span><span class="sxs-lookup"><span data-stu-id="8b1c0-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="8b1c0-145">Beroende på typen av hot och resulterande bedömning, utförs åtgärder automatiskt eller vid godkännande av organisationens säkerhetsteam.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="8b1c0-146">Väntande och slutförda åtgärder visas i [Åtgärdscenter.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="8b1c0-147">Medan en undersökning körs läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den slutförs.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="8b1c0-148">Om en okritisk enhet visas någon annanstans utökar den automatiska undersökningen dess omfattning så att den omfattar den enheten, och en allmän säkerhetsspelbok körs.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="8b1c0-149">Inte alla aviseringar utlöser en automatiserad undersökning och inte alla undersökningar resulterar i automatiska åtgärdsåtgärder. Det beror på hur automatisk undersökning och svar har konfigurerats för organisationen.</span><span class="sxs-lookup"><span data-stu-id="8b1c0-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="8b1c0-150">Se [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="8b1c0-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="8b1c0-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8b1c0-151">Next steps</span></span>

- [<span data-ttu-id="8b1c0-152">Se förutsättningarna för automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1c0-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="8b1c0-153">Konfigurera automatisk undersökning och svar för organisationen</span><span class="sxs-lookup"><span data-stu-id="8b1c0-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="8b1c0-154">Läs mer om Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="8b1c0-154">Learn more about the Action center</span></span>](mtp-action-center.md)
