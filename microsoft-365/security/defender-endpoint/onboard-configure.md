---
title: Introducera enheter till Microsoft Defender ATP-tjänsten
description: Introducera Windows 10-enheter, servrar, icke-Windows-enheter och lär dig hur du kör ett identifieringstest.
keywords: onboarding, microsoft defender för slutpunkts onboarding, windows atp onboarding, sccm, grupprincip, mdm, lokalt skript, identifieringstest
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b7a225e29b4b79b2e6caf95332cb91da3dade7f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186959"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="33875-104">Introducera enheter till Microsoft Defender för slutpunktstjänsten</span><span class="sxs-lookup"><span data-stu-id="33875-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33875-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="33875-105">**Applies to:**</span></span>
- [<span data-ttu-id="33875-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="33875-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="33875-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33875-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="33875-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="33875-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33875-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="33875-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="33875-110">Du måste gå till introduktionsavsnittet i Defender för Endpoint-portalen för att registrera någon av de enheter som stöds.</span><span class="sxs-lookup"><span data-stu-id="33875-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="33875-111">Beroende på enhet vägleds du med lämpliga steg och lämpliga alternativ för hantering och distributionsverktyg för enheten.</span><span class="sxs-lookup"><span data-stu-id="33875-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="33875-112">I allmänhet kan du registrera enheter i tjänsten:</span><span class="sxs-lookup"><span data-stu-id="33875-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="33875-113">Kontrollera att enheten uppfyller [minimikraven](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="33875-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="33875-114">Beroende på enhet följer du konfigurationsstegen i introduktionsavsnittet för Defender för slutpunktsportalen</span><span class="sxs-lookup"><span data-stu-id="33875-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="33875-115">Använd rätt hanteringsverktyg och distributionsmetod för dina enheter</span><span class="sxs-lookup"><span data-stu-id="33875-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="33875-116">Kör ett identifieringstest för att verifiera att enheterna är korrekt onboarded och rapporterar till tjänsten</span><span class="sxs-lookup"><span data-stu-id="33875-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="33875-117">Alternativ för introduktionsverktyg</span><span class="sxs-lookup"><span data-stu-id="33875-117">Onboarding tool options</span></span>
<span data-ttu-id="33875-118">I följande tabell visas de tillgängliga verktygen baserat på slutpunkten som du behöver registrera.</span><span class="sxs-lookup"><span data-stu-id="33875-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="33875-119">Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="33875-119">Endpoint</span></span>     | <span data-ttu-id="33875-120">Verktygsalternativ</span><span class="sxs-lookup"><span data-stu-id="33875-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="33875-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="33875-121">**Windows**</span></span>  |  [<span data-ttu-id="33875-122">Lokalt skript (upp till 10 enheter)</span><span class="sxs-lookup"><span data-stu-id="33875-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="33875-123">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="33875-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="33875-124">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="33875-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="33875-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33875-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="33875-126">VDI-skript</span><span class="sxs-lookup"><span data-stu-id="33875-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="33875-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="33875-127">**macOS**</span></span>    | [<span data-ttu-id="33875-128">Lokala skript</span><span class="sxs-lookup"><span data-stu-id="33875-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="33875-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="33875-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="33875-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="33875-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="33875-131">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="33875-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="33875-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="33875-132">**Linux Server**</span></span> | [<span data-ttu-id="33875-133">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="33875-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="33875-134">En- och en-</span><span class="sxs-lookup"><span data-stu-id="33875-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="33875-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="33875-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="33875-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="33875-136">**iOS**</span></span>      | [<span data-ttu-id="33875-137">Appbaserade</span><span class="sxs-lookup"><span data-stu-id="33875-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="33875-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="33875-138">**Android**</span></span>  | [<span data-ttu-id="33875-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="33875-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="33875-140">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="33875-140">In this section</span></span>
<span data-ttu-id="33875-141">Ämne</span><span class="sxs-lookup"><span data-stu-id="33875-141">Topic</span></span> | <span data-ttu-id="33875-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33875-142">Description</span></span>
:---|:---
[<span data-ttu-id="33875-143">Introducera tidigare versioner av Windows</span><span class="sxs-lookup"><span data-stu-id="33875-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="33875-144">Introducera Windows 7- och Windows 8.1-enheter i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="33875-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="33875-145">Introducera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="33875-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="33875-146">Du måste registrera enheter för att rapporten ska kunna rapportera till Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="33875-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="33875-147">Läs mer om verktyg och metoder som du kan använda för att konfigurera enheter i företaget.</span><span class="sxs-lookup"><span data-stu-id="33875-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="33875-148">Onboard servers</span><span class="sxs-lookup"><span data-stu-id="33875-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="33875-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SACK) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="33875-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="33875-150">Introducera enheter som inte är Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="33875-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="33875-151">Defender för Endpoint ger en centraliserad säkerhetsoperationer för Windows och för icke-Windows-plattformar.</span><span class="sxs-lookup"><span data-stu-id="33875-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="33875-152">Du kan se aviseringar från olika operativsystem som stöds (OS) i Microsoft Defender Säkerhetscenter och bättre skydda organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="33875-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="33875-153">Den här upplevelsen utnyttjar sensordata från tredje part.</span><span class="sxs-lookup"><span data-stu-id="33875-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="33875-154">Köra ett identifieringstest på en nyligen onboarded-enhet</span><span class="sxs-lookup"><span data-stu-id="33875-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="33875-155">Kör ett skript på en nyligen onboarded-enhet för att verifiera att den rapporterar korrekt till Defender för slutpunkt-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="33875-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="33875-156">Konfigurera proxy- och Internetinställningar</span><span class="sxs-lookup"><span data-stu-id="33875-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="33875-157">Aktivera kommunikation med Defender för slutpunktsmolntjänsten genom att konfigurera proxy- och Internetanslutningsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="33875-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="33875-158">Felsöka onboarding-problem</span><span class="sxs-lookup"><span data-stu-id="33875-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="33875-159">Läs mer om hur du löser problem som kan uppstå under registrering.</span><span class="sxs-lookup"><span data-stu-id="33875-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="33875-160">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="33875-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33875-161">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="33875-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
