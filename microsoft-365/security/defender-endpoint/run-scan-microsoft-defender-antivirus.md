---
title: Köra och anpassa genomsökningar på begäran i Microsoft Defender Antivirus
description: Köra och konfigurera genomsökningar på begäran med PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhet-appen
keywords: skanna, på begäran, dos, intune, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878814"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="1a2e4-104">Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1a2e4-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="1a2e4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1a2e4-105">**Applies to:**</span></span>

- [<span data-ttu-id="1a2e4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a2e4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1a2e4-107">Du kan köra en sökning på begäran på enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="1a2e4-108">Dessa genomsökningar startar omedelbart och du kan definiera parametrar för skanningen, till exempel plats eller typ.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="1a2e4-109">När du kör en genomsökning kan du välja mellan tre typer: Snabbsökning, fullständig sökning och anpassad sökning.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="1a2e4-110">Använd i de flesta fall en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="1a2e4-111">En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="1a2e4-112">I kombination med ständigt realtidsskydd som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp ger en snabb genomsökning ett starkt skydd mot skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="1a2e4-113">I de flesta fall är en snabbsökning tillräcklig och är det rekommenderade alternativet för schemalagda skanningar eller sökningar på begäran.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="1a2e4-114">[Läs mer om genomsökningstyper](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span><span class="sxs-lookup"><span data-stu-id="1a2e4-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a2e4-115">Microsoft Defender Antivirus körs i kontexten för [LocalSystem-kontot](/windows/win32/services/localsystem-account) när du utför en lokal genomsökning.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="1a2e4-116">För nätverkssökningar används enhetskontots kontext.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="1a2e4-117">Om domänenhetskontot inte har tillräcklig behörighet för att komma åt resursen fungerar inte genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="1a2e4-118">Kontrollera att enheten har behörigheter till den åtkomstnätverksresurs som används.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="1a2e4-119">Använda Microsoft Endpoint Manager för att köra en sökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="1a2e4-120">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="1a2e4-121">Välj **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="1a2e4-122">I listan över flikar väljer du Windows 10 **slutpunkter som inte är fel**.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="1a2e4-123">I listan med åtgärder väljer du **Snabbsökning** (rekommenderas) eller **Fullständig sökning**.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="1a2e4-124">[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1a2e4-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="1a2e4-125">Mer information om hur du använder Microsoft Endpoint Manager att köra en genomsökning finns i Program mot skadlig programvara och [brandväggsåtgärder:](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Så här gör du en sökning på begäran.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="1a2e4-126">Använd mpcmdrun.exe för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="1a2e4-127">Använd följande `-scan` parameter:</span><span class="sxs-lookup"><span data-stu-id="1a2e4-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="1a2e4-128">Mer information om hur du använder verktyget och ytterligare parametrar, inklusive hur du påbörjar en fullständig genomsökning eller definierar sökvägar, finns i använda kommandoradsverktyget mpcmdrun.exe för att konfigurera och hantera [Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1a2e4-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="1a2e4-129">Använda Microsoft Intune för att köra en sökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="1a2e4-130">Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="1a2e4-131">I sidofältet väljer du **Enheter**  >  **alla enheter** och väljer den enhet du vill skanna.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="1a2e4-132">Välj **... Mer**.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-132">Select **...More**.</span></span> <span data-ttu-id="1a2e4-133">Välj Snabbsökning **(rekommenderas) eller** Fullständig sökning bland **alternativen.**</span><span class="sxs-lookup"><span data-stu-id="1a2e4-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="1a2e4-134">Använd appen Windows-säkerhet för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="1a2e4-135">Se [Köra en genomsökning i Windows-säkerhet-appen](microsoft-defender-security-center-antivirus.md) för anvisningar om hur du kör en genomsökning av enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="1a2e4-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="1a2e4-136">Använda PowerShell-cmdlets för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="1a2e4-137">Använd följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1a2e4-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="1a2e4-138">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="1a2e4-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="1a2e4-139">Använd Windows Instruktionerna för hantering (WMI) för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="1a2e4-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="1a2e4-140">Använd [ **metoden Start** för](/previous-versions/windows/desktop/defender/start-msft-mpscan) MSFT_MpScan klassen. </span><span class="sxs-lookup"><span data-stu-id="1a2e4-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="1a2e4-141">Mer information om vilka parametrar som tillåts finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="1a2e4-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

