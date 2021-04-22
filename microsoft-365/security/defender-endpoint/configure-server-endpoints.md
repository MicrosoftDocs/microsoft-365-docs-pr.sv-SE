---
title: Introducera Windows-servrar till Microsoft Defender för slutpunktstjänsten
description: Introducera Windows-servrarna så att de kan skicka sensordata till Microsoft Defender för slutpunkts sensoren.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
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
ms.openlocfilehash: 4eea2931196c192620812c1609c506e1fb99093d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932959"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4e96d-104">Introducera Windows-servrar till Microsoft Defender för slutpunktstjänsten</span><span class="sxs-lookup"><span data-stu-id="4e96d-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4e96d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4e96d-105">**Applies to:**</span></span>

- <span data-ttu-id="4e96d-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="4e96d-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="4e96d-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4e96d-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="4e96d-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4e96d-108">Windows Server 2016</span></span>
- <span data-ttu-id="4e96d-109">Windows Server (SACK) version 1803 och senare</span><span class="sxs-lookup"><span data-stu-id="4e96d-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="4e96d-110">Windows Server 2019 och senare</span><span class="sxs-lookup"><span data-stu-id="4e96d-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="4e96d-111">Kärnversionen av Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4e96d-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="4e96d-112">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="4e96d-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e96d-113">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="4e96d-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="4e96d-114">Defender för Endpoint utökar stödet till att även omfatta Windows Server-operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="4e96d-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="4e96d-115">Det här stödet ger avancerade funktioner för identifiering och undersökning av angrepp via microsoft Defender Säkerhetscenter-konsolen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="4e96d-116">Praktiska anvisningar om vad som måste finnas för licensiering och infrastruktur finns i Skydda [Windows-servrar med Defender för slutpunkt.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="4e96d-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="4e96d-117">Information om hur du laddar ned och använder Windows-säkerhetsbaslinjer för Windows-servrar finns i [Baslinjer för Windows-säkerhet.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="4e96d-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="4e96d-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 och Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4e96d-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="4e96d-119">Du kan registrera Windows Server 2008 R2 SP1, Windows Server 2012 R2 och Windows Server 2016 till Defender för slutpunkt genom att använda något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="4e96d-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="4e96d-120">**Alternativ 1:** [Få igång genom att installera och konfigurera Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="4e96d-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="4e96d-121">**Alternativ 2:** [Hantera via Azure Säkerhetscenter](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="4e96d-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="4e96d-122">**Alternativ 3:** [Introduktion till Microsoft Endpoint Manager version 2002 och senare](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="4e96d-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="4e96d-123">När du har slutfört introduktionsstegen med något av de angivna alternativen måste du Konfigurera och uppdatera [System Center Endpoint Protection-klienter.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="4e96d-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="4e96d-124">Defender för fristående slutpunkt för serverlicens krävs per nod, för att kunna introducera en Windows-server via Microsoft Monitoring Agent (alternativ 1) eller via Microsoft Endpoint Manager (Alternativ 3).</span><span class="sxs-lookup"><span data-stu-id="4e96d-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="4e96d-125">Du kan också behöva en Azure Defender för servrar-licens per nod för att kunna hantera en Windows-server via Azure Security Center (alternativ 2) i Funktioner som stöds i [Azure Defender.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="4e96d-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="4e96d-126">Alternativ 1: Registrera dig genom att installera och konfigurera Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="4e96d-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="4e96d-127">Du måste installera och konfigurera MMA för Windows-servrar för att rapportera sensordata till Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="4e96d-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="4e96d-128">Mer information finns i Samla [in loggdata med Azure Log Analytics-agenten.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="4e96d-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="4e96d-129">Om du redan använder System Center Operations Manager (SCOM) eller Azure Monitor (tidigare kallat Operations Management Suite (OMS)) kan du koppla Microsoft Monitoring Agent (MMA) till din Defender för slutpunkt-arbetsyta via Stöd för Multihoming.</span><span class="sxs-lookup"><span data-stu-id="4e96d-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="4e96d-130">I allmänhet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="4e96d-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="4e96d-131">Uppfylla kraven för introduktion som beskrivs i **avsnittet Innan du börjar.**</span><span class="sxs-lookup"><span data-stu-id="4e96d-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="4e96d-132">Aktivera serverövervakning från Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="4e96d-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="4e96d-133">Installera och konfigurera MMA för servern för att rapportera sensordata till Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="4e96d-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="4e96d-134">Konfigurera och uppdatera System Center Endpoint Protection-klienter.</span><span class="sxs-lookup"><span data-stu-id="4e96d-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="4e96d-135">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att den är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4e96d-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="4e96d-136">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunktsslutpunkt.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="4e96d-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="4e96d-137">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="4e96d-137">Before you begin</span></span>

<span data-ttu-id="4e96d-138">Utför följande steg för att uppfylla kraven för registrering:</span><span class="sxs-lookup"><span data-stu-id="4e96d-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="4e96d-139">För Windows Server 2008 R2 SP1 eller Windows Server 2012 R2 bör du installera följande snabbkorrigering:</span><span class="sxs-lookup"><span data-stu-id="4e96d-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="4e96d-140">Uppdatering för kundupplevelse och diagnostisk telemetri</span><span class="sxs-lookup"><span data-stu-id="4e96d-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="4e96d-141">För Windows Server 2008 R2 SP1: se till att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="4e96d-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="4e96d-142">Installera den [månatliga uppdateringen för februari](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="4e96d-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="4e96d-143">Installera [antingen .NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) eller [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="4e96d-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e96d-144">Om du hanterar Windows Server 2008 R2 SP1 med SCCM installerar SCCM-klientagenten .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="4e96d-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="4e96d-145">Du behöver därför inte installera .NET Framework 4.5 (eller senare).</span><span class="sxs-lookup"><span data-stu-id="4e96d-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="4e96d-146">För Windows Server 2008 R2 SP1 och Windows Server 2012 R2: Konfigurera och uppdatera [slutpunktsskyddsklienter för System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="4e96d-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="4e96d-147">Det här steget krävs bara om din organisation använder System Center Endpoint Protection (SFÖNSTER) och du använder Windows Server 2008 R2 SP1 och Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="4e96d-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="4e96d-148">Installera och konfigurera MMA (Microsoft Monitoring Agent) för att rapportera sensordata till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="4e96d-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="4e96d-149">Ladda ned installationsfilen för agenten: [Windows 64-bitars agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="4e96d-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="4e96d-150">Med nyckeln arbetsyte-ID och arbetsyta som hämtas i föregående procedur väljer du någon av följande installationsmetoder för att installera agenten på Windows-servern:</span><span class="sxs-lookup"><span data-stu-id="4e96d-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="4e96d-151">[Installera agenten manuellt med hjälp av konfigurationen](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="4e96d-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="4e96d-152">På sidan **Alternativ för konfiguration av** agent väljer du Anslut **agenten till Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="4e96d-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="4e96d-153">[Installera agenten med kommandoraden](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="4e96d-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="4e96d-154">[Konfigurera agenten med hjälp av ett skript](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="4e96d-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="4e96d-155">Om du [](gov.md)är myndighetskund i USA måste du under "Azure Cloud" välja "Azure US Government" om du använder installationsguiden, eller om du använder en kommandorad eller ett skript – ange parametern "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" till 1.</span><span class="sxs-lookup"><span data-stu-id="4e96d-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="4e96d-156">Konfigurera Windows-serverproxy och internetanslutningsinställningar vid behov</span><span class="sxs-lookup"><span data-stu-id="4e96d-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="4e96d-157">Om dina servrar behöver använda en proxyserver för att kommunicera med Defender för Slutpunkt använder du någon av följande metoder för att konfigurera MMA att använda proxyservern:</span><span class="sxs-lookup"><span data-stu-id="4e96d-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="4e96d-158">Konfigurera MMA att använda en proxyserver</span><span class="sxs-lookup"><span data-stu-id="4e96d-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="4e96d-159">Konfigurera Windows till att använda en proxyserver för alla anslutningar</span><span class="sxs-lookup"><span data-stu-id="4e96d-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="4e96d-160">Om en proxy eller brandvägg används ska du se till att servrar kan komma åt alla URL-adresser för Microsoft Defender för Endpoint-tjänsten direkt och utan SSL-avlyssning.</span><span class="sxs-lookup"><span data-stu-id="4e96d-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="4e96d-161">Mer information finns i aktivera [åtkomst till Defender för slutpunktstjänst-URL:er.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="4e96d-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="4e96d-162">Användning av SSL-avlyssning förhindrar att systemet kommunicerar med Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4e96d-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="4e96d-163">När den är klar bör du se de onboarded Windows-servrarna i portalen inom en timme.</span><span class="sxs-lookup"><span data-stu-id="4e96d-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="4e96d-164">Alternativ 2: Hantera Windows-servrar via Azure Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="4e96d-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="4e96d-165">I navigeringsfönstret för Microsoft Defender Säkerhetscenter väljer du **Inställningar Registrering**  >  **av**  >  **enhetshantering**.</span><span class="sxs-lookup"><span data-stu-id="4e96d-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="4e96d-166">Välj **Windows Server 2008 R2 SP1, 2012 R2 och 2016** som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="4e96d-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="4e96d-167">Klicka **på Onboard Servers i Azure Security Center.**</span><span class="sxs-lookup"><span data-stu-id="4e96d-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="4e96d-168">Följ introduktionsanvisningarna i [Microsoft Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) för Endpoint med Azure Defender och Om du använder Azure ARC följer du introduktionsanvisningarna i Aktivera Microsoft Defender för [slutpunktsintegrering.](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)</span><span class="sxs-lookup"><span data-stu-id="4e96d-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="4e96d-169">När du har slutfört introduktionsstegen måste du Konfigurera och uppdatera [Slutpunktsskydd-klienter i System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="4e96d-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="4e96d-170">För att onboarding via Azure Defender for Servers ska fungera som förväntat måste servern ha en lämplig arbetsyta och nyckel konfigurerad i inställningarna för Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="4e96d-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="4e96d-171">När det har konfigurerats distribueras rätt molnhanteringspaket på datorn och sensorprocessen (MsSenseS.exe) distribueras och startas.</span><span class="sxs-lookup"><span data-stu-id="4e96d-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="4e96d-172">Det här krävs också om servern är konfigurerad att använda en OMS Gateway-server som proxy.</span><span class="sxs-lookup"><span data-stu-id="4e96d-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="4e96d-173">Alternativ 3: Introducera Windows-servrar via Microsoft Endpoint Manager version 2002 och senare</span><span class="sxs-lookup"><span data-stu-id="4e96d-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="4e96d-174">Du kan registrera Windows Server 2012 R2 och Windows Server 2016 med hjälp av Microsoft Endpoint Manager version 2002 och senare.</span><span class="sxs-lookup"><span data-stu-id="4e96d-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="4e96d-175">Mer information finns i [Microsoft Defender för Slutpunkt i Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="4e96d-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="4e96d-176">När du har slutfört introduktionsstegen måste du Konfigurera och uppdatera [Slutpunktsskydd-klienter i System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="4e96d-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="4e96d-177">Windows Server (SACK) version 1803, Windows Server 2019 och Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="4e96d-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="4e96d-178">Du kan registrera Windows Server (SACK) version 1803, Windows Server 2019 eller Windows Server 2019 Core Edition med hjälp av följande distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="4e96d-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="4e96d-179">Lokalt skript</span><span class="sxs-lookup"><span data-stu-id="4e96d-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="4e96d-180">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="4e96d-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="4e96d-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e96d-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="4e96d-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="4e96d-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="4e96d-183">VDI-onboardingskript för icke-beständiga enheter</span><span class="sxs-lookup"><span data-stu-id="4e96d-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="4e96d-184">Onboarding-paketet för Windows Server 2019 till Microsoft Endpoint Manager levereras för närvarande ett skript.</span><span class="sxs-lookup"><span data-stu-id="4e96d-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="4e96d-185">Mer information om hur du distribuerar skript i Configuration Manager finns i [Paket och program i Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="4e96d-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="4e96d-186">Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution.</span><span class="sxs-lookup"><span data-stu-id="4e96d-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="4e96d-187">För produktionsdistribution rekommenderar vi att du använder grupprinciper eller Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4e96d-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="4e96d-188">Stöd för Windows Server ger djupare insikter i serveraktiviteter, vad gäller kernel- och minnesattack och möjliggör svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4e96d-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="4e96d-189">Konfigurera onboardinginställningar för Defender för slutpunkt på Windows-servern med samma verktyg och metoder för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="4e96d-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="4e96d-190">Mer information finns i Introducera [Windows 10-enheter.](configure-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="4e96d-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="4e96d-191">Om du kör en lösning mot skadlig programvara från tredje part måste du använda följande inställningar för Microsoft Defender AV-passivt läge.</span><span class="sxs-lookup"><span data-stu-id="4e96d-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="4e96d-192">Kontrollera att den har konfigurerats korrekt:</span><span class="sxs-lookup"><span data-stu-id="4e96d-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="4e96d-193">Ange följande registerpost:</span><span class="sxs-lookup"><span data-stu-id="4e96d-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="4e96d-194">Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="4e96d-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="4e96d-195">Namn: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="4e96d-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="4e96d-196">Typ: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="4e96d-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="4e96d-197">Värde: 1</span><span class="sxs-lookup"><span data-stu-id="4e96d-197">Value: 1</span></span>

    1. <span data-ttu-id="4e96d-198">Kör följande PowerShell-kommando för att verifiera att det passiva läget har konfigurerats:</span><span class="sxs-lookup"><span data-stu-id="4e96d-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="4e96d-199">Bekräfta att en nyligen genomförd händelse som innehåller händelsen passiv form hittas:</span><span class="sxs-lookup"><span data-stu-id="4e96d-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Bild på verifieringsresultatet av passivt läge](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="4e96d-201">Kör följande kommando för att kontrollera om Microsoft Defender AV är installerat:</span><span class="sxs-lookup"><span data-stu-id="4e96d-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="4e96d-202">Om resultatet är "Den angivna tjänsten finns inte som en installerad tjänst" måste du installera Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="4e96d-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="4e96d-203">Mer information finns i [Microsoft Defender Antivirus i Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="4e96d-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="4e96d-204">Mer information om hur du använder grupprinciper för att konfigurera och hantera Microsoft Defender Antivirus på dina Windows-servrar finns i Använda grupprincipinställningar för att konfigurera och hantera [Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="4e96d-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="4e96d-205">Integrering med Azure Defender</span><span class="sxs-lookup"><span data-stu-id="4e96d-205">Integration with Azure Defender</span></span>

<span data-ttu-id="4e96d-206">Defender för Endpoint kan integreras med Azure Defender för att tillhandahålla en omfattande lösning för Windows-serverskydd.</span><span class="sxs-lookup"><span data-stu-id="4e96d-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="4e96d-207">Med den här integreringen kan Azure Defender använda kraften i Defender för Slutpunkt för att tillhandahålla förbättrad identifiering av hot för Windows-servrar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="4e96d-208">Följande funktioner ingår i den här integreringen:</span><span class="sxs-lookup"><span data-stu-id="4e96d-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="4e96d-209">Automatisk onboarding – Defender för slutpunkts sensor aktiveras automatiskt på Windows-servrar som är onboarded to Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="4e96d-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="4e96d-210">Mer information om Azure Defender-registrering finns i [Onboarding till Azure Defender Standard för förbättrad säkerhet.](https://docs.microsoft.com/azure/security-center/security-center-onboarding)</span><span class="sxs-lookup"><span data-stu-id="4e96d-210">For more information on Azure Defender onboarding, see [Onboarding to Azure Defender Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e96d-211">Integreringen mellan Azure Defender för servrar och Microsoft Defender för slutpunkt har utökats med stöd för [Windows Server 2019 och Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="4e96d-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="4e96d-212">Windows-servrar som övervakas av Azure Defender blir också tillgängliga i Defender för slutpunkt – Azure Defender ansluter sömlöst till Defender för slutpunktsklientorganisationen, vilket ger en enda vy över alla klienter och servrar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="4e96d-213">Dessutom är Defender för slutpunktsaviseringar tillgängliga i Azure Defender-konsolen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="4e96d-214">Serverundersökning – Azure Defender-kunder kan få åtkomst till Microsoft Defender Säkerhetscenter för att utföra detaljerad undersökning för att ta reda på omfattningen av en möjlig överträdelse.</span><span class="sxs-lookup"><span data-stu-id="4e96d-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="4e96d-215">När du använder Azure Defender för att övervaka servrar skapas automatiskt en Defender för slutpunktsklientorganisation (i USA för USA-användare i EU för europeiska och brittiska användare).</span><span class="sxs-lookup"><span data-stu-id="4e96d-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="4e96d-216">Data som samlas in av Defender för Endpoint lagras på klientorganisationens geoplats som identifieras under etableringen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="4e96d-217">Om du använder Defender för slutpunkt innan du använder Azure Defender lagras dina data på den plats som du angav när du skapade klientorganisationen, även om du integrerar med Azure Defender vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="4e96d-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="4e96d-218">När den har konfigurerats kan du inte ändra platsen där dina data lagras.</span><span class="sxs-lookup"><span data-stu-id="4e96d-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="4e96d-219">Om du behöver flytta dina data till en annan plats måste du kontakta Microsoft Support för att återställa klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="4e96d-220">Serverslutpunktsövervakning som använder den här integreringen har inaktiverats för Office 365 GCC-kunder.</span><span class="sxs-lookup"><span data-stu-id="4e96d-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="4e96d-221">Konfigurera och uppdatera System Center Endpoint Protection-klienter</span><span class="sxs-lookup"><span data-stu-id="4e96d-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="4e96d-222">Defender för Endpoint integreras med System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="4e96d-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="4e96d-223">Integreringen ger möjlighet till identifiering av skadlig programvara och för att stoppa spridningen av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4e96d-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="4e96d-224">Följande steg krävs för att aktivera den här integreringen:</span><span class="sxs-lookup"><span data-stu-id="4e96d-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="4e96d-225">Installera uppdateringen för plattformen för skydd mot skadlig programvara i januari [2017 för Endpoint Protection-klienter.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="4e96d-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="4e96d-226">[Konfigurera medlemskap i S FLERA-klientens Molnskyddstjänst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) till **inställningen** Avancerat.</span><span class="sxs-lookup"><span data-stu-id="4e96d-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="4e96d-227">Offboard Windows-servrar</span><span class="sxs-lookup"><span data-stu-id="4e96d-227">Offboard Windows servers</span></span>

<span data-ttu-id="4e96d-228">Du kan offboard Windows Server (SACK), Windows Server 2019 och Windows Server 2019 Core-versionen på samma sätt som för Windows 10-klientenheter.</span><span class="sxs-lookup"><span data-stu-id="4e96d-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="4e96d-229">För andra Versioner av Windows-servrar har du två alternativ för att ta bort Windows-servrar från tjänsten:</span><span class="sxs-lookup"><span data-stu-id="4e96d-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="4e96d-230">Avinstallera MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="4e96d-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="4e96d-231">Ta bort Defender för slutpunktsarbetsytans konfiguration</span><span class="sxs-lookup"><span data-stu-id="4e96d-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="4e96d-232">Offboarding gör att Windows-servern slutar skicka sensordata till portalen, men data från Windows-servern, inklusive referens till eventuella aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="4e96d-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="4e96d-233">Avinstallera Windows-servrar genom att avinstallera MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="4e96d-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="4e96d-234">Om du vill ta bort Windows-servern kan du avinstallera MMA-agenten från Windows-servern eller koppla från den från rapporteringen till Defender för slutpunkt-arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="4e96d-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="4e96d-235">Efter offboarding av agenten skickar Windows-servern inte längre sensordata till Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="4e96d-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="4e96d-236">Mer information finns i Inaktivera [en agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="4e96d-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="4e96d-237">Ta bort Defender för slutpunktsarbetsytans konfiguration</span><span class="sxs-lookup"><span data-stu-id="4e96d-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="4e96d-238">Om du vill ta bort Windows-servern från en annan dator kan du använda någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="4e96d-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="4e96d-239">Ta bort konfiguration av Defender för slutpunktsarbetsyta från MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="4e96d-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="4e96d-240">Köra ett PowerShell-kommando för att ta bort konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4e96d-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="4e96d-241">Ta bort konfiguration av Defender för slutpunktsarbetsyta från MMA-agenten</span><span class="sxs-lookup"><span data-stu-id="4e96d-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="4e96d-242">I egenskaperna **för Microsoft Monitoring Agent** väljer du fliken Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="4e96d-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="4e96d-243">Välj Defender för slutpunktsarbetsytan och klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="4e96d-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Bild på egenskaper för Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="4e96d-245">Köra ett PowerShell-kommando för att ta bort konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4e96d-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="4e96d-246">Skaffa ditt arbetsyte-ID:</span><span class="sxs-lookup"><span data-stu-id="4e96d-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="4e96d-247">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="4e96d-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="4e96d-248">Välj **Windows Server 2008 R2 SP1, 2012 R2 och 2016** som operativsystem och få ditt Arbetsyte-ID:</span><span class="sxs-lookup"><span data-stu-id="4e96d-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Bild på Onboarding för Windows-server](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="4e96d-250&quot;>Öppna en PowerShell med förhöjd behörighet och kör följande kommando.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;4e96d-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;4e96d-251&quot;>Använd det arbetsyte-ID du skaffade och `WorkspaceID` ersätter:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;4e96d-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="4e96d-252">Onboarding Servers utan hanteringslösning</span><span class="sxs-lookup"><span data-stu-id="4e96d-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="4e96d-253">Använda grupprinciper</span><span class="sxs-lookup"><span data-stu-id="4e96d-253">Using Group Policy</span></span>

<span data-ttu-id="4e96d-254">**Steg 1: Skapa de filer som behövs för att kopiera till servrarna.**</span><span class="sxs-lookup"><span data-stu-id="4e96d-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="4e96d-255">Gå till c:\windows\sysvol\domain\scripts (du kan behöva ändra kontrollen på en av domänkontrollanterna.)</span><span class="sxs-lookup"><span data-stu-id="4e96d-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="4e96d-256">Skapa en mapp med namnet MMA.</span><span class="sxs-lookup"><span data-stu-id="4e96d-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="4e96d-257">Ladda ned följande och placera den i MMA-mappen:</span><span class="sxs-lookup"><span data-stu-id="4e96d-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="4e96d-258">**Uppdatering för kundupplevelse och diagnostisk telemetri (Windows Server 2008 R2 och Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="4e96d-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="4e96d-259">För Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="4e96d-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="4e96d-260">För Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="4e96d-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="4e96d-261">Den här artikeln förutsätter att du använder x64-baserade servrar (MMA-agent .exe x64 [Ny SHA-2-kompatibel version](https://go.microsoft.com/fwlink/?LinkId=828603))</span><span class="sxs-lookup"><span data-stu-id="4e96d-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="4e96d-262">**Steg-2: Skapa ett filnamn DeployMMA.cmd (med anteckningar)** Lägg till följande rader i cmd-filen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="4e96d-263">Observera att du behöver ditt ARBETSYTE-ID och en NYCKEL.</span><span class="sxs-lookup"><span data-stu-id="4e96d-263">Note that you will need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="4e96d-264">Grupprincipkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4e96d-264">Group Policy Configuration</span></span>

<span data-ttu-id="4e96d-265">Skapa en ny grupprincip specifikt för onboarding-enheter, till exempel "Microsoft Defender för slutpunkts onboarding".</span><span class="sxs-lookup"><span data-stu-id="4e96d-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="4e96d-266">Skapa en grupprincipmapp med namnet "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="4e96d-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="mappar":::

    <span data-ttu-id="4e96d-268">**Då sparas en ny mapp på varje server där GPO:t tillämpas, en så kallad MMA-mapp, som lagras i c:\windows. Det här innehåller installationsfilerna för MMA, krav och installationsskript.**</span><span class="sxs-lookup"><span data-stu-id="4e96d-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="4e96d-269">Skapa en inställning för grupprincipfiler för var och en av de filer som lagras i Net-inloggningen.</span><span class="sxs-lookup"><span data-stu-id="4e96d-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="grupprincipbild1":::

<span data-ttu-id="4e96d-271">Filerna kopieras från DOMÄN\NETLOGON\MMA\filnamn till C:\windows\MMA\filnamn – så installationsfilerna är lokala **för servern:**</span><span class="sxs-lookup"><span data-stu-id="4e96d-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="distribuera mma cmd":::

<span data-ttu-id="4e96d-273">För de två KBs (en för Windows Server 2008R2/Windows 7 och en annan för Windows Server 2012 R2) upprepar du processen men skapar objektnivåanpassning på fliken COMMON, så filen kopieras bara till lämplig plattform/operativsystem-version i omfattning:</span><span class="sxs-lookup"><span data-stu-id="4e96d-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="målredigeraren":::

- <span data-ttu-id="4e96d-275">För Windows Server 2008 R2 behöver du (och den kopieras bara nedåt) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="4e96d-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="4e96d-276">För Windows Server 2012 R2 behöver du (och den kopieras bara nedåt) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="4e96d-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="4e96d-277">När det är klart måste du skapa en princip för startskript:</span><span class="sxs-lookup"><span data-stu-id="4e96d-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="startegenskaper":::

<span data-ttu-id="4e96d-279">Namnet på filen som ska köras här är c:\windows\MMA\DeployMMA.cmd När servern startas om som en del av startprocessen installeras uppdatering för kundupplevelse och diagnostisk telemetri KB, och SEDAN installera MMAAgent, samtidigt som du anger arbetsyte-ID och -nyckel, så tas servern med.</span><span class="sxs-lookup"><span data-stu-id="4e96d-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMAAgent, while setting the workspace id and key, and the server will be onboarded.</span></span>

<span data-ttu-id="4e96d-280">Du kan också använda en **omedelbar uppgift** för att köra distribueraMMA.cmd om du inte vill starta om alla servrar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-280">You could also use an **immediate task** to run the deployMMA.cmd if you do not want to reboot all the servers.</span></span>
<span data-ttu-id="4e96d-281">Det kan du göra i två faser.</span><span class="sxs-lookup"><span data-stu-id="4e96d-281">This could be done in two phases.</span></span> <span data-ttu-id="4e96d-282">Skapa först **filerna och** mappen i GPO – Se till att GPO:t tillämpas och att alla servrar har installationsfilerna.</span><span class="sxs-lookup"><span data-stu-id="4e96d-282">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="4e96d-283">Lägg sedan till den direkta uppgiften.</span><span class="sxs-lookup"><span data-stu-id="4e96d-283">Then, add the immediate task.</span></span> <span data-ttu-id="4e96d-284">Det här uppnår samma resultat utan att behöva starta om datorn.</span><span class="sxs-lookup"><span data-stu-id="4e96d-284">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="4e96d-285">Eftersom skriptet har en utgångsmetod och inte körs på nytt om MMA är installerat, kan du också använda en daglig schemalagd aktivitet för att uppnå samma resultat.</span><span class="sxs-lookup"><span data-stu-id="4e96d-285">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="4e96d-286">Liknar en konfigurationshanterarens efterlevnadsprincip som den kontrollerar dagligen för att säkerställa att MMA finns.</span><span class="sxs-lookup"><span data-stu-id="4e96d-286">Similar to an Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="schemalägg aktivitet":::

:::image type="content" source="images/newtaskprops.png" alt-text="nya aktivitetsegenskaper":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="distribuera mma nedladdnings-props":::

:::image type="content" source="images/tasksch.png" alt-text="schemaläggaren":::

<span data-ttu-id="4e96d-291">Som nämns i dokumentationen för onboarding för Server specifikt kring Server 2008 R2 kan du se nedan:</span><span class="sxs-lookup"><span data-stu-id="4e96d-291">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="4e96d-292">För Windows Server 2008 R2 PS1: se till att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="4e96d-292">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="4e96d-293">Installera den [månatliga uppdateringen för februari 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="4e96d-293">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="4e96d-294">Installera [antingen .NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (eller senare) eller [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="4e96d-294">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="4e96d-295">Kontrollera vilka KB som finns innan du börjar använda Windows Server 2008 R2 Den här processen gör att du kan hantera alla servrar om du inte har Configuration Manager som hanterar servrar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-295">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e96d-296">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4e96d-296">Related topics</span></span>

- [<span data-ttu-id="4e96d-297">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="4e96d-297">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="4e96d-298">Registrera icke-Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="4e96d-298">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="4e96d-299">Konfigurera inställningar för proxy- och Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="4e96d-299">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="4e96d-300">Köra ett identifieringstest på en nyligen onboarded Defender för Endpoint-enhet</span><span class="sxs-lookup"><span data-stu-id="4e96d-300">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="4e96d-301">Felsökning av problem med introduktion till Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="4e96d-301">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
