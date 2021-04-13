---
title: Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer
description: Hantera hur Microsoft Defender Antivirus får skydd och produktuppdateringar.
keywords: uppdateringar, säkerhetsbaslinjer, skydd, schemauppdateringar, tvinga uppdateringar, mobiluppdateringar, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690977"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="07ba7-104">Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer</span><span class="sxs-lookup"><span data-stu-id="07ba7-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="07ba7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07ba7-105">**Applies to:**</span></span>

- [<span data-ttu-id="07ba7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="07ba7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="07ba7-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="07ba7-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="07ba7-108">Det finns två typer av uppdateringar som är relaterade till att hålla Microsoft Defender Antivirus uppdaterat:</span><span class="sxs-lookup"><span data-stu-id="07ba7-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="07ba7-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-109">Security intelligence updates</span></span>
- <span data-ttu-id="07ba7-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07ba7-111">Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="07ba7-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="07ba7-112">Uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="07ba7-113">Om du vill se de senaste motor-, plattforms- och signaturdatumen går du till Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="07ba7-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="07ba7-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-114">Security intelligence updates</span></span>

<span data-ttu-id="07ba7-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsofts tjänst för avancerat skydd eller KARTOR) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="07ba7-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="07ba7-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="07ba7-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="07ba7-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="07ba7-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="07ba7-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="07ba7-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="07ba7-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="07ba7-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="07ba7-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="07ba7-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="07ba7-121">Mer information finns i [Använda Molnskydd i Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="07ba7-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="07ba7-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="07ba7-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="07ba7-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="07ba7-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-124">Product updates</span></span>

<span data-ttu-id="07ba7-125">Microsoft Defender Antivirus kräver [månatliga uppdateringar (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10-versioner. </span><span class="sxs-lookup"><span data-stu-id="07ba7-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="07ba7-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="07ba7-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="07ba7-127">Windows Server Update Service (WSUS)</span><span class="sxs-lookup"><span data-stu-id="07ba7-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="07ba7-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="07ba7-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="07ba7-129">Den vanliga metoden du använder för att distribuera Microsoft och Windows-uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="07ba7-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="07ba7-130">Mer information finns i [Hantera källorna för uppdateringar av Microsoft Defender Antivirus Protection](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="07ba7-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="07ba7-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="07ba7-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="07ba7-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="07ba7-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="07ba7-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender-program mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="07ba7-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="07ba7-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="07ba7-134">All our updates contain</span></span> 
- <span data-ttu-id="07ba7-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-135">performance improvements;</span></span>
- <span data-ttu-id="07ba7-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="07ba7-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="07ba7-137">förbättringar av integreringen (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="07ba7-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="07ba7-138">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="07ba7-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="07ba7-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="07ba7-140">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="07ba7-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="07ba7-141">&ensp;Plattform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="07ba7-142">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="07ba7-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="07ba7-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-144">What's new</span></span>

- <span data-ttu-id="07ba7-145">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="07ba7-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="07ba7-146">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="07ba7-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="07ba7-147">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="07ba7-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-148">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-148">Known Issues</span></span>
<span data-ttu-id="07ba7-149">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ba7-150">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="07ba7-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="07ba7-151">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="07ba7-152">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="07ba7-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="07ba7-153">&ensp;Plattform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="07ba7-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="07ba7-154">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="07ba7-155">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="07ba7-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-156">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-156">What's new</span></span>

- <span data-ttu-id="07ba7-157">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="07ba7-158">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="07ba7-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-159">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-159">Known Issues</span></span>
<span data-ttu-id="07ba7-160">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ba7-161">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="07ba7-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="07ba7-162">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="07ba7-163">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="07ba7-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="07ba7-164">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="07ba7-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="07ba7-165">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ba7-166">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="07ba7-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-167">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-167">What's new</span></span>

- <span data-ttu-id="07ba7-168">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="07ba7-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="07ba7-169">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="07ba7-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="07ba7-170">Förbättringar av antivirusfunktionerna i Microsoft Defender Antivirus services</span><span class="sxs-lookup"><span data-stu-id="07ba7-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="07ba7-171">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="07ba7-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="07ba7-172">Åtgärd: EDR-blockeringsavisering finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="07ba7-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-173">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-173">Known Issues</span></span>
<span data-ttu-id="07ba7-174">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="07ba7-175">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="07ba7-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="07ba7-176">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="07ba7-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="07ba7-177">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="07ba7-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="07ba7-178">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="07ba7-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="07ba7-179">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="07ba7-180">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="07ba7-181">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="07ba7-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="07ba7-182">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="07ba7-183">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="07ba7-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-184">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-184">What's new</span></span>

- <span data-ttu-id="07ba7-185">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="07ba7-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-186">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-186">Known Issues</span></span>
<span data-ttu-id="07ba7-187">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ba7-188">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="07ba7-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="07ba7-189">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="07ba7-190">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="07ba7-191">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="07ba7-192">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ba7-193">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="07ba7-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-194">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-194">What's new</span></span>

- <span data-ttu-id="07ba7-195">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="07ba7-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="07ba7-196">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="07ba7-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="07ba7-197">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="07ba7-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="07ba7-198">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="07ba7-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-199">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-199">Known Issues</span></span>

<span data-ttu-id="07ba7-200">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ba7-201">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="07ba7-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="07ba7-202">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="07ba7-203">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="07ba7-204">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="07ba7-205">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="07ba7-206">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-207">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-207">What's new</span></span>

- <span data-ttu-id="07ba7-208">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="07ba7-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="07ba7-209">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="07ba7-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="07ba7-210">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="07ba7-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="07ba7-211">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="07ba7-211">New management interfaces for:</span></span>
   - <span data-ttu-id="07ba7-212">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="07ba7-212">UDP Inspection</span></span>
   - <span data-ttu-id="07ba7-213">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="07ba7-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="07ba7-214">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="07ba7-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="07ba7-215">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="07ba7-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="07ba7-216">Förbättrad vba-modulskanning för Office</span><span class="sxs-lookup"><span data-stu-id="07ba7-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-217">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-217">Known Issues</span></span>

<span data-ttu-id="07ba7-218">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="07ba7-219">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="07ba7-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="07ba7-220">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="07ba7-221">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="07ba7-222">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="07ba7-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="07ba7-223">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="07ba7-224">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="07ba7-225">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-225">What's new</span></span>

- <span data-ttu-id="07ba7-226">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="07ba7-226">Add more telemetry events</span></span>
- <span data-ttu-id="07ba7-227">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="07ba7-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="07ba7-228">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="07ba7-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="07ba7-229">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="07ba7-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="07ba7-230">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="07ba7-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="07ba7-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="07ba7-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="07ba7-232">Microsoft Defender Antivirus stängs automatiskt av när programmet upptäcker ett annat antivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="07ba7-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="07ba7-233">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-233">Known Issues</span></span>
<span data-ttu-id="07ba7-234">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-235">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="07ba7-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="07ba7-236">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="07ba7-237">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="07ba7-238">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="07ba7-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="07ba7-239">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="07ba7-240">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-241">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-241">What's new</span></span>

- <span data-ttu-id="07ba7-242">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="07ba7-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="07ba7-243">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="07ba7-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-244">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-244">Known Issues</span></span>
<span data-ttu-id="07ba7-245">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-246">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="07ba7-247">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="07ba7-248">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="07ba7-249">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="07ba7-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="07ba7-250">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="07ba7-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="07ba7-251">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-252">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-252">What's new</span></span>

- <span data-ttu-id="07ba7-253">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="07ba7-254">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="07ba7-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="07ba7-255">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="07ba7-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="07ba7-256">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="07ba7-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="07ba7-257">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="07ba7-257">Fixed registry query</span></span> 
- <span data-ttu-id="07ba7-258">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="07ba7-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-259">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-259">Known Issues</span></span>
<span data-ttu-id="07ba7-260">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-261">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="07ba7-262">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="07ba7-263">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="07ba7-264">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="07ba7-265">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="07ba7-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="07ba7-266">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-267">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-267">What's new</span></span>

- <span data-ttu-id="07ba7-268">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="07ba7-268">Improved logging for scan events</span></span>
- <span data-ttu-id="07ba7-269">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="07ba7-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="07ba7-270">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="07ba7-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="07ba7-271">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="07ba7-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="07ba7-272">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="07ba7-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="07ba7-273">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="07ba7-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-274">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-274">Known Issues</span></span>
<span data-ttu-id="07ba7-275">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-276">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="07ba7-277">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="07ba7-278">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="07ba7-279">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="07ba7-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="07ba7-280">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="07ba7-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="07ba7-281">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-282">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-282">What's new</span></span>
- <span data-ttu-id="07ba7-283">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-283">WDfilter improvements</span></span>
- <span data-ttu-id="07ba7-284">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="07ba7-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="07ba7-285">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="07ba7-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="07ba7-286">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="07ba7-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="07ba7-287">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="07ba7-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="07ba7-288">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="07ba7-288">UEFI scan capability</span></span>
- <span data-ttu-id="07ba7-289">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ba7-290">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-290">Known Issues</span></span>
<span data-ttu-id="07ba7-291">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-292">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="07ba7-293">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="07ba7-294">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="07ba7-295">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="07ba7-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="07ba7-296">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="07ba7-297">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ba7-298">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-298">What's new</span></span>

- <span data-ttu-id="07ba7-299">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="07ba7-300">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="07ba7-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="07ba7-301">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="07ba7-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="07ba7-302">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="07ba7-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="07ba7-303">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="07ba7-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ba7-304">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-304">Known Issues</span></span>
<span data-ttu-id="07ba7-305">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="07ba7-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="07ba7-306">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="07ba7-307">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="07ba7-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="07ba7-308">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="07ba7-309">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="07ba7-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="07ba7-310">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="07ba7-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="07ba7-311">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="07ba7-312">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="07ba7-313">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-313">Known Issues</span></span>
<span data-ttu-id="07ba7-314">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-315">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="07ba7-316">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="07ba7-317">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="07ba7-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="07ba7-318">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="07ba7-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="07ba7-319">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="07ba7-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="07ba7-320">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="07ba7-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="07ba7-321">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-321">What's new</span></span>

- <span data-ttu-id="07ba7-322">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="07ba7-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="07ba7-323">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="07ba7-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="07ba7-324">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="07ba7-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="07ba7-325">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="07ba7-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="07ba7-326">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="07ba7-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ba7-327">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-327">Known Issues</span></span>

<span data-ttu-id="07ba7-328">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="07ba7-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="07ba7-329">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="07ba7-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="07ba7-330">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="07ba7-330">This update is:</span></span>
> - <span data-ttu-id="07ba7-331">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="07ba7-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="07ba7-332">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="07ba7-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="07ba7-333">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="07ba7-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="07ba7-334">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="07ba7-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="07ba7-335">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="07ba7-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ba7-336">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="07ba7-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="07ba7-337">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="07ba7-338">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="07ba7-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="07ba7-339">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="07ba7-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="07ba7-340">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="07ba7-341">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="07ba7-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="07ba7-342">Nyheter</span><span class="sxs-lookup"><span data-stu-id="07ba7-342">What's new</span></span>

- <span data-ttu-id="07ba7-343">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="07ba7-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="07ba7-344">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="07ba7-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="07ba7-345">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="07ba7-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="07ba7-346">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="07ba7-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ba7-347">Kända problem</span><span class="sxs-lookup"><span data-stu-id="07ba7-347">Known Issues</span></span>
<span data-ttu-id="07ba7-348">När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="07ba7-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="07ba7-349">Support för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="07ba7-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="07ba7-350">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="07ba7-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="07ba7-351">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="07ba7-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="07ba7-352">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="07ba7-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="07ba7-353">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="07ba7-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="07ba7-354">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="07ba7-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="07ba7-355">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="07ba7-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="07ba7-356">\* Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10-versionen (se Plattformsversion som ingår i [Windows 10-versioner)](#platform-version-included-with-windows-10-releases)till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="07ba7-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="07ba7-357">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="07ba7-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="07ba7-358">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="07ba7-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="07ba7-359">Plattformsversion som ingår i Windows 10-versioner</span><span class="sxs-lookup"><span data-stu-id="07ba7-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="07ba7-360">Tabellen nedan innehåller microsoft Defender Antivirus-plattformen och motorversioner som levereras med de senaste Windows 10-versionerna:</span><span class="sxs-lookup"><span data-stu-id="07ba7-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="07ba7-361">Windows 10-version</span><span class="sxs-lookup"><span data-stu-id="07ba7-361">Windows 10 release</span></span>  |<span data-ttu-id="07ba7-362">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="07ba7-362">Platform version</span></span>  |<span data-ttu-id="07ba7-363">Motorversion</span><span class="sxs-lookup"><span data-stu-id="07ba7-363">Engine version</span></span> |<span data-ttu-id="07ba7-364">Supportfas</span><span class="sxs-lookup"><span data-stu-id="07ba7-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="07ba7-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="07ba7-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="07ba7-366">4.18.1909.6</span></span> |<span data-ttu-id="07ba7-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="07ba7-367">1.1.17000.2</span></span> | <span data-ttu-id="07ba7-368">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-369">1909  (19H2)</span></span> |<span data-ttu-id="07ba7-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="07ba7-370">4.18.1902.5</span></span> |<span data-ttu-id="07ba7-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="07ba7-371">1.1.16700.3</span></span> | <span data-ttu-id="07ba7-372">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="07ba7-373">1903  (19H1)</span></span> |<span data-ttu-id="07ba7-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="07ba7-374">4.18.1902.5</span></span> |<span data-ttu-id="07ba7-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="07ba7-375">1.1.15600.4</span></span> | <span data-ttu-id="07ba7-376">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="07ba7-377">1809  (RS5)</span></span> |<span data-ttu-id="07ba7-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="07ba7-378">4.18.1807.18075</span></span> |<span data-ttu-id="07ba7-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="07ba7-379">1.1.15000.2</span></span> | <span data-ttu-id="07ba7-380">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="07ba7-381">1803  (RS4)</span></span> |<span data-ttu-id="07ba7-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="07ba7-382">4.13.17134.1</span></span> |<span data-ttu-id="07ba7-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="07ba7-383">1.1.14600.4</span></span> | <span data-ttu-id="07ba7-384">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="07ba7-385">1709  (RS3)</span></span> |<span data-ttu-id="07ba7-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="07ba7-386">4.12.16299.15</span></span> |<span data-ttu-id="07ba7-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="07ba7-387">1.1.14104.0</span></span> | <span data-ttu-id="07ba7-388">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="07ba7-389">1703  (RS2)</span></span> |<span data-ttu-id="07ba7-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="07ba7-390">4.11.15603.2</span></span> |<span data-ttu-id="07ba7-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="07ba7-391">1.1.13504.0</span></span> | <span data-ttu-id="07ba7-392">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ba7-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="07ba7-393">1607 (RS1)</span></span> |<span data-ttu-id="07ba7-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="07ba7-394">4.10.14393.3683</span></span> |<span data-ttu-id="07ba7-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="07ba7-395">1.1.12805.0</span></span> | <span data-ttu-id="07ba7-396">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="07ba7-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="07ba7-397">Information om versionen av Windows 10 finns i informationsbladet [om Windows livscykel.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="07ba7-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="07ba7-398">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="07ba7-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="07ba7-399">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirus och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="07ba7-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="07ba7-400">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="07ba7-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="07ba7-401">Mer information finns i [Installationsbilder för Microsoft Defender-operativsystemet för Windows.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="07ba7-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="07ba7-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="07ba7-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="07ba7-403">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="07ba7-404">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="07ba7-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="07ba7-405">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="07ba7-406">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-407">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-407">Fixes</span></span>
- <span data-ttu-id="07ba7-408">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-409">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-409">Additional information</span></span>
- <span data-ttu-id="07ba7-410">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="07ba7-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="07ba7-412">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="07ba7-413">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="07ba7-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="07ba7-414">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ba7-415">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-416">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-416">Fixes</span></span>
- <span data-ttu-id="07ba7-417">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-418">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-418">Additional information</span></span>
- <span data-ttu-id="07ba7-419">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="07ba7-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="07ba7-421">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="07ba7-422">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="07ba7-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="07ba7-423">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ba7-424">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-425">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-425">Fixes</span></span>
- <span data-ttu-id="07ba7-426">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-427">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-427">Additional information</span></span>
- <span data-ttu-id="07ba7-428">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="07ba7-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="07ba7-430">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="07ba7-431">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="07ba7-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="07ba7-432">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="07ba7-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="07ba7-433">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-434">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-434">Fixes</span></span>
- <span data-ttu-id="07ba7-435">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-436">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-436">Additional information</span></span>
- <span data-ttu-id="07ba7-437">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="07ba7-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="07ba7-439">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="07ba7-440">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="07ba7-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="07ba7-441">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ba7-442">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-443">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-443">Fixes</span></span>
- <span data-ttu-id="07ba7-444">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-445">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-445">Additional information</span></span>
- <span data-ttu-id="07ba7-446">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="07ba7-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="07ba7-448">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="07ba7-449">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="07ba7-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="07ba7-450">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ba7-451">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-452">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-452">Fixes</span></span>
- <span data-ttu-id="07ba7-453">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-454">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-454">Additional information</span></span>
- <span data-ttu-id="07ba7-455">Uppdaterade Microsoft Defender Antivirus-signaturer</span><span class="sxs-lookup"><span data-stu-id="07ba7-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="07ba7-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="07ba7-457">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="07ba7-458">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="07ba7-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="07ba7-459">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ba7-460">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-461">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-461">Fixes</span></span>
- <span data-ttu-id="07ba7-462">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-463">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-463">Additional information</span></span>
- <span data-ttu-id="07ba7-464">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ba7-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="07ba7-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="07ba7-466">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="07ba7-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="07ba7-467">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="07ba7-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="07ba7-468">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="07ba7-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="07ba7-469">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="07ba7-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ba7-470">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-470">Fixes</span></span>
- <span data-ttu-id="07ba7-471">Ingen</span><span class="sxs-lookup"><span data-stu-id="07ba7-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ba7-472">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="07ba7-472">Additional information</span></span>
- <span data-ttu-id="07ba7-473">Lade till stöd för installationsbilder för Windows 10 RS1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="07ba7-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="07ba7-474">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="07ba7-474">Additional resources</span></span>

| <span data-ttu-id="07ba7-475">Artikel</span><span class="sxs-lookup"><span data-stu-id="07ba7-475">Article</span></span> | <span data-ttu-id="07ba7-476">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="07ba7-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="07ba7-477">Installationsbilder för Microsoft Defender-uppdatering för Windows-operativsystemet</span><span class="sxs-lookup"><span data-stu-id="07ba7-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="07ba7-478">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="07ba7-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="07ba7-479">Hämta installationsbilder för Microsoft Defender Antivirus för Windows 10 (Enterprise, Pro och Home), Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="07ba7-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="07ba7-480">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="07ba7-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="07ba7-481">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="07ba7-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="07ba7-482">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="07ba7-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="07ba7-483">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="07ba7-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="07ba7-484">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="07ba7-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="07ba7-485">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="07ba7-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="07ba7-486">Hantera händelsebaserade tvingade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="07ba7-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="07ba7-487">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="07ba7-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="07ba7-488">Hantera uppdateringar för mobila enheter och virtuella maskiner (VMs)</span><span class="sxs-lookup"><span data-stu-id="07ba7-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="07ba7-489">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="07ba7-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
