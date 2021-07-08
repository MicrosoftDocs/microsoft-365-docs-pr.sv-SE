---
title: Microsoft Defender Antivirus
description: Lär dig att hantera, konfigurera och använda Microsoft Defender Antivirus, inbyggt skydd mot skadlig programvara och antivirusskydd.
keywords: Microsoft Defender Antivirus, windows defender, skydd mot skadlig kod, scep, system center endpoint protection, system center configuration manager, virus, skadlig programvara, hot, identifiering, skydd, säkerhet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323050"
---
# <a name="microsoft-defender-antivirus-in-windows"></a><span data-ttu-id="93c12-104">Microsoft Defender Antivirus i Windows</span><span class="sxs-lookup"><span data-stu-id="93c12-104">Microsoft Defender Antivirus in Windows</span></span>

<span data-ttu-id="93c12-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="93c12-105">**Applies to:**</span></span>

- [<span data-ttu-id="93c12-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="93c12-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="93c12-107">Microsoft Defender Antivirus är en viktig komponent i nästa generations skydd i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="93c12-107">Microsoft Defender Antivirus is a major component of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="93c12-108">Det här skyddet sammanför maskininlärning, stordataanalys, djupgående forskning om hotresistens och Microsofts molninfrastruktur för att skydda enheter (eller slutpunkter) i din organisation.</span><span class="sxs-lookup"><span data-stu-id="93c12-108">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices (or endpoints) in your organization.</span></span> <span data-ttu-id="93c12-109">Microsoft Defender Antivirus är inbyggt i Windows och fungerar med Microsoft Defender för Endpoint för att ge skydd på din enhet och i molnet.</span><span class="sxs-lookup"><span data-stu-id="93c12-109">Microsoft Defender Antivirus is built into Windows, and it works with Microsoft Defender for Endpoint to provide protection on your device and in the cloud.</span></span> 

## <a name="compatibility-with-other-antivirus-products"></a><span data-ttu-id="93c12-110">Kompatibilitet med andra antivirusprodukter</span><span class="sxs-lookup"><span data-stu-id="93c12-110">Compatibility with other antivirus products</span></span>

<span data-ttu-id="93c12-111">Om du använder en antivirusprodukt som inte kommer från Microsoft på enheten kan du eventuellt köra Microsoft Defender Antivirus i passivt läge tillsammans med antiviruslösningen som inte kommer från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93c12-111">If you're using a non-Microsoft antivirus/antimalware product on your device, you might be able to run Microsoft Defender Antivirus in passive mode alongside the non-Microsoft antivirus solution.</span></span> <span data-ttu-id="93c12-112">Det beror på vilket operativsystem som används och om enheten är registrerad på Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="93c12-112">It depends on the operating system used and whether your device is onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="93c12-113">Mer information finns i [Kompatibilitet för Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="93c12-113">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a><span data-ttu-id="93c12-114">Jämföra aktivt läge, passivt läge och inaktiverat läge</span><span class="sxs-lookup"><span data-stu-id="93c12-114">Comparing active mode, passive mode, and disabled mode</span></span>

<span data-ttu-id="93c12-115">I följande tabell beskrivs vad du kan förvänta dig när Microsoft Defender Antivirus är i aktivt läge, passivt läge eller inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="93c12-115">The following table describes what to expect when Microsoft Defender Antivirus is in active mode, passive mode, or disabled.</span></span>

| <span data-ttu-id="93c12-116">Mode</span><span class="sxs-lookup"><span data-stu-id="93c12-116">Mode</span></span>  | <span data-ttu-id="93c12-117">Vad som händer</span><span class="sxs-lookup"><span data-stu-id="93c12-117">What happens</span></span>  |
|---------|---------|
| <span data-ttu-id="93c12-118">Aktivt läge</span><span class="sxs-lookup"><span data-stu-id="93c12-118">Active mode</span></span> | <span data-ttu-id="93c12-119">I aktivt läge används Microsoft Defender Antivirus som den primära antivirusappen på enheten.</span><span class="sxs-lookup"><span data-stu-id="93c12-119">In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device.</span></span> <span data-ttu-id="93c12-120">Filer genomsöks, hot åtgärdas och identifierade hot visas i organisationens säkerhetsrapporter och i din app Windows-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="93c12-120">Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.</span></span> |
| <span data-ttu-id="93c12-121">Passivt läge</span><span class="sxs-lookup"><span data-stu-id="93c12-121">Passive mode</span></span> | <span data-ttu-id="93c12-122">I passivt läge används inte Microsoft Defender Antivirus som den primära antivirusappen på enheten.</span><span class="sxs-lookup"><span data-stu-id="93c12-122">In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device.</span></span> <span data-ttu-id="93c12-123">Filer genomsöks och identifierade hot rapporteras, men hot åtgärdas inte av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="93c12-123">Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus.</span></span>   |
| <span data-ttu-id="93c12-124">Inaktiverad eller avinstallerad</span><span class="sxs-lookup"><span data-stu-id="93c12-124">Disabled or uninstalled</span></span>  | <span data-ttu-id="93c12-125">När Microsoft Defender Antivirus inaktiveras eller avinstalleras används den inte.</span><span class="sxs-lookup"><span data-stu-id="93c12-125">When disabled or uninstalled, Microsoft Defender Antivirus is not used.</span></span> <span data-ttu-id="93c12-126">Filer genomsöks inte och hot åtgärdas inte.</span><span class="sxs-lookup"><span data-stu-id="93c12-126">Files are not scanned, and threats are not remediated.</span></span> <span data-ttu-id="93c12-127">I allmänhet rekommenderar vi inte att du inaktiverar eller avinstallerar Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="93c12-127">In general, we do not recommend disabling or uninstalling Microsoft Defender Antivirus.</span></span>  |

<span data-ttu-id="93c12-128">Mer information finns i [Kompatibilitet för Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="93c12-128">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a><span data-ttu-id="93c12-129">Kontrollera tillståndet för Microsoft Defender Antivirus på enheten</span><span class="sxs-lookup"><span data-stu-id="93c12-129">Check the state of Microsoft Defender Antivirus on your device</span></span>

<span data-ttu-id="93c12-130">Om du vill kontrollera tillståndet för Microsoft Defender Antivirus på enheten kan du använda en av flera metoder, till exempel appen Windows-säkerhet eller Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93c12-130">If you want to check the state of Microsoft Defender Antivirus on your device, you can use one of several methods, such as the Windows Security app or Windows PowerShell.</span></span>

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="93c12-131">Använd appen Windows-säkerhet för att kontrollera status för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="93c12-131">Use the Windows Security app to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="93c12-132">Välj Start-menyn på din Windows-enhet och börja skriva `Security`.</span><span class="sxs-lookup"><span data-stu-id="93c12-132">On your Windows device, select the Start menu, and begin typing `Security`.</span></span> <span data-ttu-id="93c12-133">Öppna sedan appen Windows-säkerhet i resultaten.</span><span class="sxs-lookup"><span data-stu-id="93c12-133">Then open the Windows Security app in the results.</span></span>

2. <span data-ttu-id="93c12-134">Välj **Skydd mot virus och hot**.</span><span class="sxs-lookup"><span data-stu-id="93c12-134">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="93c12-135">Under **Inställningar för skydd mot virus och hot** väljer du **Hantera inställningar**.</span><span class="sxs-lookup"><span data-stu-id="93c12-135">Under **Virus & threat protection settings**, choose **Manage settings**.</span></span>

<span data-ttu-id="93c12-136">Namnet på din antiviruslösning visas på inställningssidan.</span><span class="sxs-lookup"><span data-stu-id="93c12-136">You'll see the name of your antivirus/antimalware solution on the settings page.</span></span>

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="93c12-137">Använd PowerShell för att kontrollera status för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="93c12-137">Use PowerShell to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="93c12-138">Välj Start-menyn och börja skriva `PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="93c12-138">Select the Start menu, and begin typing `PowerShell`.</span></span> <span data-ttu-id="93c12-139">Öppna sedan Windows PowerShell i resultaten.</span><span class="sxs-lookup"><span data-stu-id="93c12-139">Then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="93c12-140">Skriv `Get-MpComputerStatus`.</span><span class="sxs-lookup"><span data-stu-id="93c12-140">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="93c12-141">I resultatlistan tittar du på raden **AMRunningMode**.</span><span class="sxs-lookup"><span data-stu-id="93c12-141">In the list of results, look at the **AMRunningMode** row.</span></span>

   - <span data-ttu-id="93c12-142">**Normal** innebär att Microsoft Defender Antivirus körs i aktivt läge.</span><span class="sxs-lookup"><span data-stu-id="93c12-142">**Normal** means Microsoft Defender Antivirus is running in active mode.</span></span>
   - <span data-ttu-id="93c12-143">**Passivt läge** innebär att Microsoft Defender Antivirus körs, men är inte den primära antivirusprodukten på enheten.</span><span class="sxs-lookup"><span data-stu-id="93c12-143">**Passive mode** means Microsoft Defender Antivirus running, but is not the primary antivirus/antimalware product on your device.</span></span>
   - <span data-ttu-id="93c12-144">**EDR-blockeringsläge** innebär att Microsoft Defender Antivirus körs och en funktion i Microsoft Defender för Endpoint som kallas "EDR i blockeringsläge" är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="93c12-144">**EDR Block Mode** means Microsoft Defender Antivirus is running and a capability in Microsoft Defender for Endpoint that is called "EDR in block mode" is enabled.</span></span> <span data-ttu-id="93c12-145">(Gå till [Identifiering och åtgärd på slutpunkt (EDR) i blockeringsläge](edr-in-block-mode.md).)</span><span class="sxs-lookup"><span data-stu-id="93c12-145">(See [Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md).)</span></span>
   - <span data-ttu-id="93c12-146">**Passivt SxS-läge** innebär att Microsoft Defender Antivirus körs i passivt läge tillsammans med ett annat antivirusprogram och att enheten inte har registrerats i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="93c12-146">**SxS Passive Mode** means Microsoft Defender Antivirus is running in passive mode alongside another antivirus/antimalware product, and your device is not onboarded to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="93c12-147">I det här fallet används begränsad regelbunden genomsökning för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="93c12-147">In this case, limited periodic scanning is used for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="93c12-148">Mer information finns i [Använda begränsad regelbunden genomsökning i Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="93c12-148">To learn more, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="93c12-149">Mer information om PowerShell-cmdleten Get-MpComputerStatus finns i referensartikeln [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span><span class="sxs-lookup"><span data-stu-id="93c12-149">To learn more about the Get-MpComputerStatus PowerShell cmdlet, see the reference article [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

## <a name="get-your-antivirusantimalware-platform-updates"></a><span data-ttu-id="93c12-150">Hämta uppdateringar för plattformen för antivirusprogrammet</span><span class="sxs-lookup"><span data-stu-id="93c12-150">Get your antivirus/antimalware platform updates</span></span>

<span data-ttu-id="93c12-151">Det är viktigt att hålla Microsoft Defender Antivirus eller annat antivirusprogram uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="93c12-151">It's important to keep Microsoft Defender Antivirus, or any antivirus/antimalware solution, up to date.</span></span> <span data-ttu-id="93c12-152">Microsoft släpper regelbundna uppdateringar för att säkerställa att dina enheter har den senaste tekniken för att skydda mot ny skadlig kod och attacktekniker.</span><span class="sxs-lookup"><span data-stu-id="93c12-152">Microsoft releases regular updates to help ensure that your devices have the latest technology to protect against new malware and attack techniques.</span></span> <span data-ttu-id="93c12-153">Mer information finns i [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="93c12-153">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

## <a name="see-also"></a><span data-ttu-id="93c12-154">Mer information finns även i</span><span class="sxs-lookup"><span data-stu-id="93c12-154">See also</span></span>

- [<span data-ttu-id="93c12-155">Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="93c12-155">Microsoft Defender Antivirus on Windows Server</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="93c12-156">Hantering och konfiguration av Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="93c12-156">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="93c12-157">Utvärdera Microsoft Defender Antivirus skydd</span><span class="sxs-lookup"><span data-stu-id="93c12-157">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
