---
title: Introduktion till Microsoft Defender ATP-tjänsten
description: Lär dig hur du onboardar slutpunkter till Microsoft Defender ATP-tjänsten
keywords: ''
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
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2b3ce535ba5abddbf1175e568638f7ee186e093d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076522"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="65222-103">Onboard to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="65222-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65222-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="65222-104">**Applies to:**</span></span>
- [<span data-ttu-id="65222-105">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="65222-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="65222-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65222-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="65222-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="65222-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65222-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="65222-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="65222-109">Läs mer om de olika faserna i distributionen av Microsoft Defender för Endpoint och hur du konfigurerar funktionerna i lösningen.</span><span class="sxs-lookup"><span data-stu-id="65222-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="65222-110">Distribution av Defender för Endpoint är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="65222-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="65222-111">[![distributionsfas – förbereda](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="65222-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="65222-112">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="65222-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="65222-113">[![distributionsfas – konfiguration](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="65222-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="65222-114">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="65222-114">Phase 2: Setup</span></span>](production-deployment.md) | ![distributionsfas – onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="65222-116">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="65222-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="65222-117">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="65222-117">*You are here!*</span></span>|

<span data-ttu-id="65222-118">Du befinner dig för närvarande i introduktionsfasen.</span><span class="sxs-lookup"><span data-stu-id="65222-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="65222-119">Det här är de steg du måste vidta för att distribuera Defender för Slutpunkt:</span><span class="sxs-lookup"><span data-stu-id="65222-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="65222-120">Steg 1: Introducera slutpunkter till tjänsten</span><span class="sxs-lookup"><span data-stu-id="65222-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="65222-121">Steg 2: Konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="65222-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="65222-122">Steg 1: Hantera slutpunkter som använder något av de hanteringsverktyg som stöds</span><span class="sxs-lookup"><span data-stu-id="65222-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="65222-123">I [avsnittet Planera](deployment-strategy.md) distribution beskrivs de allmänna åtgärder du behöver vidta för att distribuera Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="65222-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="65222-124">Titta på den här videon för en snabb överblick över registreringsprocessen och lär dig mer om tillgängliga verktyg och metoder.</span><span class="sxs-lookup"><span data-stu-id="65222-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="65222-125">När du har identifierat arkitekturen måste du bestämma vilken distributionsmetod du ska använda.</span><span class="sxs-lookup"><span data-stu-id="65222-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="65222-126">Distributionsverktyget du väljer påverkar hur du onboardar slutpunkter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="65222-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="65222-127">Alternativ för introduktionsverktyg</span><span class="sxs-lookup"><span data-stu-id="65222-127">Onboarding tool options</span></span>

<span data-ttu-id="65222-128">I följande tabell visas de tillgängliga verktygen baserat på slutpunkten som du behöver registrera.</span><span class="sxs-lookup"><span data-stu-id="65222-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="65222-129">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="65222-129">Endpoint</span></span>     | <span data-ttu-id="65222-130">Verktygsalternativ</span><span class="sxs-lookup"><span data-stu-id="65222-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="65222-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="65222-131">**Windows**</span></span>  |  [<span data-ttu-id="65222-132">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="65222-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="65222-133">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="65222-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="65222-134">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="65222-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="65222-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="65222-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="65222-136">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="65222-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="65222-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="65222-137">**macOS**</span></span>    | [<span data-ttu-id="65222-138">Lokala skript</span><span class="sxs-lookup"><span data-stu-id="65222-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="65222-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="65222-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="65222-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="65222-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="65222-141">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="65222-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="65222-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="65222-142">**Linux Server**</span></span> | [<span data-ttu-id="65222-143">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="65222-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="65222-144">En- och en-</span><span class="sxs-lookup"><span data-stu-id="65222-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="65222-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="65222-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="65222-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="65222-146">**iOS**</span></span>      | [<span data-ttu-id="65222-147">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="65222-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="65222-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="65222-148">**Android**</span></span>  | [<span data-ttu-id="65222-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="65222-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="65222-150">Steg 2: Konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="65222-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="65222-151">Efter att slutpunkterna introduceras konfigurerar du de olika funktionerna, till exempel identifiering och svar av slutpunkter, nästa generations skydd och minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="65222-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="65222-152">Exempeldistributioner</span><span class="sxs-lookup"><span data-stu-id="65222-152">Example deployments</span></span>
<span data-ttu-id="65222-153">I den här distributionsguiden vägleder vi dig genom att använda två distributionsverktyg för att introducera slutpunkter och konfigurera funktioner.</span><span class="sxs-lookup"><span data-stu-id="65222-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="65222-154">Verktygen i exempeldistributionerna är:</span><span class="sxs-lookup"><span data-stu-id="65222-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="65222-155">Introduktion med Konfigurationshanteraren för Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="65222-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="65222-156">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="65222-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="65222-157">Med hjälp av de omnämnda distributionsverktygen ovan vägleds du när du konfigurerar följande Defender för Slutpunkt-funktioner:</span><span class="sxs-lookup"><span data-stu-id="65222-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="65222-158">Konfiguration av slutpunktsidentifiering och -svar</span><span class="sxs-lookup"><span data-stu-id="65222-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="65222-159">Konfiguration av nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="65222-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="65222-160">Konfiguration för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="65222-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="65222-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65222-161">Related topics</span></span>
- [<span data-ttu-id="65222-162">Introduktion med Konfigurationshanteraren för Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="65222-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="65222-163">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="65222-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
