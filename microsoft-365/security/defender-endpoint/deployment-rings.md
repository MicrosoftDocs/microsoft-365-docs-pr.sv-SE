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
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297212"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="00aff-104">Distribuera Microsoft Defender för slutpunkt i ringar</span><span class="sxs-lookup"><span data-stu-id="00aff-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00aff-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="00aff-105">**Applies to:**</span></span>
- [<span data-ttu-id="00aff-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="00aff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00aff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00aff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="00aff-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="00aff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="00aff-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="00aff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="00aff-110">Distribution av Microsoft Defender för Endpoint kan göras med en ringbaserad distributionsmetod.</span><span class="sxs-lookup"><span data-stu-id="00aff-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="00aff-111">Distributionsringarna kan användas i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="00aff-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="00aff-112">Nya distributioner</span><span class="sxs-lookup"><span data-stu-id="00aff-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="00aff-113">Befintliga distributioner</span><span class="sxs-lookup"><span data-stu-id="00aff-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="00aff-114">Nya distributioner</span><span class="sxs-lookup"><span data-stu-id="00aff-114">New deployments</span></span>

![Bild på distributionsringar](images/deployment-rings.png)


<span data-ttu-id="00aff-116">En ringbaserad metod är en metod för att identifiera en uppsättning slutpunkter för att registrera och verifiera att vissa villkor uppfylls innan du fortsätter att distribuera tjänsten till en större uppsättning enheter.</span><span class="sxs-lookup"><span data-stu-id="00aff-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="00aff-117">Du kan definiera utgångsvillkor för varje ring och säkerställa att de är nöjda innan du går vidare till nästa ring.</span><span class="sxs-lookup"><span data-stu-id="00aff-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="00aff-118">Genom att införa en ringbaserad distribution minskar du eventuella problem som kan uppstå när tjänsten distribueras.</span><span class="sxs-lookup"><span data-stu-id="00aff-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="00aff-119">Genom att pilottesta ett visst antal enheter först kan du identifiera potentiella problem och minimera potentiella risker som kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="00aff-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="00aff-120">Tabell 1 innehåller ett exempel på de distributionsringar som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="00aff-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="00aff-121">**Tabell 1**</span><span class="sxs-lookup"><span data-stu-id="00aff-121">**Table 1**</span></span>

|<span data-ttu-id="00aff-122">**Distributionsringen**</span><span class="sxs-lookup"><span data-stu-id="00aff-122">**Deployment ring**</span></span>|<span data-ttu-id="00aff-123">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="00aff-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="00aff-124">Utvärdera</span><span class="sxs-lookup"><span data-stu-id="00aff-124">Evaluate</span></span> | <span data-ttu-id="00aff-125">Ring 1: Identifiera 50 system för pilottestning</span><span class="sxs-lookup"><span data-stu-id="00aff-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="00aff-126">Pilot</span><span class="sxs-lookup"><span data-stu-id="00aff-126">Pilot</span></span> | <span data-ttu-id="00aff-127">Ring 2: Identifiera de nästa 50–100 slutpunkterna i produktionsmiljön</span><span class="sxs-lookup"><span data-stu-id="00aff-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="00aff-128">Fullständig distribution</span><span class="sxs-lookup"><span data-stu-id="00aff-128">Full deployment</span></span> | <span data-ttu-id="00aff-129">Ring 3: Distribuera tjänsten till resten av miljön stegvis.</span><span class="sxs-lookup"><span data-stu-id="00aff-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="00aff-130">Avsluta villkor</span><span class="sxs-lookup"><span data-stu-id="00aff-130">Exit criteria</span></span>
<span data-ttu-id="00aff-131">Ett exempel på utgångsvillkor för dessa ringar kan vara:</span><span class="sxs-lookup"><span data-stu-id="00aff-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="00aff-132">Enheter visas i enhetsinventeringslistan</span><span class="sxs-lookup"><span data-stu-id="00aff-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="00aff-133">Aviseringar visas i instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="00aff-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="00aff-134">Köra ett identifieringstest</span><span class="sxs-lookup"><span data-stu-id="00aff-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="00aff-135">Köra en simulerad attack på en enhet</span><span class="sxs-lookup"><span data-stu-id="00aff-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="00aff-136">Utvärdera</span><span class="sxs-lookup"><span data-stu-id="00aff-136">Evaluate</span></span>
<span data-ttu-id="00aff-137">Identifiera ett litet antal testdatorer i din miljö som kan komma igång med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="00aff-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="00aff-138">Helst bör dessa datorer ha färre än 50 slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="00aff-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="00aff-139">Pilot</span><span class="sxs-lookup"><span data-stu-id="00aff-139">Pilot</span></span>
<span data-ttu-id="00aff-140">Microsoft Defender för Endpoint har stöd för ett antal olika slutpunkter som du kan introducera till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="00aff-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="00aff-141">I den här ringen identifierar du flera enheter som kan introduceras och utifrån de utgångsvillkor som du anger, bestämmer dig för att gå vidare till nästa distributionsring.</span><span class="sxs-lookup"><span data-stu-id="00aff-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="00aff-142">I följande tabell visas de slutpunkter som stöds och motsvarande verktyg som du kan använda för att registrera enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="00aff-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="00aff-143">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="00aff-143">Endpoint</span></span>     | <span data-ttu-id="00aff-144">Distributionsverktyget</span><span class="sxs-lookup"><span data-stu-id="00aff-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="00aff-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="00aff-145">**Windows**</span></span>  |  [<span data-ttu-id="00aff-146">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="00aff-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="00aff-147">Obs! Om du vill distribuera fler än 10 enheter i en produktionsmiljö använder du grupprincipmetoden i stället eller andra verktyg som stöds nedan.</span><span class="sxs-lookup"><span data-stu-id="00aff-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="00aff-148">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="00aff-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="00aff-149">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="00aff-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="00aff-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="00aff-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="00aff-151">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="00aff-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="00aff-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="00aff-152">**macOS**</span></span>    | [<span data-ttu-id="00aff-153">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="00aff-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="00aff-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="00aff-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="00aff-155">JAMF-Pro</span><span class="sxs-lookup"><span data-stu-id="00aff-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="00aff-156">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="00aff-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="00aff-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="00aff-157">**Linux Server**</span></span> | [<span data-ttu-id="00aff-158">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="00aff-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="00aff-159">En- och en-</span><span class="sxs-lookup"><span data-stu-id="00aff-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="00aff-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="00aff-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="00aff-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="00aff-161">**iOS**</span></span>      | [<span data-ttu-id="00aff-162">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="00aff-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="00aff-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="00aff-163">**Android**</span></span>  | [<span data-ttu-id="00aff-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="00aff-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="00aff-165">Fullständig distribution</span><span class="sxs-lookup"><span data-stu-id="00aff-165">Full deployment</span></span>
<span data-ttu-id="00aff-166">I det här läget kan du använda planera [distributionsmaterial](deployment-strategy.md) för att planera distributionen.</span><span class="sxs-lookup"><span data-stu-id="00aff-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="00aff-167">Använd följande material för att välja lämplig Microsoft Defender för Slutpunktsarkitektur som bäst passar din organisation.</span><span class="sxs-lookup"><span data-stu-id="00aff-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="00aff-168">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="00aff-168">**Item**</span></span>|<span data-ttu-id="00aff-169">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="00aff-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00aff-170">[![Thumb-bild för Microsoft Defender för distributionsstrategi för slutpunkt](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="00aff-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="00aff-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="00aff-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="00aff-172">Med hjälp av arkitekturmaterialet kan du planera din distribution för följande arkitekturer:</span><span class="sxs-lookup"><span data-stu-id="00aff-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="00aff-173">Molnbaserad</span><span class="sxs-lookup"><span data-stu-id="00aff-173">Cloud-native</span></span> </li><li> <span data-ttu-id="00aff-174">Samhantering</span><span class="sxs-lookup"><span data-stu-id="00aff-174">Co-management</span></span> </li><li> <span data-ttu-id="00aff-175">Lokal</span><span class="sxs-lookup"><span data-stu-id="00aff-175">On-premise</span></span></li><li><span data-ttu-id="00aff-176">Utvärdering och lokal registrering</span><span class="sxs-lookup"><span data-stu-id="00aff-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="00aff-177">Befintliga distributioner</span><span class="sxs-lookup"><span data-stu-id="00aff-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="00aff-178">Windows slutpunkter</span><span class="sxs-lookup"><span data-stu-id="00aff-178">Windows endpoints</span></span>
<span data-ttu-id="00aff-179">För Windows-servrar och/eller Windows-servrar väljer du flera datorer för att testa i förväg (före korrigeringen tisdag) med hjälp av programmet FÖR **säkerhetsuppdateringsverifiering (SÅD).**</span><span class="sxs-lookup"><span data-stu-id="00aff-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="00aff-180">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="00aff-180">For more information, see:</span></span>
- [<span data-ttu-id="00aff-181">Vad är verifieringsprogrammet för säkerhetsuppdateringar?</span><span class="sxs-lookup"><span data-stu-id="00aff-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="00aff-182">Valideringsprogram för program för programuppdatering och Microsoft Malware Protection Center upp - TwC Interaktiv tidslinje del 4</span><span class="sxs-lookup"><span data-stu-id="00aff-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="00aff-183">Slutpunkter som Windows inte är slutpunkter</span><span class="sxs-lookup"><span data-stu-id="00aff-183">Non-Windows endpoints</span></span>
<span data-ttu-id="00aff-184">Med macOS och Linux kan du köra ett par system i Beta-kanalen.</span><span class="sxs-lookup"><span data-stu-id="00aff-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="00aff-185">Under idealiska som helst minst en säkerhetsadministratör och en utvecklare så att du kan hitta kompatibilitets-, prestanda- och tillförlitlighetsproblem innan versionen tar den till aktuell kanal.</span><span class="sxs-lookup"><span data-stu-id="00aff-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="00aff-186">Valet av kanal avgör typ och frekvens för uppdateringar som erbjuds till din enhet.</span><span class="sxs-lookup"><span data-stu-id="00aff-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="00aff-187">Enheter i betaversion är de första som får uppdateringar och nya funktioner, följt senare av Förhandsversion och slutligen av Aktuell.</span><span class="sxs-lookup"><span data-stu-id="00aff-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![Bild på insiderringar](images/insider-rings.png)

<span data-ttu-id="00aff-189">Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i företaget för användning med antingen betaversion eller förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="00aff-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="00aff-190">Om du byter kanal efter den första installationen måste produkten installeras om.</span><span class="sxs-lookup"><span data-stu-id="00aff-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="00aff-191">Om du vill byta produktkanal: avinstallera det befintliga paketet, konfigurera om enheten så att den nya kanalen används och följ stegen i det här dokumentet för att installera paketet från den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="00aff-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
