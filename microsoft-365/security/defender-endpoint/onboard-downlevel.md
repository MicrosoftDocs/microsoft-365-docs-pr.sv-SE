---
title: Introducera tidigare versioner av Windows på Microsoft Defender för Endpoint
description: Registrera tidigare versioner av Windows enheter som stöds så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensor
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, nedåtnivå
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844436"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="18c9d-104">Registrera tidigare versioner av Windows</span><span class="sxs-lookup"><span data-stu-id="18c9d-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="18c9d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="18c9d-105">**Applies to:**</span></span>
- [<span data-ttu-id="18c9d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="18c9d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="18c9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18c9d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="18c9d-108">**Plattformar**</span><span class="sxs-lookup"><span data-stu-id="18c9d-108">**Platforms**</span></span>
- <span data-ttu-id="18c9d-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="18c9d-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="18c9d-110">Windows 7 SP1-Pro</span><span class="sxs-lookup"><span data-stu-id="18c9d-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="18c9d-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="18c9d-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="18c9d-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="18c9d-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="18c9d-113">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="18c9d-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="18c9d-114">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="18c9d-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="18c9d-115">Defender för Endpoint utökar stödet till att inkludera operativsystem på undernivå, med avancerade funktioner för identifiering och undersökning av attacker i versioner som Windows.</span><span class="sxs-lookup"><span data-stu-id="18c9d-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="18c9d-116">Om du vill introducera Windows-slutpunkter i Defender för Endpoint måste du:</span><span class="sxs-lookup"><span data-stu-id="18c9d-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="18c9d-117">Konfigurera och uppdatera System Center Endpoint Protection klienter.</span><span class="sxs-lookup"><span data-stu-id="18c9d-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="18c9d-118">Installera och konfigurera Microsoft Monitoring Agent (MMA) för att rapportera sensordata till Defender för Slutpunkt enligt anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="18c9d-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="18c9d-119">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att den är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="18c9d-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="18c9d-120">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunktsslutpunkt.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="18c9d-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="18c9d-121">Konfigurera och uppdatera System Center Endpoint Protection klienter</span><span class="sxs-lookup"><span data-stu-id="18c9d-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="18c9d-122">Det här steget krävs bara om din organisation använder System Center Endpoint Protection (S UPP)..</span><span class="sxs-lookup"><span data-stu-id="18c9d-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="18c9d-123">Defender för Endpoint integreras med System Center Endpoint Protection för att göra det möjligt att identifiera skadlig programvara och stoppa spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="18c9d-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="18c9d-124">Följande steg krävs för att aktivera den här integreringen:</span><span class="sxs-lookup"><span data-stu-id="18c9d-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="18c9d-125">Installera uppdateringen [för plattformsuppdateringen för skydd mot skadlig programvara i januari 2017 Endpoint Protection klienter](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="18c9d-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="18c9d-126">Konfigurera medlemskap i S FLERA-klientens Molnskyddstjänst till **inställningen** Avancerat</span><span class="sxs-lookup"><span data-stu-id="18c9d-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="18c9d-127">Konfigurera nätverket för att tillåta anslutningar till Microsoft Defender Antivirus molnet.</span><span class="sxs-lookup"><span data-stu-id="18c9d-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="18c9d-128">Mer information finns i [Tillåta anslutningar till Microsoft Defender Antivirus molnet](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="18c9d-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="18c9d-129">Installera och konfigurera MMA (Microsoft Monitoring Agent) för att rapportera sensordata till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="18c9d-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="18c9d-130">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="18c9d-130">Before you begin</span></span>
<span data-ttu-id="18c9d-131">Granska följande information för att verifiera lägsta systemkrav:</span><span class="sxs-lookup"><span data-stu-id="18c9d-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="18c9d-132">Installera den [månatliga uppdateringen för februari 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="18c9d-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="18c9d-133">Gäller endast för Windows 7 SP1 Enterprise och Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="18c9d-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="18c9d-134">Installera uppdatering [för kundupplevelse och diagnostisk telemetri](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="18c9d-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="18c9d-135">Installera [antingen .NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) eller [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="18c9d-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="18c9d-136">Gäller endast för Windows 7 SP1 Enterprise och Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="18c9d-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="18c9d-137">Installera inte .NET Framework 4.0.x, eftersom ovanstående installation kommer att avse.</span><span class="sxs-lookup"><span data-stu-id="18c9d-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="18c9d-138">Uppfylla systemkraven för Azure Log Analytics-agenten.</span><span class="sxs-lookup"><span data-stu-id="18c9d-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="18c9d-139">Mer information finns i Samla [in data från datorer i din miljö med logganalys.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="18c9d-139">For more information, see [Collect data from computers in your environment with Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).</span></span>



1. <span data-ttu-id="18c9d-140">Ladda ned installationsfilen för agenten: [Windows 64-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828603) [eller Windows 32-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span><span class="sxs-lookup"><span data-stu-id="18c9d-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="18c9d-141">Hämta arbetsyte-ID:</span><span class="sxs-lookup"><span data-stu-id="18c9d-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="18c9d-142">I navigeringsfönstret i Defender för slutpunkt väljer **du Inställningar > Enhetshantering > Onboarding**</span><span class="sxs-lookup"><span data-stu-id="18c9d-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="18c9d-143">Välj **Windows 7 SP1 och 8.1** som operativsystem</span><span class="sxs-lookup"><span data-stu-id="18c9d-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="18c9d-144">Kopiera arbetsyte-ID:t och arbetsytenyckeln</span><span class="sxs-lookup"><span data-stu-id="18c9d-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="18c9d-145">Använd nyckeln Arbetsyte-ID och Arbetsyta genom att välja någon av följande installationsmetoder för att installera agenten:</span><span class="sxs-lookup"><span data-stu-id="18c9d-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="18c9d-146">[Installera agenten manuellt med hjälp av konfigurationen](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="18c9d-146">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="18c9d-147">På sidan **Installationsalternativ för** agent väljer du **Anslut agenten till Azure Log Analytics (OMS)**</span><span class="sxs-lookup"><span data-stu-id="18c9d-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="18c9d-148">[Installera agenten med kommandoraden](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="18c9d-148">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="18c9d-149">[Konfigurera agenten med hjälp av ett skript](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="18c9d-149">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="18c9d-150">Om du [](gov.md)är myndighetskund i USA måste du under "Azure Cloud" välja "Azure US Government" om du använder installationsguiden, eller om du använder en kommandorad eller ett skript – ange parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.</span><span class="sxs-lookup"><span data-stu-id="18c9d-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="18c9d-151">Om du använder en proxyserver för att ansluta till Internet kan du gå till avsnittet Konfigurera proxyinställningar.</span><span class="sxs-lookup"><span data-stu-id="18c9d-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="18c9d-152">När den är klar bör du se onboarded endpoints i portalen inom en timme.</span><span class="sxs-lookup"><span data-stu-id="18c9d-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="18c9d-153">Konfigurera inställningar för proxy- och Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="18c9d-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="18c9d-154">Varje Windows måste kunna ansluta till Internet med https.</span><span class="sxs-lookup"><span data-stu-id="18c9d-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="18c9d-155">Den här anslutningen kan vara direkt, med hjälp av en proxy eller via [OMS-gatewayen.](/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="18c9d-155">This connection can be direct, using a proxy, or through the [OMS Gateway](/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="18c9d-156">Om en proxy eller brandvägg blockerar all trafik som standard och bara tillåter specifika domäner via eller HTTPS-genomsökning (SSL-kontroll) är aktiverat ska du se till att du aktiverar åtkomst till Defender för [slutpunktstjänst-URL:er.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="18c9d-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="18c9d-157">Offboard-klientslutpunkter</span><span class="sxs-lookup"><span data-stu-id="18c9d-157">Offboard client endpoints</span></span>
<span data-ttu-id="18c9d-158">Till offboard kan du avinstallera MMA-agenten från slutpunkten eller koppla från den från rapporteringen till Defender för slutpunkt-arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="18c9d-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="18c9d-159">När agenten har offboarding skickar slutpunkten inte längre sensordata till Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="18c9d-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="18c9d-160">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="18c9d-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="18c9d-161">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span><span class="sxs-lookup"><span data-stu-id="18c9d-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>
