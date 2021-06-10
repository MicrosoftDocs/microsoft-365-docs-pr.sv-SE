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
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ea82e-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="ea82e-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ea82e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ea82e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ea82e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ea82e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ea82e-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ea82e-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ea82e-108">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="ea82e-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ea82e-109">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-109">Security intelligence updates</span></span>
- <span data-ttu-id="ea82e-110">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea82e-111">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="ea82e-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="ea82e-112">Se till att uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="ea82e-113">Du kan se de mest aktuella motor-, plattforms- och signaturdatumen i Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ea82e-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ea82e-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-114">Security intelligence updates</span></span>

<span data-ttu-id="ea82e-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="ea82e-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ea82e-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="ea82e-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="ea82e-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="ea82e-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="ea82e-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="ea82e-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ea82e-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="ea82e-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ea82e-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="ea82e-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ea82e-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="ea82e-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ea82e-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ea82e-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ea82e-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="ea82e-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ea82e-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-124">Product updates</span></span>

<span data-ttu-id="ea82e-125">Microsoft Defender Antivirus kräver månatliga uppdateringar [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10 versioner. </span><span class="sxs-lookup"><span data-stu-id="ea82e-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="ea82e-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ea82e-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ea82e-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="ea82e-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ea82e-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ea82e-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ea82e-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="ea82e-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ea82e-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="ea82e-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="ea82e-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="ea82e-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ea82e-132">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="ea82e-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="ea82e-133">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="ea82e-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ea82e-134">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="ea82e-134">All our updates contain</span></span> 
- <span data-ttu-id="ea82e-135">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-135">performance improvements;</span></span>
- <span data-ttu-id="ea82e-136">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="ea82e-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="ea82e-137">integreringsförbättringar (Molnet, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="ea82e-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ea82e-138">Maj-2021 (plattform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="ea82e-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="ea82e-139">&ensp;Uppdateringsversion av säkerhetsinformation: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="ea82e-140">&ensp;**Utgiven: 4 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="ea82e-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="ea82e-141">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="ea82e-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="ea82e-143">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="ea82e-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-144">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-144">What's new</span></span>
- <span data-ttu-id="ea82e-145">Förbättringar av [beteendeövervakning](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="ea82e-146">[Meddelandefiltrering med](network-protection.md) fast nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ea82e-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-147">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-147">Known Issues</span></span>
<span data-ttu-id="ea82e-148">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-149">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ea82e-150">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ea82e-151">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="ea82e-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ea82e-152">&ensp;Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="ea82e-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="ea82e-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ea82e-154">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="ea82e-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-155">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-155">What's new</span></span>
- <span data-ttu-id="ea82e-156">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="ea82e-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ea82e-157">Förbättrad identifiering av kernelläge</span><span class="sxs-lookup"><span data-stu-id="ea82e-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="ea82e-158">Nya kontroller för hantering av den gradvisa utrullningsprocessen för [Microsoft Defender-uppdateringar har lagts till](updates.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-159">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-159">Known Issues</span></span>
<span data-ttu-id="ea82e-160">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-161">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ea82e-162">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ea82e-163">&ensp;Utgiven: **1 april 2021**</span><span class="sxs-lookup"><span data-stu-id="ea82e-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ea82e-164">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="ea82e-165">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ea82e-166">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="ea82e-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-167">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-167">What's new</span></span>

- <span data-ttu-id="ea82e-168">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="ea82e-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ea82e-169">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="ea82e-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ea82e-170">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="ea82e-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-171">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-171">Known Issues</span></span>
<span data-ttu-id="ea82e-172">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ea82e-173">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="ea82e-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ea82e-174">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="ea82e-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ea82e-175">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="ea82e-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="ea82e-176">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="ea82e-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ea82e-177">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ea82e-178">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="ea82e-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ea82e-179">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ea82e-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="ea82e-180">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ea82e-181">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-182">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-182">What's new</span></span>

- <span data-ttu-id="ea82e-183">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ea82e-184">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="ea82e-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-185">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-185">Known Issues</span></span>
<span data-ttu-id="ea82e-186">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-187">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ea82e-188">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ea82e-189">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="ea82e-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ea82e-190">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ea82e-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ea82e-191">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ea82e-192">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-193">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-193">What's new</span></span>

- <span data-ttu-id="ea82e-194">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="ea82e-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ea82e-195">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="ea82e-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ea82e-196">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="ea82e-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ea82e-197">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="ea82e-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ea82e-198">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="ea82e-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-199">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-199">Known Issues</span></span>
<span data-ttu-id="ea82e-200">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-201">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="ea82e-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ea82e-202">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ea82e-203">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ea82e-204">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ea82e-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ea82e-205">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ea82e-206">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-207">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-207">What's new</span></span>

- <span data-ttu-id="ea82e-208">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="ea82e-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-209">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-209">Known Issues</span></span>
<span data-ttu-id="ea82e-210">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-211">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ea82e-212">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ea82e-213">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ea82e-214">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ea82e-215">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ea82e-216">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-217">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-217">What's new</span></span>

- <span data-ttu-id="ea82e-218">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="ea82e-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ea82e-219">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="ea82e-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="ea82e-220">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="ea82e-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ea82e-221">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="ea82e-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-222">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-222">Known Issues</span></span>

<span data-ttu-id="ea82e-223">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ea82e-224">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="ea82e-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ea82e-225">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ea82e-226">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ea82e-227">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ea82e-228">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ea82e-229">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-230">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-230">What's new</span></span>

- <span data-ttu-id="ea82e-231">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="ea82e-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ea82e-232">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="ea82e-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="ea82e-233">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="ea82e-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ea82e-234">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="ea82e-234">New management interfaces for:</span></span>
   - <span data-ttu-id="ea82e-235">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="ea82e-235">UDP Inspection</span></span>
   - <span data-ttu-id="ea82e-236">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="ea82e-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ea82e-237">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="ea82e-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ea82e-238">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="ea82e-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ea82e-239">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="ea82e-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-240">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-240">Known Issues</span></span>

<span data-ttu-id="ea82e-241">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ea82e-242">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ea82e-243">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ea82e-244">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ea82e-245">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ea82e-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ea82e-246">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ea82e-247">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ea82e-248">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-248">What's new</span></span>

- <span data-ttu-id="ea82e-249">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="ea82e-249">Add more telemetry events</span></span>
- <span data-ttu-id="ea82e-250">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="ea82e-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="ea82e-251">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="ea82e-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ea82e-252">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="ea82e-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="ea82e-253">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea82e-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ea82e-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="ea82e-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ea82e-255">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="ea82e-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ea82e-256">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-256">Known Issues</span></span>
<span data-ttu-id="ea82e-257">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-258">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="ea82e-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ea82e-259">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ea82e-260">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ea82e-261">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ea82e-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ea82e-262">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ea82e-263">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-264">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-264">What's new</span></span>

- <span data-ttu-id="ea82e-265">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="ea82e-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ea82e-266">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="ea82e-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-267">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-267">Known Issues</span></span>
<span data-ttu-id="ea82e-268">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-269">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ea82e-270">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ea82e-271">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ea82e-272">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ea82e-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ea82e-273">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ea82e-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ea82e-274">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-275">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-275">What's new</span></span>

- <span data-ttu-id="ea82e-276">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ea82e-277">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="ea82e-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ea82e-278">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="ea82e-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ea82e-279">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="ea82e-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ea82e-280">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="ea82e-280">Fixed registry query</span></span> 
- <span data-ttu-id="ea82e-281">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="ea82e-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-282">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-282">Known Issues</span></span>
<span data-ttu-id="ea82e-283">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-284">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ea82e-285">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ea82e-286">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ea82e-287">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ea82e-288">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ea82e-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ea82e-289">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-290">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-290">What's new</span></span>

- <span data-ttu-id="ea82e-291">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="ea82e-291">Improved logging for scan events</span></span>
- <span data-ttu-id="ea82e-292">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="ea82e-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ea82e-293">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="ea82e-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ea82e-294">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="ea82e-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ea82e-295">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="ea82e-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ea82e-296">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="ea82e-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-297">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-297">Known Issues</span></span>
<span data-ttu-id="ea82e-298">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-299">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ea82e-300">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ea82e-301">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ea82e-302">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ea82e-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ea82e-303">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ea82e-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ea82e-304">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-305">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-305">What's new</span></span>
- <span data-ttu-id="ea82e-306">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-306">WDfilter improvements</span></span>
- <span data-ttu-id="ea82e-307">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="ea82e-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ea82e-308">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="ea82e-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ea82e-309">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="ea82e-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ea82e-310">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="ea82e-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ea82e-311">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="ea82e-311">UEFI scan capability</span></span>
- <span data-ttu-id="ea82e-312">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ea82e-313">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-313">Known Issues</span></span>
<span data-ttu-id="ea82e-314">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-315">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ea82e-316">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ea82e-317">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ea82e-318">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ea82e-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ea82e-319">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ea82e-320">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ea82e-321">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-321">What's new</span></span>

- <span data-ttu-id="ea82e-322">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ea82e-323">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="ea82e-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="ea82e-324">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="ea82e-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ea82e-325">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="ea82e-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ea82e-326">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="ea82e-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ea82e-327">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-327">Known Issues</span></span>
<span data-ttu-id="ea82e-328">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="ea82e-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ea82e-329">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ea82e-330">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ea82e-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ea82e-331">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ea82e-332">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="ea82e-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ea82e-333">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ea82e-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ea82e-334">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ea82e-335">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ea82e-336">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-336">Known Issues</span></span>
<span data-ttu-id="ea82e-337">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-338">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ea82e-339">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ea82e-340">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="ea82e-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ea82e-341">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ea82e-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ea82e-342">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ea82e-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ea82e-343">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="ea82e-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ea82e-344">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-344">What's new</span></span>

- <span data-ttu-id="ea82e-345">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="ea82e-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ea82e-346">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="ea82e-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ea82e-347">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ea82e-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ea82e-348">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ea82e-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ea82e-349">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="ea82e-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ea82e-350">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-350">Known Issues</span></span>

<span data-ttu-id="ea82e-351">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="ea82e-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ea82e-352">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="ea82e-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ea82e-353">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="ea82e-353">This update is:</span></span>
> - <span data-ttu-id="ea82e-354">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="ea82e-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ea82e-355">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="ea82e-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ea82e-356">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="ea82e-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ea82e-357">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="ea82e-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ea82e-358">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="ea82e-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ea82e-359">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="ea82e-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ea82e-360">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ea82e-361">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="ea82e-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ea82e-362">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ea82e-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ea82e-363">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ea82e-364">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="ea82e-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ea82e-365">Nyheter</span><span class="sxs-lookup"><span data-stu-id="ea82e-365">What's new</span></span>

- <span data-ttu-id="ea82e-366">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="ea82e-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ea82e-367">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="ea82e-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ea82e-368">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="ea82e-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ea82e-369">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="ea82e-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ea82e-370">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ea82e-370">Known Issues</span></span>
<span data-ttu-id="ea82e-371">När den här uppdateringen är installerad behöver enheten hopppaketet 4.18.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="ea82e-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ea82e-372">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="ea82e-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ea82e-373">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="ea82e-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ea82e-374">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="ea82e-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ea82e-375">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="ea82e-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ea82e-376">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="ea82e-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ea82e-377">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="ea82e-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ea82e-378">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="ea82e-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ea82e-379">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="ea82e-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ea82e-380">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="ea82e-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ea82e-381">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="ea82e-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ea82e-382">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="ea82e-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ea82e-383">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="ea82e-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ea82e-384">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="ea82e-384">Windows 10 release</span></span>  |<span data-ttu-id="ea82e-385">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="ea82e-385">Platform version</span></span>  |<span data-ttu-id="ea82e-386">Motorversion</span><span class="sxs-lookup"><span data-stu-id="ea82e-386">Engine version</span></span> |<span data-ttu-id="ea82e-387">Supportfas</span><span class="sxs-lookup"><span data-stu-id="ea82e-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ea82e-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ea82e-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ea82e-389">4.18.1909.6</span></span> |<span data-ttu-id="ea82e-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ea82e-390">1.1.17000.2</span></span> | <span data-ttu-id="ea82e-391">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-392">1909  (19H2)</span></span> |<span data-ttu-id="ea82e-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ea82e-393">4.18.1902.5</span></span> |<span data-ttu-id="ea82e-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ea82e-394">1.1.16700.3</span></span> | <span data-ttu-id="ea82e-395">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="ea82e-396">1903  (19H1)</span></span> |<span data-ttu-id="ea82e-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ea82e-397">4.18.1902.5</span></span> |<span data-ttu-id="ea82e-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ea82e-398">1.1.15600.4</span></span> | <span data-ttu-id="ea82e-399">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="ea82e-400">1809  (RS5)</span></span> |<span data-ttu-id="ea82e-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ea82e-401">4.18.1807.18075</span></span> |<span data-ttu-id="ea82e-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ea82e-402">1.1.15000.2</span></span> | <span data-ttu-id="ea82e-403">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="ea82e-404">1803  (RS4)</span></span> |<span data-ttu-id="ea82e-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ea82e-405">4.13.17134.1</span></span> |<span data-ttu-id="ea82e-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ea82e-406">1.1.14600.4</span></span> | <span data-ttu-id="ea82e-407">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="ea82e-408">1709  (RS3)</span></span> |<span data-ttu-id="ea82e-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ea82e-409">4.12.16299.15</span></span> |<span data-ttu-id="ea82e-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ea82e-410">1.1.14104.0</span></span> | <span data-ttu-id="ea82e-411">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="ea82e-412">1703  (RS2)</span></span> |<span data-ttu-id="ea82e-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ea82e-413">4.11.15603.2</span></span> |<span data-ttu-id="ea82e-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ea82e-414">1.1.13504.0</span></span> | <span data-ttu-id="ea82e-415">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ea82e-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="ea82e-416">1607 (RS1)</span></span> |<span data-ttu-id="ea82e-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ea82e-417">4.10.14393.3683</span></span> |<span data-ttu-id="ea82e-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ea82e-418">1.1.12805.0</span></span> | <span data-ttu-id="ea82e-419">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="ea82e-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ea82e-420">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="ea82e-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ea82e-421">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="ea82e-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ea82e-422">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="ea82e-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ea82e-423">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="ea82e-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ea82e-424">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="ea82e-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ea82e-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="ea82e-426">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="ea82e-427">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="ea82e-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="ea82e-428">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ea82e-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ea82e-429">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-430">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-430">Fixes</span></span>
- <span data-ttu-id="ea82e-431">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-432">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-432">Additional information</span></span>
- <span data-ttu-id="ea82e-433">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="ea82e-435">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ea82e-436">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ea82e-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ea82e-437">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ea82e-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ea82e-438">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-439">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-439">Fixes</span></span>
- <span data-ttu-id="ea82e-440">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-441">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-441">Additional information</span></span>
- <span data-ttu-id="ea82e-442">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="ea82e-444">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ea82e-445">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ea82e-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ea82e-446">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ea82e-447">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-448">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-448">Fixes</span></span>
- <span data-ttu-id="ea82e-449">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-450">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-450">Additional information</span></span>
- <span data-ttu-id="ea82e-451">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="ea82e-453">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ea82e-454">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ea82e-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ea82e-455">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ea82e-456">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-457">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-457">Fixes</span></span>
- <span data-ttu-id="ea82e-458">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-459">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-459">Additional information</span></span>
- <span data-ttu-id="ea82e-460">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ea82e-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="ea82e-462">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ea82e-463">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ea82e-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ea82e-464">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ea82e-465">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-466">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-466">Fixes</span></span>
- <span data-ttu-id="ea82e-467">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-468">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-468">Additional information</span></span>
- <span data-ttu-id="ea82e-469">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ea82e-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="ea82e-471">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ea82e-472">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ea82e-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ea82e-473">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ea82e-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ea82e-474">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-475">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-475">Fixes</span></span>
- <span data-ttu-id="ea82e-476">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-477">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-477">Additional information</span></span>
- <span data-ttu-id="ea82e-478">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="ea82e-480">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ea82e-481">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ea82e-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ea82e-482">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ea82e-483">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-484">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-484">Fixes</span></span>
- <span data-ttu-id="ea82e-485">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-486">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-486">Additional information</span></span>
- <span data-ttu-id="ea82e-487">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ea82e-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="ea82e-489">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ea82e-490">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ea82e-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ea82e-491">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ea82e-492">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-493">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-493">Fixes</span></span>
- <span data-ttu-id="ea82e-494">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-495">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-495">Additional information</span></span>
- <span data-ttu-id="ea82e-496">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="ea82e-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ea82e-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="ea82e-498">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ea82e-499">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ea82e-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ea82e-500">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ea82e-501">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-502">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-502">Fixes</span></span>
- <span data-ttu-id="ea82e-503">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-504">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-504">Additional information</span></span>
- <span data-ttu-id="ea82e-505">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ea82e-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ea82e-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="ea82e-507">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ea82e-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ea82e-508">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ea82e-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ea82e-509">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ea82e-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ea82e-510">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ea82e-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ea82e-511">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-511">Fixes</span></span>
- <span data-ttu-id="ea82e-512">Inga</span><span class="sxs-lookup"><span data-stu-id="ea82e-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ea82e-513">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="ea82e-513">Additional information</span></span>
- <span data-ttu-id="ea82e-514">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="ea82e-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ea82e-515">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ea82e-515">Additional resources</span></span>

| <span data-ttu-id="ea82e-516">Artikel</span><span class="sxs-lookup"><span data-stu-id="ea82e-516">Article</span></span> | <span data-ttu-id="ea82e-517">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ea82e-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ea82e-518">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="ea82e-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ea82e-519">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="ea82e-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ea82e-520">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="ea82e-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ea82e-521">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="ea82e-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ea82e-522">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="ea82e-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ea82e-523">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="ea82e-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ea82e-524">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="ea82e-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ea82e-525">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="ea82e-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ea82e-526">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="ea82e-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ea82e-527">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="ea82e-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ea82e-528">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="ea82e-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ea82e-529">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="ea82e-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ea82e-530">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="ea82e-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
