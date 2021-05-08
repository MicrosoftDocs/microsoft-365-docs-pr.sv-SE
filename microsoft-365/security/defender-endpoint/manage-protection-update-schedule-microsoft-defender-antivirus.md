---
title: Schemalägga Microsoft Defender Antivirus säkerhetsuppdateringar
description: Schemalägga dag, tid och intervall för när skyddsuppdateringar ska laddas ned
keywords: uppdateringar, säkerhetsbaslinjer, schemauppdateringar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275042"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="7fff4-104">Hantera schemat för när skyddsuppdateringar ska laddas ned och tillämpas</span><span class="sxs-lookup"><span data-stu-id="7fff4-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7fff4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7fff4-105">**Applies to:**</span></span>

- [<span data-ttu-id="7fff4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7fff4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7fff4-107">Microsoft Defender Antivirus kan du avgöra när den ska söka efter och ladda ned uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="7fff4-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="7fff4-108">Du kan schemalägga uppdateringar för slutpunkterna genom att:</span><span class="sxs-lookup"><span data-stu-id="7fff4-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="7fff4-109">Ange veckodag för att söka efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="7fff4-110">Ange intervallet som ska söka efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="7fff4-111">Ange tiden för att söka efter skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="7fff4-112">Du kan också slumpmässigt ändra tidpunkterna när varje slutpunkt kontrollerar och laddar ned skyddsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="7fff4-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="7fff4-113">Mer information [finns i avsnittet](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Schemalägga genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="7fff4-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="7fff4-114">Använda Konfigurationshanteraren för att schemalägga skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="7fff4-115">Öppna den Microsoft Endpoint Manager programkonsol på datorn som du vill ändra  (klicka på Tillgångar och efterlevnad i navigeringsfönstret till vänster och expandera trädet till Översikt Endpoint Protection Program mot skadlig  >    >  **programvara**)</span><span class="sxs-lookup"><span data-stu-id="7fff4-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="7fff4-116">Gå till avsnittet **Säkerhetsintelligensuppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="7fff4-117">Så här kontrollerar och laddar du ned uppdateringar vid en viss tidpunkt:</span><span class="sxs-lookup"><span data-stu-id="7fff4-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="7fff4-118">Ställ **in Sök Endpoint Protection säkerhetsintelligensuppdateringar med ett visst intervall...** till **0**.</span><span class="sxs-lookup"><span data-stu-id="7fff4-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="7fff4-119">Ställ **in Sök Endpoint Protection säkerhetsintelligensuppdateringar varje dag...** till den tidpunkt då uppdateringarna ska kontrolleras.</span><span class="sxs-lookup"><span data-stu-id="7fff4-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="7fff4-120">3</span><span class="sxs-lookup"><span data-stu-id="7fff4-120">3</span></span>
4. <span data-ttu-id="7fff4-121">Om du vill söka efter och ladda ned uppdateringar kontinuerligt, ställ in Sök efter Endpoint Protection säkerhetsintelligensuppdateringar med ett visst **intervall...** på antalet timmar som ska ske mellan uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="7fff4-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="7fff4-122">[Distribuera den uppdaterade principen som vanligt](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="7fff4-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="7fff4-123">Använda grupprinciper för att schemalägga skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fff4-124">Som standard söker Microsoft Defender Antivirus uppdatering 15 minuter före tiden för schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="7fff4-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="7fff4-125">Om du aktiverar de här inställningarna åsidosätts den standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="7fff4-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="7fff4-126">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="7fff4-127">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="7fff4-128">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="7fff4-129">Expandera trädet så att **Windows delar**  >  **Microsoft Defender Antivirus signaturintelligensuppdateringar** och konfigurera följande  >   inställningar:</span><span class="sxs-lookup"><span data-stu-id="7fff4-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="7fff4-130">Dubbelklicka på ange **dagen i veckan för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7fff4-131">Ange veckodagen för att söka efter uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="7fff4-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="7fff4-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fff4-132">Click **OK**.</span></span>
    2. <span data-ttu-id="7fff4-133">Dubbelklicka på inställningen Ange **intervallet för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7fff4-134">Ange antalet timmar mellan uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="7fff4-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="7fff4-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fff4-135">Click **OK**.</span></span>
    3. <span data-ttu-id="7fff4-136">Dubbelklicka på inställningen **Ange tiden för att söka efter säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="7fff4-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="7fff4-137">Ange när uppdateringarna ska kontrolleras.</span><span class="sxs-lookup"><span data-stu-id="7fff4-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="7fff4-138">Tiden baseras på slutpunktens lokala tid.</span><span class="sxs-lookup"><span data-stu-id="7fff4-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="7fff4-139">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fff4-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="7fff4-140">Använda PowerShell-cmdlets för att schemalägga skyddsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="7fff4-141">Använd följande cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7fff4-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="7fff4-142">Se [Använda PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="7fff4-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="7fff4-143">Använda Windows (WMI) för att schemalägga säkerhetsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="7fff4-144">Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="7fff4-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="7fff4-145">Mer information och tillåtna parametrar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="7fff4-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="7fff4-146">Windows Defender WMIv2-API:er</span><span class="sxs-lookup"><span data-stu-id="7fff4-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="7fff4-147">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="7fff4-147">Related articles</span></span>

- [<span data-ttu-id="7fff4-148">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7fff4-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7fff4-149">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="7fff4-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7fff4-150">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="7fff4-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7fff4-151">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="7fff4-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7fff4-152">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="7fff4-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7fff4-153">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="7fff4-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)