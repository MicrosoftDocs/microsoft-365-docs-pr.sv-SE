---
title: Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer
description: Hantera hur Microsoft Defender Antivirus får skydd och produktuppdateringar.
keywords: uppdateringar, säkerhetsbaslinjer, skydd, schemauppdateringar, tvinga uppdateringar, mobiluppdateringar, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 92f903f750ea5e7f2cb971b535c50bfecced65a2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242318"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="f8d8f-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="f8d8f-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="f8d8f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8d8f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8d8f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="f8d8f-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="f8d8f-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="f8d8f-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="f8d8f-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-109">Security intelligence updates</span></span>
- <span data-ttu-id="f8d8f-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8d8f-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="f8d8f-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="f8d8f-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="f8d8f-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-114">Security intelligence updates</span></span>

<span data-ttu-id="f8d8f-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="f8d8f-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="f8d8f-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="f8d8f-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="f8d8f-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="f8d8f-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="f8d8f-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="f8d8f-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="f8d8f-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="f8d8f-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="f8d8f-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="f8d8f-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-124">Product updates</span></span>

<span data-ttu-id="f8d8f-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="f8d8f-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="f8d8f-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="f8d8f-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="f8d8f-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f8d8f-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="f8d8f-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="f8d8f-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="f8d8f-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="f8d8f-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="f8d8f-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="f8d8f-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="f8d8f-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="f8d8f-134">All our updates contain</span></span> 
- <span data-ttu-id="f8d8f-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-135">performance improvements;</span></span>
- <span data-ttu-id="f8d8f-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="f8d8f-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="f8d8f-137">förbättringar av integreringen (Cloud Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="f8d8f-138">April 2021 (plattform: 4.19.2104.9| Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="f8d8f-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="f8d8f-140">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f8d8f-141">&ensp;Plattform: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="f8d8f-142">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="f8d8f-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-144">What's new</span></span>
- <span data-ttu-id="f8d8f-145">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="f8d8f-146">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="f8d8f-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-147">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-147">Known Issues</span></span>
<span data-ttu-id="f8d8f-148">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-149">Mars-2021 (plattform: 4.19.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="f8d8f-150">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="f8d8f-151">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="f8d8f-152">&ensp;Plattform: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="f8d8f-153">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="f8d8f-154">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-155">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-155">What's new</span></span>

- <span data-ttu-id="f8d8f-156">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="f8d8f-157">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="f8d8f-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="f8d8f-158">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="f8d8f-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-159">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-159">Known Issues</span></span>
<span data-ttu-id="f8d8f-160">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f8d8f-161">Februari-2021 (Plattform: 4.19.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="f8d8f-162">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="f8d8f-163">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="f8d8f-164">&ensp;Plattform: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="f8d8f-165">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="f8d8f-166">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-167">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-167">What's new</span></span>

- <span data-ttu-id="f8d8f-168">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="f8d8f-169">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-170">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-170">Known Issues</span></span>
<span data-ttu-id="f8d8f-171">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="f8d8f-172">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="f8d8f-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="f8d8f-173">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="f8d8f-174">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="f8d8f-175">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="f8d8f-176">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f8d8f-177">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="f8d8f-178">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="f8d8f-179">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="f8d8f-180">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-181">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-181">What's new</span></span>

- <span data-ttu-id="f8d8f-182">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="f8d8f-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="f8d8f-183">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="f8d8f-184">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="f8d8f-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="f8d8f-185">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="f8d8f-186">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="f8d8f-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-187">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-187">Known Issues</span></span>
<span data-ttu-id="f8d8f-188">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f8d8f-189">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="f8d8f-190">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="f8d8f-191">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="f8d8f-192">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="f8d8f-193">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="f8d8f-194">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-195">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-195">What's new</span></span>

- <span data-ttu-id="f8d8f-196">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-197">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-197">Known Issues</span></span>
<span data-ttu-id="f8d8f-198">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f8d8f-199">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="f8d8f-200">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="f8d8f-201">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="f8d8f-202">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="f8d8f-203">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="f8d8f-204">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-205">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-205">What's new</span></span>

- <span data-ttu-id="f8d8f-206">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="f8d8f-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="f8d8f-207">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="f8d8f-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="f8d8f-208">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="f8d8f-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="f8d8f-209">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="f8d8f-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-210">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-210">Known Issues</span></span>

<span data-ttu-id="f8d8f-211">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="f8d8f-212">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="f8d8f-213">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="f8d8f-214">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="f8d8f-215">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="f8d8f-216">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="f8d8f-217">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-218">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-218">What's new</span></span>

- <span data-ttu-id="f8d8f-219">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="f8d8f-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="f8d8f-220">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="f8d8f-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="f8d8f-221">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="f8d8f-222">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-222">New management interfaces for:</span></span>
   - <span data-ttu-id="f8d8f-223">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="f8d8f-223">UDP Inspection</span></span>
   - <span data-ttu-id="f8d8f-224">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="f8d8f-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="f8d8f-225">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="f8d8f-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="f8d8f-226">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="f8d8f-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="f8d8f-227">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-228">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-228">Known Issues</span></span>

<span data-ttu-id="f8d8f-229">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="f8d8f-230">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="f8d8f-231">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="f8d8f-232">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="f8d8f-233">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="f8d8f-234">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="f8d8f-235">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="f8d8f-236">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-236">What's new</span></span>

- <span data-ttu-id="f8d8f-237">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="f8d8f-237">Add more telemetry events</span></span>
- <span data-ttu-id="f8d8f-238">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="f8d8f-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="f8d8f-239">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="f8d8f-240">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="f8d8f-241">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="f8d8f-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="f8d8f-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="f8d8f-243">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="f8d8f-244">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-244">Known Issues</span></span>
<span data-ttu-id="f8d8f-245">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-246">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="f8d8f-247">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="f8d8f-248">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="f8d8f-249">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="f8d8f-250">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="f8d8f-251">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-252">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-252">What's new</span></span>

- <span data-ttu-id="f8d8f-253">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="f8d8f-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="f8d8f-254">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="f8d8f-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-255">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-255">Known Issues</span></span>
<span data-ttu-id="f8d8f-256">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-257">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="f8d8f-258">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="f8d8f-259">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="f8d8f-260">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="f8d8f-261">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="f8d8f-262">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-263">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-263">What's new</span></span>

- <span data-ttu-id="f8d8f-264">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="f8d8f-265">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="f8d8f-266">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="f8d8f-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="f8d8f-267">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="f8d8f-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="f8d8f-268">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="f8d8f-268">Fixed registry query</span></span> 
- <span data-ttu-id="f8d8f-269">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="f8d8f-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-270">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-270">Known Issues</span></span>
<span data-ttu-id="f8d8f-271">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-272">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="f8d8f-273">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="f8d8f-274">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="f8d8f-275">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="f8d8f-276">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="f8d8f-277">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-278">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-278">What's new</span></span>

- <span data-ttu-id="f8d8f-279">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="f8d8f-279">Improved logging for scan events</span></span>
- <span data-ttu-id="f8d8f-280">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="f8d8f-281">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="f8d8f-282">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="f8d8f-283">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="f8d8f-284">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="f8d8f-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-285">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-285">Known Issues</span></span>
<span data-ttu-id="f8d8f-286">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-287">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="f8d8f-288">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="f8d8f-289">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="f8d8f-290">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="f8d8f-291">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="f8d8f-292">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-293">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-293">What's new</span></span>
- <span data-ttu-id="f8d8f-294">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-294">WDfilter improvements</span></span>
- <span data-ttu-id="f8d8f-295">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="f8d8f-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="f8d8f-296">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="f8d8f-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="f8d8f-297">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="f8d8f-298">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="f8d8f-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="f8d8f-299">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="f8d8f-299">UEFI scan capability</span></span>
- <span data-ttu-id="f8d8f-300">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="f8d8f-301">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-301">Known Issues</span></span>
<span data-ttu-id="f8d8f-302">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-303">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="f8d8f-304">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="f8d8f-305">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="f8d8f-306">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="f8d8f-307">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="f8d8f-308">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="f8d8f-309">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-309">What's new</span></span>

- <span data-ttu-id="f8d8f-310">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="f8d8f-311">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="f8d8f-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="f8d8f-312">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="f8d8f-313">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="f8d8f-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="f8d8f-314">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="f8d8f-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f8d8f-315">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-315">Known Issues</span></span>
<span data-ttu-id="f8d8f-316">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="f8d8f-317">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="f8d8f-318">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="f8d8f-319">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="f8d8f-320">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="f8d8f-321">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="f8d8f-322">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f8d8f-323">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="f8d8f-324">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-324">Known Issues</span></span>
<span data-ttu-id="f8d8f-325">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-326">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="f8d8f-327">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="f8d8f-328">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="f8d8f-329">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="f8d8f-330">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="f8d8f-331">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="f8d8f-332">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-332">What's new</span></span>

- <span data-ttu-id="f8d8f-333">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="f8d8f-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="f8d8f-334">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="f8d8f-335">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="f8d8f-336">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="f8d8f-337">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="f8d8f-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f8d8f-338">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-338">Known Issues</span></span>

<span data-ttu-id="f8d8f-339">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="f8d8f-340">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="f8d8f-341">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-341">This update is:</span></span>
> - <span data-ttu-id="f8d8f-342">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="f8d8f-343">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="f8d8f-344">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="f8d8f-345">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="f8d8f-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="f8d8f-346">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="f8d8f-347">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="f8d8f-348">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="f8d8f-349">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="f8d8f-350">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="f8d8f-351">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="f8d8f-352">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="f8d8f-353">Nyheter</span><span class="sxs-lookup"><span data-stu-id="f8d8f-353">What's new</span></span>

- <span data-ttu-id="f8d8f-354">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="f8d8f-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="f8d8f-355">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="f8d8f-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="f8d8f-356">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="f8d8f-357">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="f8d8f-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="f8d8f-358">Kända problem</span><span class="sxs-lookup"><span data-stu-id="f8d8f-358">Known Issues</span></span>
<span data-ttu-id="f8d8f-359">När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="f8d8f-360">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="f8d8f-361">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="f8d8f-362">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="f8d8f-363">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="f8d8f-364">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="f8d8f-365">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="f8d8f-366">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="f8d8f-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="f8d8f-367">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="f8d8f-368">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="f8d8f-369">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="f8d8f-370">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="f8d8f-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="f8d8f-371">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="f8d8f-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="f8d8f-372">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="f8d8f-372">Windows 10 release</span></span>  |<span data-ttu-id="f8d8f-373">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="f8d8f-373">Platform version</span></span>  |<span data-ttu-id="f8d8f-374">Motorversion</span><span class="sxs-lookup"><span data-stu-id="f8d8f-374">Engine version</span></span> |<span data-ttu-id="f8d8f-375">Supportfas</span><span class="sxs-lookup"><span data-stu-id="f8d8f-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="f8d8f-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="f8d8f-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="f8d8f-377">4.18.1909.6</span></span> |<span data-ttu-id="f8d8f-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="f8d8f-378">1.1.17000.2</span></span> | <span data-ttu-id="f8d8f-379">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-380">1909  (19H2)</span></span> |<span data-ttu-id="f8d8f-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f8d8f-381">4.18.1902.5</span></span> |<span data-ttu-id="f8d8f-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="f8d8f-382">1.1.16700.3</span></span> | <span data-ttu-id="f8d8f-383">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-384">1903  (19H1)</span></span> |<span data-ttu-id="f8d8f-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="f8d8f-385">4.18.1902.5</span></span> |<span data-ttu-id="f8d8f-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="f8d8f-386">1.1.15600.4</span></span> | <span data-ttu-id="f8d8f-387">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-388">1809  (RS5)</span></span> |<span data-ttu-id="f8d8f-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="f8d8f-389">4.18.1807.18075</span></span> |<span data-ttu-id="f8d8f-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="f8d8f-390">1.1.15000.2</span></span> | <span data-ttu-id="f8d8f-391">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-392">1803  (RS4)</span></span> |<span data-ttu-id="f8d8f-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="f8d8f-393">4.13.17134.1</span></span> |<span data-ttu-id="f8d8f-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="f8d8f-394">1.1.14600.4</span></span> | <span data-ttu-id="f8d8f-395">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-396">1709  (RS3)</span></span> |<span data-ttu-id="f8d8f-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="f8d8f-397">4.12.16299.15</span></span> |<span data-ttu-id="f8d8f-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="f8d8f-398">1.1.14104.0</span></span> | <span data-ttu-id="f8d8f-399">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-400">1703  (RS2)</span></span> |<span data-ttu-id="f8d8f-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="f8d8f-401">4.11.15603.2</span></span> |<span data-ttu-id="f8d8f-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="f8d8f-402">1.1.13504.0</span></span> | <span data-ttu-id="f8d8f-403">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="f8d8f-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-404">1607 (RS1)</span></span> |<span data-ttu-id="f8d8f-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="f8d8f-405">4.10.14393.3683</span></span> |<span data-ttu-id="f8d8f-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="f8d8f-406">1.1.12805.0</span></span> | <span data-ttu-id="f8d8f-407">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="f8d8f-408">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="f8d8f-409">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="f8d8f-410">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="f8d8f-411">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="f8d8f-412">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="f8d8f-413">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="f8d8f-413">1.1.2104.01</span></span></summary>

<span data-ttu-id="f8d8f-414">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-414">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="f8d8f-415">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-415">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="f8d8f-416">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-416">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="f8d8f-417">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-417">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-418">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-418">Fixes</span></span>
- <span data-ttu-id="f8d8f-419">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-420">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-420">Additional information</span></span>
- <span data-ttu-id="f8d8f-421">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-422">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="f8d8f-422">1.1.2103.01</span></span></summary>

<span data-ttu-id="f8d8f-423">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-423">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="f8d8f-424">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-424">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="f8d8f-425">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-425">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f8d8f-426">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-426">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-427">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-427">Fixes</span></span>
- <span data-ttu-id="f8d8f-428">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-429">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-429">Additional information</span></span>
- <span data-ttu-id="f8d8f-430">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-431">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="f8d8f-431">1.1.2102.03</span></span></summary>

<span data-ttu-id="f8d8f-432">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-432">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="f8d8f-433">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-433">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f8d8f-434">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="f8d8f-435">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-435">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-436">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-436">Fixes</span></span>
- <span data-ttu-id="f8d8f-437">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-438">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-438">Additional information</span></span>
- <span data-ttu-id="f8d8f-439">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-440">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="f8d8f-440">1.1.2101.02</span></span></summary>

<span data-ttu-id="f8d8f-441">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-441">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="f8d8f-442">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="f8d8f-443">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-443">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="f8d8f-444">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-444">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-445">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-445">Fixes</span></span>
- <span data-ttu-id="f8d8f-446">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-447">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-447">Additional information</span></span>
- <span data-ttu-id="f8d8f-448">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-449">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="f8d8f-449">1.1.2012.01</span></span></summary>

<span data-ttu-id="f8d8f-450">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-450">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="f8d8f-451">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-451">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f8d8f-452">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-452">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f8d8f-453">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-453">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-454">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-454">Fixes</span></span>
- <span data-ttu-id="f8d8f-455">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-456">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-456">Additional information</span></span>
- <span data-ttu-id="f8d8f-457">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-458">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="f8d8f-458">1.1.2011.02</span></span></summary>

<span data-ttu-id="f8d8f-459">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-459">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="f8d8f-460">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="f8d8f-461">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f8d8f-462">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-462">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-463">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-463">Fixes</span></span>
- <span data-ttu-id="f8d8f-464">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-465">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-465">Additional information</span></span>
- <span data-ttu-id="f8d8f-466">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="f8d8f-466">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-467">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="f8d8f-467">1.1.2011.01</span></span></summary>

<span data-ttu-id="f8d8f-468">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-468">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f8d8f-469">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-469">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="f8d8f-470">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="f8d8f-471">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-471">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-472">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-472">Fixes</span></span>
- <span data-ttu-id="f8d8f-473">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-474">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-474">Additional information</span></span>
- <span data-ttu-id="f8d8f-475">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="f8d8f-476">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="f8d8f-476">1.1.2009.10</span></span></summary>

<span data-ttu-id="f8d8f-477">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="f8d8f-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="f8d8f-478">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="f8d8f-478">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="f8d8f-479">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-479">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="f8d8f-480">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="f8d8f-480">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="f8d8f-481">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-481">Fixes</span></span>
- <span data-ttu-id="f8d8f-482">Ingen</span><span class="sxs-lookup"><span data-stu-id="f8d8f-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="f8d8f-483">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="f8d8f-483">Additional information</span></span>
- <span data-ttu-id="f8d8f-484">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-484">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="f8d8f-485">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f8d8f-485">Additional resources</span></span>

| <span data-ttu-id="f8d8f-486">Artikel</span><span class="sxs-lookup"><span data-stu-id="f8d8f-486">Article</span></span> | <span data-ttu-id="f8d8f-487">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8d8f-487">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="f8d8f-488">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="f8d8f-488">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="f8d8f-489">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="f8d8f-489">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="f8d8f-490">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-490">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="f8d8f-491">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="f8d8f-491">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f8d8f-492">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-492">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="f8d8f-493">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="f8d8f-493">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="f8d8f-494">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-494">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="f8d8f-495">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="f8d8f-495">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="f8d8f-496">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-496">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="f8d8f-497">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f8d8f-497">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="f8d8f-498">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-498">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="f8d8f-499">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="f8d8f-499">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="f8d8f-500">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="f8d8f-500">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
