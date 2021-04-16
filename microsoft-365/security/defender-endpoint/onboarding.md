---
title: Onboard to the Microsoft Defender for Endpoint service
description: Lär dig hur du onboardar slutpunkter till Microsoft Defender för Endpoint-tjänsten
keywords: microsoft defender för slutpunkt, onboard, distribuera
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
ms.openlocfilehash: 2a3325a290dc985bdb99a5a843b4b9e1f642a62b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861809"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="90856-104">Onboard to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="90856-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="90856-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="90856-105">**Applies to:**</span></span>
- [<span data-ttu-id="90856-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="90856-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="90856-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90856-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="90856-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="90856-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="90856-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="90856-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="90856-110">Läs mer om de olika faserna i distributionen av Microsoft Defender för Endpoint och hur du konfigurerar funktionerna i lösningen.</span><span class="sxs-lookup"><span data-stu-id="90856-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="90856-111">Distribution av Defender för Endpoint är en process i tre steg:</span><span class="sxs-lookup"><span data-stu-id="90856-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="90856-112">[![distributionsfas – förbereda](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="90856-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="90856-113">Fas 1: Förbereda</span><span class="sxs-lookup"><span data-stu-id="90856-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="90856-114">[![distributionsfas – konfiguration](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="90856-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="90856-115">Fas 2: Installation</span><span class="sxs-lookup"><span data-stu-id="90856-115">Phase 2: Setup</span></span>](production-deployment.md) | ![distributionsfas – onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="90856-117">Fas 3: Introduktion</span><span class="sxs-lookup"><span data-stu-id="90856-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="90856-118">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="90856-118">*You are here!*</span></span>|

<span data-ttu-id="90856-119">Du befinner dig för närvarande i introduktionsfasen.</span><span class="sxs-lookup"><span data-stu-id="90856-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="90856-120">Det här är de steg du måste vidta för att distribuera Defender för Slutpunkt:</span><span class="sxs-lookup"><span data-stu-id="90856-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="90856-121">Steg 1: Introducera slutpunkter till tjänsten</span><span class="sxs-lookup"><span data-stu-id="90856-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="90856-122">Steg 2: Konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="90856-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="90856-123">Steg 1: Hantera slutpunkter som använder något av de hanteringsverktyg som stöds</span><span class="sxs-lookup"><span data-stu-id="90856-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="90856-124">I [avsnittet Planera](deployment-strategy.md) distribution beskrivs de allmänna åtgärder du behöver vidta för att distribuera Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="90856-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="90856-125">Titta på den här videon för en snabb överblick över registreringsprocessen och lär dig mer om tillgängliga verktyg och metoder.</span><span class="sxs-lookup"><span data-stu-id="90856-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="90856-126">När du har identifierat arkitekturen måste du bestämma vilken distributionsmetod du ska använda.</span><span class="sxs-lookup"><span data-stu-id="90856-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="90856-127">Distributionsverktyget du väljer påverkar hur du onboardar slutpunkter till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="90856-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="90856-128">Alternativ för introduktionsverktyg</span><span class="sxs-lookup"><span data-stu-id="90856-128">Onboarding tool options</span></span>

<span data-ttu-id="90856-129">I följande tabell visas de tillgängliga verktygen baserat på slutpunkten som du behöver registrera.</span><span class="sxs-lookup"><span data-stu-id="90856-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="90856-130">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="90856-130">Endpoint</span></span>     | <span data-ttu-id="90856-131">Verktygsalternativ</span><span class="sxs-lookup"><span data-stu-id="90856-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="90856-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="90856-132">**Windows**</span></span>  |  [<span data-ttu-id="90856-133">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="90856-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="90856-134">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="90856-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="90856-135">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="90856-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="90856-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="90856-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="90856-137">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="90856-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="90856-138">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="90856-138">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="90856-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="90856-139">**macOS**</span></span>    | [<span data-ttu-id="90856-140">Lokala skript</span><span class="sxs-lookup"><span data-stu-id="90856-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="90856-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="90856-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="90856-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="90856-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="90856-143">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="90856-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="90856-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="90856-144">**Linux Server**</span></span> | [<span data-ttu-id="90856-145">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="90856-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="90856-146">En- och en-</span><span class="sxs-lookup"><span data-stu-id="90856-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="90856-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="90856-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="90856-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="90856-148">**iOS**</span></span>      | [<span data-ttu-id="90856-149">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="90856-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="90856-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="90856-150">**Android**</span></span>  | [<span data-ttu-id="90856-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="90856-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="90856-152">Steg 2: Konfigurera funktioner</span><span class="sxs-lookup"><span data-stu-id="90856-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="90856-153">Efter att slutpunkterna introduceras konfigurerar du de olika funktionerna, till exempel identifiering och svar av slutpunkter, nästa generations skydd och minskning av attackytan.</span><span class="sxs-lookup"><span data-stu-id="90856-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="90856-154">Exempeldistributioner</span><span class="sxs-lookup"><span data-stu-id="90856-154">Example deployments</span></span>
<span data-ttu-id="90856-155">I den här distributionsguiden vägleder vi dig genom att använda två distributionsverktyg för att introducera slutpunkter och konfigurera funktioner.</span><span class="sxs-lookup"><span data-stu-id="90856-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="90856-156">Verktygen i exempeldistributionerna är:</span><span class="sxs-lookup"><span data-stu-id="90856-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="90856-157">Introduktion med hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="90856-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="90856-158">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="90856-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="90856-159">Med hjälp av de omnämnda distributionsverktygen ovan vägleds du när du konfigurerar följande Defender för Slutpunkt-funktioner:</span><span class="sxs-lookup"><span data-stu-id="90856-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="90856-160">Konfiguration av slutpunktsidentifiering och -svar</span><span class="sxs-lookup"><span data-stu-id="90856-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="90856-161">Konfiguration av nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="90856-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="90856-162">Konfiguration för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="90856-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="90856-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="90856-163">Related topics</span></span>
- [<span data-ttu-id="90856-164">Introduktion med hjälp av Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="90856-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="90856-165">Introduktion med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="90856-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="90856-166">Säkra dokument i Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90856-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
