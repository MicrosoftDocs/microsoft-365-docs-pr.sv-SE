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
ms.date: 06/04/2021
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789189"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="fec5f-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="fec5f-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="fec5f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fec5f-105">**Applies to:**</span></span>

- [<span data-ttu-id="fec5f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fec5f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="fec5f-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fec5f-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="fec5f-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="fec5f-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="fec5f-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-109">Security intelligence updates</span></span>
- <span data-ttu-id="fec5f-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fec5f-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="fec5f-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="fec5f-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fec5f-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="fec5f-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fec5f-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="fec5f-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-114">Security intelligence updates</span></span>

<span data-ttu-id="fec5f-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="fec5f-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="fec5f-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="fec5f-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="fec5f-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="fec5f-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="fec5f-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="fec5f-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="fec5f-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="fec5f-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="fec5f-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="fec5f-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="fec5f-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="fec5f-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="fec5f-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fec5f-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="fec5f-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="fec5f-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="fec5f-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-124">Product updates</span></span>

<span data-ttu-id="fec5f-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="fec5f-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="fec5f-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="fec5f-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="fec5f-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="fec5f-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="fec5f-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fec5f-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="fec5f-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="fec5f-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="fec5f-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="fec5f-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="fec5f-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="fec5f-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="fec5f-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="fec5f-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="fec5f-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="fec5f-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="fec5f-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="fec5f-134">All our updates contain</span></span> 
- <span data-ttu-id="fec5f-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-135">performance improvements;</span></span>
- <span data-ttu-id="fec5f-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="fec5f-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="fec5f-137">förbättringar av integreringen (Cloud Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="fec5f-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="fec5f-138">Maj-2021 (plattform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="fec5f-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="fec5f-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="fec5f-140">&ensp;**Utgiven: 4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="fec5f-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="fec5f-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="fec5f-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="fec5f-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="fec5f-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-144">What's new</span></span>
- <span data-ttu-id="fec5f-145">Förbättringar av beteendeövervakning</span><span class="sxs-lookup"><span data-stu-id="fec5f-145">Improvements to behavior monitoring</span></span> 

### <a name="known-issues"></a><span data-ttu-id="fec5f-146">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-146">Known Issues</span></span>
<span data-ttu-id="fec5f-147">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-147">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-148">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-148">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="fec5f-149">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-149">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="fec5f-150">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="fec5f-150">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="fec5f-151">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="fec5f-151">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="fec5f-152">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="fec5f-153">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="fec5f-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-154">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-154">What's new</span></span>
- <span data-ttu-id="fec5f-155">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="fec5f-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="fec5f-156">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="fec5f-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-157">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-157">Known Issues</span></span>
<span data-ttu-id="fec5f-158">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-159">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="fec5f-160">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="fec5f-161">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="fec5f-161">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="fec5f-162">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="fec5f-163">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="fec5f-164">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="fec5f-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-165">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-165">What's new</span></span>

- <span data-ttu-id="fec5f-166">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="fec5f-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="fec5f-167">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="fec5f-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="fec5f-168">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="fec5f-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-169">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-169">Known Issues</span></span>
<span data-ttu-id="fec5f-170">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="fec5f-171">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="fec5f-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="fec5f-172">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="fec5f-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="fec5f-173">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="fec5f-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="fec5f-174">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="fec5f-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="fec5f-175">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="fec5f-176">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="fec5f-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="fec5f-177">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="fec5f-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="fec5f-178">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="fec5f-179">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-180">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-180">What's new</span></span>

- <span data-ttu-id="fec5f-181">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="fec5f-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="fec5f-182">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="fec5f-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-183">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-183">Known Issues</span></span>
<span data-ttu-id="fec5f-184">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-185">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="fec5f-186">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fec5f-187">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="fec5f-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="fec5f-188">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="fec5f-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="fec5f-189">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="fec5f-190">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-191">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-191">What's new</span></span>

- <span data-ttu-id="fec5f-192">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="fec5f-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="fec5f-193">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="fec5f-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="fec5f-194">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="fec5f-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="fec5f-195">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="fec5f-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="fec5f-196">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="fec5f-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-197">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-197">Known Issues</span></span>
<span data-ttu-id="fec5f-198">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-199">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="fec5f-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="fec5f-200">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="fec5f-201">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="fec5f-202">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="fec5f-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="fec5f-203">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="fec5f-204">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-205">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-205">What's new</span></span>

- <span data-ttu-id="fec5f-206">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="fec5f-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-207">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-207">Known Issues</span></span>
<span data-ttu-id="fec5f-208">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-209">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="fec5f-210">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="fec5f-211">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="fec5f-212">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="fec5f-213">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="fec5f-214">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-215">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-215">What's new</span></span>

- <span data-ttu-id="fec5f-216">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="fec5f-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="fec5f-217">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="fec5f-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="fec5f-218">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="fec5f-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="fec5f-219">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="fec5f-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-220">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-220">Known Issues</span></span>

<span data-ttu-id="fec5f-221">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="fec5f-222">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="fec5f-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="fec5f-223">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="fec5f-224">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="fec5f-225">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="fec5f-226">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="fec5f-227">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-228">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-228">What's new</span></span>

- <span data-ttu-id="fec5f-229">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="fec5f-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="fec5f-230">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="fec5f-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="fec5f-231">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="fec5f-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="fec5f-232">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="fec5f-232">New management interfaces for:</span></span>
   - <span data-ttu-id="fec5f-233">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="fec5f-233">UDP Inspection</span></span>
   - <span data-ttu-id="fec5f-234">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="fec5f-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="fec5f-235">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fec5f-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="fec5f-236">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="fec5f-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="fec5f-237">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="fec5f-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-238">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-238">Known Issues</span></span>

<span data-ttu-id="fec5f-239">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="fec5f-240">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="fec5f-241">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="fec5f-242">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="fec5f-243">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="fec5f-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="fec5f-244">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="fec5f-245">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="fec5f-246">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-246">What's new</span></span>

- <span data-ttu-id="fec5f-247">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="fec5f-247">Add more telemetry events</span></span>
- <span data-ttu-id="fec5f-248">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="fec5f-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="fec5f-249">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="fec5f-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="fec5f-250">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="fec5f-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="fec5f-251">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="fec5f-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="fec5f-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="fec5f-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="fec5f-253">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="fec5f-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="fec5f-254">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-254">Known Issues</span></span>
<span data-ttu-id="fec5f-255">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-256">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="fec5f-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="fec5f-257">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="fec5f-258">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="fec5f-259">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="fec5f-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="fec5f-260">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="fec5f-261">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-262">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-262">What's new</span></span>

- <span data-ttu-id="fec5f-263">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="fec5f-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="fec5f-264">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="fec5f-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-265">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-265">Known Issues</span></span>
<span data-ttu-id="fec5f-266">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-267">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="fec5f-268">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="fec5f-269">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="fec5f-270">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="fec5f-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="fec5f-271">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="fec5f-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="fec5f-272">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-273">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-273">What's new</span></span>

- <span data-ttu-id="fec5f-274">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="fec5f-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="fec5f-275">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="fec5f-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="fec5f-276">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="fec5f-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="fec5f-277">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="fec5f-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="fec5f-278">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="fec5f-278">Fixed registry query</span></span> 
- <span data-ttu-id="fec5f-279">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="fec5f-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-280">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-280">Known Issues</span></span>
<span data-ttu-id="fec5f-281">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-282">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="fec5f-283">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="fec5f-284">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="fec5f-285">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="fec5f-286">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="fec5f-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="fec5f-287">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-288">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-288">What's new</span></span>

- <span data-ttu-id="fec5f-289">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="fec5f-289">Improved logging for scan events</span></span>
- <span data-ttu-id="fec5f-290">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="fec5f-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="fec5f-291">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="fec5f-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="fec5f-292">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="fec5f-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="fec5f-293">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="fec5f-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="fec5f-294">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="fec5f-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-295">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-295">Known Issues</span></span>
<span data-ttu-id="fec5f-296">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-297">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="fec5f-298">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="fec5f-299">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="fec5f-300">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="fec5f-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="fec5f-301">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="fec5f-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="fec5f-302">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-303">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-303">What's new</span></span>
- <span data-ttu-id="fec5f-304">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-304">WDfilter improvements</span></span>
- <span data-ttu-id="fec5f-305">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="fec5f-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="fec5f-306">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="fec5f-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="fec5f-307">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="fec5f-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="fec5f-308">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="fec5f-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="fec5f-309">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="fec5f-309">UEFI scan capability</span></span>
- <span data-ttu-id="fec5f-310">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="fec5f-311">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-311">Known Issues</span></span>
<span data-ttu-id="fec5f-312">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-313">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="fec5f-314">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="fec5f-315">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="fec5f-316">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="fec5f-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="fec5f-317">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="fec5f-318">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="fec5f-319">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-319">What's new</span></span>

- <span data-ttu-id="fec5f-320">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fec5f-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="fec5f-321">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="fec5f-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="fec5f-322">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="fec5f-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="fec5f-323">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="fec5f-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="fec5f-324">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="fec5f-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fec5f-325">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-325">Known Issues</span></span>
<span data-ttu-id="fec5f-326">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="fec5f-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="fec5f-327">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="fec5f-328">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="fec5f-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="fec5f-329">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="fec5f-330">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="fec5f-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="fec5f-331">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="fec5f-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="fec5f-332">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fec5f-333">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="fec5f-334">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-334">Known Issues</span></span>
<span data-ttu-id="fec5f-335">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-336">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="fec5f-337">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="fec5f-338">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="fec5f-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="fec5f-339">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="fec5f-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="fec5f-340">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="fec5f-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="fec5f-341">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="fec5f-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="fec5f-342">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-342">What's new</span></span>

- <span data-ttu-id="fec5f-343">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="fec5f-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="fec5f-344">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="fec5f-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="fec5f-345">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="fec5f-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="fec5f-346">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="fec5f-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="fec5f-347">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="fec5f-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fec5f-348">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-348">Known Issues</span></span>

<span data-ttu-id="fec5f-349">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="fec5f-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="fec5f-350">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fec5f-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="fec5f-351">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="fec5f-351">This update is:</span></span>
> - <span data-ttu-id="fec5f-352">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="fec5f-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="fec5f-353">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="fec5f-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="fec5f-354">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="fec5f-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="fec5f-355">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="fec5f-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="fec5f-356">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="fec5f-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="fec5f-357">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="fec5f-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="fec5f-358">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="fec5f-359">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="fec5f-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="fec5f-360">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="fec5f-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="fec5f-361">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="fec5f-362">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="fec5f-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="fec5f-363">Nyheter</span><span class="sxs-lookup"><span data-stu-id="fec5f-363">What's new</span></span>

- <span data-ttu-id="fec5f-364">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="fec5f-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="fec5f-365">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="fec5f-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="fec5f-366">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="fec5f-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="fec5f-367">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="fec5f-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="fec5f-368">Kända problem</span><span class="sxs-lookup"><span data-stu-id="fec5f-368">Known Issues</span></span>
<span data-ttu-id="fec5f-369">När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="fec5f-369">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="fec5f-370">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="fec5f-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="fec5f-371">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="fec5f-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="fec5f-372">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="fec5f-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="fec5f-373">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="fec5f-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="fec5f-374">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fec5f-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="fec5f-375">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="fec5f-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="fec5f-376">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="fec5f-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="fec5f-377">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="fec5f-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="fec5f-378">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="fec5f-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="fec5f-379">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="fec5f-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="fec5f-380">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="fec5f-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="fec5f-381">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="fec5f-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="fec5f-382">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="fec5f-382">Windows 10 release</span></span>  |<span data-ttu-id="fec5f-383">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="fec5f-383">Platform version</span></span>  |<span data-ttu-id="fec5f-384">Motorversion</span><span class="sxs-lookup"><span data-stu-id="fec5f-384">Engine version</span></span> |<span data-ttu-id="fec5f-385">Supportfas</span><span class="sxs-lookup"><span data-stu-id="fec5f-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="fec5f-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="fec5f-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="fec5f-387">4.18.1909.6</span></span> |<span data-ttu-id="fec5f-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="fec5f-388">1.1.17000.2</span></span> | <span data-ttu-id="fec5f-389">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-390">1909  (19H2)</span></span> |<span data-ttu-id="fec5f-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fec5f-391">4.18.1902.5</span></span> |<span data-ttu-id="fec5f-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="fec5f-392">1.1.16700.3</span></span> | <span data-ttu-id="fec5f-393">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="fec5f-394">1903  (19H1)</span></span> |<span data-ttu-id="fec5f-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="fec5f-395">4.18.1902.5</span></span> |<span data-ttu-id="fec5f-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="fec5f-396">1.1.15600.4</span></span> | <span data-ttu-id="fec5f-397">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="fec5f-398">1809  (RS5)</span></span> |<span data-ttu-id="fec5f-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="fec5f-399">4.18.1807.18075</span></span> |<span data-ttu-id="fec5f-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="fec5f-400">1.1.15000.2</span></span> | <span data-ttu-id="fec5f-401">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="fec5f-402">1803  (RS4)</span></span> |<span data-ttu-id="fec5f-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="fec5f-403">4.13.17134.1</span></span> |<span data-ttu-id="fec5f-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="fec5f-404">1.1.14600.4</span></span> | <span data-ttu-id="fec5f-405">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="fec5f-406">1709  (RS3)</span></span> |<span data-ttu-id="fec5f-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="fec5f-407">4.12.16299.15</span></span> |<span data-ttu-id="fec5f-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="fec5f-408">1.1.14104.0</span></span> | <span data-ttu-id="fec5f-409">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="fec5f-410">1703  (RS2)</span></span> |<span data-ttu-id="fec5f-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="fec5f-411">4.11.15603.2</span></span> |<span data-ttu-id="fec5f-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="fec5f-412">1.1.13504.0</span></span> | <span data-ttu-id="fec5f-413">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="fec5f-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="fec5f-414">1607 (RS1)</span></span> |<span data-ttu-id="fec5f-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="fec5f-415">4.10.14393.3683</span></span> |<span data-ttu-id="fec5f-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="fec5f-416">1.1.12805.0</span></span> | <span data-ttu-id="fec5f-417">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="fec5f-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="fec5f-418">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="fec5f-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="fec5f-419">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="fec5f-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="fec5f-420">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="fec5f-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="fec5f-421">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="fec5f-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="fec5f-422">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="fec5f-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="fec5f-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="fec5f-424">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="fec5f-425">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="fec5f-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="fec5f-426">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fec5f-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fec5f-427">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-428">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-428">Fixes</span></span>
- <span data-ttu-id="fec5f-429">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-430">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-430">Additional information</span></span>
- <span data-ttu-id="fec5f-431">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="fec5f-433">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="fec5f-434">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="fec5f-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="fec5f-435">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="fec5f-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="fec5f-436">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-437">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-437">Fixes</span></span>
- <span data-ttu-id="fec5f-438">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-439">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-439">Additional information</span></span>
- <span data-ttu-id="fec5f-440">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="fec5f-442">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="fec5f-443">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="fec5f-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="fec5f-444">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="fec5f-445">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-446">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-446">Fixes</span></span>
- <span data-ttu-id="fec5f-447">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-448">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-448">Additional information</span></span>
- <span data-ttu-id="fec5f-449">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="fec5f-451">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="fec5f-452">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="fec5f-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="fec5f-453">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fec5f-454">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-455">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-455">Fixes</span></span>
- <span data-ttu-id="fec5f-456">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-457">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-457">Additional information</span></span>
- <span data-ttu-id="fec5f-458">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="fec5f-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="fec5f-460">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="fec5f-461">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fec5f-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fec5f-462">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="fec5f-463">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-464">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-464">Fixes</span></span>
- <span data-ttu-id="fec5f-465">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-466">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-466">Additional information</span></span>
- <span data-ttu-id="fec5f-467">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="fec5f-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="fec5f-469">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="fec5f-470">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="fec5f-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="fec5f-471">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="fec5f-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="fec5f-472">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-473">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-473">Fixes</span></span>
- <span data-ttu-id="fec5f-474">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-475">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-475">Additional information</span></span>
- <span data-ttu-id="fec5f-476">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="fec5f-478">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="fec5f-479">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fec5f-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fec5f-480">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fec5f-481">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-482">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-482">Fixes</span></span>
- <span data-ttu-id="fec5f-483">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-484">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-484">Additional information</span></span>
- <span data-ttu-id="fec5f-485">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="fec5f-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="fec5f-487">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="fec5f-488">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="fec5f-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="fec5f-489">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fec5f-490">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-491">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-491">Fixes</span></span>
- <span data-ttu-id="fec5f-492">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-493">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-493">Additional information</span></span>
- <span data-ttu-id="fec5f-494">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="fec5f-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="fec5f-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="fec5f-496">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fec5f-497">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="fec5f-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="fec5f-498">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="fec5f-499">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-500">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-500">Fixes</span></span>
- <span data-ttu-id="fec5f-501">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-502">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-502">Additional information</span></span>
- <span data-ttu-id="fec5f-503">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="fec5f-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="fec5f-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="fec5f-505">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="fec5f-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="fec5f-506">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="fec5f-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="fec5f-507">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="fec5f-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="fec5f-508">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="fec5f-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="fec5f-509">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-509">Fixes</span></span>
- <span data-ttu-id="fec5f-510">Inga</span><span class="sxs-lookup"><span data-stu-id="fec5f-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="fec5f-511">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="fec5f-511">Additional information</span></span>
- <span data-ttu-id="fec5f-512">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="fec5f-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="fec5f-513">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fec5f-513">Additional resources</span></span>

| <span data-ttu-id="fec5f-514">Artikel</span><span class="sxs-lookup"><span data-stu-id="fec5f-514">Article</span></span> | <span data-ttu-id="fec5f-515">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fec5f-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="fec5f-516">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="fec5f-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="fec5f-517">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="fec5f-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="fec5f-518">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="fec5f-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="fec5f-519">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="fec5f-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fec5f-520">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="fec5f-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="fec5f-521">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="fec5f-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="fec5f-522">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="fec5f-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="fec5f-523">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="fec5f-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="fec5f-524">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="fec5f-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="fec5f-525">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="fec5f-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="fec5f-526">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="fec5f-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="fec5f-527">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="fec5f-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="fec5f-528">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="fec5f-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
