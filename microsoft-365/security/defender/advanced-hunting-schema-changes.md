---
title: Namnge ändringar i det avancerade sökschemat i Microsoft 365 Defender
description: Spåra och granska namnändringar – tabeller och kolumner i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eb6dfa628488239e3953d19d5e78b338e76f50a2
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023791"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="8b1d3-104">Avancerat schema för sökning – Namnändringar</span><span class="sxs-lookup"><span data-stu-id="8b1d3-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b1d3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b1d3-105">**Applies to:**</span></span>
- <span data-ttu-id="8b1d3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1d3-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8b1d3-107">Det [avancerade schemat för sökning](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="8b1d3-108">I vissa fall byter befintliga kolumner namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="8b1d3-109">Läs den här artikeln om du vill granska namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="8b1d3-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="8b1d3-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="8b1d3-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="8b1d3-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="8b1d3-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="8b1d3-113">Queries that are run using the API</span></span>
- <span data-ttu-id="8b1d3-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="8b1d3-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="8b1d3-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="8b1d3-115">December 2020</span></span>

| <span data-ttu-id="8b1d3-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-116">Table name</span></span> | <span data-ttu-id="8b1d3-117">Det ursprungliga kolumnnamnet</span><span class="sxs-lookup"><span data-stu-id="8b1d3-117">Original column name</span></span> | <span data-ttu-id="8b1d3-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-118">New column name</span></span> | <span data-ttu-id="8b1d3-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="8b1d3-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="8b1d3-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8b1d3-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="8b1d3-121">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-121">Customer feedback</span></span> |
| [<span data-ttu-id="8b1d3-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8b1d3-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="8b1d3-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-123">Customer feedback</span></span> |
| [<span data-ttu-id="8b1d3-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8b1d3-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="8b1d3-125">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="8b1d3-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="8b1d3-126">January 2021</span></span>

| <span data-ttu-id="8b1d3-127">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-127">Column name</span></span> | <span data-ttu-id="8b1d3-128">Namn på det ursprungliga värdet</span><span class="sxs-lookup"><span data-stu-id="8b1d3-128">Original value name</span></span> | <span data-ttu-id="8b1d3-129">Namn på nytt värde</span><span class="sxs-lookup"><span data-stu-id="8b1d3-129">New value name</span></span> | <span data-ttu-id="8b1d3-130">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="8b1d3-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="8b1d3-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="8b1d3-131">MCAS</span></span> |    <span data-ttu-id="8b1d3-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8b1d3-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8b1d3-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="8b1d3-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="8b1d3-135">EDR</span><span class="sxs-lookup"><span data-stu-id="8b1d3-135">EDR</span></span>| <span data-ttu-id="8b1d3-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="8b1d3-137">WindowsDefenderAv</span></span> | <span data-ttu-id="8b1d3-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8b1d3-138">Antivirus</span></span> | <span data-ttu-id="8b1d3-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-140">WindowsDefender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="8b1d3-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="8b1d3-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="8b1d3-141">SmartScreen</span></span> | <span data-ttu-id="8b1d3-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="8b1d3-143">CustomerTI</span></span> |  <span data-ttu-id="8b1d3-144">Anpassat TI</span><span class="sxs-lookup"><span data-stu-id="8b1d3-144">Custom TI</span></span> | <span data-ttu-id="8b1d3-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="8b1d3-146">OfficeATP</span></span> | <span data-ttu-id="8b1d3-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1d3-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="8b1d3-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-149">MTP</span><span class="sxs-lookup"><span data-stu-id="8b1d3-149">MTP</span></span>   | <span data-ttu-id="8b1d3-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1d3-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="8b1d3-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="8b1d3-152">AzureATP</span></span> |    <span data-ttu-id="8b1d3-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8b1d3-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="8b1d3-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-155">AnpassadDetection</span><span class="sxs-lookup"><span data-stu-id="8b1d3-155">CustomDetection</span></span>   | <span data-ttu-id="8b1d3-156">Anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="8b1d3-156">Custom detection</span></span> | <span data-ttu-id="8b1d3-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="8b1d3-158">AutomatedInvestigation</span></span> |<span data-ttu-id="8b1d3-159">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="8b1d3-159">Automated investigation</span></span> | <span data-ttu-id="8b1d3-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="8b1d3-161">ThreatExperts</span></span> | <span data-ttu-id="8b1d3-162">Microsoft Hotexperter</span><span class="sxs-lookup"><span data-stu-id="8b1d3-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="8b1d3-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="8b1d3-164">TREDJEPARTS TI</span><span class="sxs-lookup"><span data-stu-id="8b1d3-164">3rd party TI</span></span> | <span data-ttu-id="8b1d3-165">Tredjepartssensorer</span><span class="sxs-lookup"><span data-stu-id="8b1d3-165">3rd Party sensors</span></span> | <span data-ttu-id="8b1d3-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="8b1d3-167">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="8b1d3-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="8b1d3-168">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b1d3-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="8b1d3-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="8b1d3-170">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="8b1d3-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="8b1d3-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1d3-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="8b1d3-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="8b1d3-173">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8b1d3-173">Office 365 ATP</span></span>  |<span data-ttu-id="8b1d3-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1d3-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="8b1d3-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="8b1d3-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8b1d3-176">Azure ATP</span></span>    |<span data-ttu-id="8b1d3-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8b1d3-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="8b1d3-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="8b1d3-178">Rebranding</span></span> |

<span data-ttu-id="8b1d3-179">`DetectionSource`är tillgänglig i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="8b1d3-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="8b1d3-180">`ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="8b1d3-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="8b1d3-181">Februari 2021</span><span class="sxs-lookup"><span data-stu-id="8b1d3-181">February 2021</span></span>

1. <span data-ttu-id="8b1d3-182">I [tabellerna EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) [och EmailEvents](advanced-hunting-emailevents-table.md) har kolumnerna och `MalwareFilterVerdict` `PhishFilterVerdict` ersatts med `ThreatTypes` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="8b1d3-183">Kolumnerna `MalwareDetectionMethod` `PhishDetectionMethod` och har också ersatts med `DetectionMethods` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="8b1d3-184">Denna effektivisering gör att vi kan ge mer information under de nya kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="8b1d3-185">Mappningen anges nedan.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-185">The mapping is provided below.</span></span>

| <span data-ttu-id="8b1d3-186">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-186">Table name</span></span> | <span data-ttu-id="8b1d3-187">Det ursprungliga kolumnnamnet</span><span class="sxs-lookup"><span data-stu-id="8b1d3-187">Original column name</span></span> | <span data-ttu-id="8b1d3-188">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-188">New column name</span></span> | <span data-ttu-id="8b1d3-189">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="8b1d3-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="8b1d3-190">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="8b1d3-191">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="8b1d3-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="8b1d3-192">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="8b1d3-193">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="8b1d3-193">Include more threat types</span></span> |


2. <span data-ttu-id="8b1d3-194">I `EmailAttachmentInfo` tabellerna `EmailEvents` och i tabellerna `ThreatNames` har kolumnen lagts till för att ge mer information om e-posthotet.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="8b1d3-195">Den här kolumnen innehåller värden som Skräppost eller Phish.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="8b1d3-196">I tabellen [DeviceInfo](advanced-hunting-deviceinfo-table.md) har kolumnen `DeviceObjectId` ersatts med kolumnen `AadDeviceId` baserat på feedback från kunder.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="8b1d3-197">I tabellen [DeviceEvents](advanced-hunting-deviceevents-table.md) har flera ActionType-namn ändrats för att bättre återspegla beskrivningen av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="8b1d3-198">Information om ändringarna finns nedan.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="8b1d3-199">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-199">Table name</span></span> | <span data-ttu-id="8b1d3-200">Ursprungligt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-200">Original ActionType name</span></span> | <span data-ttu-id="8b1d3-201">Nytt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="8b1d3-201">New ActionType name</span></span> | <span data-ttu-id="8b1d3-202">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="8b1d3-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="8b1d3-203">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="8b1d3-204">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="8b1d3-205">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="8b1d3-206">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="8b1d3-206">Customer feedback</span></span> |

## <a name="march-2021"></a><span data-ttu-id="8b1d3-207">Mars 2021</span><span class="sxs-lookup"><span data-stu-id="8b1d3-207">March 2021</span></span>

<span data-ttu-id="8b1d3-208">Tabellen `DeviceTvmSoftwareInventoryVulnerabilities` har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-208">The `DeviceTvmSoftwareInventoryVulnerabilities` table has been deprecated.</span></span> <span data-ttu-id="8b1d3-209">Om du ersätter detta `DeviceTvmSoftwareInventory` ersätts `DeviceTvmSoftwareVulnerabilities` tabellerna och.</span><span class="sxs-lookup"><span data-stu-id="8b1d3-209">Replacing it are the `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables.</span></span>



## <a name="related-topics"></a><span data-ttu-id="8b1d3-210">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8b1d3-210">Related topics</span></span>
- [<span data-ttu-id="8b1d3-211">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8b1d3-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8b1d3-212">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8b1d3-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)