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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822280"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="0147d-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="0147d-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="0147d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0147d-105">**Applies to:**</span></span>

- [<span data-ttu-id="0147d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0147d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="0147d-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0147d-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="0147d-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="0147d-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="0147d-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-109">Security intelligence updates</span></span>
- <span data-ttu-id="0147d-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0147d-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="0147d-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="0147d-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="0147d-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="0147d-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="0147d-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-114">Security intelligence updates</span></span>

<span data-ttu-id="0147d-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="0147d-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="0147d-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="0147d-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="0147d-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="0147d-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="0147d-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="0147d-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="0147d-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="0147d-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="0147d-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="0147d-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="0147d-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="0147d-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="0147d-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="0147d-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="0147d-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="0147d-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="0147d-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-124">Product updates</span></span>

<span data-ttu-id="0147d-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="0147d-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="0147d-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="0147d-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="0147d-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="0147d-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="0147d-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0147d-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="0147d-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="0147d-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="0147d-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="0147d-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="0147d-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="0147d-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="0147d-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="0147d-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="0147d-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="0147d-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="0147d-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="0147d-134">All our updates contain</span></span> 
- <span data-ttu-id="0147d-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="0147d-135">performance improvements;</span></span>
- <span data-ttu-id="0147d-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="0147d-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="0147d-137">integreringsförbättringar (Molnet, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="0147d-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="0147d-138">Maj-2021 (plattform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="0147d-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="0147d-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="0147d-140">&ensp;**Utgiven: 4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="0147d-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="0147d-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="0147d-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="0147d-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="0147d-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-144">What's new</span></span>
- <span data-ttu-id="0147d-145">Förbättringar av [beteendeövervakning](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="0147d-146">[Meddelandefiltrering med](network-protection.md) fast nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="0147d-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-147">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-147">Known Issues</span></span>
<span data-ttu-id="0147d-148">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-149">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="0147d-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="0147d-150">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="0147d-151">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="0147d-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="0147d-152">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="0147d-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="0147d-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="0147d-154">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="0147d-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-155">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-155">What's new</span></span>
- <span data-ttu-id="0147d-156">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="0147d-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="0147d-157">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="0147d-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="0147d-158">Nya kontroller för hantering av den gradvisa utrullningsprocessen för [Microsoft Defender-uppdateringar har lagts till](updates.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-159">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-159">Known Issues</span></span>
<span data-ttu-id="0147d-160">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-161">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="0147d-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="0147d-162">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="0147d-163">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="0147d-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="0147d-164">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="0147d-165">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="0147d-166">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="0147d-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-167">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-167">What's new</span></span>

- <span data-ttu-id="0147d-168">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="0147d-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="0147d-169">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="0147d-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="0147d-170">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="0147d-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-171">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-171">Known Issues</span></span>
<span data-ttu-id="0147d-172">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="0147d-173">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="0147d-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="0147d-174">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="0147d-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="0147d-175">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="0147d-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="0147d-176">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="0147d-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="0147d-177">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="0147d-178">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="0147d-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="0147d-179">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="0147d-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="0147d-180">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="0147d-181">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-182">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-182">What's new</span></span>

- <span data-ttu-id="0147d-183">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="0147d-184">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="0147d-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-185">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-185">Known Issues</span></span>
<span data-ttu-id="0147d-186">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-187">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="0147d-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="0147d-188">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="0147d-189">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="0147d-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="0147d-190">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="0147d-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="0147d-191">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="0147d-192">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-193">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-193">What's new</span></span>

- <span data-ttu-id="0147d-194">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="0147d-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="0147d-195">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="0147d-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="0147d-196">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="0147d-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="0147d-197">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="0147d-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="0147d-198">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="0147d-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-199">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-199">Known Issues</span></span>
<span data-ttu-id="0147d-200">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-201">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="0147d-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="0147d-202">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="0147d-203">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="0147d-204">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="0147d-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="0147d-205">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="0147d-206">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-207">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-207">What's new</span></span>

- <span data-ttu-id="0147d-208">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="0147d-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-209">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-209">Known Issues</span></span>
<span data-ttu-id="0147d-210">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-211">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="0147d-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="0147d-212">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="0147d-213">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="0147d-214">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="0147d-215">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="0147d-216">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-217">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-217">What's new</span></span>

- <span data-ttu-id="0147d-218">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="0147d-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="0147d-219">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="0147d-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="0147d-220">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="0147d-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="0147d-221">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="0147d-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-222">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-222">Known Issues</span></span>

<span data-ttu-id="0147d-223">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="0147d-224">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="0147d-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="0147d-225">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="0147d-226">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="0147d-227">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="0147d-228">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="0147d-229">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-230">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-230">What's new</span></span>

- <span data-ttu-id="0147d-231">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="0147d-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="0147d-232">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="0147d-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="0147d-233">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="0147d-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="0147d-234">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="0147d-234">New management interfaces for:</span></span>
   - <span data-ttu-id="0147d-235">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="0147d-235">UDP Inspection</span></span>
   - <span data-ttu-id="0147d-236">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="0147d-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="0147d-237">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="0147d-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="0147d-238">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="0147d-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="0147d-239">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="0147d-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-240">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-240">Known Issues</span></span>

<span data-ttu-id="0147d-241">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="0147d-242">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="0147d-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="0147d-243">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="0147d-244">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="0147d-245">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="0147d-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="0147d-246">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="0147d-247">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="0147d-248">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-248">What's new</span></span>

- <span data-ttu-id="0147d-249">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="0147d-249">Add more telemetry events</span></span>
- <span data-ttu-id="0147d-250">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="0147d-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="0147d-251">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="0147d-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="0147d-252">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="0147d-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="0147d-253">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="0147d-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="0147d-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="0147d-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="0147d-255">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="0147d-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="0147d-256">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-256">Known Issues</span></span>
<span data-ttu-id="0147d-257">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-258">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="0147d-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="0147d-259">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="0147d-260">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="0147d-261">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="0147d-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="0147d-262">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="0147d-263">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-264">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-264">What's new</span></span>

- <span data-ttu-id="0147d-265">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="0147d-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="0147d-266">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="0147d-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-267">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-267">Known Issues</span></span>
<span data-ttu-id="0147d-268">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-269">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="0147d-270">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="0147d-271">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="0147d-272">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="0147d-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="0147d-273">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="0147d-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="0147d-274">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-275">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-275">What's new</span></span>

- <span data-ttu-id="0147d-276">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="0147d-277">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="0147d-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="0147d-278">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="0147d-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="0147d-279">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="0147d-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="0147d-280">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="0147d-280">Fixed registry query</span></span> 
- <span data-ttu-id="0147d-281">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="0147d-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-282">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-282">Known Issues</span></span>
<span data-ttu-id="0147d-283">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-284">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="0147d-285">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="0147d-286">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="0147d-287">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="0147d-288">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="0147d-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="0147d-289">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-290">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-290">What's new</span></span>

- <span data-ttu-id="0147d-291">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="0147d-291">Improved logging for scan events</span></span>
- <span data-ttu-id="0147d-292">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="0147d-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="0147d-293">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="0147d-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="0147d-294">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="0147d-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="0147d-295">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="0147d-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="0147d-296">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="0147d-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-297">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-297">Known Issues</span></span>
<span data-ttu-id="0147d-298">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-299">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="0147d-300">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="0147d-301">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="0147d-302">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="0147d-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="0147d-303">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="0147d-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="0147d-304">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-305">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-305">What's new</span></span>
- <span data-ttu-id="0147d-306">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="0147d-306">WDfilter improvements</span></span>
- <span data-ttu-id="0147d-307">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="0147d-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="0147d-308">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="0147d-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="0147d-309">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="0147d-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="0147d-310">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="0147d-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="0147d-311">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="0147d-311">UEFI scan capability</span></span>
- <span data-ttu-id="0147d-312">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="0147d-313">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-313">Known Issues</span></span>
<span data-ttu-id="0147d-314">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-315">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="0147d-316">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="0147d-317">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="0147d-318">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="0147d-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="0147d-319">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="0147d-320">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="0147d-321">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-321">What's new</span></span>

- <span data-ttu-id="0147d-322">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="0147d-323">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="0147d-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="0147d-324">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="0147d-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="0147d-325">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="0147d-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="0147d-326">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="0147d-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="0147d-327">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-327">Known Issues</span></span>
<span data-ttu-id="0147d-328">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="0147d-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="0147d-329">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="0147d-330">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="0147d-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="0147d-331">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="0147d-332">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="0147d-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="0147d-333">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="0147d-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="0147d-334">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="0147d-335">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="0147d-336">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-336">Known Issues</span></span>
<span data-ttu-id="0147d-337">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-338">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="0147d-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="0147d-339">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="0147d-340">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="0147d-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="0147d-341">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="0147d-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="0147d-342">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="0147d-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="0147d-343">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="0147d-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="0147d-344">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-344">What's new</span></span>

- <span data-ttu-id="0147d-345">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="0147d-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="0147d-346">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="0147d-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="0147d-347">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="0147d-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="0147d-348">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="0147d-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="0147d-349">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="0147d-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="0147d-350">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-350">Known Issues</span></span>

<span data-ttu-id="0147d-351">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="0147d-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="0147d-352">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0147d-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="0147d-353">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="0147d-353">This update is:</span></span>
> - <span data-ttu-id="0147d-354">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="0147d-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="0147d-355">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="0147d-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="0147d-356">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="0147d-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="0147d-357">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="0147d-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="0147d-358">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="0147d-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="0147d-359">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="0147d-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="0147d-360">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="0147d-361">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="0147d-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="0147d-362">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="0147d-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="0147d-363">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="0147d-364">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="0147d-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="0147d-365">Nyheter</span><span class="sxs-lookup"><span data-stu-id="0147d-365">What's new</span></span>

- <span data-ttu-id="0147d-366">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="0147d-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="0147d-367">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="0147d-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="0147d-368">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="0147d-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="0147d-369">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="0147d-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="0147d-370">Kända problem</span><span class="sxs-lookup"><span data-stu-id="0147d-370">Known Issues</span></span>
<span data-ttu-id="0147d-371">När den här uppdateringen är installerad behöver enheten hopppaketet 4.18.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="0147d-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="0147d-372">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="0147d-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="0147d-373">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="0147d-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="0147d-374">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="0147d-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="0147d-375">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="0147d-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="0147d-376">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0147d-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="0147d-377">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="0147d-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="0147d-378">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="0147d-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="0147d-379">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="0147d-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="0147d-380">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="0147d-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="0147d-381">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="0147d-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="0147d-382">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="0147d-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="0147d-383">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="0147d-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="0147d-384">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="0147d-384">Windows 10 release</span></span>  |<span data-ttu-id="0147d-385">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="0147d-385">Platform version</span></span>  |<span data-ttu-id="0147d-386">Motorversion</span><span class="sxs-lookup"><span data-stu-id="0147d-386">Engine version</span></span> |<span data-ttu-id="0147d-387">Supportfas</span><span class="sxs-lookup"><span data-stu-id="0147d-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="0147d-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="0147d-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="0147d-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="0147d-389">4.18.1909.6</span></span> |<span data-ttu-id="0147d-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="0147d-390">1.1.17000.2</span></span> | <span data-ttu-id="0147d-391">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="0147d-392">1909  (19H2)</span></span> |<span data-ttu-id="0147d-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="0147d-393">4.18.1902.5</span></span> |<span data-ttu-id="0147d-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="0147d-394">1.1.16700.3</span></span> | <span data-ttu-id="0147d-395">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="0147d-396">1903  (19H1)</span></span> |<span data-ttu-id="0147d-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="0147d-397">4.18.1902.5</span></span> |<span data-ttu-id="0147d-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="0147d-398">1.1.15600.4</span></span> | <span data-ttu-id="0147d-399">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="0147d-400">1809  (RS5)</span></span> |<span data-ttu-id="0147d-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="0147d-401">4.18.1807.18075</span></span> |<span data-ttu-id="0147d-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="0147d-402">1.1.15000.2</span></span> | <span data-ttu-id="0147d-403">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="0147d-404">1803  (RS4)</span></span> |<span data-ttu-id="0147d-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="0147d-405">4.13.17134.1</span></span> |<span data-ttu-id="0147d-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="0147d-406">1.1.14600.4</span></span> | <span data-ttu-id="0147d-407">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="0147d-408">1709  (RS3)</span></span> |<span data-ttu-id="0147d-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="0147d-409">4.12.16299.15</span></span> |<span data-ttu-id="0147d-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="0147d-410">1.1.14104.0</span></span> | <span data-ttu-id="0147d-411">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="0147d-412">1703  (RS2)</span></span> |<span data-ttu-id="0147d-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="0147d-413">4.11.15603.2</span></span> |<span data-ttu-id="0147d-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="0147d-414">1.1.13504.0</span></span> | <span data-ttu-id="0147d-415">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="0147d-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="0147d-416">1607 (RS1)</span></span> |<span data-ttu-id="0147d-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="0147d-417">4.10.14393.3683</span></span> |<span data-ttu-id="0147d-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="0147d-418">1.1.12805.0</span></span> | <span data-ttu-id="0147d-419">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="0147d-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="0147d-420">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="0147d-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="0147d-421">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="0147d-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="0147d-422">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0147d-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="0147d-423">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="0147d-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="0147d-424">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="0147d-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="0147d-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="0147d-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="0147d-426">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="0147d-427">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="0147d-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="0147d-428">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="0147d-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="0147d-429">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-430">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-430">Fixes</span></span>
- <span data-ttu-id="0147d-431">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-432">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-432">Additional information</span></span>
- <span data-ttu-id="0147d-433">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="0147d-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="0147d-435">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="0147d-436">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="0147d-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="0147d-437">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="0147d-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="0147d-438">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-439">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-439">Fixes</span></span>
- <span data-ttu-id="0147d-440">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-441">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-441">Additional information</span></span>
- <span data-ttu-id="0147d-442">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="0147d-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="0147d-444">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="0147d-445">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="0147d-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="0147d-446">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="0147d-447">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-448">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-448">Fixes</span></span>
- <span data-ttu-id="0147d-449">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-450">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-450">Additional information</span></span>
- <span data-ttu-id="0147d-451">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="0147d-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="0147d-453">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="0147d-454">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="0147d-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="0147d-455">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="0147d-456">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-457">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-457">Fixes</span></span>
- <span data-ttu-id="0147d-458">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-459">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-459">Additional information</span></span>
- <span data-ttu-id="0147d-460">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="0147d-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="0147d-462">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="0147d-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="0147d-463">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="0147d-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="0147d-464">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="0147d-465">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-466">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-466">Fixes</span></span>
- <span data-ttu-id="0147d-467">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-468">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-468">Additional information</span></span>
- <span data-ttu-id="0147d-469">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="0147d-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="0147d-471">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="0147d-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="0147d-472">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="0147d-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="0147d-473">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="0147d-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="0147d-474">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-475">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-475">Fixes</span></span>
- <span data-ttu-id="0147d-476">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-477">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-477">Additional information</span></span>
- <span data-ttu-id="0147d-478">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="0147d-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="0147d-480">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="0147d-481">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="0147d-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="0147d-482">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="0147d-483">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-484">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-484">Fixes</span></span>
- <span data-ttu-id="0147d-485">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-486">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-486">Additional information</span></span>
- <span data-ttu-id="0147d-487">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="0147d-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="0147d-489">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="0147d-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="0147d-490">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="0147d-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="0147d-491">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="0147d-492">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-493">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-493">Fixes</span></span>
- <span data-ttu-id="0147d-494">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-495">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-495">Additional information</span></span>
- <span data-ttu-id="0147d-496">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="0147d-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="0147d-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="0147d-498">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="0147d-499">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="0147d-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="0147d-500">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="0147d-501">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-502">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-502">Fixes</span></span>
- <span data-ttu-id="0147d-503">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-504">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-504">Additional information</span></span>
- <span data-ttu-id="0147d-505">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="0147d-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="0147d-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="0147d-507">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="0147d-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="0147d-508">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="0147d-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="0147d-509">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="0147d-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="0147d-510">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="0147d-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="0147d-511">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="0147d-511">Fixes</span></span>
- <span data-ttu-id="0147d-512">Inga</span><span class="sxs-lookup"><span data-stu-id="0147d-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="0147d-513">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="0147d-513">Additional information</span></span>
- <span data-ttu-id="0147d-514">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="0147d-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="0147d-515">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0147d-515">Additional resources</span></span>

| <span data-ttu-id="0147d-516">Artikel</span><span class="sxs-lookup"><span data-stu-id="0147d-516">Article</span></span> | <span data-ttu-id="0147d-517">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0147d-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="0147d-518">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="0147d-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="0147d-519">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="0147d-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="0147d-520">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="0147d-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="0147d-521">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="0147d-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="0147d-522">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="0147d-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="0147d-523">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="0147d-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="0147d-524">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="0147d-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="0147d-525">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="0147d-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="0147d-526">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="0147d-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="0147d-527">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="0147d-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="0147d-528">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="0147d-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="0147d-529">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="0147d-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="0147d-530">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="0147d-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
