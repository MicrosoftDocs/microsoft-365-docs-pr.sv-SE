---
title: Köra och anpassa genomsökningar på begäran i Microsoft Defender AV
description: Köra och konfigurera genomsökningar på begäran med Hjälp av PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhetsappen
keywords: skanna, på begäran, dos, intune, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 976531e1b7e1b87c4cd2dd2af66f294f68c5d4f1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764405"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="faf74-104">Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran</span><span class="sxs-lookup"><span data-stu-id="faf74-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="faf74-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="faf74-105">**Applies to:**</span></span>

- [<span data-ttu-id="faf74-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="faf74-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="faf74-107">Du kan köra en sökning på begäran på enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="faf74-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="faf74-108">Dessa genomsökningar startar omedelbart och du kan definiera parametrar för skanningen, till exempel plats eller typ.</span><span class="sxs-lookup"><span data-stu-id="faf74-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="faf74-109">Snabbsökning jämfört med fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="faf74-109">Quick scan versus full scan</span></span>

<span data-ttu-id="faf74-110">Snabbsökning söker igenom alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända startmappar i Windows.</span><span class="sxs-lookup"><span data-stu-id="faf74-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="faf74-111">Microsoft Defender Antivirus körs i kontexten för [LocalSystem-kontot](/windows/win32/services/localsystem-account) när du gör en lokal genomsökning.</span><span class="sxs-lookup"><span data-stu-id="faf74-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="faf74-112">För nätverkssökningar används enhetskontots kontext.</span><span class="sxs-lookup"><span data-stu-id="faf74-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="faf74-113">Om domänenhetskontot inte har tillräcklig behörighet för att komma åt resursen fungerar inte genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="faf74-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="faf74-114">Kontrollera att enheten har behörigheter till den åtkomstnätverksresurs som används.</span><span class="sxs-lookup"><span data-stu-id="faf74-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="faf74-115">I [](configure-real-time-protection-microsoft-defender-antivirus.md)kombination med ständigt realtidsskydd – som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp – ger en snabb genomsökning stark täckning både för skadlig programvara som börjar med systemet och kernel-nivå-skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="faf74-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="faf74-116">I de flesta fall är en snabb genomsökning lämplig för att hitta skadlig programvara som inte hämtades med realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="faf74-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="faf74-117">En fullständig genomsökning kan vara användbar på slutpunkter som har rapporterat ett hot mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="faf74-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="faf74-118">Genomsökningen kan identifiera om det finns inaktiva komponenter som kräver en mer omfattande rensning.</span><span class="sxs-lookup"><span data-stu-id="faf74-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="faf74-119">Det här är bra om din organisation kör genomsökningar på begäran.</span><span class="sxs-lookup"><span data-stu-id="faf74-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="faf74-120">Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="faf74-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="faf74-121">Använda Microsoft Endpoint Manager för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="faf74-122">Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="faf74-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="faf74-123">Välj **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="faf74-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="faf74-124">I listan med flikar väljer du **Slutpunkter som inte är fel i Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="faf74-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="faf74-125">I listan med åtgärder väljer du **Snabbsökning eller** **Fullständig sökning.**</span><span class="sxs-lookup"><span data-stu-id="faf74-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="faf74-126">[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="faf74-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="faf74-127">Mer information om hur du använder Microsoft Endpoint Manager för att köra en genomsökning finns i Åtgärder mot skadlig programvara och brandvägg: Så här gör du [en sökning på begäran.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)</span><span class="sxs-lookup"><span data-stu-id="faf74-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="faf74-128">Använd mpcmdrun.exe för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="faf74-129">Använd följande `-scan` parameter:</span><span class="sxs-lookup"><span data-stu-id="faf74-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="faf74-130">Mer information om hur du använder verktyget och ytterligare parametrar, t.ex. hur du startar en fullständig genomsökning eller definierar sökvägar, finns i Använda kommandoradsverktyget mpcmdrun.exe för att konfigurera och hantera [Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="faf74-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="faf74-131">Använda Microsoft Intune för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="faf74-132">Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="faf74-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="faf74-133">I sidofältet väljer du **Enheter > Alla enheter och** väljer den enhet du vill skanna.</span><span class="sxs-lookup"><span data-stu-id="faf74-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="faf74-134">Välj **... Mer**.</span><span class="sxs-lookup"><span data-stu-id="faf74-134">Select **...More**.</span></span> <span data-ttu-id="faf74-135">Välj Snabbsökning eller **Fullständig sökning bland** **alternativen.**</span><span class="sxs-lookup"><span data-stu-id="faf74-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="faf74-136">Använda appen Windows-säkerhet för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="faf74-137">Se [Köra en genomsökning i Windows-säkerhetsappen](microsoft-defender-security-center-antivirus.md) för anvisningar om hur du kör en genomsökning av enskilda slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="faf74-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="faf74-138">Använda PowerShell-cmdlets för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="faf74-139">Använd följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="faf74-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="faf74-140">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra [cmdlets](/powershell/module/defender/)för Microsoft Defender Antivirus och Defender.</span><span class="sxs-lookup"><span data-stu-id="faf74-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="faf74-141">Använd WMI (Windows Management Instruction) för att köra en genomsökning</span><span class="sxs-lookup"><span data-stu-id="faf74-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="faf74-142">Använd [ **metoden Start** för](/previous-versions/windows/desktop/defender/start-msft-mpscan) MSFT_MpScan klassen. </span><span class="sxs-lookup"><span data-stu-id="faf74-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="faf74-143">Mer information om vilka parametrar som tillåts finns i [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="faf74-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="faf74-144">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="faf74-144">Related articles</span></span>

- [<span data-ttu-id="faf74-145">Konfigurera sökalternativ för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="faf74-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="faf74-146">Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="faf74-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="faf74-147">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="faf74-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)