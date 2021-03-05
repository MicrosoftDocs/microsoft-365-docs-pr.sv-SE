---
title: Namnge ändringar i det avancerade sökschemat i Microsoft 365 Defender
description: Spåra och granska namnändringar – tabeller och kolumner i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, data, namnändringar, namnbyte, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461673"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="01d3e-104">Avancerat schema för sök – namnändringar</span><span class="sxs-lookup"><span data-stu-id="01d3e-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01d3e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="01d3e-105">**Applies to:**</span></span>
- <span data-ttu-id="01d3e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01d3e-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="01d3e-107">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="01d3e-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="01d3e-108">I vissa fall byter befintliga kolumnnamn namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="01d3e-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="01d3e-109">I den här artikeln kan du läsa om vilka namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="01d3e-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="01d3e-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="01d3e-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="01d3e-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="01d3e-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="01d3e-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="01d3e-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="01d3e-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="01d3e-113">Queries that are run using the API</span></span>
- <span data-ttu-id="01d3e-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="01d3e-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="01d3e-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="01d3e-115">December 2020</span></span>

| <span data-ttu-id="01d3e-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-116">Table name</span></span> | <span data-ttu-id="01d3e-117">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-117">Original column name</span></span> | <span data-ttu-id="01d3e-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-118">New column name</span></span> | <span data-ttu-id="01d3e-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="01d3e-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="01d3e-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="01d3e-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="01d3e-121">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-121">Customer feedback</span></span> |
| [<span data-ttu-id="01d3e-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="01d3e-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="01d3e-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-123">Customer feedback</span></span> |
| [<span data-ttu-id="01d3e-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="01d3e-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="01d3e-125">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="01d3e-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="01d3e-126">January 2021</span></span>

| <span data-ttu-id="01d3e-127">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-127">Column name</span></span> | <span data-ttu-id="01d3e-128">Det ursprungliga värdenamnet</span><span class="sxs-lookup"><span data-stu-id="01d3e-128">Original value name</span></span> | <span data-ttu-id="01d3e-129">Nytt värdenamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-129">New value name</span></span> | <span data-ttu-id="01d3e-130">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="01d3e-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="01d3e-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="01d3e-131">MCAS</span></span> |    <span data-ttu-id="01d3e-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="01d3e-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="01d3e-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="01d3e-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="01d3e-135">EDR</span><span class="sxs-lookup"><span data-stu-id="01d3e-135">EDR</span></span>| <span data-ttu-id="01d3e-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="01d3e-137">WindowsDefenderAv</span></span> | <span data-ttu-id="01d3e-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="01d3e-138">Antivirus</span></span> | <span data-ttu-id="01d3e-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-140">WindowsDefender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="01d3e-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="01d3e-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="01d3e-141">SmartScreen</span></span> | <span data-ttu-id="01d3e-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="01d3e-143">CustomerTI</span></span> |  <span data-ttu-id="01d3e-144">Anpassat TI</span><span class="sxs-lookup"><span data-stu-id="01d3e-144">Custom TI</span></span> | <span data-ttu-id="01d3e-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="01d3e-146">OfficeATP</span></span> | <span data-ttu-id="01d3e-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="01d3e-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="01d3e-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-149">MTP</span><span class="sxs-lookup"><span data-stu-id="01d3e-149">MTP</span></span>   | <span data-ttu-id="01d3e-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01d3e-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="01d3e-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="01d3e-152">AzureATP</span></span> |    <span data-ttu-id="01d3e-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="01d3e-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="01d3e-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="01d3e-155">CustomDetection</span></span>   | <span data-ttu-id="01d3e-156">Anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="01d3e-156">Custom detection</span></span> | <span data-ttu-id="01d3e-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="01d3e-158">AutomatedInvestigation</span></span> |<span data-ttu-id="01d3e-159">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="01d3e-159">Automated investigation</span></span> | <span data-ttu-id="01d3e-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="01d3e-161">ThreatExperts</span></span> | <span data-ttu-id="01d3e-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="01d3e-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="01d3e-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="01d3e-164">TI från tredje part</span><span class="sxs-lookup"><span data-stu-id="01d3e-164">3rd party TI</span></span> | <span data-ttu-id="01d3e-165">Tredje parts sensor</span><span class="sxs-lookup"><span data-stu-id="01d3e-165">3rd Party sensors</span></span> | <span data-ttu-id="01d3e-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="01d3e-167">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="01d3e-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="01d3e-168">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="01d3e-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="01d3e-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="01d3e-170">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="01d3e-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="01d3e-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01d3e-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="01d3e-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="01d3e-173">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="01d3e-173">Office 365 ATP</span></span>  |<span data-ttu-id="01d3e-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="01d3e-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="01d3e-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="01d3e-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="01d3e-176">Azure ATP</span></span>    |<span data-ttu-id="01d3e-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="01d3e-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="01d3e-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="01d3e-178">Rebranding</span></span> |

<span data-ttu-id="01d3e-179">`DetectionSource`är tillgängligt i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="01d3e-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="01d3e-180">`ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="01d3e-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="01d3e-181">Februari 2021</span><span class="sxs-lookup"><span data-stu-id="01d3e-181">February 2021</span></span>

1. <span data-ttu-id="01d3e-182">I [tabellerna EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) och [EmailEvents](advanced-hunting-emailevents-table.md) inaktuelle vi kolumnerna och `MalwareFilterVerdict` ersatt dem med `PhishFilterVerdict` `ThreatTypes` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="01d3e-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, we deprecated the `MalwareFilterVerdict`and `PhishFilterVerdict` columns and replaced them with the `ThreatTypes` column.</span></span> <span data-ttu-id="01d3e-183">Vi har även utfasat `MalwareDetectionMethod` `PhishDetectionMethod` kolumnerna och ersatt dem med `DetectionMethods` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="01d3e-183">We also deprecated the `MalwareDetectionMethod` and `PhishDetectionMethod` columns and replaced them with the `DetectionMethods` column.</span></span> <span data-ttu-id="01d3e-184">På så sätt kan vi ge mer information under de nya kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="01d3e-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="01d3e-185">Mappningen anges nedan.</span><span class="sxs-lookup"><span data-stu-id="01d3e-185">The mapping is provided below.</span></span>

| <span data-ttu-id="01d3e-186">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-186">Table name</span></span> | <span data-ttu-id="01d3e-187">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-187">Original column name</span></span> | <span data-ttu-id="01d3e-188">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-188">New column name</span></span> | <span data-ttu-id="01d3e-189">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="01d3e-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="01d3e-190">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="01d3e-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="01d3e-191">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="01d3e-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="01d3e-192">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="01d3e-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="01d3e-193">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="01d3e-193">Include more threat types</span></span> |


2. <span data-ttu-id="01d3e-194">I `EmailAttachmentInfo` tabellerna `EmailEvents` och i tabellerna lade vi till kolumnen `ThreatNames` för att ge mer information om e-posthotet.</span><span class="sxs-lookup"><span data-stu-id="01d3e-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, we added the column `ThreatNames` to give more information about the email threat.</span></span> <span data-ttu-id="01d3e-195">Den här kolumnen innehåller värden som Spam eller Phish.</span><span class="sxs-lookup"><span data-stu-id="01d3e-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="01d3e-196">I [tabellen DeviceInfo](advanced-hunting-deviceinfo-table.md) har vi ersatt kolumnen `DeviceObjectId` med baserat på feedback från `AadDeviceId` kunder.</span><span class="sxs-lookup"><span data-stu-id="01d3e-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, we replaced the `DeviceObjectId` column with `AadDeviceId` based on customer feedback.</span></span>

4. <span data-ttu-id="01d3e-197">I [tabellen DeviceEvents](advanced-hunting-deviceevents-table.md) uppdaterade vi flera ActionType-namn för att bättre beskriva åtgärden.</span><span class="sxs-lookup"><span data-stu-id="01d3e-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, we updated several ActionType names to better reflect the description of the action.</span></span> <span data-ttu-id="01d3e-198">Information finns nedan.</span><span class="sxs-lookup"><span data-stu-id="01d3e-198">Details can be found below.</span></span>

| <span data-ttu-id="01d3e-199">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="01d3e-199">Table name</span></span> | <span data-ttu-id="01d3e-200">Ursprungligt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="01d3e-200">Original ActionType name</span></span> | <span data-ttu-id="01d3e-201">Nytt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="01d3e-201">New ActionType name</span></span> | <span data-ttu-id="01d3e-202">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="01d3e-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="01d3e-203">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="01d3e-204">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="01d3e-205">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="01d3e-206">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-206">Customer feedback</span></span> |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | <span data-ttu-id="01d3e-207">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="01d3e-207">Customer feedback</span></span> |





## <a name="related-topics"></a><span data-ttu-id="01d3e-208">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="01d3e-208">Related topics</span></span>
- [<span data-ttu-id="01d3e-209">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="01d3e-209">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01d3e-210">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="01d3e-210">Understand the schema</span></span>](advanced-hunting-schema-tables.md)