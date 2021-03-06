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
ms.openlocfilehash: 31a2f647351c05842f36198ad05b149086b53b1f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509308"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="81b16-104">Avancerat schema för sök – namnändringar</span><span class="sxs-lookup"><span data-stu-id="81b16-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81b16-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="81b16-105">**Applies to:**</span></span>
- <span data-ttu-id="81b16-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81b16-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="81b16-107">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="81b16-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="81b16-108">I vissa fall byter befintliga kolumnnamn namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="81b16-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="81b16-109">I den här artikeln kan du läsa om vilka namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="81b16-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="81b16-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="81b16-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="81b16-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="81b16-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="81b16-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="81b16-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="81b16-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="81b16-113">Queries that are run using the API</span></span>
- <span data-ttu-id="81b16-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="81b16-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="81b16-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="81b16-115">December 2020</span></span>

| <span data-ttu-id="81b16-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-116">Table name</span></span> | <span data-ttu-id="81b16-117">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-117">Original column name</span></span> | <span data-ttu-id="81b16-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-118">New column name</span></span> | <span data-ttu-id="81b16-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="81b16-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="81b16-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="81b16-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="81b16-121">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-121">Customer feedback</span></span> |
| [<span data-ttu-id="81b16-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="81b16-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="81b16-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-123">Customer feedback</span></span> |
| [<span data-ttu-id="81b16-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="81b16-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="81b16-125">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="81b16-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="81b16-126">January 2021</span></span>

| <span data-ttu-id="81b16-127">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-127">Column name</span></span> | <span data-ttu-id="81b16-128">Det ursprungliga värdenamnet</span><span class="sxs-lookup"><span data-stu-id="81b16-128">Original value name</span></span> | <span data-ttu-id="81b16-129">Nytt värdenamn</span><span class="sxs-lookup"><span data-stu-id="81b16-129">New value name</span></span> | <span data-ttu-id="81b16-130">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="81b16-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="81b16-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="81b16-131">MCAS</span></span> |    <span data-ttu-id="81b16-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="81b16-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="81b16-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="81b16-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="81b16-135">EDR</span><span class="sxs-lookup"><span data-stu-id="81b16-135">EDR</span></span>| <span data-ttu-id="81b16-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="81b16-137">WindowsDefenderAv</span></span> | <span data-ttu-id="81b16-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="81b16-138">Antivirus</span></span> | <span data-ttu-id="81b16-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-140">WindowsDefender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="81b16-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="81b16-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="81b16-141">SmartScreen</span></span> | <span data-ttu-id="81b16-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="81b16-143">CustomerTI</span></span> |  <span data-ttu-id="81b16-144">Anpassat TI</span><span class="sxs-lookup"><span data-stu-id="81b16-144">Custom TI</span></span> | <span data-ttu-id="81b16-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="81b16-146">OfficeATP</span></span> | <span data-ttu-id="81b16-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="81b16-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="81b16-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-149">MTP</span><span class="sxs-lookup"><span data-stu-id="81b16-149">MTP</span></span>   | <span data-ttu-id="81b16-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81b16-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="81b16-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="81b16-152">AzureATP</span></span> |    <span data-ttu-id="81b16-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="81b16-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="81b16-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="81b16-155">CustomDetection</span></span>   | <span data-ttu-id="81b16-156">Anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="81b16-156">Custom detection</span></span> | <span data-ttu-id="81b16-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="81b16-158">AutomatedInvestigation</span></span> |<span data-ttu-id="81b16-159">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="81b16-159">Automated investigation</span></span> | <span data-ttu-id="81b16-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="81b16-161">ThreatExperts</span></span> | <span data-ttu-id="81b16-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="81b16-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="81b16-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="81b16-164">TI från tredje part</span><span class="sxs-lookup"><span data-stu-id="81b16-164">3rd party TI</span></span> | <span data-ttu-id="81b16-165">Tredje parts sensor</span><span class="sxs-lookup"><span data-stu-id="81b16-165">3rd Party sensors</span></span> | <span data-ttu-id="81b16-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="81b16-167">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="81b16-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="81b16-168">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="81b16-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="81b16-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="81b16-170">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="81b16-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="81b16-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81b16-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="81b16-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="81b16-173">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="81b16-173">Office 365 ATP</span></span>  |<span data-ttu-id="81b16-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="81b16-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="81b16-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="81b16-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="81b16-176">Azure ATP</span></span>    |<span data-ttu-id="81b16-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="81b16-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="81b16-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="81b16-178">Rebranding</span></span> |

<span data-ttu-id="81b16-179">`DetectionSource`är tillgängligt i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="81b16-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="81b16-180">`ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="81b16-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="81b16-181">Februari 2021</span><span class="sxs-lookup"><span data-stu-id="81b16-181">February 2021</span></span>

1. <span data-ttu-id="81b16-182">I [tabellerna EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) och [EmailEvents](advanced-hunting-emailevents-table.md) `MalwareFilterVerdict` har `PhishFilterVerdict` kolumnerna ersatts med `ThreatTypes` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="81b16-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="81b16-183">Kolumnerna `MalwareDetectionMethod` och de har också `PhishDetectionMethod` ersatts med `DetectionMethods` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="81b16-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="81b16-184">På så sätt kan vi ge mer information under de nya kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="81b16-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="81b16-185">Mappningen anges nedan.</span><span class="sxs-lookup"><span data-stu-id="81b16-185">The mapping is provided below.</span></span>

| <span data-ttu-id="81b16-186">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-186">Table name</span></span> | <span data-ttu-id="81b16-187">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-187">Original column name</span></span> | <span data-ttu-id="81b16-188">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-188">New column name</span></span> | <span data-ttu-id="81b16-189">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="81b16-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="81b16-190">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="81b16-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="81b16-191">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="81b16-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="81b16-192">Inkludera fler identifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="81b16-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="81b16-193">Inkludera fler hottyper</span><span class="sxs-lookup"><span data-stu-id="81b16-193">Include more threat types</span></span> |


2. <span data-ttu-id="81b16-194">I `EmailAttachmentInfo` tabellerna `EmailEvents` och kolumnen har lagts till för att ge mer information om `ThreatNames` e-posthotet.</span><span class="sxs-lookup"><span data-stu-id="81b16-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="81b16-195">Den här kolumnen innehåller värden som Spam eller Phish.</span><span class="sxs-lookup"><span data-stu-id="81b16-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="81b16-196">I [tabellen DeviceInfo](advanced-hunting-deviceinfo-table.md) har kolumnen `DeviceObjectId` ersatts med kolumnen `AadDeviceId` baserat på feedback från kunder.</span><span class="sxs-lookup"><span data-stu-id="81b16-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="81b16-197">I tabellen [DeviceEvents](advanced-hunting-deviceevents-table.md) har flera ActionType-namn ändrats för att bättre återspegla beskrivningen av åtgärden.</span><span class="sxs-lookup"><span data-stu-id="81b16-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="81b16-198">Information om ändringarna finns nedan.</span><span class="sxs-lookup"><span data-stu-id="81b16-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="81b16-199">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="81b16-199">Table name</span></span> | <span data-ttu-id="81b16-200">Ursprungligt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="81b16-200">Original ActionType name</span></span> | <span data-ttu-id="81b16-201">Nytt ActionType-namn</span><span class="sxs-lookup"><span data-stu-id="81b16-201">New ActionType name</span></span> | <span data-ttu-id="81b16-202">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="81b16-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="81b16-203">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="81b16-204">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="81b16-205">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="81b16-206">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-206">Customer feedback</span></span> |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | <span data-ttu-id="81b16-207">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="81b16-207">Customer feedback</span></span> |





## <a name="related-topics"></a><span data-ttu-id="81b16-208">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="81b16-208">Related topics</span></span>
- [<span data-ttu-id="81b16-209">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="81b16-209">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81b16-210">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="81b16-210">Understand the schema</span></span>](advanced-hunting-schema-tables.md)