---
title: Minimikraven för Microsoft Defender för Slutpunkt
description: Förstå licenskraven och kraven för onboarding-enheter för tjänsten
keywords: minimikrav, licensiering, jämförelsetabell
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
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069434"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="f55c3-104">Minimikraven för Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f55c3-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f55c3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="f55c3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f55c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f55c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f55c3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f55c3-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f55c3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f55c3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f55c3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f55c3-110">Det finns några minimikrav för onboarding-enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f55c3-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="f55c3-111">Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att hantera enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f55c3-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="f55c3-112">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f55c3-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="f55c3-113">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="f55c3-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="f55c3-114">Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Defender för Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="f55c3-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="f55c3-115">Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="f55c3-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="f55c3-116">Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="f55c3-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f55c3-117">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="f55c3-117">Licensing requirements</span></span>
<span data-ttu-id="f55c3-118">Microsoft Defender för Endpoint kräver något av följande volymlicensieringserbjudanden från Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f55c3-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="f55c3-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="f55c3-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="f55c3-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="f55c3-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="f55c3-121">Microsoft 365 E5 (M365 E5) som inkluderar Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="f55c3-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="f55c3-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="f55c3-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="f55c3-123">Microsoft 365 E5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="f55c3-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="f55c3-124">Microsoft 365 A5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="f55c3-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="f55c3-125">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f55c3-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-126">Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.</span><span class="sxs-lookup"><span data-stu-id="f55c3-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="f55c3-127">Microsoft Defender för Endpoint kan också köpas från en leverantör av molnlösningar (CSP).</span><span class="sxs-lookup"><span data-stu-id="f55c3-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="f55c3-128">Microsoft Defender för slutpunkt för servrar kräver något av följande licensalternativ:</span><span class="sxs-lookup"><span data-stu-id="f55c3-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="f55c3-129">Azure Säkerhetscenter med Azure Defender aktiverat</span><span class="sxs-lookup"><span data-stu-id="f55c3-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="f55c3-130">Microsoft Defender för slutpunkt för server (en per server som omfattas)</span><span class="sxs-lookup"><span data-stu-id="f55c3-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-131">Kunder kan skaffa serverlicenser (en per operativsystemmiljö för servrar (OSE)) för Microsoft Defender för Endpoint för servrar om de har kombinerat minst 50 licenser för en eller flera av följande användarlicenser:</span><span class="sxs-lookup"><span data-stu-id="f55c3-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="f55c3-132">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f55c3-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="f55c3-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="f55c3-133">Windows E5/A5</span></span>
> * <span data-ttu-id="f55c3-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="f55c3-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="f55c3-135">Microsoft 365 E5/A5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="f55c3-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="f55c3-136">Detaljerad licensinformation finns på webbplatsen [med produktvillkor och du](https://www.microsoft.com/licensing/terms/) kan arbeta med ditt kontoteam för att få mer information om villkoren.</span><span class="sxs-lookup"><span data-stu-id="f55c3-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="f55c3-137">Mer information om de många olika funktionerna i Windows 10-versioner finns i [Jämför Windows 10-utgåvor.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="f55c3-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="f55c3-138">En detaljerad jämförelsetabell för den kommersiella jämförelsen av Windows 10-versioner finns i [JÄMFÖRELSEn AV PDF-format.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="f55c3-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="f55c3-139">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="f55c3-139">Browser requirements</span></span>
<span data-ttu-id="f55c3-140">Åtkomst till Defender för Slutpunkt görs via en webbläsare med stöd för följande webbläsare:</span><span class="sxs-lookup"><span data-stu-id="f55c3-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="f55c3-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f55c3-141">Microsoft Edge</span></span>
- <span data-ttu-id="f55c3-142">Internet Explorer version 11</span><span class="sxs-lookup"><span data-stu-id="f55c3-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="f55c3-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="f55c3-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-144">Andra webbläsare kanske fungerar, men de nämnda webbläsarna är de som stöds.</span><span class="sxs-lookup"><span data-stu-id="f55c3-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="f55c3-145">Maskin- och programvarukrav</span><span class="sxs-lookup"><span data-stu-id="f55c3-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="f55c3-146">Windows-versioner som stöds</span><span class="sxs-lookup"><span data-stu-id="f55c3-146">Supported Windows versions</span></span>
- <span data-ttu-id="f55c3-147">Windows 7 SP1 Enterprise[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="f55c3-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="f55c3-148">Windows 7 SP1 Pro[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="f55c3-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="f55c3-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f55c3-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="f55c3-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="f55c3-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="f55c3-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f55c3-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="f55c3-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="f55c3-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="f55c3-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="f55c3-153">Windows 10 Education</span></span>
- <span data-ttu-id="f55c3-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="f55c3-154">Windows 10 Pro</span></span>
- <span data-ttu-id="f55c3-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="f55c3-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="f55c3-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="f55c3-156">Windows server</span></span>
  - <span data-ttu-id="f55c3-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f55c3-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="f55c3-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f55c3-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="f55c3-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f55c3-159">Windows Server 2016</span></span>
  - <span data-ttu-id="f55c3-160">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="f55c3-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="f55c3-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f55c3-161">Windows Server 2019</span></span>
- <span data-ttu-id="f55c3-162">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="f55c3-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="f55c3-163">Enheter i nätverket måste köras på någon av dessa versioner.</span><span class="sxs-lookup"><span data-stu-id="f55c3-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="f55c3-164">Maskinvarukraven för Defender för Endpoint på enheter är samma för de versioner som stöds.</span><span class="sxs-lookup"><span data-stu-id="f55c3-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-165">Datorer som kör mobila versioner av Windows (till exempel Windows CE och Windows 10 Mobile) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="f55c3-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="f55c3-166">Virtuella datorer med Windows 10 Enterprise 2016 LTSB kan stöta på prestandaproblem om de körs på virtualiseringsplattformar som inte är microsoft.</span><span class="sxs-lookup"><span data-stu-id="f55c3-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="f55c3-167">För virtuella miljöer rekommenderar vi att du använder Windows 10 Enterprise LTSC 2019 eller senare.</span><span class="sxs-lookup"><span data-stu-id="f55c3-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="f55c3-168">Andra operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="f55c3-168">Other supported operating systems</span></span>
- <span data-ttu-id="f55c3-169">Android</span><span class="sxs-lookup"><span data-stu-id="f55c3-169">Android</span></span>
- <span data-ttu-id="f55c3-170">Linux</span><span class="sxs-lookup"><span data-stu-id="f55c3-170">Linux</span></span>
- <span data-ttu-id="f55c3-171">macOS</span><span class="sxs-lookup"><span data-stu-id="f55c3-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-172">Du måste känna till exakt vilka Linux-distributioner och versioner av Android och macOS som är kompatibla med Defender för Endpoint för att integreringen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="f55c3-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="f55c3-173">Krav för nätverks- och datalagring och konfiguration</span><span class="sxs-lookup"><span data-stu-id="f55c3-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="f55c3-174">När du kör onboardingguiden för första gången måste du välja var microsoft Defender för slutpunktsrelaterad information ska lagras: i EUROPEISKA UNIONEN, Storbritannien eller i USA-datacentret.</span><span class="sxs-lookup"><span data-stu-id="f55c3-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="f55c3-175">Du kan inte ändra datalagringsplatsen efter den första installationen.</span><span class="sxs-lookup"><span data-stu-id="f55c3-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="f55c3-176">Läs [Microsoft Defender för slutpunktens datalagring och sekretess för](data-storage-privacy.md) mer information om var och hur Microsoft lagrar dina data.</span><span class="sxs-lookup"><span data-stu-id="f55c3-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="f55c3-177">Inställningar för diagnostikdata</span><span class="sxs-lookup"><span data-stu-id="f55c3-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-178">Microsoft Defender för Endpoint kräver ingen specifik diagnostiknivå så länge den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f55c3-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="f55c3-179">Kontrollera att tjänsten för diagnostikdata är aktiverad på alla enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f55c3-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="f55c3-180">Den här tjänsten är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="f55c3-180">By default, this service is enabled.</span></span> <span data-ttu-id="f55c3-181">Det är bra att kontrollera att du får sensordata från dem.</span><span class="sxs-lookup"><span data-stu-id="f55c3-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="f55c3-182">**Använd kommandoraden för att kontrollera starttypen för Windows 10-diagnostikdatatjänsten:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="f55c3-183">Öppna en upphöjd kommandoradsfråga på enheten:</span><span class="sxs-lookup"><span data-stu-id="f55c3-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="f55c3-184">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="f55c3-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="f55c3-185">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="f55c3-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="f55c3-186">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="f55c3-187">Om tjänsten är aktiverad bör resultatet se ut som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="f55c3-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Resultatet av sc-frågekommandot för diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="f55c3-189">Du måste ange att tjänsten ska startas automatiskt om tjänsten START_TYPE **är** inställd på **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="f55c3-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="f55c3-190">**Använd kommandoraden för att ställa in Windows 10-diagnostikdatatjänsten så att den startas automatiskt:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="f55c3-191">Öppna en upphöjd kommandoradsfråga i slutpunkten:</span><span class="sxs-lookup"><span data-stu-id="f55c3-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="f55c3-192">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="f55c3-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="f55c3-193">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="f55c3-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="f55c3-194">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="f55c3-195">Ett meddelande om att det har lyckats visas.</span><span class="sxs-lookup"><span data-stu-id="f55c3-195">A success message is displayed.</span></span> <span data-ttu-id="f55c3-196">Verifiera ändringen genom att ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="f55c3-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="f55c3-197">Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="f55c3-197">Internet connectivity</span></span>
<span data-ttu-id="f55c3-198">Internetanslutningen på enheter krävs antingen direkt eller via proxy.</span><span class="sxs-lookup"><span data-stu-id="f55c3-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="f55c3-199">Defender för slutpunkts sensor kan använda en daglig genomsnittlig bandbredd på 5 MB för att kommunicera med Defender för Endpoint-molntjänsten och rapportera cyberdata.</span><span class="sxs-lookup"><span data-stu-id="f55c3-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="f55c3-200">One-off-aktiviteter, till exempel filuppladdningar och insamling av undersökningspaket, ingår inte i den här dagliga genomsnittliga bandbredden.</span><span class="sxs-lookup"><span data-stu-id="f55c3-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="f55c3-201">Mer information om ytterligare proxykonfigurationsinställningar finns i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="f55c3-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="f55c3-202">Innan du börjar använda enheter måste diagnostikdatatjänsten vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f55c3-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="f55c3-203">Tjänsten är aktiverad som standard i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f55c3-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="f55c3-204">Krav för konfiguration av Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f55c3-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="f55c3-205">Defender för slutpunktsagenten är beroende av microsoft Defender Antiviruss möjlighet att söka igenom filer och ge information om dem.</span><span class="sxs-lookup"><span data-stu-id="f55c3-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="f55c3-206">Konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett om Microsoft Defender Antivirus är det aktiva program mot skadlig programvara eller inte.</span><span class="sxs-lookup"><span data-stu-id="f55c3-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="f55c3-207">Mer information finns i Hantera [uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="f55c3-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="f55c3-208">Om Microsoft Defender Antivirus inte är den aktiva skadlig programvara i organisationen och du använder Defender för slutpunktstjänsten, aktiveras Microsoft Defender Antivirus som passiv form.</span><span class="sxs-lookup"><span data-stu-id="f55c3-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="f55c3-209">Om din organisation har inaktiverat Microsoft Defender Antivirus genom grupprinciper eller andra metoder måste enheter som är onboarded uteslutas från den här grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="f55c3-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="f55c3-210">Om du onboarding-servrar och Microsoft Defender Antivirus inte är det aktiva program mot skadlig programvara på servrarna måste du antingen konfigurera Microsoft Defender Antivirus för att gå på passiv form eller avinstallera det.</span><span class="sxs-lookup"><span data-stu-id="f55c3-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="f55c3-211">Konfigurationen är beroende av serverversionen.</span><span class="sxs-lookup"><span data-stu-id="f55c3-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="f55c3-212">Mer information finns i Kompatibilitet [för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f55c3-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f55c3-213">Din vanliga grupprincip gäller inte för skydd mot manipulering, och ändringar i inställningarna för Microsoft Defender Antivirus ignoreras när Skydd mot manipulering är på.</span><span class="sxs-lookup"><span data-stu-id="f55c3-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="f55c3-214">Drivrutinen Microsoft Defender Antivirus Early Launch Antimalware (ELAM) är aktiverad</span><span class="sxs-lookup"><span data-stu-id="f55c3-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="f55c3-215">Om du kör Microsoft Defender Antivirus som primärt program mot skadlig programvara på dina enheter kan Defender för Slutpunkt-agenten registrera sig.</span><span class="sxs-lookup"><span data-stu-id="f55c3-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="f55c3-216">Om du kör en tredjepartsklient för program mot skadlig programvara och använder mobila enhetshanteringslösningar eller Microsoft Endpoint Manager (current branch) måste du se till att Microsoft Defender Antivirus ELAM-drivrutinen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f55c3-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="f55c3-217">Mer information finns i Se [till att Microsoft Defender Antivirus inte är inaktiverat enligt policy.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="f55c3-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="f55c3-218">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f55c3-218">Related topics</span></span>
- [<span data-ttu-id="f55c3-219">Konfigurera Microsoft Defender för distribution av Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f55c3-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="f55c3-220">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="f55c3-220">Onboard devices</span></span>](onboard-configure.md)
