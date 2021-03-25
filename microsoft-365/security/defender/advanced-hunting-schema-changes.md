---
title: Namnge ändringar i det avancerade sökschemat i Microsoft 365 Defender
description: Spåra och granska namnändringar – tabeller och kolumner i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: acb259088717b2772ec9798027545f2ff6dbc5e0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076706"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="d9039-104">Avancerat schema för sökning – Namnändringar</span><span class="sxs-lookup"><span data-stu-id="d9039-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9039-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d9039-105">**Applies to:**</span></span>
- <span data-ttu-id="d9039-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9039-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d9039-107">Det [avancerade schemat för sökning](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="d9039-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="d9039-108">I vissa fall byter befintliga kolumner namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="d9039-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="d9039-109">Läs den här artikeln om du vill granska namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="d9039-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="d9039-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="d9039-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="d9039-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="d9039-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="d9039-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="d9039-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="d9039-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="d9039-113">Queries that are run using the API</span></span>
- <span data-ttu-id="d9039-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="d9039-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="d9039-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="d9039-115">December 2020</span></span>

| <span data-ttu-id="d9039-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-116">Table name</span></span> | <span data-ttu-id="d9039-117">Det ursprungliga kolumnnamnet</span><span class="sxs-lookup"><span data-stu-id="d9039-117">Original column name</span></span> | <span data-ttu-id="d9039-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-118">New column name</span></span> | <span data-ttu-id="d9039-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="d9039-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="d9039-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d9039-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="d9039-121">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-121">Customer feedback</span></span> |
| [<span data-ttu-id="d9039-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d9039-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="d9039-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-123">Customer feedback</span></span> |
| [<span data-ttu-id="d9039-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d9039-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="d9039-125">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="d9039-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="d9039-126">January 2021</span></span>

| <span data-ttu-id="d9039-127">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-127">Column name</span></span> | <span data-ttu-id="d9039-128">Namn på det ursprungliga värdet</span><span class="sxs-lookup"><span data-stu-id="d9039-128">Original value name</span></span> | <span data-ttu-id="d9039-129">Namn på nytt värde</span><span class="sxs-lookup"><span data-stu-id="d9039-129">New value name</span></span> | <span data-ttu-id="d9039-130">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="d9039-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="d9039-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9039-131">MCAS</span></span> |    <span data-ttu-id="d9039-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d9039-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="d9039-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="d9039-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="d9039-135">EDR</span><span class="sxs-lookup"><span data-stu-id="d9039-135">EDR</span></span>| <span data-ttu-id="d9039-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="d9039-137">WindowsDefenderAv</span></span> | <span data-ttu-id="d9039-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d9039-138">Antivirus</span></span> | <span data-ttu-id="d9039-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-140">WindowsDefender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="d9039-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="d9039-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="d9039-141">SmartScreen</span></span> | <span data-ttu-id="d9039-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="d9039-143">CustomerTI</span></span> |  <span data-ttu-id="d9039-144">Anpassat TI</span><span class="sxs-lookup"><span data-stu-id="d9039-144">Custom TI</span></span> | <span data-ttu-id="d9039-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="d9039-146">OfficeATP</span></span> | <span data-ttu-id="d9039-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="d9039-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="d9039-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-149">MTP</span><span class="sxs-lookup"><span data-stu-id="d9039-149">MTP</span></span>   | <span data-ttu-id="d9039-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9039-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="d9039-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="d9039-152">AzureATP</span></span> |    <span data-ttu-id="d9039-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="d9039-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="d9039-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-155">AnpassadDetection</span><span class="sxs-lookup"><span data-stu-id="d9039-155">CustomDetection</span></span>   | <span data-ttu-id="d9039-156">Anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="d9039-156">Custom detection</span></span> | <span data-ttu-id="d9039-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="d9039-158">AutomatedInvestigation</span></span> |<span data-ttu-id="d9039-159">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="d9039-159">Automated investigation</span></span> | <span data-ttu-id="d9039-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="d9039-161">ThreatExperts</span></span> | <span data-ttu-id="d9039-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="d9039-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="d9039-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="d9039-164">TREDJEPARTS TI</span><span class="sxs-lookup"><span data-stu-id="d9039-164">3rd party TI</span></span> | <span data-ttu-id="d9039-165">Tredjepartssensorer</span><span class="sxs-lookup"><span data-stu-id="d9039-165">3rd Party sensors</span></span> | <span data-ttu-id="d9039-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="d9039-167">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="d9039-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="d9039-168">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9039-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="d9039-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="d9039-170">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d9039-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="d9039-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9039-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="d9039-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="d9039-173">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d9039-173">Office 365 ATP</span></span>  |<span data-ttu-id="d9039-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="d9039-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="d9039-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="d9039-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="d9039-176">Azure ATP</span></span>    |<span data-ttu-id="d9039-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="d9039-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="d9039-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="d9039-178">Rebranding</span></span> |

<span data-ttu-id="d9039-179">`DetectionSource`är tillgänglig i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="d9039-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="d9039-180">`ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="d9039-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="d9039-181">Februari 2021</span><span class="sxs-lookup"><span data-stu-id="d9039-181">February 2021</span></span>

1. <span data-ttu-id="d9039-182">I [tabellerna EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) [och EmailEvents](advanced-hunting-emailevents-table.md) har kolumnerna och `MalwareFilterVerdict` `PhishFilterVerdict` ersatts med `ThreatTypes` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="d9039-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="d9039-183">Kolumnerna `MalwareDetectionMethod` `PhishDetectionMethod` och har också ersatts med `DetectionMethods` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="d9039-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="d9039-184">Denna effektivisering gör att vi kan ge mer information under de nya kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="d9039-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="d9039-185">Mappningen anges nedan.</span><span class="sxs-lookup"><span data-stu-id="d9039-185">The mapping is provided below.</span></span>

| <span data-ttu-id="d9039-186">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-186">Table name</span></span> | <span data-ttu-id="d9039-187">Det ursprungliga kolumnnamnet</span><span class="sxs-lookup"><span data-stu-id="d9039-187">Original column name</span></span> | <span data-ttu-id="d9039-188">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-188">New column name</span></span> | <span data-ttu-id="d9039-189">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="d9039-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="d9039-190">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="d9039-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="d9039-191">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="d9039-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="d9039-192">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="d9039-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="d9039-193">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="d9039-193">Include more threat types</span></span> |


2. <span data-ttu-id="d9039-194">I `EmailAttachmentInfo` tabellerna `EmailEvents` och i tabellerna `ThreatNames` har kolumnen lagts till för att ge mer information om e-posthotet.</span><span class="sxs-lookup"><span data-stu-id="d9039-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="d9039-195">Den här kolumnen innehåller värden som Skräppost eller Phish.</span><span class="sxs-lookup"><span data-stu-id="d9039-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="d9039-196">I tabellen [DeviceInfo](advanced-hunting-deviceinfo-table.md) har kolumnen `DeviceObjectId` ersatts med kolumnen `AadDeviceId` baserat på feedback från kunder.</span><span class="sxs-lookup"><span data-stu-id="d9039-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="d9039-197">I tabellen [DeviceEvents](advanced-hunting-deviceevents-table.md) har flera ActionType-namn ändrats för att bättre återspegla beskrivningen av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d9039-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="d9039-198">Information om ändringarna finns nedan.</span><span class="sxs-lookup"><span data-stu-id="d9039-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="d9039-199">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="d9039-199">Table name</span></span> | <span data-ttu-id="d9039-200">Ursprungligt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="d9039-200">Original ActionType name</span></span> | <span data-ttu-id="d9039-201">Nytt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="d9039-201">New ActionType name</span></span> | <span data-ttu-id="d9039-202">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="d9039-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="d9039-203">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="d9039-204">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="d9039-205">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="d9039-206">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="d9039-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="d9039-207">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d9039-207">Related topics</span></span>
- [<span data-ttu-id="d9039-208">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d9039-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d9039-209">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d9039-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)