---
title: Distribuera Microsoft Defender för slutpunkt i ringar
description: Lär dig hur du distribuerar Microsoft Defender för slutpunkt i ringar
keywords: distribuera, ringar, utvärdera, pilottesta, insider snabbt, insider – långsamt, konfiguration, onboard, phase, deployment, deploying, adoption, configuring
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
ms.openlocfilehash: 8123bdf610b30407e5d262296f9c3639bc21b12f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893491"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="0edca-104">Distribuera Microsoft Defender för slutpunkt i ringar</span><span class="sxs-lookup"><span data-stu-id="0edca-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0edca-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0edca-105">**Applies to:**</span></span>
- [<span data-ttu-id="0edca-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0edca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0edca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0edca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0edca-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0edca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0edca-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0edca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="0edca-110">Distribution av Microsoft Defender för Endpoint kan göras med en ringbaserad distributionsmetod.</span><span class="sxs-lookup"><span data-stu-id="0edca-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="0edca-111">Distributionsringarna kan användas i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="0edca-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="0edca-112">Nya distributioner</span><span class="sxs-lookup"><span data-stu-id="0edca-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="0edca-113">Befintliga distributioner</span><span class="sxs-lookup"><span data-stu-id="0edca-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="0edca-114">Nya distributioner</span><span class="sxs-lookup"><span data-stu-id="0edca-114">New deployments</span></span>

![Bild på distributionsringar](images/deployment-rings.png)


<span data-ttu-id="0edca-116">En ringbaserad metod är en metod för att identifiera en uppsättning slutpunkter för att registrera och verifiera att vissa villkor uppfylls innan du fortsätter att distribuera tjänsten till en större uppsättning enheter.</span><span class="sxs-lookup"><span data-stu-id="0edca-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="0edca-117">Du kan definiera utgångsvillkor för varje ring och säkerställa att de är nöjda innan du går vidare till nästa ring.</span><span class="sxs-lookup"><span data-stu-id="0edca-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="0edca-118">Genom att införa en ringbaserad distribution minskar du eventuella problem som kan uppstå när tjänsten distribueras.</span><span class="sxs-lookup"><span data-stu-id="0edca-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="0edca-119">Genom att pilottesta ett visst antal enheter först kan du identifiera potentiella problem och minimera potentiella risker som kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="0edca-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="0edca-120">Tabell 1 innehåller ett exempel på de distributionsringar som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="0edca-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="0edca-121">**Tabell 1**</span><span class="sxs-lookup"><span data-stu-id="0edca-121">**Table 1**</span></span>

|<span data-ttu-id="0edca-122">**Distributionsringen**</span><span class="sxs-lookup"><span data-stu-id="0edca-122">**Deployment ring**</span></span>|<span data-ttu-id="0edca-123">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0edca-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="0edca-124">Utvärdera</span><span class="sxs-lookup"><span data-stu-id="0edca-124">Evaluate</span></span> | <span data-ttu-id="0edca-125">Ring 1: Identifiera 50 system för pilottestning</span><span class="sxs-lookup"><span data-stu-id="0edca-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="0edca-126">Pilot</span><span class="sxs-lookup"><span data-stu-id="0edca-126">Pilot</span></span> | <span data-ttu-id="0edca-127">Ring 2: Identifiera de nästa 50–100 slutpunkterna i produktionsmiljön</span><span class="sxs-lookup"><span data-stu-id="0edca-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="0edca-128">Fullständig distribution</span><span class="sxs-lookup"><span data-stu-id="0edca-128">Full deployment</span></span> | <span data-ttu-id="0edca-129">Ring 3: Distribuera tjänsten till resten av miljön stegvis.</span><span class="sxs-lookup"><span data-stu-id="0edca-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="0edca-130">Avsluta villkor</span><span class="sxs-lookup"><span data-stu-id="0edca-130">Exit criteria</span></span>
<span data-ttu-id="0edca-131">Ett exempel på utgångsvillkor för dessa ringar kan vara:</span><span class="sxs-lookup"><span data-stu-id="0edca-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="0edca-132">Enheter visas i enhetsinventeringslistan</span><span class="sxs-lookup"><span data-stu-id="0edca-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="0edca-133">Aviseringar visas i instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="0edca-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="0edca-134">Köra ett identifieringstest</span><span class="sxs-lookup"><span data-stu-id="0edca-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="0edca-135">Köra en simulerad attack på en enhet</span><span class="sxs-lookup"><span data-stu-id="0edca-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="0edca-136">Utvärdera</span><span class="sxs-lookup"><span data-stu-id="0edca-136">Evaluate</span></span>
<span data-ttu-id="0edca-137">Identifiera ett litet antal testdatorer i din miljö som kan komma igång med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0edca-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="0edca-138">Helst bör dessa datorer ha färre än 50 slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="0edca-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="0edca-139">Pilot</span><span class="sxs-lookup"><span data-stu-id="0edca-139">Pilot</span></span>
<span data-ttu-id="0edca-140">Microsoft Defender för Endpoint har stöd för ett antal olika slutpunkter som du kan introducera till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0edca-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="0edca-141">I den här ringen identifierar du flera enheter som kan introduceras och utifrån de utgångsvillkor som du anger, bestämmer dig för att gå vidare till nästa distributionsring.</span><span class="sxs-lookup"><span data-stu-id="0edca-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="0edca-142">I följande tabell visas de slutpunkter som stöds och motsvarande verktyg som du kan använda för att registrera enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0edca-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="0edca-143">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="0edca-143">Endpoint</span></span>     | <span data-ttu-id="0edca-144">Distributionsverktyget</span><span class="sxs-lookup"><span data-stu-id="0edca-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="0edca-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="0edca-145">**Windows**</span></span>  |  [<span data-ttu-id="0edca-146">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="0edca-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="0edca-147">Obs! Om du vill distribuera fler än 10 enheter i en produktionsmiljö använder du grupprincipmetoden i stället eller andra verktyg som stöds nedan.</span><span class="sxs-lookup"><span data-stu-id="0edca-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="0edca-148">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="0edca-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="0edca-149">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="0edca-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="0edca-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0edca-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="0edca-151">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="0edca-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="0edca-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="0edca-152">**macOS**</span></span>    | [<span data-ttu-id="0edca-153">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="0edca-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="0edca-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0edca-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="0edca-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="0edca-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="0edca-156">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="0edca-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="0edca-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="0edca-157">**Linux Server**</span></span> | [<span data-ttu-id="0edca-158">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="0edca-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="0edca-159">En- och en-</span><span class="sxs-lookup"><span data-stu-id="0edca-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="0edca-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="0edca-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="0edca-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="0edca-161">**iOS**</span></span>      | [<span data-ttu-id="0edca-162">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="0edca-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="0edca-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="0edca-163">**Android**</span></span>  | [<span data-ttu-id="0edca-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0edca-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="0edca-165">Fullständig distribution</span><span class="sxs-lookup"><span data-stu-id="0edca-165">Full deployment</span></span>
<span data-ttu-id="0edca-166">I det här läget kan du använda planera [distributionsmaterial](deployment-strategy.md) för att planera distributionen.</span><span class="sxs-lookup"><span data-stu-id="0edca-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="0edca-167">Använd följande material för att välja lämplig Microsoft Defender för Slutpunktsarkitektur som bäst passar din organisation.</span><span class="sxs-lookup"><span data-stu-id="0edca-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="0edca-168">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="0edca-168">**Item**</span></span>|<span data-ttu-id="0edca-169">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0edca-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0edca-170">[![Thumb-bild för Microsoft Defender för distributionsstrategi för slutpunkt](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="0edca-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="0edca-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="0edca-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="0edca-172">Med hjälp av arkitekturmaterialet kan du planera din distribution för följande arkitekturer:</span><span class="sxs-lookup"><span data-stu-id="0edca-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="0edca-173">Molnbaserad</span><span class="sxs-lookup"><span data-stu-id="0edca-173">Cloud-native</span></span> </li><li> <span data-ttu-id="0edca-174">Samhantering</span><span class="sxs-lookup"><span data-stu-id="0edca-174">Co-management</span></span> </li><li> <span data-ttu-id="0edca-175">Lokal</span><span class="sxs-lookup"><span data-stu-id="0edca-175">On-premise</span></span></li><li><span data-ttu-id="0edca-176">Utvärdering och lokal registrering</span><span class="sxs-lookup"><span data-stu-id="0edca-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="0edca-177">Befintliga distributioner</span><span class="sxs-lookup"><span data-stu-id="0edca-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="0edca-178">Windows-slutpunkter</span><span class="sxs-lookup"><span data-stu-id="0edca-178">Windows endpoints</span></span>
<span data-ttu-id="0edca-179">För Windows och/eller Windows-servrar väljer du flera datorer som du vill testa i förväg (före korrigeringen tisdag) med hjälp av programmet VALIDERING av säkerhetsuppdateringar **(HURP).**</span><span class="sxs-lookup"><span data-stu-id="0edca-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="0edca-180">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="0edca-180">For more information, see:</span></span>
- [<span data-ttu-id="0edca-181">Vad är verifieringsprogrammet för säkerhetsuppdateringar?</span><span class="sxs-lookup"><span data-stu-id="0edca-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="0edca-182">Program för validering av program för programuppdatering och det program som används av Microsoft Malware Protection Center – TwC interaktiv tidslinje del 4</span><span class="sxs-lookup"><span data-stu-id="0edca-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="0edca-183">Slutpunkter som inte är Windows</span><span class="sxs-lookup"><span data-stu-id="0edca-183">Non-Windows endpoints</span></span>
<span data-ttu-id="0edca-184">Med macOS och Linux kunde du köra ett par system i "InsidersFast"-kanalen.</span><span class="sxs-lookup"><span data-stu-id="0edca-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="0edca-185">Under idealiska som helst minst en säkerhetsadministratör och en utvecklare så att du kan hitta kompatibilitets-, prestanda- och tillförlitlighetsproblem innan versionen tar den till kanalen "Produktion".</span><span class="sxs-lookup"><span data-stu-id="0edca-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="0edca-186">Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet.</span><span class="sxs-lookup"><span data-stu-id="0edca-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="0edca-187">Enheter inom insiders – snabbt är de första som får uppdateringar och nya funktioner, följt senare av insiders-slow och slutligen av prod.</span><span class="sxs-lookup"><span data-stu-id="0edca-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![Bild på insiderringar](images/insider-rings.png)

<span data-ttu-id="0edca-189">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget så att de använder Insiders -snabbt eller Insiders-slow.</span><span class="sxs-lookup"><span data-stu-id="0edca-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="0edca-190">Om du byter kanal efter den första installationen måste produkten installeras om.</span><span class="sxs-lookup"><span data-stu-id="0edca-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="0edca-191">Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="0edca-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
