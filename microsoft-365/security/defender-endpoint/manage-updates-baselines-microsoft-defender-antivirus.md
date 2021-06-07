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
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795988"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="073b7-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="073b7-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="073b7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="073b7-105">**Applies to:**</span></span>

- [<span data-ttu-id="073b7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="073b7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="073b7-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="073b7-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="073b7-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="073b7-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="073b7-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-109">Security intelligence updates</span></span>
- <span data-ttu-id="073b7-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="073b7-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="073b7-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="073b7-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="073b7-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="073b7-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="073b7-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-114">Security intelligence updates</span></span>

<span data-ttu-id="073b7-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="073b7-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="073b7-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="073b7-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="073b7-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="073b7-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="073b7-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="073b7-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="073b7-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="073b7-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="073b7-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="073b7-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="073b7-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="073b7-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="073b7-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="073b7-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="073b7-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="073b7-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="073b7-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-124">Product updates</span></span>

<span data-ttu-id="073b7-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="073b7-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="073b7-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="073b7-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="073b7-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="073b7-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="073b7-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="073b7-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="073b7-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="073b7-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="073b7-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="073b7-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="073b7-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="073b7-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="073b7-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="073b7-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="073b7-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="073b7-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="073b7-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="073b7-134">All our updates contain</span></span> 
- <span data-ttu-id="073b7-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="073b7-135">performance improvements;</span></span>
- <span data-ttu-id="073b7-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="073b7-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="073b7-137">integreringsförbättringar (Molnet, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="073b7-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="073b7-138">Maj-2021 (plattform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="073b7-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="073b7-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="073b7-140">&ensp;**Utgiven: 4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="073b7-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="073b7-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="073b7-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="073b7-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="073b7-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-144">What's new</span></span>
- <span data-ttu-id="073b7-145">Förbättringar av [beteendeövervakning](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="073b7-146">[Meddelandefiltrering med](network-protection.md) fast nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="073b7-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-147">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-147">Known Issues</span></span>
<span data-ttu-id="073b7-148">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-149">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="073b7-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="073b7-150">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="073b7-151">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="073b7-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="073b7-152">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="073b7-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="073b7-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="073b7-154">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="073b7-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-155">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-155">What's new</span></span>
- <span data-ttu-id="073b7-156">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="073b7-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="073b7-157">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="073b7-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-158">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-158">Known Issues</span></span>
<span data-ttu-id="073b7-159">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-160">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="073b7-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="073b7-161">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="073b7-162">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="073b7-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="073b7-163">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="073b7-164">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="073b7-165">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="073b7-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-166">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-166">What's new</span></span>

- <span data-ttu-id="073b7-167">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="073b7-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="073b7-168">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="073b7-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="073b7-169">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="073b7-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-170">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-170">Known Issues</span></span>
<span data-ttu-id="073b7-171">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="073b7-172">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="073b7-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="073b7-173">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="073b7-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="073b7-174">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="073b7-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="073b7-175">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="073b7-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="073b7-176">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="073b7-177">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="073b7-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="073b7-178">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="073b7-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="073b7-179">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="073b7-180">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-181">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-181">What's new</span></span>

- <span data-ttu-id="073b7-182">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="073b7-183">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="073b7-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-184">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-184">Known Issues</span></span>
<span data-ttu-id="073b7-185">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-186">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="073b7-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="073b7-187">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="073b7-188">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="073b7-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="073b7-189">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="073b7-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="073b7-190">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="073b7-191">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-192">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-192">What's new</span></span>

- <span data-ttu-id="073b7-193">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="073b7-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="073b7-194">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="073b7-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="073b7-195">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="073b7-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="073b7-196">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="073b7-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="073b7-197">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="073b7-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-198">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-198">Known Issues</span></span>
<span data-ttu-id="073b7-199">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-200">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="073b7-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="073b7-201">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="073b7-202">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="073b7-203">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="073b7-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="073b7-204">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="073b7-205">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-206">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-206">What's new</span></span>

- <span data-ttu-id="073b7-207">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="073b7-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-208">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-208">Known Issues</span></span>
<span data-ttu-id="073b7-209">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-210">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="073b7-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="073b7-211">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="073b7-212">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="073b7-213">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="073b7-214">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="073b7-215">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-216">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-216">What's new</span></span>

- <span data-ttu-id="073b7-217">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="073b7-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="073b7-218">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="073b7-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="073b7-219">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="073b7-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="073b7-220">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="073b7-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-221">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-221">Known Issues</span></span>

<span data-ttu-id="073b7-222">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="073b7-223">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="073b7-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="073b7-224">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="073b7-225">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="073b7-226">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="073b7-227">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="073b7-228">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-229">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-229">What's new</span></span>

- <span data-ttu-id="073b7-230">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="073b7-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="073b7-231">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="073b7-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="073b7-232">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="073b7-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="073b7-233">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="073b7-233">New management interfaces for:</span></span>
   - <span data-ttu-id="073b7-234">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="073b7-234">UDP Inspection</span></span>
   - <span data-ttu-id="073b7-235">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="073b7-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="073b7-236">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="073b7-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="073b7-237">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="073b7-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="073b7-238">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="073b7-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-239">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-239">Known Issues</span></span>

<span data-ttu-id="073b7-240">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="073b7-241">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="073b7-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="073b7-242">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="073b7-243">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="073b7-244">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="073b7-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="073b7-245">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="073b7-246">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="073b7-247">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-247">What's new</span></span>

- <span data-ttu-id="073b7-248">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="073b7-248">Add more telemetry events</span></span>
- <span data-ttu-id="073b7-249">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="073b7-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="073b7-250">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="073b7-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="073b7-251">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="073b7-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="073b7-252">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="073b7-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="073b7-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="073b7-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="073b7-254">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="073b7-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="073b7-255">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-255">Known Issues</span></span>
<span data-ttu-id="073b7-256">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-257">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="073b7-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="073b7-258">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="073b7-259">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="073b7-260">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="073b7-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="073b7-261">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="073b7-262">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-263">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-263">What's new</span></span>

- <span data-ttu-id="073b7-264">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="073b7-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="073b7-265">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="073b7-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-266">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-266">Known Issues</span></span>
<span data-ttu-id="073b7-267">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-268">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="073b7-269">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="073b7-270">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="073b7-271">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="073b7-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="073b7-272">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="073b7-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="073b7-273">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-274">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-274">What's new</span></span>

- <span data-ttu-id="073b7-275">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="073b7-276">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="073b7-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="073b7-277">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="073b7-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="073b7-278">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="073b7-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="073b7-279">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="073b7-279">Fixed registry query</span></span> 
- <span data-ttu-id="073b7-280">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="073b7-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-281">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-281">Known Issues</span></span>
<span data-ttu-id="073b7-282">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-283">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="073b7-284">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="073b7-285">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="073b7-286">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="073b7-287">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="073b7-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="073b7-288">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-289">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-289">What's new</span></span>

- <span data-ttu-id="073b7-290">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="073b7-290">Improved logging for scan events</span></span>
- <span data-ttu-id="073b7-291">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="073b7-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="073b7-292">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="073b7-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="073b7-293">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="073b7-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="073b7-294">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="073b7-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="073b7-295">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="073b7-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-296">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-296">Known Issues</span></span>
<span data-ttu-id="073b7-297">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-298">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="073b7-299">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="073b7-300">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="073b7-301">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="073b7-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="073b7-302">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="073b7-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="073b7-303">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-304">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-304">What's new</span></span>
- <span data-ttu-id="073b7-305">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="073b7-305">WDfilter improvements</span></span>
- <span data-ttu-id="073b7-306">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="073b7-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="073b7-307">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="073b7-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="073b7-308">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="073b7-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="073b7-309">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="073b7-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="073b7-310">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="073b7-310">UEFI scan capability</span></span>
- <span data-ttu-id="073b7-311">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="073b7-312">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-312">Known Issues</span></span>
<span data-ttu-id="073b7-313">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-314">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="073b7-315">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="073b7-316">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="073b7-317">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="073b7-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="073b7-318">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="073b7-319">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="073b7-320">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-320">What's new</span></span>

- <span data-ttu-id="073b7-321">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="073b7-322">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="073b7-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="073b7-323">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="073b7-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="073b7-324">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="073b7-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="073b7-325">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="073b7-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="073b7-326">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-326">Known Issues</span></span>
<span data-ttu-id="073b7-327">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="073b7-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="073b7-328">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="073b7-329">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="073b7-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="073b7-330">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="073b7-331">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="073b7-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="073b7-332">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="073b7-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="073b7-333">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="073b7-334">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="073b7-335">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-335">Known Issues</span></span>
<span data-ttu-id="073b7-336">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-337">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="073b7-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="073b7-338">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="073b7-339">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="073b7-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="073b7-340">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="073b7-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="073b7-341">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="073b7-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="073b7-342">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="073b7-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="073b7-343">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-343">What's new</span></span>

- <span data-ttu-id="073b7-344">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="073b7-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="073b7-345">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="073b7-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="073b7-346">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="073b7-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="073b7-347">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="073b7-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="073b7-348">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="073b7-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="073b7-349">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-349">Known Issues</span></span>

<span data-ttu-id="073b7-350">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="073b7-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="073b7-351">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="073b7-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="073b7-352">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="073b7-352">This update is:</span></span>
> - <span data-ttu-id="073b7-353">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="073b7-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="073b7-354">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="073b7-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="073b7-355">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="073b7-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="073b7-356">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="073b7-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="073b7-357">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="073b7-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="073b7-358">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="073b7-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="073b7-359">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="073b7-360">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="073b7-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="073b7-361">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="073b7-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="073b7-362">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="073b7-363">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="073b7-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="073b7-364">Nyheter</span><span class="sxs-lookup"><span data-stu-id="073b7-364">What's new</span></span>

- <span data-ttu-id="073b7-365">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="073b7-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="073b7-366">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="073b7-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="073b7-367">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="073b7-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="073b7-368">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="073b7-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="073b7-369">Kända problem</span><span class="sxs-lookup"><span data-stu-id="073b7-369">Known Issues</span></span>
<span data-ttu-id="073b7-370">När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="073b7-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="073b7-371">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="073b7-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="073b7-372">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="073b7-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="073b7-373">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="073b7-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="073b7-374">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="073b7-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="073b7-375">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="073b7-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="073b7-376">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="073b7-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="073b7-377">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="073b7-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="073b7-378">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="073b7-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="073b7-379">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="073b7-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="073b7-380">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="073b7-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="073b7-381">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="073b7-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="073b7-382">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="073b7-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="073b7-383">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="073b7-383">Windows 10 release</span></span>  |<span data-ttu-id="073b7-384">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="073b7-384">Platform version</span></span>  |<span data-ttu-id="073b7-385">Motorversion</span><span class="sxs-lookup"><span data-stu-id="073b7-385">Engine version</span></span> |<span data-ttu-id="073b7-386">Supportfas</span><span class="sxs-lookup"><span data-stu-id="073b7-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="073b7-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="073b7-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="073b7-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="073b7-388">4.18.1909.6</span></span> |<span data-ttu-id="073b7-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="073b7-389">1.1.17000.2</span></span> | <span data-ttu-id="073b7-390">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="073b7-391">1909  (19H2)</span></span> |<span data-ttu-id="073b7-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="073b7-392">4.18.1902.5</span></span> |<span data-ttu-id="073b7-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="073b7-393">1.1.16700.3</span></span> | <span data-ttu-id="073b7-394">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="073b7-395">1903  (19H1)</span></span> |<span data-ttu-id="073b7-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="073b7-396">4.18.1902.5</span></span> |<span data-ttu-id="073b7-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="073b7-397">1.1.15600.4</span></span> | <span data-ttu-id="073b7-398">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="073b7-399">1809  (RS5)</span></span> |<span data-ttu-id="073b7-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="073b7-400">4.18.1807.18075</span></span> |<span data-ttu-id="073b7-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="073b7-401">1.1.15000.2</span></span> | <span data-ttu-id="073b7-402">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="073b7-403">1803  (RS4)</span></span> |<span data-ttu-id="073b7-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="073b7-404">4.13.17134.1</span></span> |<span data-ttu-id="073b7-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="073b7-405">1.1.14600.4</span></span> | <span data-ttu-id="073b7-406">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="073b7-407">1709  (RS3)</span></span> |<span data-ttu-id="073b7-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="073b7-408">4.12.16299.15</span></span> |<span data-ttu-id="073b7-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="073b7-409">1.1.14104.0</span></span> | <span data-ttu-id="073b7-410">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="073b7-411">1703  (RS2)</span></span> |<span data-ttu-id="073b7-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="073b7-412">4.11.15603.2</span></span> |<span data-ttu-id="073b7-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="073b7-413">1.1.13504.0</span></span> | <span data-ttu-id="073b7-414">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="073b7-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="073b7-415">1607 (RS1)</span></span> |<span data-ttu-id="073b7-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="073b7-416">4.10.14393.3683</span></span> |<span data-ttu-id="073b7-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="073b7-417">1.1.12805.0</span></span> | <span data-ttu-id="073b7-418">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="073b7-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="073b7-419">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="073b7-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="073b7-420">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="073b7-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="073b7-421">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="073b7-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="073b7-422">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="073b7-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="073b7-423">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="073b7-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="073b7-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="073b7-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="073b7-425">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="073b7-426">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="073b7-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="073b7-427">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="073b7-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="073b7-428">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-429">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-429">Fixes</span></span>
- <span data-ttu-id="073b7-430">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-431">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-431">Additional information</span></span>
- <span data-ttu-id="073b7-432">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="073b7-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="073b7-434">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="073b7-435">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="073b7-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="073b7-436">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="073b7-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="073b7-437">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-438">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-438">Fixes</span></span>
- <span data-ttu-id="073b7-439">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-440">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-440">Additional information</span></span>
- <span data-ttu-id="073b7-441">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="073b7-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="073b7-443">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="073b7-444">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="073b7-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="073b7-445">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="073b7-446">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-447">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-447">Fixes</span></span>
- <span data-ttu-id="073b7-448">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-449">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-449">Additional information</span></span>
- <span data-ttu-id="073b7-450">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="073b7-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="073b7-452">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="073b7-453">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="073b7-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="073b7-454">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="073b7-455">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-456">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-456">Fixes</span></span>
- <span data-ttu-id="073b7-457">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-458">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-458">Additional information</span></span>
- <span data-ttu-id="073b7-459">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="073b7-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="073b7-461">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="073b7-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="073b7-462">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="073b7-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="073b7-463">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="073b7-464">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-465">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-465">Fixes</span></span>
- <span data-ttu-id="073b7-466">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-467">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-467">Additional information</span></span>
- <span data-ttu-id="073b7-468">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="073b7-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="073b7-470">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="073b7-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="073b7-471">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="073b7-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="073b7-472">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="073b7-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="073b7-473">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-474">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-474">Fixes</span></span>
- <span data-ttu-id="073b7-475">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-476">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-476">Additional information</span></span>
- <span data-ttu-id="073b7-477">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="073b7-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="073b7-479">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="073b7-480">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="073b7-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="073b7-481">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="073b7-482">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-483">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-483">Fixes</span></span>
- <span data-ttu-id="073b7-484">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-485">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-485">Additional information</span></span>
- <span data-ttu-id="073b7-486">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="073b7-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="073b7-488">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="073b7-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="073b7-489">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="073b7-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="073b7-490">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="073b7-491">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-492">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-492">Fixes</span></span>
- <span data-ttu-id="073b7-493">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-494">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-494">Additional information</span></span>
- <span data-ttu-id="073b7-495">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="073b7-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="073b7-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="073b7-497">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="073b7-498">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="073b7-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="073b7-499">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="073b7-500">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-501">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-501">Fixes</span></span>
- <span data-ttu-id="073b7-502">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-503">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-503">Additional information</span></span>
- <span data-ttu-id="073b7-504">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="073b7-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="073b7-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="073b7-506">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="073b7-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="073b7-507">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="073b7-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="073b7-508">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="073b7-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="073b7-509">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="073b7-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="073b7-510">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="073b7-510">Fixes</span></span>
- <span data-ttu-id="073b7-511">Inga</span><span class="sxs-lookup"><span data-stu-id="073b7-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="073b7-512">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="073b7-512">Additional information</span></span>
- <span data-ttu-id="073b7-513">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="073b7-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="073b7-514">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="073b7-514">Additional resources</span></span>

| <span data-ttu-id="073b7-515">Artikel</span><span class="sxs-lookup"><span data-stu-id="073b7-515">Article</span></span> | <span data-ttu-id="073b7-516">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="073b7-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="073b7-517">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="073b7-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="073b7-518">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="073b7-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="073b7-519">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="073b7-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="073b7-520">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="073b7-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="073b7-521">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="073b7-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="073b7-522">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="073b7-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="073b7-523">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="073b7-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="073b7-524">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="073b7-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="073b7-525">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="073b7-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="073b7-526">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="073b7-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="073b7-527">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="073b7-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="073b7-528">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="073b7-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="073b7-529">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="073b7-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
