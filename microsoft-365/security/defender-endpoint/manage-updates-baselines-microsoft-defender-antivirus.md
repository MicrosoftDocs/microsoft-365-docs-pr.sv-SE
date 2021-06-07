---
title: Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer
description: Hantera hur Microsoft Defender Antivirus får skydd och produktuppdateringar.
keywords: uppdateringar, säkerhetsbaslinjer, skydd, schemauppdateringar, tvinga uppdateringar, mobiluppdateringar, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/03/2021
ms.openlocfilehash: e67f783552cca5cc36c1563f5e5557796028ea18
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772023"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="7f491-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="7f491-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="7f491-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7f491-105">**Applies to:**</span></span>

- [<span data-ttu-id="7f491-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f491-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="7f491-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="7f491-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="7f491-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="7f491-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="7f491-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-109">Security intelligence updates</span></span>
- <span data-ttu-id="7f491-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f491-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="7f491-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="7f491-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="7f491-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="7f491-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7f491-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="7f491-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-114">Security intelligence updates</span></span>

<span data-ttu-id="7f491-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="7f491-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="7f491-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="7f491-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="7f491-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="7f491-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="7f491-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="7f491-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="7f491-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="7f491-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="7f491-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="7f491-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="7f491-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="7f491-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="7f491-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7f491-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="7f491-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="7f491-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="7f491-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-124">Product updates</span></span>

<span data-ttu-id="7f491-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="7f491-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="7f491-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="7f491-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="7f491-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="7f491-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="7f491-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7f491-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="7f491-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="7f491-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="7f491-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="7f491-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="7f491-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="7f491-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="7f491-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="7f491-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="7f491-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="7f491-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="7f491-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="7f491-134">All our updates contain</span></span> 
- <span data-ttu-id="7f491-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="7f491-135">performance improvements;</span></span>
- <span data-ttu-id="7f491-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="7f491-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="7f491-137">förbättringar av integreringen (Cloud Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="7f491-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="7f491-138">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="7f491-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="7f491-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="7f491-140">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="7f491-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="7f491-141">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="7f491-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="7f491-142">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="7f491-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="7f491-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-144">What's new</span></span>
- <span data-ttu-id="7f491-145">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="7f491-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="7f491-146">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="7f491-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-147">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-147">Known Issues</span></span>
<span data-ttu-id="7f491-148">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-149">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="7f491-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="7f491-150">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="7f491-151">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="7f491-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="7f491-152">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="7f491-153">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="7f491-154">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="7f491-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-155">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-155">What's new</span></span>

- <span data-ttu-id="7f491-156">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="7f491-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="7f491-157">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="7f491-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="7f491-158">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="7f491-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-159">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-159">Known Issues</span></span>
<span data-ttu-id="7f491-160">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7f491-161">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="7f491-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="7f491-162">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="7f491-163">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="7f491-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="7f491-164">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="7f491-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="7f491-165">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="7f491-166">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="7f491-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-167">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-167">What's new</span></span>

- <span data-ttu-id="7f491-168">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7f491-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="7f491-169">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="7f491-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-170">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-170">Known Issues</span></span>
<span data-ttu-id="7f491-171">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="7f491-172">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="7f491-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="7f491-173">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="7f491-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="7f491-174">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="7f491-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="7f491-175">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="7f491-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="7f491-176">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7f491-177">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="7f491-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="7f491-178">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="7f491-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="7f491-179">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="7f491-180">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-181">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-181">What's new</span></span>

- <span data-ttu-id="7f491-182">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="7f491-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="7f491-183">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="7f491-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="7f491-184">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="7f491-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="7f491-185">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="7f491-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="7f491-186">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="7f491-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-187">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-187">Known Issues</span></span>
<span data-ttu-id="7f491-188">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7f491-189">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="7f491-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="7f491-190">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="7f491-191">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="7f491-192">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="7f491-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="7f491-193">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="7f491-194">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-195">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-195">What's new</span></span>

- <span data-ttu-id="7f491-196">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="7f491-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-197">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-197">Known Issues</span></span>
<span data-ttu-id="7f491-198">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7f491-199">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="7f491-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="7f491-200">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="7f491-201">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="7f491-202">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="7f491-203">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="7f491-204">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-205">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-205">What's new</span></span>

- <span data-ttu-id="7f491-206">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="7f491-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="7f491-207">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="7f491-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="7f491-208">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="7f491-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="7f491-209">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="7f491-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-210">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-210">Known Issues</span></span>

<span data-ttu-id="7f491-211">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="7f491-212">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="7f491-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="7f491-213">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="7f491-214">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="7f491-215">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="7f491-216">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="7f491-217">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-218">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-218">What's new</span></span>

- <span data-ttu-id="7f491-219">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="7f491-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="7f491-220">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="7f491-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="7f491-221">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="7f491-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="7f491-222">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="7f491-222">New management interfaces for:</span></span>
   - <span data-ttu-id="7f491-223">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="7f491-223">UDP Inspection</span></span>
   - <span data-ttu-id="7f491-224">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="7f491-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="7f491-225">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="7f491-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="7f491-226">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="7f491-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="7f491-227">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="7f491-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-228">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-228">Known Issues</span></span>

<span data-ttu-id="7f491-229">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="7f491-230">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="7f491-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="7f491-231">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="7f491-232">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="7f491-233">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="7f491-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="7f491-234">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="7f491-235">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="7f491-236">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-236">What's new</span></span>

- <span data-ttu-id="7f491-237">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="7f491-237">Add more telemetry events</span></span>
- <span data-ttu-id="7f491-238">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="7f491-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="7f491-239">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="7f491-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="7f491-240">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="7f491-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="7f491-241">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f491-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="7f491-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="7f491-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="7f491-243">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="7f491-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="7f491-244">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-244">Known Issues</span></span>
<span data-ttu-id="7f491-245">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-246">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="7f491-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="7f491-247">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="7f491-248">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="7f491-249">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="7f491-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="7f491-250">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="7f491-251">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-252">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-252">What's new</span></span>

- <span data-ttu-id="7f491-253">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="7f491-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="7f491-254">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="7f491-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-255">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-255">Known Issues</span></span>
<span data-ttu-id="7f491-256">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-257">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="7f491-258">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="7f491-259">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="7f491-260">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="7f491-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="7f491-261">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="7f491-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="7f491-262">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-263">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-263">What's new</span></span>

- <span data-ttu-id="7f491-264">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="7f491-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="7f491-265">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="7f491-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="7f491-266">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="7f491-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="7f491-267">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="7f491-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="7f491-268">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="7f491-268">Fixed registry query</span></span> 
- <span data-ttu-id="7f491-269">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="7f491-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-270">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-270">Known Issues</span></span>
<span data-ttu-id="7f491-271">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-272">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="7f491-273">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="7f491-274">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="7f491-275">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="7f491-276">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="7f491-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="7f491-277">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-278">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-278">What's new</span></span>

- <span data-ttu-id="7f491-279">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="7f491-279">Improved logging for scan events</span></span>
- <span data-ttu-id="7f491-280">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="7f491-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="7f491-281">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="7f491-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="7f491-282">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="7f491-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="7f491-283">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="7f491-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="7f491-284">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="7f491-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-285">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-285">Known Issues</span></span>
<span data-ttu-id="7f491-286">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-287">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="7f491-288">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="7f491-289">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="7f491-290">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="7f491-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="7f491-291">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="7f491-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="7f491-292">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-293">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-293">What's new</span></span>
- <span data-ttu-id="7f491-294">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="7f491-294">WDfilter improvements</span></span>
- <span data-ttu-id="7f491-295">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="7f491-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="7f491-296">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="7f491-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="7f491-297">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="7f491-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="7f491-298">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="7f491-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="7f491-299">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="7f491-299">UEFI scan capability</span></span>
- <span data-ttu-id="7f491-300">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="7f491-301">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-301">Known Issues</span></span>
<span data-ttu-id="7f491-302">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-303">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="7f491-304">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="7f491-305">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="7f491-306">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="7f491-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="7f491-307">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="7f491-308">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="7f491-309">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-309">What's new</span></span>

- <span data-ttu-id="7f491-310">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7f491-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="7f491-311">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="7f491-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="7f491-312">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="7f491-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="7f491-313">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="7f491-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="7f491-314">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="7f491-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7f491-315">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-315">Known Issues</span></span>
<span data-ttu-id="7f491-316">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="7f491-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="7f491-317">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="7f491-318">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="7f491-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="7f491-319">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="7f491-320">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="7f491-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="7f491-321">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="7f491-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="7f491-322">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7f491-323">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="7f491-324">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-324">Known Issues</span></span>
<span data-ttu-id="7f491-325">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-326">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="7f491-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="7f491-327">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="7f491-328">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="7f491-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="7f491-329">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="7f491-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="7f491-330">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="7f491-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="7f491-331">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="7f491-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="7f491-332">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-332">What's new</span></span>

- <span data-ttu-id="7f491-333">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="7f491-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="7f491-334">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="7f491-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="7f491-335">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7f491-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="7f491-336">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="7f491-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="7f491-337">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="7f491-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7f491-338">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-338">Known Issues</span></span>

<span data-ttu-id="7f491-339">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="7f491-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="7f491-340">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7f491-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="7f491-341">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="7f491-341">This update is:</span></span>
> - <span data-ttu-id="7f491-342">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="7f491-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="7f491-343">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="7f491-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="7f491-344">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="7f491-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="7f491-345">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="7f491-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="7f491-346">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="7f491-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="7f491-347">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="7f491-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="7f491-348">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="7f491-349">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="7f491-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="7f491-350">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="7f491-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="7f491-351">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="7f491-352">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="7f491-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="7f491-353">Nyheter</span><span class="sxs-lookup"><span data-stu-id="7f491-353">What's new</span></span>

- <span data-ttu-id="7f491-354">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="7f491-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="7f491-355">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="7f491-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="7f491-356">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="7f491-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="7f491-357">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="7f491-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="7f491-358">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7f491-358">Known Issues</span></span>
<span data-ttu-id="7f491-359">När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="7f491-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="7f491-360">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="7f491-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="7f491-361">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="7f491-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="7f491-362">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="7f491-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="7f491-363">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="7f491-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="7f491-364">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7f491-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="7f491-365">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="7f491-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="7f491-366">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="7f491-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="7f491-367">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="7f491-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="7f491-368">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="7f491-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="7f491-369">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="7f491-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="7f491-370">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="7f491-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="7f491-371">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="7f491-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="7f491-372">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="7f491-372">Windows 10 release</span></span>  |<span data-ttu-id="7f491-373">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="7f491-373">Platform version</span></span>  |<span data-ttu-id="7f491-374">Motorversion</span><span class="sxs-lookup"><span data-stu-id="7f491-374">Engine version</span></span> |<span data-ttu-id="7f491-375">Supportfas</span><span class="sxs-lookup"><span data-stu-id="7f491-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="7f491-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="7f491-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="7f491-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="7f491-377">4.18.1909.6</span></span> |<span data-ttu-id="7f491-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="7f491-378">1.1.17000.2</span></span> | <span data-ttu-id="7f491-379">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="7f491-380">1909  (19H2)</span></span> |<span data-ttu-id="7f491-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7f491-381">4.18.1902.5</span></span> |<span data-ttu-id="7f491-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="7f491-382">1.1.16700.3</span></span> | <span data-ttu-id="7f491-383">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="7f491-384">1903  (19H1)</span></span> |<span data-ttu-id="7f491-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="7f491-385">4.18.1902.5</span></span> |<span data-ttu-id="7f491-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="7f491-386">1.1.15600.4</span></span> | <span data-ttu-id="7f491-387">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="7f491-388">1809  (RS5)</span></span> |<span data-ttu-id="7f491-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="7f491-389">4.18.1807.18075</span></span> |<span data-ttu-id="7f491-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="7f491-390">1.1.15000.2</span></span> | <span data-ttu-id="7f491-391">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="7f491-392">1803  (RS4)</span></span> |<span data-ttu-id="7f491-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="7f491-393">4.13.17134.1</span></span> |<span data-ttu-id="7f491-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="7f491-394">1.1.14600.4</span></span> | <span data-ttu-id="7f491-395">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="7f491-396">1709  (RS3)</span></span> |<span data-ttu-id="7f491-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="7f491-397">4.12.16299.15</span></span> |<span data-ttu-id="7f491-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="7f491-398">1.1.14104.0</span></span> | <span data-ttu-id="7f491-399">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="7f491-400">1703  (RS2)</span></span> |<span data-ttu-id="7f491-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="7f491-401">4.11.15603.2</span></span> |<span data-ttu-id="7f491-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="7f491-402">1.1.13504.0</span></span> | <span data-ttu-id="7f491-403">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="7f491-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="7f491-404">1607 (RS1)</span></span> |<span data-ttu-id="7f491-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="7f491-405">4.10.14393.3683</span></span> |<span data-ttu-id="7f491-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="7f491-406">1.1.12805.0</span></span> | <span data-ttu-id="7f491-407">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="7f491-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="7f491-408">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="7f491-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="7f491-409">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="7f491-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="7f491-410">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7f491-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="7f491-411">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="7f491-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="7f491-412">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="7f491-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="7f491-413">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="7f491-413">1.1.2106.01</span></span></summary>

<span data-ttu-id="7f491-414">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-414">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="7f491-415">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="7f491-415">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="7f491-416">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7f491-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7f491-417">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-417">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-418">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-418">Fixes</span></span>
- <span data-ttu-id="7f491-419">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-420">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-420">Additional information</span></span>
- <span data-ttu-id="7f491-421">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-422">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="7f491-422">1.1.2105.01</span></span></summary>

<span data-ttu-id="7f491-423">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-423">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="7f491-424">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="7f491-424">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="7f491-425">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="7f491-425">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="7f491-426">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-426">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-427">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-427">Fixes</span></span>
- <span data-ttu-id="7f491-428">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-429">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-429">Additional information</span></span>
- <span data-ttu-id="7f491-430">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-431">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="7f491-431">1.1.2104.01</span></span></summary>

<span data-ttu-id="7f491-432">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-432">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="7f491-433">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="7f491-433">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="7f491-434">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-434">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="7f491-435">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-435">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-436">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-436">Fixes</span></span>
- <span data-ttu-id="7f491-437">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-438">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-438">Additional information</span></span>
- <span data-ttu-id="7f491-439">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-440">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="7f491-440">1.1.2103.01</span></span></summary>

<span data-ttu-id="7f491-441">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-441">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="7f491-442">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="7f491-442">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="7f491-443">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7f491-444">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-444">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-445">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-445">Fixes</span></span>
- <span data-ttu-id="7f491-446">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-447">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-447">Additional information</span></span>
- <span data-ttu-id="7f491-448">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-449">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="7f491-449">1.1.2102.03</span></span></summary>

<span data-ttu-id="7f491-450">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="7f491-450">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="7f491-451">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7f491-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7f491-452">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-452">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="7f491-453">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-453">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-454">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-454">Fixes</span></span>
- <span data-ttu-id="7f491-455">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-456">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-456">Additional information</span></span>
- <span data-ttu-id="7f491-457">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-458">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="7f491-458">1.1.2101.02</span></span></summary>

<span data-ttu-id="7f491-459">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="7f491-459">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="7f491-460">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="7f491-460">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="7f491-461">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="7f491-461">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="7f491-462">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-462">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-463">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-463">Fixes</span></span>
- <span data-ttu-id="7f491-464">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-465">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-465">Additional information</span></span>
- <span data-ttu-id="7f491-466">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-467">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="7f491-467">1.1.2012.01</span></span></summary>

<span data-ttu-id="7f491-468">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-468">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="7f491-469">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7f491-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7f491-470">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7f491-471">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-471">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-472">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-472">Fixes</span></span>
- <span data-ttu-id="7f491-473">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-474">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-474">Additional information</span></span>
- <span data-ttu-id="7f491-475">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-476">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="7f491-476">1.1.2011.02</span></span></summary>

<span data-ttu-id="7f491-477">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="7f491-477">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="7f491-478">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="7f491-478">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="7f491-479">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7f491-480">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-480">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-481">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-481">Fixes</span></span>
- <span data-ttu-id="7f491-482">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-483">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-483">Additional information</span></span>
- <span data-ttu-id="7f491-484">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="7f491-484">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-485">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="7f491-485">1.1.2011.01</span></span></summary>

<span data-ttu-id="7f491-486">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7f491-487">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="7f491-487">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="7f491-488">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-488">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="7f491-489">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-489">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-490">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-490">Fixes</span></span>
- <span data-ttu-id="7f491-491">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-492">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-492">Additional information</span></span>
- <span data-ttu-id="7f491-493">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-493">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="7f491-494">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="7f491-494">1.1.2009.10</span></span></summary>

<span data-ttu-id="7f491-495">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="7f491-495">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="7f491-496">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="7f491-496">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="7f491-497">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="7f491-497">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="7f491-498">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="7f491-498">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="7f491-499">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="7f491-499">Fixes</span></span>
- <span data-ttu-id="7f491-500">Inga</span><span class="sxs-lookup"><span data-stu-id="7f491-500">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="7f491-501">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="7f491-501">Additional information</span></span>
- <span data-ttu-id="7f491-502">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="7f491-502">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="7f491-503">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7f491-503">Additional resources</span></span>

| <span data-ttu-id="7f491-504">Artikel</span><span class="sxs-lookup"><span data-stu-id="7f491-504">Article</span></span> | <span data-ttu-id="7f491-505">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7f491-505">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="7f491-506">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="7f491-506">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="7f491-507">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="7f491-507">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="7f491-508">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="7f491-508">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="7f491-509">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="7f491-509">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7f491-510">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="7f491-510">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="7f491-511">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="7f491-511">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="7f491-512">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="7f491-512">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="7f491-513">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="7f491-513">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="7f491-514">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="7f491-514">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="7f491-515">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="7f491-515">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="7f491-516">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="7f491-516">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="7f491-517">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="7f491-517">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="7f491-518">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="7f491-518">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
