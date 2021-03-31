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
ms.openlocfilehash: 1b203a29083aaa4a1f86abcd7e2c7b24bd63f186
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445750"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="1af9f-104">Minimikraven för Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="1af9f-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1af9f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1af9f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1af9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1af9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1af9f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1af9f-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1af9f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1af9f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1af9f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="1af9f-110">Det finns några minimikrav för onboarding-enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1af9f-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="1af9f-111">Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att hantera enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1af9f-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="1af9f-112">Läs mer om de senaste förbättringarna i Defender för Slutpunkt: [Defender för Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="1af9f-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="1af9f-113">Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="1af9f-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="1af9f-114">Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="1af9f-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="1af9f-115">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="1af9f-115">Licensing requirements</span></span>
<span data-ttu-id="1af9f-116">Microsoft Defender för Endpoint kräver något av följande volymlicensieringserbjudanden från Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1af9f-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="1af9f-117">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="1af9f-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="1af9f-118">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="1af9f-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="1af9f-119">Microsoft 365 E5 (M365 E5) som inkluderar Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="1af9f-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="1af9f-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="1af9f-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="1af9f-121">Microsoft 365 E5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="1af9f-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="1af9f-122">Microsoft 365 A5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="1af9f-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="1af9f-123">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1af9f-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-124">Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.</span><span class="sxs-lookup"><span data-stu-id="1af9f-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="1af9f-125">Microsoft Defender för Endpoint kan också köpas från en leverantör av molnlösningar (CSP).</span><span class="sxs-lookup"><span data-stu-id="1af9f-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="1af9f-126">Virtuella RDSH-maskiner kräver inte en separat Defender för Endpoint-licens.</span><span class="sxs-lookup"><span data-stu-id="1af9f-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="1af9f-127">Microsoft Defender för slutpunkt för servrar kräver något av följande licensalternativ:</span><span class="sxs-lookup"><span data-stu-id="1af9f-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="1af9f-128">Azure Säkerhetscenter med Azure Defender aktiverat</span><span class="sxs-lookup"><span data-stu-id="1af9f-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="1af9f-129">Microsoft Defender för slutpunkt för server (en per server som omfattas)</span><span class="sxs-lookup"><span data-stu-id="1af9f-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-130">Kunder kan skaffa serverlicenser (en per operativsystemmiljö för servrar (OSE)) för Microsoft Defender för Endpoint för servrar om de har kombinerat minst 50 licenser för en eller flera av följande användarlicenser:</span><span class="sxs-lookup"><span data-stu-id="1af9f-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="1af9f-131">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1af9f-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="1af9f-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="1af9f-132">Windows E5/A5</span></span>
> * <span data-ttu-id="1af9f-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="1af9f-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="1af9f-134">Microsoft 365 E5/A5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="1af9f-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="1af9f-135">Detaljerad licensinformation finns på webbplatsen [med produktvillkor och du](https://www.microsoft.com/licensing/terms/) kan arbeta med ditt kontoteam för att få mer information om villkoren.</span><span class="sxs-lookup"><span data-stu-id="1af9f-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="1af9f-136">Mer information om de många olika funktionerna i Windows 10-versioner finns i [Jämför Windows 10-utgåvor.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="1af9f-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="1af9f-137">En detaljerad jämförelsetabell för den kommersiella jämförelsen av Windows 10-versioner finns i [JÄMFÖRELSEn AV PDF-format.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="1af9f-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="1af9f-138">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="1af9f-138">Browser requirements</span></span>
<span data-ttu-id="1af9f-139">Åtkomst till Defender för Slutpunkt görs via en webbläsare med stöd för följande webbläsare:</span><span class="sxs-lookup"><span data-stu-id="1af9f-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="1af9f-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1af9f-140">Microsoft Edge</span></span>
- <span data-ttu-id="1af9f-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="1af9f-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-142">Andra webbläsare kanske fungerar, men de nämnda webbläsarna är de som stöds.</span><span class="sxs-lookup"><span data-stu-id="1af9f-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="1af9f-143">Maskin- och programvarukrav</span><span class="sxs-lookup"><span data-stu-id="1af9f-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="1af9f-144">Windows-versioner som stöds</span><span class="sxs-lookup"><span data-stu-id="1af9f-144">Supported Windows versions</span></span>
- <span data-ttu-id="1af9f-145">Windows 7 SP1 Enterprise[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="1af9f-145">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="1af9f-146">Windows 7 SP1 Pro[(kräver ESU för stöd](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="1af9f-146">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="1af9f-147">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af9f-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="1af9f-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="1af9f-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="1af9f-149">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af9f-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="1af9f-150">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="1af9f-150">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="1af9f-151">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="1af9f-151">Windows 10 Education</span></span>
- <span data-ttu-id="1af9f-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="1af9f-152">Windows 10 Pro</span></span>
- <span data-ttu-id="1af9f-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="1af9f-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="1af9f-154">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1af9f-154">Windows server</span></span>
  - <span data-ttu-id="1af9f-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="1af9f-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="1af9f-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1af9f-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="1af9f-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1af9f-157">Windows Server 2016</span></span>
  - <span data-ttu-id="1af9f-158">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="1af9f-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="1af9f-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1af9f-159">Windows Server 2019</span></span>
- <span data-ttu-id="1af9f-160">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="1af9f-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="1af9f-161">Enheter i nätverket måste köras på någon av dessa versioner.</span><span class="sxs-lookup"><span data-stu-id="1af9f-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="1af9f-162">Maskinvarukraven för Defender för Endpoint på enheter är samma för de versioner som stöds.</span><span class="sxs-lookup"><span data-stu-id="1af9f-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-163">Datorer som kör mobila versioner av Windows (till exempel Windows CE och Windows 10 Mobile) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="1af9f-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="1af9f-164">Virtuella datorer med Windows 10 Enterprise 2016 LTSB kan stöta på prestandaproblem om de körs på virtualiseringsplattformar som inte är microsoft.</span><span class="sxs-lookup"><span data-stu-id="1af9f-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="1af9f-165">För virtuella miljöer rekommenderar vi att du använder Windows 10 Enterprise LTSC 2019 eller senare.</span><span class="sxs-lookup"><span data-stu-id="1af9f-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="1af9f-166">Andra operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="1af9f-166">Other supported operating systems</span></span>
- <span data-ttu-id="1af9f-167">Android</span><span class="sxs-lookup"><span data-stu-id="1af9f-167">Android</span></span>
- <span data-ttu-id="1af9f-168">iOS</span><span class="sxs-lookup"><span data-stu-id="1af9f-168">iOS</span></span>
- <span data-ttu-id="1af9f-169">Linux</span><span class="sxs-lookup"><span data-stu-id="1af9f-169">Linux</span></span>
- <span data-ttu-id="1af9f-170">macOS</span><span class="sxs-lookup"><span data-stu-id="1af9f-170">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-171">Du måste bekräfta linux-distributionerna och versionerna av Android, iOS och macOS som du har kompatibelt med Defender för Endpoint för att integreringen ska fungera.</span><span class="sxs-lookup"><span data-stu-id="1af9f-171">You'll need to confirm the Linux distributions and versions of Android, iOS and macOS you've are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="1af9f-172">Krav för nätverks- och datalagring och konfiguration</span><span class="sxs-lookup"><span data-stu-id="1af9f-172">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="1af9f-173">När du kör onboardingguiden för första gången måste du välja var microsoft Defender för slutpunktsrelaterad information ska lagras: i EUROPEISKA UNIONEN, Storbritannien eller i USA-datacentret.</span><span class="sxs-lookup"><span data-stu-id="1af9f-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="1af9f-174">Du kan inte ändra datalagringsplatsen efter den första installationen.</span><span class="sxs-lookup"><span data-stu-id="1af9f-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="1af9f-175">Läs [Microsoft Defender för slutpunktens datalagring och sekretess för](data-storage-privacy.md) mer information om var och hur Microsoft lagrar dina data.</span><span class="sxs-lookup"><span data-stu-id="1af9f-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="1af9f-176">Inställningar för diagnostikdata</span><span class="sxs-lookup"><span data-stu-id="1af9f-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-177">Microsoft Defender för Endpoint kräver ingen specifik diagnostiknivå så länge den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="1af9f-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="1af9f-178">Kontrollera att tjänsten för diagnostikdata är aktiverad på alla enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1af9f-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="1af9f-179">Den här tjänsten är aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="1af9f-179">By default, this service is enabled.</span></span> <span data-ttu-id="1af9f-180">Det är bra att kontrollera att du får sensordata från dem.</span><span class="sxs-lookup"><span data-stu-id="1af9f-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="1af9f-181">**Använd kommandoraden för att kontrollera starttypen för Windows 10-diagnostikdatatjänsten:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="1af9f-182">Öppna en upphöjd kommandoradsfråga på enheten:</span><span class="sxs-lookup"><span data-stu-id="1af9f-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="1af9f-183">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="1af9f-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="1af9f-184">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="1af9f-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="1af9f-185">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="1af9f-186">Om tjänsten är aktiverad bör resultatet se ut som på följande skärmbild:</span><span class="sxs-lookup"><span data-stu-id="1af9f-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Resultatet av sc-frågekommandot för diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="1af9f-188">Du måste ange att tjänsten ska startas automatiskt om tjänsten START_TYPE **är** inställd på **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="1af9f-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="1af9f-189">**Använd kommandoraden för att ställa in Windows 10-diagnostikdatatjänsten så att den startas automatiskt:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="1af9f-190">Öppna en upphöjd kommandoradsfråga i slutpunkten:</span><span class="sxs-lookup"><span data-stu-id="1af9f-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="1af9f-191">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="1af9f-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="1af9f-192">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="1af9f-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="1af9f-193">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="1af9f-194">Ett meddelande om att det har lyckats visas.</span><span class="sxs-lookup"><span data-stu-id="1af9f-194">A success message is displayed.</span></span> <span data-ttu-id="1af9f-195">Verifiera ändringen genom att ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="1af9f-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="1af9f-196">Internetanslutning</span><span class="sxs-lookup"><span data-stu-id="1af9f-196">Internet connectivity</span></span>
<span data-ttu-id="1af9f-197">Internetanslutningen på enheter krävs antingen direkt eller via proxy.</span><span class="sxs-lookup"><span data-stu-id="1af9f-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="1af9f-198">Defender för slutpunkts sensor kan använda en daglig genomsnittlig bandbredd på 5 MB för att kommunicera med Defender för Endpoint-molntjänsten och rapportera cyberdata.</span><span class="sxs-lookup"><span data-stu-id="1af9f-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="1af9f-199">En-off-aktiviteter, till exempel filuppladdningar och insamling av undersökningspaket, tas inte med i den här dagliga genomsnittliga bandbredden.</span><span class="sxs-lookup"><span data-stu-id="1af9f-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="1af9f-200">Mer information om ytterligare proxykonfigurationsinställningar finns i Konfigurera [enhetsproxy och internetanslutningsinställningar.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="1af9f-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="1af9f-201">Innan du börjar använda enheter måste diagnostikdatatjänsten vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="1af9f-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="1af9f-202">Tjänsten är aktiverad som standard i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1af9f-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="1af9f-203">Krav för konfiguration av Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1af9f-203">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="1af9f-204">Defender för slutpunktsagenten är beroende av microsoft Defender Antiviruss möjlighet att söka igenom filer och ge information om dem.</span><span class="sxs-lookup"><span data-stu-id="1af9f-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="1af9f-205">Konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett om Microsoft Defender Antivirus är det aktiva program mot skadlig programvara eller inte.</span><span class="sxs-lookup"><span data-stu-id="1af9f-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="1af9f-206">Mer information finns i Hantera [uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="1af9f-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="1af9f-207">Om Microsoft Defender Antivirus inte är det aktiva skydd mot skadlig programvara i organisationen och du använder Defender för slutpunktstjänsten, aktiveras Microsoft Defender Antivirus som passivt läge.</span><span class="sxs-lookup"><span data-stu-id="1af9f-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="1af9f-208">Om din organisation har inaktiverat Microsoft Defender Antivirus genom grupprinciper eller andra metoder måste enheter som är onboarded uteslutas från den här grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="1af9f-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="1af9f-209">Om du onboarding servers och Microsoft Defender Antivirus inte är det aktiva program mot skadlig programvara på dina servrar måste du antingen konfigurera Microsoft Defender Antivirus för att gå på passiv form eller avinstallera det.</span><span class="sxs-lookup"><span data-stu-id="1af9f-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="1af9f-210">Konfigurationen är beroende av serverversionen.</span><span class="sxs-lookup"><span data-stu-id="1af9f-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="1af9f-211">Mer information finns i Kompatibilitet [för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="1af9f-211">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1af9f-212">Din vanliga grupprincip gäller inte för skydd mot manipulering, och ändringar i inställningarna för Microsoft Defender Antivirus ignoreras när Skydd mot manipulering är på.</span><span class="sxs-lookup"><span data-stu-id="1af9f-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="1af9f-213">Drivrutinen Microsoft Defender Antivirus Early Launch Antimalware (ELAM) är aktiverad</span><span class="sxs-lookup"><span data-stu-id="1af9f-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="1af9f-214">Om du kör Microsoft Defender Antivirus som primärt program mot skadlig programvara på dina enheter kan Defender för Slutpunkt-agenten registrera sig.</span><span class="sxs-lookup"><span data-stu-id="1af9f-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="1af9f-215">Om du kör en tredjepartsklient för program mot skadlig programvara och använder mobila enhetshanteringslösningar eller Microsoft Endpoint Manager (current branch), måste du se till att Microsoft Defender Antivirus ELAM-drivrutinen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="1af9f-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="1af9f-216">Mer information finns i Se [till att Microsoft Defender Antivirus inte är inaktiverat enligt policy.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="1af9f-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1af9f-217">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1af9f-217">Related topics</span></span>
- [<span data-ttu-id="1af9f-218">Konfigurera Microsoft Defender för distribution av Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="1af9f-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="1af9f-219">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="1af9f-219">Onboard devices</span></span>](onboard-configure.md)
