---
title: Introducera Windows-servrar till Microsoft Defender för slutpunktstjänsten
description: Introducera Windows-servrarna så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensoren.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Windows ATP servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1757160b37500e97586fbb6dfb16d81303bc54e4
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476487"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="7c140-104">Introducera Windows-servrar till Microsoft Defender för slutpunktstjänsten</span><span class="sxs-lookup"><span data-stu-id="7c140-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7c140-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7c140-105">**Applies to:**</span></span>

- <span data-ttu-id="7c140-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="7c140-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="7c140-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7c140-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="7c140-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c140-108">Windows Server 2016</span></span>
- <span data-ttu-id="7c140-109">Windows Server (SACK) version 1803 och senare</span><span class="sxs-lookup"><span data-stu-id="7c140-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="7c140-110">Windows Server 2019 och senare</span><span class="sxs-lookup"><span data-stu-id="7c140-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="7c140-111">Kärnversionen av Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c140-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="7c140-112">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7c140-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7c140-113">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7c140-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="7c140-114">Defender för Endpoint utökar stödet till att även omfatta Windows Server-operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="7c140-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="7c140-115">Det här stödet ger avancerade funktioner för identifiering och undersökning av angrepp via microsoft Defender Säkerhetscenter-konsolen.</span><span class="sxs-lookup"><span data-stu-id="7c140-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="7c140-116">Praktiska anvisningar om vad som måste finnas för licensiering och infrastruktur finns i Skydda [Windows-servrar med Defender för slutpunkt.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="7c140-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="7c140-117">Information om hur du laddar ned och använder Windows-säkerhetsbaslinjer för Windows-servrar finns i [Baslinjer för Windows-säkerhet.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="7c140-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="7c140-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 och Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7c140-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="7c140-119">Du kan registrera Windows Server 2008 R2 SP1, Windows Server 2012 R2 och Windows Server 2016 till Defender för slutpunkt genom att använda något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="7c140-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="7c140-120">**Alternativ 1:** [Få igång genom att installera och konfigurera Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="7c140-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="7c140-121">**Alternativ 2:** [Hantera via Azure Säkerhetscenter](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="7c140-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="7c140-122">**Alternativ 3:** [Introduktion till Microsoft Endpoint Manager version 2002 och senare](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="7c140-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="7c140-123">När du har slutfört introduktionsstegen med något av de angivna alternativen måste du Konfigurera och uppdatera [System Center Endpoint Protection-klienter.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7c140-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="7c140-124">Defender för fristående slutpunkt för serverlicens krävs per nod, för att kunna introducera en Windows-server via Microsoft Monitoring Agent (alternativ 1) eller via Microsoft Endpoint Manager (Alternativ 3).</span><span class="sxs-lookup"><span data-stu-id="7c140-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="7c140-125">Du kan också behöva en Azure Defender för servrar-licens per nod för att kunna hantera en Windows-server via Azure Säkerhetscenter (alternativ 2) i Funktioner som stöds i [Azure Säkerhetscenter.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="7c140-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="7c140-126">Alternativ 1: Registrera dig genom att installera och konfigurera Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="7c140-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="7c140-127">Du måste installera och konfigurera MMA för Windows-servrar för att rapportera sensordata till Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7c140-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="7c140-128">Mer information finns i Samla [in loggdata med Azure Log Analytics-agenten.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="7c140-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="7c140-129">Om du redan använder System Center Operations Manager (SCOM) eller Azure Monitor (tidigare kallat Operations Management Suite (OMS)) kan du koppla Microsoft Monitoring Agent (MMA) till din Defender för slutpunkt-arbetsyta via Stöd för Multihoming.</span><span class="sxs-lookup"><span data-stu-id="7c140-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="7c140-130">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="7c140-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="7c140-131">Uppfylla kraven för introduktion som beskrivs i **avsnittet Innan du börjar.**</span><span class="sxs-lookup"><span data-stu-id="7c140-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="7c140-132">Aktivera serverövervakning från Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="7c140-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="7c140-133">Installera och konfigurera MMA för servern för att rapportera sensordata till Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7c140-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="7c140-134">Konfigurera och uppdatera System Center Endpoint Protection-klienter.</span><span class="sxs-lookup"><span data-stu-id="7c140-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="7c140-135">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att den är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7c140-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="7c140-136">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunktsslutpunkt.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="7c140-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="7c140-137">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="7c140-137">Before you begin</span></span> 
<span data-ttu-id="7c140-138">Utför följande steg för att uppfylla kraven för registrering:</span><span class="sxs-lookup"><span data-stu-id="7c140-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="7c140-139">För Windows Server 2008 R2 SP1 eller Windows Server 2012 R2 bör du installera följande snabbkorrigering:</span><span class="sxs-lookup"><span data-stu-id="7c140-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="7c140-140">Uppdatering för kundupplevelse och diagnostisk telemetri</span><span class="sxs-lookup"><span data-stu-id="7c140-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="7c140-141">För Windows Server 2008 R2 SP1 ska du dessutom kontrollera att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="7c140-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="7c140-142">Installera den [månatliga uppdateringen för februari](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="7c140-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="7c140-143">Installera [antingen .NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) eller [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="7c140-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>
   
   > [!NOTE]
    > <span data-ttu-id="7c140-144">Om du hanterar Windows Server 2008 R2 SP1 med SCCM installerar SCCM-klientagenten .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="7c140-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="7c140-145">Du behöver därför inte installera .NET Framework 4.5 (eller senare).</span><span class="sxs-lookup"><span data-stu-id="7c140-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>
   
 - <span data-ttu-id="7c140-146">För Windows Server 2008 R2 SP1 och Windows Server 2012 R2: Konfigurera och uppdatera [slutpunktsskyddsklienter för System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7c140-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c140-147">Det här steget krävs bara om din organisation använder System Center Endpoint Protection (SFÖNSTER) och du använder Windows Server 2008 R2 SP1 och Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="7c140-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="7c140-148">Installera och konfigurera MMA (Microsoft Monitoring Agent) för att rapportera sensordata till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="7c140-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="7c140-149">Ladda ned installationsfilen för agenten: [Windows 64-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="7c140-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="7c140-150">Med nyckeln arbetsyte-ID och arbetsyta som hämtas i föregående procedur väljer du någon av följande installationsmetoder för att installera agenten på Windows-servern:</span><span class="sxs-lookup"><span data-stu-id="7c140-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="7c140-151">[Installera agenten manuellt med hjälp av konfigurationen](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="7c140-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="7c140-152">På sidan **Alternativ för konfiguration av** agent väljer du Anslut **agenten till Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="7c140-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="7c140-153">[Installera agenten med kommandoraden](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="7c140-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="7c140-154">[Konfigurera agenten med hjälp av ett skript](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="7c140-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="7c140-155">Om du [](gov.md)är myndighetskund i USA måste du under "Azure Cloud" välja "Azure US Government" om du använder installationsguiden, eller om du använder en kommandorad eller ett skript – ange parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.</span><span class="sxs-lookup"><span data-stu-id="7c140-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="7c140-156">Konfigurera Windows-serverproxy och internetanslutningsinställningar vid behov</span><span class="sxs-lookup"><span data-stu-id="7c140-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="7c140-157">Om dina servrar behöver använda en proxyserver för att kommunicera med Defender för Slutpunkt använder du någon av följande metoder för att konfigurera MMA att använda proxyservern:</span><span class="sxs-lookup"><span data-stu-id="7c140-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="7c140-158">Konfigurera MMA att använda en proxyserver</span><span class="sxs-lookup"><span data-stu-id="7c140-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="7c140-159">Konfigurera Windows till att använda en proxyserver för alla anslutningar</span><span class="sxs-lookup"><span data-stu-id="7c140-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="7c140-160">Om en proxy eller brandvägg används ska du se till att servrar kan komma åt alla URL-adresser för Microsoft Defender för Endpoint-tjänsten direkt och utan SSL-avlyssning.</span><span class="sxs-lookup"><span data-stu-id="7c140-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="7c140-161">Mer information finns i aktivera [åtkomst till Defender för slutpunktstjänst-URL:er.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="7c140-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="7c140-162">Användning av SSL-avlyssning förhindrar att systemet kommunicerar med Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7c140-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="7c140-163">När den är klar bör du se de onboarded Windows-servrarna i portalen inom en timme.</span><span class="sxs-lookup"><span data-stu-id="7c140-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="7c140-164">Alternativ 2: Hantera Windows-servrar via Azure Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="7c140-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="7c140-165">I navigeringsfönstret för Microsoft Defender Säkerhetscenter väljer du **Inställningar Registrering**  >  **av**  >  **enhetshantering**.</span><span class="sxs-lookup"><span data-stu-id="7c140-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="7c140-166">Välj **Windows Server 2008 R2 SP1, 2012 R2 och 2016** som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="7c140-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="7c140-167">Klicka **på Onboard Servers i Azure Security Center.**</span><span class="sxs-lookup"><span data-stu-id="7c140-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="7c140-168">Följ introduktionsanvisningarna i [Microsoft Defender för Endpoint med Azure Säkerhetscenter.](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="7c140-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="7c140-169">När du har slutfört introduktionsstegen måste du Konfigurera och uppdatera [Slutpunktsskydd-klienter i System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7c140-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="7c140-170">För att onboarding via Azure Defender for Servers (tidigare Azure Security Center Standard Edition) ska fungera som förväntat måste servern ha en lämplig arbetsyta och nyckel konfigurerad i inställningarna för Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="7c140-170">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="7c140-171">När det har konfigurerats distribueras rätt molnhanteringspaket på datorn och sensorprocessen (MsSenseS.exe) distribueras och startas.</span><span class="sxs-lookup"><span data-stu-id="7c140-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="7c140-172">Det här krävs också om servern är konfigurerad att använda en OMS Gateway-server som proxy.</span><span class="sxs-lookup"><span data-stu-id="7c140-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="7c140-173">Alternativ 3: Introducera Windows-servrar via Microsoft Endpoint Manager version 2002 och senare</span><span class="sxs-lookup"><span data-stu-id="7c140-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="7c140-174">Du kan registrera Windows Server 2012 R2 och Windows Server 2016 med hjälp av Microsoft Endpoint Manager version 2002 och senare.</span><span class="sxs-lookup"><span data-stu-id="7c140-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="7c140-175">Mer information finns i [Microsoft Defender för Slutpunkt i Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="7c140-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="7c140-176">När du har slutfört introduktionsstegen måste du Konfigurera och uppdatera [Slutpunktsskydd-klienter i System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="7c140-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="7c140-177">Windows Server (SACK) version 1803, Windows Server 2019 och Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="7c140-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="7c140-178">Du kan registrera Windows Server (SACK) version 1803, Windows Server 2019 eller Windows Server 2019 Core Edition med hjälp av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="7c140-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="7c140-179">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="7c140-179">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="7c140-180">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="7c140-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="7c140-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7c140-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="7c140-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="7c140-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="7c140-183">VDI-onboardingskript för icke-beständiga enheter</span><span class="sxs-lookup"><span data-stu-id="7c140-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="7c140-184">Onboarding-paketet för Windows Server 2019 till Microsoft Endpoint Manager levereras för närvarande ett skript.</span><span class="sxs-lookup"><span data-stu-id="7c140-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="7c140-185">Mer information om hur du distribuerar skript i Configuration Manager finns i [Paket och program i Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="7c140-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="7c140-186">Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution.</span><span class="sxs-lookup"><span data-stu-id="7c140-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="7c140-187">För produktionsdistribution rekommenderar vi att du använder grupprinciper eller Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7c140-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="7c140-188">Stöd för Windows Server ger djupare insikter i serveraktiviteter, vad gäller kernel- och minnesattack och möjliggör svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="7c140-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="7c140-189">Konfigurera onboardinginställningar för Defender för slutpunkt på Windows-servern med samma verktyg och metoder för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="7c140-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="7c140-190">Mer information finns i Introducera [Windows 10-enheter.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="7c140-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="7c140-191">Om du kör en antimalwarelösning från tredje part måste du använda följande inställningar för Microsoft Defender AV-passivt läge.</span><span class="sxs-lookup"><span data-stu-id="7c140-191">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="7c140-192">Kontrollera att den har konfigurerats korrekt:</span><span class="sxs-lookup"><span data-stu-id="7c140-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="7c140-193">Ange följande registerpost:</span><span class="sxs-lookup"><span data-stu-id="7c140-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="7c140-194">Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="7c140-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="7c140-195">Namn: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="7c140-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="7c140-196">Typ: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7c140-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="7c140-197">Värde: 1</span><span class="sxs-lookup"><span data-stu-id="7c140-197">Value: 1</span></span>

    1. <span data-ttu-id="7c140-198">Kör följande PowerShell-kommando för att verifiera att det passiva läget har konfigurerats:</span><span class="sxs-lookup"><span data-stu-id="7c140-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="7c140-199">Bekräfta att en nyligen genomförd händelse som innehåller händelsen passiv form hittas:</span><span class="sxs-lookup"><span data-stu-id="7c140-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Bild på verifieringsresultatet av passivt läge](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="7c140-201">Kör följande kommando för att kontrollera om Microsoft Defender AV är installerat:</span><span class="sxs-lookup"><span data-stu-id="7c140-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="7c140-202">Om resultatet är "Den angivna tjänsten finns inte som en installerad tjänst" måste du installera Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="7c140-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="7c140-203">Mer information finns i [Microsoft Defender Antivirus i Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="7c140-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="7c140-204">Mer information om hur du använder grupprinciper för att konfigurera och hantera Microsoft Defender Antivirus på dina Windows-servrar finns i Använda grupprincipinställningar för att konfigurera och hantera [Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="7c140-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="7c140-205">Integrering med Azure Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="7c140-205">Integration with Azure Security Center</span></span>
<span data-ttu-id="7c140-206">Defender för Endpoint kan integreras med Azure Security Center för att tillhandahålla en omfattande lösning för Windows serverskydd.</span><span class="sxs-lookup"><span data-stu-id="7c140-206">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="7c140-207">Med den här integreringen kan Azure Säkerhetscenter använda kraften i Defender för Endpoint för att tillhandahålla förbättrad identifiering av hot för Windows-servrar.</span><span class="sxs-lookup"><span data-stu-id="7c140-207">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="7c140-208">Följande funktioner ingår i den här integreringen:</span><span class="sxs-lookup"><span data-stu-id="7c140-208">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="7c140-209">Automatisk onboarding – Defender för slutpunkts sensor aktiveras automatiskt på Windows-servrar som skickas till Azure Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="7c140-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="7c140-210">Mer information om onboarding av Azure Säkerhetscenter finns i [Onboarding till Azure Security Center Standard för förbättrad säkerhet.](https://docs.microsoft.com/azure/security-center/security-center-onboarding)</span><span class="sxs-lookup"><span data-stu-id="7c140-210">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c140-211">Integreringen mellan Azure Defender för servrar och Microsoft Defender för slutpunkt har utökats med stöd för [Windows Server 2019 och Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="7c140-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="7c140-212">Windows-servrar som övervakas av Azure Säkerhetscenter blir också tillgängliga i Defender för slutpunkt – Azure Säkerhetscenter ansluter smidigt till Defender för slutpunktsklientorganisationen, vilket ger en enda vy mellan klienter och servrar.</span><span class="sxs-lookup"><span data-stu-id="7c140-212">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="7c140-213">Dessutom är Defender för slutpunktsaviseringar tillgängliga i Azure Säkerhetscenter-konsolen.</span><span class="sxs-lookup"><span data-stu-id="7c140-213">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="7c140-214">Serverundersökning – Azure Säkerhetscenter-kunder kan använda Microsoft Defender Säkerhetscenter för att utföra detaljerad undersökning för att upptäcka omfattningen av en möjlig intrång.</span><span class="sxs-lookup"><span data-stu-id="7c140-214">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="7c140-215">När du använder Azure Säkerhetscenter för att övervaka servrar skapas automatiskt en Defender för slutpunktsklientorganisation (i USA för USA-användare i EU för europeiska och brittiska användare).</span><span class="sxs-lookup"><span data-stu-id="7c140-215">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="7c140-216">Data som samlas in av Defender för Endpoint lagras på klientorganisationens geoplats som identifieras under etableringen.</span><span class="sxs-lookup"><span data-stu-id="7c140-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="7c140-217">Om du använder Defender för slutpunkt innan du använder Azure Säkerhetscenter lagras dina data på den plats som du angav när du skapade klientorganisationen, även om du integrerar med Azure Säkerhetscenter vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="7c140-217">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="7c140-218">När den har konfigurerats kan du inte ändra platsen där dina data lagras.</span><span class="sxs-lookup"><span data-stu-id="7c140-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="7c140-219">Om du behöver flytta dina data till en annan plats måste du kontakta Microsoft Support för att återställa klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="7c140-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="7c140-220">Serverslutpunktsövervakning som använder den här integreringen har inaktiverats för Office 365 GCC-kunder.</span><span class="sxs-lookup"><span data-stu-id="7c140-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="7c140-221">Konfigurera och uppdatera System Center Endpoint Protection-klienter</span><span class="sxs-lookup"><span data-stu-id="7c140-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="7c140-222">Defender för Endpoint integreras med System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="7c140-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="7c140-223">Integreringen ger möjlighet till identifiering av skadlig programvara och för att stoppa spridningen av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7c140-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="7c140-224">Följande steg krävs för att aktivera den här integreringen:</span><span class="sxs-lookup"><span data-stu-id="7c140-224">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="7c140-225">Installera uppdateringen för plattformen för skydd mot skadlig programvara i januari [2017 för Endpoint Protection-klienter.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="7c140-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="7c140-226">[Konfigurera medlemskap i S FLERA-klientens Molnskyddstjänst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) till **inställningen** Avancerat.</span><span class="sxs-lookup"><span data-stu-id="7c140-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="7c140-227">Offboard Windows-servrar</span><span class="sxs-lookup"><span data-stu-id="7c140-227">Offboard Windows servers</span></span>
<span data-ttu-id="7c140-228">Du kan offboard Windows Server (SACK), Windows Server 2019 och Windows Server 2019 Core-versionen på samma sätt som för Windows 10-klientenheter.</span><span class="sxs-lookup"><span data-stu-id="7c140-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="7c140-229">För andra Versioner av Windows-servrar har du två alternativ för att ta bort Windows-servrar från tjänsten:</span><span class="sxs-lookup"><span data-stu-id="7c140-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="7c140-230">Avinstallera MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="7c140-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="7c140-231">Ta bort Defender för slutpunktsarbetsytans konfiguration</span><span class="sxs-lookup"><span data-stu-id="7c140-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="7c140-232">Offboarding gör att Windows-servern slutar skicka sensordata till portalen, men data från Windows-servern, inklusive referens till eventuella aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="7c140-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="7c140-233">Avinstallera Windows-servrar genom att avinstallera MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="7c140-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="7c140-234">Om du vill ta bort Windows-servern kan du avinstallera MMA-agenten från Windows-servern eller koppla från den från rapporteringen till Defender för slutpunkt-arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="7c140-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="7c140-235">Efter offboarding av agenten skickar Windows-servern inte längre sensordata till Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="7c140-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="7c140-236">Mer information finns i Inaktivera [en agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="7c140-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="7c140-237">Ta bort Defender för slutpunktsarbetsytans konfiguration</span><span class="sxs-lookup"><span data-stu-id="7c140-237">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="7c140-238">Om du vill ta bort Windows-servern från en annan dator kan du använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="7c140-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="7c140-239">Ta bort konfiguration av Defender för slutpunktsarbetsyta från MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="7c140-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="7c140-240">Köra ett PowerShell-kommando för att ta bort konfigurationen</span><span class="sxs-lookup"><span data-stu-id="7c140-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="7c140-241">Ta bort konfiguration av Defender för slutpunktsarbetsyta från MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="7c140-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="7c140-242">I egenskaperna **för Microsoft Monitoring Agent** väljer du fliken Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="7c140-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="7c140-243">Välj Defender för slutpunktsarbetsytan och klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="7c140-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Bild på egenskaper för Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="7c140-245">Köra ett PowerShell-kommando för att ta bort konfigurationen</span><span class="sxs-lookup"><span data-stu-id="7c140-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="7c140-246">Skaffa ditt arbetsyte-ID:</span><span class="sxs-lookup"><span data-stu-id="7c140-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="7c140-247">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="7c140-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="7c140-248">Välj **Windows Server 2008 R2 SP1, 2012 R2 och 2016** som operativsystem och få ditt Arbetsyte-ID:</span><span class="sxs-lookup"><span data-stu-id="7c140-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Bild på Onboarding för Windows-server](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="7c140-250">Öppna en PowerShell med förhöjd behörighet och kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="7c140-250">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="7c140-251">Använd det arbetsyte-ID du skaffade och `WorkspaceID` ersätter:</span><span class="sxs-lookup"><span data-stu-id="7c140-251">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="7c140-252">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7c140-252">Related topics</span></span>
- [<span data-ttu-id="7c140-253">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="7c140-253">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="7c140-254">Registrera icke-Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="7c140-254">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="7c140-255">Konfigurera inställningar för proxy- och Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="7c140-255">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="7c140-256">Köra ett identifieringstest på en nyligen onboarded Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="7c140-256">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="7c140-257">Felsökning av problem med introduktion till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="7c140-257">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
