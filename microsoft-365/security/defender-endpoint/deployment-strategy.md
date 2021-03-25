---
title: Planera distribution av Microsoft Defender för Slutpunkt
description: Välj den bästa distributionsstrategin för Microsoft Defender för slutpunkten för din miljö
keywords: distribuera, planera, distributionsstrategi, inbyggd molntjänst, hantering, lokal, utvärdering, onboarding, lokal, grupprincip, gp, slutpunktsansvarig, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163581"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="d6024-104">Planera distribution av Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="d6024-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d6024-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d6024-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6024-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d6024-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d6024-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6024-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d6024-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d6024-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d6024-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d6024-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="d6024-110">Planera distributionen av Microsoft Defender för slutpunkt så att du kan maximera säkerhetsfunktionerna i paketet och bättre skydda ditt företag mot cyberhot.</span><span class="sxs-lookup"><span data-stu-id="d6024-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="d6024-111">Den här lösningen innehåller vägledning om hur du identifierar din miljöarkitektur, väljer den typ av distributionsverktyg som bäst passar dina behov och vägledning om hur du konfigurerar funktioner.</span><span class="sxs-lookup"><span data-stu-id="d6024-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Bild av distributionsflöde](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="d6024-113">Steg 1: Identifiera arkitektur</span><span class="sxs-lookup"><span data-stu-id="d6024-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="d6024-114">Vi förstår att alla företagsmiljöer är unika, så vi har tillhandahållit flera alternativ för att ge dig flexibiliteten att välja hur tjänsten ska distribueras.</span><span class="sxs-lookup"><span data-stu-id="d6024-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="d6024-115">Beroende på din miljö passar vissa verktyg bättre för vissa arkitekturer.</span><span class="sxs-lookup"><span data-stu-id="d6024-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="d6024-116">Använd följande material för att välja lämplig Defender för Endpoint-arkitektur som bäst passar din organisation.</span><span class="sxs-lookup"><span data-stu-id="d6024-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="d6024-117">Objekt</span><span class="sxs-lookup"><span data-stu-id="d6024-117">Item</span></span> | <span data-ttu-id="d6024-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d6024-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="d6024-119">[![Thumb-bild för Defender för slutpunktsdistributionsstrategi](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="d6024-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="d6024-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="d6024-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="d6024-121">Med hjälp av arkitekturmaterialet kan du planera din distribution för följande arkitekturer:</span><span class="sxs-lookup"><span data-stu-id="d6024-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="d6024-122">Molnbaserad</span><span class="sxs-lookup"><span data-stu-id="d6024-122">Cloud-native</span></span> </li><li> <span data-ttu-id="d6024-123">Samhantering</span><span class="sxs-lookup"><span data-stu-id="d6024-123">Co-management</span></span> </li><li> <span data-ttu-id="d6024-124">Lokal</span><span class="sxs-lookup"><span data-stu-id="d6024-124">On-premise</span></span></li><li><span data-ttu-id="d6024-125">Utvärdering och lokal registrering</span><span class="sxs-lookup"><span data-stu-id="d6024-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="d6024-126">Steg 2: Välj distributionsmetod</span><span class="sxs-lookup"><span data-stu-id="d6024-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="d6024-127">Defender för Endpoint har stöd för ett antal olika slutpunkter som du kan introducera till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6024-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="d6024-128">I följande tabell visas de slutpunkter som stöds och motsvarande distributionsverktyg som du kan använda så att du kan planera distributionen på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="d6024-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="d6024-129">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="d6024-129">Endpoint</span></span>     | <span data-ttu-id="d6024-130">Distributionsverktyget</span><span class="sxs-lookup"><span data-stu-id="d6024-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d6024-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d6024-131">**Windows**</span></span>  |  [<span data-ttu-id="d6024-132">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="d6024-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="d6024-133">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="d6024-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="d6024-134">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="d6024-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="d6024-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d6024-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="d6024-136">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="d6024-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="d6024-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d6024-137">**macOS**</span></span>    | [<span data-ttu-id="d6024-138">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="d6024-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="d6024-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d6024-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="d6024-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="d6024-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="d6024-141">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="d6024-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="d6024-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="d6024-142">**Linux Server**</span></span> | [<span data-ttu-id="d6024-143">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="d6024-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="d6024-144">En- och en-</span><span class="sxs-lookup"><span data-stu-id="d6024-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="d6024-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="d6024-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="d6024-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d6024-146">**iOS**</span></span>      | [<span data-ttu-id="d6024-147">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="d6024-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="d6024-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="d6024-148">**Android**</span></span>  | [<span data-ttu-id="d6024-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d6024-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="d6024-150">Steg 3: Konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="d6024-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="d6024-151">Efter slutpunkter för onboarding konfigurerar du säkerhetsfunktionerna i Defender för Endpoint så att du kan maximera det robusta säkerhetsskydd som finns tillgängligt i programsviten.</span><span class="sxs-lookup"><span data-stu-id="d6024-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="d6024-152">Funktionerna omfattar:</span><span class="sxs-lookup"><span data-stu-id="d6024-152">Capabilities include:</span></span>

- <span data-ttu-id="d6024-153">Identifiering och svar av slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d6024-153">Endpoint detection and response</span></span>
- <span data-ttu-id="d6024-154">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="d6024-154">Next-generation protection</span></span>
- <span data-ttu-id="d6024-155">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="d6024-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="d6024-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d6024-156">Related topics</span></span>
- [<span data-ttu-id="d6024-157">Distributionsfaser</span><span class="sxs-lookup"><span data-stu-id="d6024-157">Deployment phases</span></span>](deployment-phases.md)
