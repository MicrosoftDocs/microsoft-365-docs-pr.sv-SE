---
title: Distributionsfaser
description: Lär dig hur du distribuerar Microsoft Defender för Slutpunkt genom att förbereda, konfigurera och registrera slutpunkter för den tjänsten
keywords: distribuera, förbereda, konfigurera, registrera, fas, distribution, distribuera, införa, konfigurera
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165171"
---
# <a name="deployment-phases"></a><span data-ttu-id="257f9-104">Distributionsfaser</span><span class="sxs-lookup"><span data-stu-id="257f9-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="257f9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="257f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="257f9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="257f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="257f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="257f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="257f9-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="257f9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="257f9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="257f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="257f9-110">Lär dig hur du distribuerar Microsoft Defender för Endpoint så att ditt företag kan dra nytta av förebyggande skydd, identifiering efter intrång, automatisk undersökning och svar.</span><span class="sxs-lookup"><span data-stu-id="257f9-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="257f9-111">Den här guiden hjälper dig att arbeta med intressenter för att förbereda miljön och sedan introducera enheter på ett metodiskt sätt, flytta från utvärdering till ett meningsfullt pilottest till en fullständig distribution.</span><span class="sxs-lookup"><span data-stu-id="257f9-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="257f9-112">Varje avsnitt motsvarar en separat artikel i den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="257f9-112">Each section corresponds to a separate article in this solution.</span></span>

![Bild av distributionsfaser med information från tabell](images/deployment-guide-phases.png)


![Sammanfattning av distributionsfaser: förbereda, konfigurera, registrera](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="257f9-115">Fas</span><span class="sxs-lookup"><span data-stu-id="257f9-115">Phase</span></span> | <span data-ttu-id="257f9-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="257f9-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="257f9-117">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="257f9-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="257f9-118">Läs mer om vad du behöver tänka på när du distribuerar Defender för Endpoint, till exempel godkännanden från intressenter, miljööverväganden, åtkomstbehörigheter och införandeordningen för funktioner.</span><span class="sxs-lookup"><span data-stu-id="257f9-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="257f9-119">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="257f9-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="257f9-120">Få vägledning om de inledande åtgärder du behöver vidta så att du kan komma åt portalen, till exempel validera licensiering, slutföra installationsguiden och nätverkskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="257f9-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="257f9-121">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="257f9-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="257f9-122">Lär dig hur du använder distributionsringar, onboarding-verktyg som stöds baserat på typen av slutpunkt och hur du konfigurerar tillgängliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="257f9-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="257f9-123">När du har slutfört den här guiden konfigureras du med rätt åtkomstbehörighet, dina slutpunkter kommer att introduceras och rapportera sensordata till tjänsten, och funktioner som nästa generations skydd och minskning av attackytan kommer att finnas.</span><span class="sxs-lookup"><span data-stu-id="257f9-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="257f9-124">Oavsett vilken miljöarkitektur och distributionsmetod du väljer i distributionsvägledning för [Abonnemang](deployment-strategy.md) får du stöd för den här guiden i slutpunkter för onboarding.</span><span class="sxs-lookup"><span data-stu-id="257f9-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="257f9-125">Viktiga funktioner</span><span class="sxs-lookup"><span data-stu-id="257f9-125">Key capabilities</span></span>

<span data-ttu-id="257f9-126">Även om Microsoft Defender för Slutpunkt innehåller många funktioner är det primära syftet med den här distributionsguiden att komma igång med att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="257f9-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="257f9-127">Förutom introduktionen får du i den här vägledningen även hjälp att komma igång med följande funktioner.</span><span class="sxs-lookup"><span data-stu-id="257f9-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="257f9-128">Funktion</span><span class="sxs-lookup"><span data-stu-id="257f9-128">Capability</span></span> | <span data-ttu-id="257f9-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="257f9-129">Description</span></span> 
:---|:---
<span data-ttu-id="257f9-130">Identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="257f9-130">Endpoint detection and response</span></span> | <span data-ttu-id="257f9-131">Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och svara på intrångsförsök och aktiva intrång.</span><span class="sxs-lookup"><span data-stu-id="257f9-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="257f9-132">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="257f9-132">Next-generation protection</span></span> | <span data-ttu-id="257f9-133">För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="257f9-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="257f9-134">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="257f9-134">Attack surface reduction</span></span> |  <span data-ttu-id="257f9-135">Tillhandahåll den första försvarslinjen i högen.</span><span class="sxs-lookup"><span data-stu-id="257f9-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="257f9-136">Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.</span><span class="sxs-lookup"><span data-stu-id="257f9-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="257f9-137">Alla dessa funktioner är tillgängliga för Microsoft Defender för Endpoint-licensinnehavare.</span><span class="sxs-lookup"><span data-stu-id="257f9-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="257f9-138">Mer information finns i [Licenskrav](minimum-requirements.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="257f9-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="257f9-139">Omfattning</span><span class="sxs-lookup"><span data-stu-id="257f9-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="257f9-140">I omfattning</span><span class="sxs-lookup"><span data-stu-id="257f9-140">In scope</span></span>

-   <span data-ttu-id="257f9-141">Användning av Microsoft Endpoint Manager och Microsoft Endpoint Manager för att introducera slutpunkter i tjänsten och konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="257f9-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="257f9-142">Aktivera Defender för funktioner för identifiering av slutpunkt och svar (EDR)</span><span class="sxs-lookup"><span data-stu-id="257f9-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="257f9-143">Aktivera Defender för funktioner för Slutpunktsskyddsplattform (DEFENDER)</span><span class="sxs-lookup"><span data-stu-id="257f9-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="257f9-144">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="257f9-144">Next-generation protection</span></span>

    -   <span data-ttu-id="257f9-145">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="257f9-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="257f9-146">Inte begränsad</span><span class="sxs-lookup"><span data-stu-id="257f9-146">Out of scope</span></span>

<span data-ttu-id="257f9-147">Följande ingår inte i den här distributionsguiden:</span><span class="sxs-lookup"><span data-stu-id="257f9-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="257f9-148">Konfiguration av lösningar från tredje part som kan integreras med Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="257f9-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="257f9-149">Test av test vid test i produktionsmiljö</span><span class="sxs-lookup"><span data-stu-id="257f9-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="257f9-150">Se även</span><span class="sxs-lookup"><span data-stu-id="257f9-150">See also</span></span>
- [<span data-ttu-id="257f9-151">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="257f9-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="257f9-152">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="257f9-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="257f9-153">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="257f9-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="257f9-154">Planera distribution</span><span class="sxs-lookup"><span data-stu-id="257f9-154">Plan deployment</span></span>](deployment-strategy.md)