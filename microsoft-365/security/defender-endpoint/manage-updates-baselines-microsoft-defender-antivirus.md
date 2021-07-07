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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314470"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="4fcc8-104">Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer</span><span class="sxs-lookup"><span data-stu-id="4fcc8-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="4fcc8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-105">**Applies to:**</span></span>

- [<span data-ttu-id="4fcc8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4fcc8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="4fcc8-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="4fcc8-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="4fcc8-108">Att Microsoft Defender Antivirus uppdaterade är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="4fcc8-109">Uppdatera antivirusskyddet, även om det Microsoft Defender Antivirus i passiv [form.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="4fcc8-110">Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="4fcc8-111">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-111">Security intelligence updates</span></span>
- <span data-ttu-id="4fcc8-112">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="4fcc8-113">Om du vill se den mest aktuella motorn, plattformen och signaturdatumet går du till Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus andra Microsoft-program](https://www.microsoft.com/en-us/wdsi/defenderupdates) mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="4fcc8-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="4fcc8-114">Säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-114">Security intelligence updates</span></span>

<span data-ttu-id="4fcc8-115">Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsoft Advanced Protection Service eller MAPS) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="4fcc8-116">Uppdateringar släpps under kb-nummer nedan:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="4fcc8-117">Microsoft Defender Antivirus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="4fcc8-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="4fcc8-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="4fcc8-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="4fcc8-119">Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="4fcc8-120">Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="4fcc8-121">Mer information finns i [Använda Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="4fcc8-122">En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="4fcc8-123">Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="4fcc8-124">Produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-124">Product updates</span></span>

<span data-ttu-id="4fcc8-125">Microsoft Defender Antivirus kräver [månatliga uppdateringar (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) som kallas *plattformsuppdateringar.*</span><span class="sxs-lookup"><span data-stu-id="4fcc8-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="4fcc8-126">Du kan hantera distributionen av uppdateringar på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="4fcc8-127">Windows Tjänst för serveruppdatering (WSUS)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="4fcc8-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4fcc8-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="4fcc8-129">Den vanliga metoden du använder för att distribuera Microsoft Windows uppdateringar till slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="4fcc8-130">Mer information finns i [Hantera källor för Microsoft Defender Antivirus säkerhetsuppdateringar.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="4fcc8-131">Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="4fcc8-132">I den här artikeln listas de ändringar som ingår i den breda utgivningskanalen.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="4fcc8-133">[Se den senaste versionen av den breda kanalen här](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="4fcc8-134">Mer information om den gradvisa lanseringsprocessen och mer information om nästa version finns i Hantera den gradvisa lanseringsprocessen [för Microsoft Defender-uppdateringar.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="4fcc8-135">Mer information om säkerhetsintelligensuppdateringar finns [i Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="4fcc8-136">Månadsplattform och motorversioner</span><span class="sxs-lookup"><span data-stu-id="4fcc8-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="4fcc8-137">Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="4fcc8-138">Alla våra uppdateringar innehåller</span><span class="sxs-lookup"><span data-stu-id="4fcc8-138">All our updates contain</span></span> 
- <span data-ttu-id="4fcc8-139">prestandaförbättringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-139">performance improvements;</span></span>
- <span data-ttu-id="4fcc8-140">förbättringar av användbarheten. och</span><span class="sxs-lookup"><span data-stu-id="4fcc8-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="4fcc8-141">integreringsförbättringar (Moln, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="4fcc8-142">Juni-2021 (plattform: 4.18.2106.5 | Motor: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="4fcc8-143">&ensp;Uppdateringsversion av säkerhetsinformation: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="4fcc8-144">&ensp;**Utgiven: 28 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="4fcc8-145">&ensp;Plattform: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="4fcc8-146">&ensp;Motor: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="4fcc8-147">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-148">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-148">What's new</span></span>
- <span data-ttu-id="4fcc8-149">Nya kontroller för hantering av den gradvisa utrullningsprocessen av Microsoft Defender-uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="4fcc8-150">Se [Hantera den stegvisa införandeprocessen för Microsoft Defender-uppdateringar.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="4fcc8-151">Förbättring av funktionsövervakningsmotorn</span><span class="sxs-lookup"><span data-stu-id="4fcc8-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="4fcc8-152">Förbättringar av utrullningen av definitioner för program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="4fcc8-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="4fcc8-153">Extended Edge-nätverkshändelseinspektioner</span><span class="sxs-lookup"><span data-stu-id="4fcc8-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-154">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-154">Known Issues</span></span>
<span data-ttu-id="4fcc8-155">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-156">Maj-2021 (plattform: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="4fcc8-157">&ensp;Uppdateringsversion av säkerhetsinformation: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="4fcc8-158">&ensp;**Utgiven: 3 juni 2021**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="4fcc8-159">&ensp;Plattform: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="4fcc8-160">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="4fcc8-161">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-162">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-162">What's new</span></span>
- <span data-ttu-id="4fcc8-163">Förbättringar av [beteendeövervakning](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="4fcc8-164">[Meddelandefiltrering med](network-protection.md) fast nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="4fcc8-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-165">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-165">Known Issues</span></span>
<span data-ttu-id="4fcc8-166">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-167">April 2021 (plattform: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="4fcc8-168">&ensp;Uppdateringsversion av säkerhetsinformation: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="4fcc8-169">&ensp;Utgiven: **26 april 2021**  (Motor: 1.1.18100.6 utgiven 5 maj 2021) &ensp; Plattform: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="4fcc8-170">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="4fcc8-171">&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-172">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-172">What's new</span></span>
- <span data-ttu-id="4fcc8-173">Ytterligare logik för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="4fcc8-174">Förbättrad identifiering av kernellägesnyckel</span><span class="sxs-lookup"><span data-stu-id="4fcc8-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="4fcc8-175">Nya kontroller för hantering av den gradvisa utrullningsprocessen för [Microsoft Defender-uppdateringar har lagts till](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="4fcc8-176">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-176">Known Issues</span></span>
<span data-ttu-id="4fcc8-177">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="4fcc8-178">Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport</span><span class="sxs-lookup"><span data-stu-id="4fcc8-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="4fcc8-179">När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="4fcc8-180">Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="4fcc8-181">Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="4fcc8-182">&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="4fcc8-183">&ensp;**Utgiven: 2 april 2021**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="4fcc8-184">&ensp;Plattform: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="4fcc8-185">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="4fcc8-186">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-187">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-187">What's new</span></span>

- <span data-ttu-id="4fcc8-188">Förbättring av motor för funktionsövervakning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="4fcc8-189">Expanderade nätverkets råstyrt-attackåtgärder</span><span class="sxs-lookup"><span data-stu-id="4fcc8-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="4fcc8-190">Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat</span><span class="sxs-lookup"><span data-stu-id="4fcc8-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-191">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-191">Known Issues</span></span>
<span data-ttu-id="4fcc8-192">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-193">Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="4fcc8-194">&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="4fcc8-195">&ensp;**Utgiven: 9 mars 2021**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="4fcc8-196">&ensp;Plattform: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="4fcc8-197">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="4fcc8-198">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-199">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-199">What's new</span></span>

- <span data-ttu-id="4fcc8-200">Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="4fcc8-201">Utöka skyddsområdet för manipulering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-202">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-202">Known Issues</span></span>
<span data-ttu-id="4fcc8-203">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-204">Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="4fcc8-205">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="4fcc8-206">&ensp;**Utgiven: 2 februari 2021**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="4fcc8-207">&ensp;Plattform: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="4fcc8-208">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="4fcc8-209">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-210">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-210">What's new</span></span>

- <span data-ttu-id="4fcc8-211">Sårbarhetsidentifieringsförbättringar i Shellcode</span><span class="sxs-lookup"><span data-stu-id="4fcc8-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="4fcc8-212">Bättre synlighet för försök att stjäl autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="4fcc8-213">Förbättringar av funktionerna för att ta fram nya funktioner Microsoft Defender Antivirus tjänster</span><span class="sxs-lookup"><span data-stu-id="4fcc8-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="4fcc8-214">Förbättrat stöd för ARM x64-egulering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="4fcc8-215">Åtgärd: Identifiering och åtgärd på slutpunkt blockera meddelande finns kvar i hothistoriken efter att initial identifiering utförts i realtid</span><span class="sxs-lookup"><span data-stu-id="4fcc8-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-216">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-216">Known Issues</span></span>
<span data-ttu-id="4fcc8-217">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-218">November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="4fcc8-219">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="4fcc8-220">&ensp;Utgiven: **3 december 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="4fcc8-221">&ensp;Plattform: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="4fcc8-222">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="4fcc8-223">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-224">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-224">What's new</span></span>

- <span data-ttu-id="4fcc8-225">Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-226">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-226">Known Issues</span></span>
<span data-ttu-id="4fcc8-227">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-228">Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="4fcc8-229">&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="4fcc8-230">&ensp;**Utgiven: 29 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="4fcc8-231">&ensp;Plattform: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="4fcc8-232">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="4fcc8-233">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-234">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-234">What's new</span></span>

- <span data-ttu-id="4fcc8-235">Nya beskrivningar av särskilda hotkategorier</span><span class="sxs-lookup"><span data-stu-id="4fcc8-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="4fcc8-236">Förbättrade funktioner för emulerande</span><span class="sxs-lookup"><span data-stu-id="4fcc8-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="4fcc8-237">Förbättrade funktioner för tillåtna/blockerade värdadresser</span><span class="sxs-lookup"><span data-stu-id="4fcc8-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="4fcc8-238">Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare</span><span class="sxs-lookup"><span data-stu-id="4fcc8-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-239">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-239">Known Issues</span></span>

<span data-ttu-id="4fcc8-240">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4fcc8-241">September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="4fcc8-242">&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="4fcc8-243">&ensp;**Utgiven: 01 oktober 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="4fcc8-244">&ensp;Plattform: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="4fcc8-245">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="4fcc8-246">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-247">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-247">What's new</span></span>

- <span data-ttu-id="4fcc8-248">Administratörsbehörighet krävs för att återställa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="4fcc8-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="4fcc8-249">XML-formaterade händelser stöds nu</span><span class="sxs-lookup"><span data-stu-id="4fcc8-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="4fcc8-250">Stöd för CSP för att ignorera undantagskopplingar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="4fcc8-251">Nya hanteringsgränssnitt för:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-251">New management interfaces for:</span></span>
   - <span data-ttu-id="4fcc8-252">UDP-kontroll</span><span class="sxs-lookup"><span data-stu-id="4fcc8-252">UDP Inspection</span></span>
   - <span data-ttu-id="4fcc8-253">Nätverksskydd på Server 2019</span><span class="sxs-lookup"><span data-stu-id="4fcc8-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="4fcc8-254">Undantag för IP-adress i nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="4fcc8-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="4fcc8-255">Förbättrad insyn i TPM-mått</span><span class="sxs-lookup"><span data-stu-id="4fcc8-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="4fcc8-256">Förbättrad Office VBA-modulskanning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-257">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-257">Known Issues</span></span>

<span data-ttu-id="4fcc8-258">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="4fcc8-259">Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="4fcc8-260">&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="4fcc8-261">&ensp;Släppt: **27 augusti 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="4fcc8-262">&ensp;Plattform: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="4fcc8-263">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="4fcc8-264">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="4fcc8-265">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-265">What's new</span></span>

- <span data-ttu-id="4fcc8-266">Lägga till fler telemetrihändelser</span><span class="sxs-lookup"><span data-stu-id="4fcc8-266">Add more telemetry events</span></span>
- <span data-ttu-id="4fcc8-267">Förbättrad sökhändelsetelemetri</span><span class="sxs-lookup"><span data-stu-id="4fcc8-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="4fcc8-268">Förbättrad övervakning av beteende för minnessökningar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="4fcc8-269">Förbättrad genomsökning av makroströmmar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="4fcc8-270">`AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet</span><span class="sxs-lookup"><span data-stu-id="4fcc8-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="4fcc8-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="4fcc8-272">Microsoft Defender Antivirus inaktiveras automatiskt när ett annat antivirusprogram upptäcks.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="4fcc8-273">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-273">Known Issues</span></span>
<span data-ttu-id="4fcc8-274">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-275">Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="4fcc8-276">&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="4fcc8-277">&ensp;**Utgiven: 28 juli 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="4fcc8-278">&ensp;Plattform: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="4fcc8-279">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="4fcc8-280">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-281">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-281">What's new</span></span>

- <span data-ttu-id="4fcc8-282">Förbättrad telemetri för BITS</span><span class="sxs-lookup"><span data-stu-id="4fcc8-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="4fcc8-283">Förbättrad validering av Authenticode-kodsigneringscertifikat</span><span class="sxs-lookup"><span data-stu-id="4fcc8-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-284">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-284">Known Issues</span></span>
<span data-ttu-id="4fcc8-285">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-286">Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="4fcc8-287">&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="4fcc8-288">&ensp;**Utgiven: 22 juni 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="4fcc8-289">&ensp;Plattform: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="4fcc8-290">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="4fcc8-291">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-292">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-292">What's new</span></span>

- <span data-ttu-id="4fcc8-293">Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="4fcc8-294">Hoppa över en aggressiv uppslagssökning i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="4fcc8-295">Tillåt att Defender uppdaterar med anslutningar med datamätare</span><span class="sxs-lookup"><span data-stu-id="4fcc8-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="4fcc8-296">Korrigerad prestandajustering när cachelagring är inaktiverat</span><span class="sxs-lookup"><span data-stu-id="4fcc8-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="4fcc8-297">Åtgärdad registerfråga</span><span class="sxs-lookup"><span data-stu-id="4fcc8-297">Fixed registry query</span></span> 
- <span data-ttu-id="4fcc8-298">Fast genomsöknings slumpvisisering i ADMX</span><span class="sxs-lookup"><span data-stu-id="4fcc8-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-299">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-299">Known Issues</span></span>
<span data-ttu-id="4fcc8-300">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-301">Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="4fcc8-302">&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="4fcc8-303">&ensp;**Utgiven: 26 maj 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="4fcc8-304">&ensp;Plattform: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="4fcc8-305">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="4fcc8-306">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-307">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-307">What's new</span></span>

- <span data-ttu-id="4fcc8-308">Förbättrad loggning för genomsökningshändelser</span><span class="sxs-lookup"><span data-stu-id="4fcc8-308">Improved logging for scan events</span></span>
- <span data-ttu-id="4fcc8-309">Förbättrad kraschhantering i användarläge.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="4fcc8-310">Händelsespårning har lagts till för skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="4fcc8-311">Åtgärdat AMSI-exempel för inskickning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="4fcc8-312">Åtgärdat AMSI-molnblockering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="4fcc8-313">Installationslogg för säkerhetsuppdatering åtgärdad</span><span class="sxs-lookup"><span data-stu-id="4fcc8-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-314">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-314">Known Issues</span></span>
<span data-ttu-id="4fcc8-315">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-316">April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="4fcc8-317">&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="4fcc8-318">&ensp;Utgiven: **30 april 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="4fcc8-319">&ensp;Plattform: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="4fcc8-320">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="4fcc8-321">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-322">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-322">What's new</span></span>
- <span data-ttu-id="4fcc8-323">WDfilterförbättringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-323">WDfilter improvements</span></span>
- <span data-ttu-id="4fcc8-324">Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="4fcc8-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="4fcc8-325">Åtgärdad versionsinformation i diagnostikdata och WMI</span><span class="sxs-lookup"><span data-stu-id="4fcc8-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="4fcc8-326">Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="4fcc8-327">Dynamisk URL-information för skydd mot fillösa hot</span><span class="sxs-lookup"><span data-stu-id="4fcc8-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="4fcc8-328">Sökfunktion för UEFI</span><span class="sxs-lookup"><span data-stu-id="4fcc8-328">UEFI scan capability</span></span>
- <span data-ttu-id="4fcc8-329">Utöka loggning för uppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="4fcc8-330">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-330">Known Issues</span></span>
<span data-ttu-id="4fcc8-331">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-332">Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="4fcc8-333">&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="4fcc8-334">&ensp;Utgiven: **24 mars 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="4fcc8-335">&ensp;Plattform: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="4fcc8-336">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="4fcc8-337">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4fcc8-338">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-338">What's new</span></span>

- <span data-ttu-id="4fcc8-339">Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="4fcc8-340">Förbättra diagnostikfunktionerna</span><span class="sxs-lookup"><span data-stu-id="4fcc8-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="4fcc8-341">minska timeout för säkerhetsintelligens (5 min)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="4fcc8-342">Utöka funktionen intern AMSI-motorlogg</span><span class="sxs-lookup"><span data-stu-id="4fcc8-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="4fcc8-343">Förbättra meddelandet om processblockering</span><span class="sxs-lookup"><span data-stu-id="4fcc8-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4fcc8-344">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-344">Known Issues</span></span>
<span data-ttu-id="4fcc8-345">[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="4fcc8-346">Februari-2020 (plattform: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="4fcc8-347">&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="4fcc8-348">&ensp;**Utgiven: 25 februari 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="4fcc8-349">&ensp;Plattform/klient: **-**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="4fcc8-350">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="4fcc8-351">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="4fcc8-352">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="4fcc8-353">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-353">Known Issues</span></span>
<span data-ttu-id="4fcc8-354">Inga kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-355">Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="4fcc8-356">Uppdateringsversion av säkerhetsinformation: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="4fcc8-357">Utgiven: **30 januari 2020**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="4fcc8-358">Plattform/klient: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="4fcc8-359">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="4fcc8-360">&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="4fcc8-361">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-361">What's new</span></span>

- <span data-ttu-id="4fcc8-362">Åtgärdat BSOD på WS2016 med Exchange</span><span class="sxs-lookup"><span data-stu-id="4fcc8-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="4fcc8-363">Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="4fcc8-364">Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="4fcc8-365">utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="4fcc8-366">Åtgärda att 4.18.1911.3 hänger sig</span><span class="sxs-lookup"><span data-stu-id="4fcc8-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4fcc8-367">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-367">Known Issues</span></span>

<span data-ttu-id="4fcc8-368">[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att Windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="4fcc8-369">Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="4fcc8-370">Den här uppdateringen är:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-370">This update is:</span></span>
> - <span data-ttu-id="4fcc8-371">krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="4fcc8-372">har en omstartsflagga för system som har hängande problem.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="4fcc8-373">återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="4fcc8-374">kategoriseras som en uppdatering på grund av omstartskravet; och</span><span class="sxs-lookup"><span data-stu-id="4fcc8-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="4fcc8-375">erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="4fcc8-376">November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="4fcc8-377">Uppdateringsversion av säkerhetsinformation: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="4fcc8-378">**Utgiven: 7 december 2019**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="4fcc8-379">Plattform: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="4fcc8-380">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="4fcc8-381">Supportfas: **Inget stöd**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="4fcc8-382">Nyheter</span><span class="sxs-lookup"><span data-stu-id="4fcc8-382">What's new</span></span>

- <span data-ttu-id="4fcc8-383">Åtgärdat MpCmdRun-spårningsnivå</span><span class="sxs-lookup"><span data-stu-id="4fcc8-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="4fcc8-384">Åtgärdat WDFilter-versionsinformation</span><span class="sxs-lookup"><span data-stu-id="4fcc8-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="4fcc8-385">Förbättra meddelanden (PUA)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="4fcc8-386">lägga till MRT-loggar i stödfiler</span><span class="sxs-lookup"><span data-stu-id="4fcc8-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4fcc8-387">Kända problem</span><span class="sxs-lookup"><span data-stu-id="4fcc8-387">Known Issues</span></span>
<span data-ttu-id="4fcc8-388">När den här uppdateringen är installerad behöver enheten hopppaketet 4.18.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="4fcc8-389">Microsoft Defender Antivirus stöd för Microsoft Defender Antivirus-plattformen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="4fcc8-390">Plattforms- och motoruppdateringar tillhandahålls varje månad.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="4fcc8-391">Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="4fcc8-392">Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="4fcc8-393">**Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="4fcc8-394">**Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="4fcc8-395">Plattformsversioner äldre än N-2 stöds inte längre.\*</span><span class="sxs-lookup"><span data-stu-id="4fcc8-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="4fcc8-396">\*Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10 release-versionen (se [Plattformsversion](#platform-version-included-with-windows-10-releases)som ingår i Windows 10-versioner) till den senaste versionen av plattformen.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="4fcc8-397">Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="4fcc8-398">Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (\*).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="4fcc8-399">Plattformsversion som ingår Windows 10 versioner</span><span class="sxs-lookup"><span data-stu-id="4fcc8-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="4fcc8-400">Tabellen nedan innehåller de Microsoft Defender Antivirus-plattform och motorversioner som levereras med de senaste Windows 10 versionerna:</span><span class="sxs-lookup"><span data-stu-id="4fcc8-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="4fcc8-401">Windows 10 version</span><span class="sxs-lookup"><span data-stu-id="4fcc8-401">Windows 10 release</span></span>  |<span data-ttu-id="4fcc8-402">Plattformsversion</span><span class="sxs-lookup"><span data-stu-id="4fcc8-402">Platform version</span></span>  |<span data-ttu-id="4fcc8-403">Motorversion</span><span class="sxs-lookup"><span data-stu-id="4fcc8-403">Engine version</span></span> |<span data-ttu-id="4fcc8-404">Supportfas</span><span class="sxs-lookup"><span data-stu-id="4fcc8-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="4fcc8-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="4fcc8-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="4fcc8-406">4.18.1909.6</span></span> |<span data-ttu-id="4fcc8-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="4fcc8-407">1.1.17000.2</span></span> | <span data-ttu-id="4fcc8-408">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-409">1909  (19H2)</span></span> |<span data-ttu-id="4fcc8-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="4fcc8-410">4.18.1902.5</span></span> |<span data-ttu-id="4fcc8-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="4fcc8-411">1.1.16700.3</span></span> | <span data-ttu-id="4fcc8-412">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-413">1903  (19H1)</span></span> |<span data-ttu-id="4fcc8-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="4fcc8-414">4.18.1902.5</span></span> |<span data-ttu-id="4fcc8-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="4fcc8-415">1.1.15600.4</span></span> | <span data-ttu-id="4fcc8-416">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-417">1809  (RS5)</span></span> |<span data-ttu-id="4fcc8-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="4fcc8-418">4.18.1807.18075</span></span> |<span data-ttu-id="4fcc8-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="4fcc8-419">1.1.15000.2</span></span> | <span data-ttu-id="4fcc8-420">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-421">1803  (RS4)</span></span> |<span data-ttu-id="4fcc8-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="4fcc8-422">4.13.17134.1</span></span> |<span data-ttu-id="4fcc8-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="4fcc8-423">1.1.14600.4</span></span> | <span data-ttu-id="4fcc8-424">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-425">1709  (RS3)</span></span> |<span data-ttu-id="4fcc8-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="4fcc8-426">4.12.16299.15</span></span> |<span data-ttu-id="4fcc8-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="4fcc8-427">1.1.14104.0</span></span> | <span data-ttu-id="4fcc8-428">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-429">1703  (RS2)</span></span> |<span data-ttu-id="4fcc8-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="4fcc8-430">4.11.15603.2</span></span> |<span data-ttu-id="4fcc8-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="4fcc8-431">1.1.13504.0</span></span> | <span data-ttu-id="4fcc8-432">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4fcc8-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-433">1607 (RS1)</span></span> |<span data-ttu-id="4fcc8-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="4fcc8-434">4.10.14393.3683</span></span> |<span data-ttu-id="4fcc8-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="4fcc8-435">1.1.12805.0</span></span> | <span data-ttu-id="4fcc8-436">Teknisk uppgraderingssupport (endast)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="4fcc8-437">Mer Windows 10 information finns i Windows [informationsblad om livscykeln.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="4fcc8-438">Uppdateringar för DISM (Deployment Image Servicing and Management)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="4fcc8-439">Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirusprogram och program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="4fcc8-440">Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="4fcc8-441">Mer information finns i [Microsoft Defender Update för Windows av installationsbilder för operativsystemet.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="4fcc8-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="4fcc8-443">&ensp;Paketversion: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="4fcc8-444">&ensp;Plattformsversion: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="4fcc8-445">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="4fcc8-446">&ensp;Signaturversion: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-447">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-447">Fixes</span></span>
- <span data-ttu-id="4fcc8-448">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-449">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-449">Additional information</span></span>
- <span data-ttu-id="4fcc8-450">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="4fcc8-452">&ensp;Paketversion: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="4fcc8-453">&ensp;Plattformsversion: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="4fcc8-454">&ensp;Motorversion: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="4fcc8-455">&ensp;Signaturversion: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-456">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-456">Fixes</span></span>
- <span data-ttu-id="4fcc8-457">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-458">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-458">Additional information</span></span>
- <span data-ttu-id="4fcc8-459">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="4fcc8-461">&ensp;Paketversion: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="4fcc8-462">&ensp;Plattformsversion: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="4fcc8-463">&ensp;Motorversion: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="4fcc8-464">&ensp;Signaturversion: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-465">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-465">Fixes</span></span>
- <span data-ttu-id="4fcc8-466">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-467">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-467">Additional information</span></span>
- <span data-ttu-id="4fcc8-468">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="4fcc8-470">&ensp;Paketversion: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="4fcc8-471">&ensp;Plattformsversion: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="4fcc8-472">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="4fcc8-473">&ensp;Signaturversion: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-474">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-474">Fixes</span></span>
- <span data-ttu-id="4fcc8-475">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-476">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-476">Additional information</span></span>
- <span data-ttu-id="4fcc8-477">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="4fcc8-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="4fcc8-479">&ensp;Paketversion: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="4fcc8-480">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="4fcc8-481">&ensp;Motorversion: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="4fcc8-482">&ensp;Signaturversion: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-483">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-483">Fixes</span></span>
- <span data-ttu-id="4fcc8-484">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-485">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-485">Additional information</span></span>
- <span data-ttu-id="4fcc8-486">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="4fcc8-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="4fcc8-488">&ensp;Paketversion: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="4fcc8-489">&ensp;Plattformsversion: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="4fcc8-490">&ensp;Motorversion: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="4fcc8-491">&ensp;Signaturversion: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-492">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-492">Fixes</span></span>
- <span data-ttu-id="4fcc8-493">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-494">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-494">Additional information</span></span>
- <span data-ttu-id="4fcc8-495">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="4fcc8-497">&ensp;Paketversion: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="4fcc8-498">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="4fcc8-499">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4fcc8-500">&ensp;Signaturversion: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-501">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-501">Fixes</span></span>
- <span data-ttu-id="4fcc8-502">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-503">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-503">Additional information</span></span>
- <span data-ttu-id="4fcc8-504">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="4fcc8-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="4fcc8-506">&ensp;Paketversion: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="4fcc8-507">&ensp;Plattformsversion: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="4fcc8-508">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4fcc8-509">&ensp;Signaturversion: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-510">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-510">Fixes</span></span>
- <span data-ttu-id="4fcc8-511">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-512">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-512">Additional information</span></span>
- <span data-ttu-id="4fcc8-513">Uppdaterade Microsoft Defender Antivirus signaturer</span><span class="sxs-lookup"><span data-stu-id="4fcc8-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="4fcc8-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="4fcc8-515">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="4fcc8-516">&ensp;Plattformsversion: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="4fcc8-517">&ensp;Motorversion: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4fcc8-518">&ensp;Signaturversion: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-519">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-519">Fixes</span></span>
- <span data-ttu-id="4fcc8-520">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-521">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-521">Additional information</span></span>
- <span data-ttu-id="4fcc8-522">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4fcc8-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="4fcc8-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="4fcc8-524">&ensp;Paketversion: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="4fcc8-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="4fcc8-525">&ensp;Plattformsversion: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="4fcc8-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="4fcc8-526">&ensp;Motorversion: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="4fcc8-527">&ensp;Signaturversion: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="4fcc8-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4fcc8-528">Korrigeringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-528">Fixes</span></span>
- <span data-ttu-id="4fcc8-529">Ingen</span><span class="sxs-lookup"><span data-stu-id="4fcc8-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4fcc8-530">Ytterligare information</span><span class="sxs-lookup"><span data-stu-id="4fcc8-530">Additional information</span></span>
- <span data-ttu-id="4fcc8-531">Lade till stöd för Windows 10 RS1 eller senare OS-installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="4fcc8-532">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4fcc8-532">Additional resources</span></span>

| <span data-ttu-id="4fcc8-533">Artikel</span><span class="sxs-lookup"><span data-stu-id="4fcc8-533">Article</span></span> | <span data-ttu-id="4fcc8-534">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4fcc8-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="4fcc8-535">Installationsbilder för Microsoft Defender Windows för operativsystemet</span><span class="sxs-lookup"><span data-stu-id="4fcc8-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="4fcc8-536">Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer).</span><span class="sxs-lookup"><span data-stu-id="4fcc8-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="4fcc8-537">Hämta Microsoft Defender Antivirus uppdateringar för Windows 10 (versionerna Enterprise, Pro, Home), Windows Server 2019 och Windows Server 2016 installationsbilder.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="4fcc8-538">Hantera hur skyddsuppdateringar hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="4fcc8-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="4fcc8-539">Skyddsuppdateringar kan skickas via många källor.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="4fcc8-540">Hantera när skyddsuppdateringar ska hämtas och tillämpas</span><span class="sxs-lookup"><span data-stu-id="4fcc8-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="4fcc8-541">Du kan schemalägga när skyddsuppdateringar ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="4fcc8-542">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="4fcc8-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="4fcc8-543">Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="4fcc8-544">Hantera händelsebaserade uppdateringar</span><span class="sxs-lookup"><span data-stu-id="4fcc8-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="4fcc8-545">Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="4fcc8-546">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="4fcc8-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="4fcc8-547">Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer.</span><span class="sxs-lookup"><span data-stu-id="4fcc8-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
