---
title: Onboard-enheter utan internetanslutning till Microsoft Defender för Endpoint
ms.reviewer: ''
description: Onboard-enheter utan internetanslutning så att de kan skicka sensordata till Microsoft Defender ATP-sensorn
keywords: onboard, servers, VM, on-premise, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: daf766113baf6c7a9b0a4649afdae8f88dacfd41
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069163"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="83885-104">Onboard-enheter utan internetanslutning till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="83885-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83885-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="83885-105">**Applies to:**</span></span>
- [<span data-ttu-id="83885-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="83885-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="83885-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83885-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="83885-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="83885-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83885-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="83885-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="83885-110">Om du vill registrera enheter utan åtkomst till Internet måste du göra följande allmänna steg:</span><span class="sxs-lookup"><span data-stu-id="83885-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="83885-111">Stegen nedan gäller endast för enheter som kör tidigare versioner av Windows, till exempel: Windows Server 2016 och tidigare eller Windows 8.1 och tidigare.</span><span class="sxs-lookup"><span data-stu-id="83885-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="83885-112">En OMS-gatewayserver kan inte användas som proxy för frånkopplade Windows 10- eller Windows Server 2019-enheter när de konfigureras via registret 'TelemetryProxyServer' eller GPO.</span><span class="sxs-lookup"><span data-stu-id="83885-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="83885-113">För Windows 10 eller Windows Server 2019 – även om du använder telemetriproxyServer måste det peka på en vanlig proxyenhet eller enhet.</span><span class="sxs-lookup"><span data-stu-id="83885-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="83885-114">Dessutom måste Windows 10 eller Windows Server 2019 i frånkopplade miljöer kunna uppdatera certifikatförtroendelistor offline via en intern fil eller webbserver.</span><span class="sxs-lookup"><span data-stu-id="83885-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="83885-115">Mer information om hur du uppdaterar CTLs offline finns i [Konfigurera en fil eller webbserver för att ladda ned CTL-filer.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)</span><span class="sxs-lookup"><span data-stu-id="83885-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="83885-116">Mer information om onboarding-metoder finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="83885-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="83885-117">Introducera tidigare versioner av Windows</span><span class="sxs-lookup"><span data-stu-id="83885-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="83885-118">Onboard servers to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="83885-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="83885-119">Konfigurera enhetsproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="83885-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="83885-120">Lokala enheter</span><span class="sxs-lookup"><span data-stu-id="83885-120">On-premise devices</span></span>

- <span data-ttu-id="83885-121">Konfigurera Azure Log Analytics (hette tidigare OMS Gateway) som proxy eller hubb:</span><span class="sxs-lookup"><span data-stu-id="83885-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="83885-122">Azure Log Analytics-agent</span><span class="sxs-lookup"><span data-stu-id="83885-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="83885-123">[Installera och konfigurera MMA-pekaren på Defender för](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) slutpunktsarbetsytans nyckel &-ID</span><span class="sxs-lookup"><span data-stu-id="83885-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="83885-124">Offlineenheter i samma nätverk av Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="83885-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="83885-125">Konfigurera MMA så att det pekar på:</span><span class="sxs-lookup"><span data-stu-id="83885-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="83885-126">IP för Azure-logganalys som proxy</span><span class="sxs-lookup"><span data-stu-id="83885-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="83885-127">Nyckel för Defender för slutpunktsarbetsyta & ID</span><span class="sxs-lookup"><span data-stu-id="83885-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="83885-128">Virtuella Azure-datorer</span><span class="sxs-lookup"><span data-stu-id="83885-128">Azure virtual machines</span></span>
- <span data-ttu-id="83885-129">Konfigurera och aktivera [arbetsytan för Azure Logganalys](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="83885-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="83885-130">Konfigurera Azure Log Analytics Gateway (kallades tidigare OMS Gateway) som proxy eller nav:</span><span class="sxs-lookup"><span data-stu-id="83885-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="83885-131">Azure Log Analytics Gateway</span><span class="sxs-lookup"><span data-stu-id="83885-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="83885-132">[Installera och konfigurera MMA-pekaren på Defender för](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) slutpunktsarbetsytans nyckel &-ID</span><span class="sxs-lookup"><span data-stu-id="83885-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="83885-133">Offline-Azure VMs i samma nätverk av OMS Gateway</span><span class="sxs-lookup"><span data-stu-id="83885-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="83885-134">Konfigurera IP för Azure-logganalys som proxy</span><span class="sxs-lookup"><span data-stu-id="83885-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="83885-135">Nyckel för arbetsyta i Azure Log Analytics & ID</span><span class="sxs-lookup"><span data-stu-id="83885-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="83885-136">Azure Säkerhetscenter (ASC)</span><span class="sxs-lookup"><span data-stu-id="83885-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="83885-137">Arbetsytan \> Logganalys för säkerhetsprinciper</span><span class="sxs-lookup"><span data-stu-id="83885-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="83885-138">Tillåt identifiering \> av hot Låt Defender för Slutpunkt få åtkomst till mina data</span><span class="sxs-lookup"><span data-stu-id="83885-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="83885-139">Mer information finns i [Arbeta med säkerhetsprinciper.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="83885-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>