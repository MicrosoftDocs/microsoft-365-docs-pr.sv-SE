---
title: Namnändringar i det avancerade sökschemat i Microsoft 365 Defender
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066875"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="eab89-104">Avancerat schema för sök – namnändringar</span><span class="sxs-lookup"><span data-stu-id="eab89-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eab89-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="eab89-105">**Applies to:**</span></span>
- <span data-ttu-id="eab89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eab89-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="eab89-107">Det [avancerade sökschemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner.</span><span class="sxs-lookup"><span data-stu-id="eab89-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="eab89-108">I vissa fall byter befintliga kolumnnamn namn eller ersätts för att förbättra användarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="eab89-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="eab89-109">I den här artikeln kan du läsa om vilka namnändringar som kan påverka dina frågor.</span><span class="sxs-lookup"><span data-stu-id="eab89-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="eab89-110">Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="eab89-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="eab89-111">Du behöver inte uppdatera dessa frågor manuellt.</span><span class="sxs-lookup"><span data-stu-id="eab89-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="eab89-112">Du måste dock uppdatera följande frågor:</span><span class="sxs-lookup"><span data-stu-id="eab89-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="eab89-113">Frågor som körs med API:t</span><span class="sxs-lookup"><span data-stu-id="eab89-113">Queries that are run using the API</span></span>
- <span data-ttu-id="eab89-114">Frågor som sparas någon annanstans utanför säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="eab89-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="eab89-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="eab89-115">December 2020</span></span>

| <span data-ttu-id="eab89-116">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="eab89-116">Table name</span></span> | <span data-ttu-id="eab89-117">Ursprungligt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="eab89-117">Original column name</span></span> | <span data-ttu-id="eab89-118">Nytt kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="eab89-118">New column name</span></span> | <span data-ttu-id="eab89-119">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="eab89-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="eab89-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="eab89-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="eab89-121">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="eab89-121">Customer feedback</span></span> |
| [<span data-ttu-id="eab89-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="eab89-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="eab89-123">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="eab89-123">Customer feedback</span></span> |
| [<span data-ttu-id="eab89-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="eab89-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="eab89-125">Feedback från kunder</span><span class="sxs-lookup"><span data-stu-id="eab89-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="eab89-126">Januari 2021</span><span class="sxs-lookup"><span data-stu-id="eab89-126">January 2021</span></span>

| <span data-ttu-id="eab89-127">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="eab89-127">Column name</span></span> | <span data-ttu-id="eab89-128">Det ursprungliga värdenamnet</span><span class="sxs-lookup"><span data-stu-id="eab89-128">Original value name</span></span> | <span data-ttu-id="eab89-129">Nytt värdenamn</span><span class="sxs-lookup"><span data-stu-id="eab89-129">New value name</span></span> | <span data-ttu-id="eab89-130">Orsak till ändring</span><span class="sxs-lookup"><span data-stu-id="eab89-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="eab89-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="eab89-131">MCAS</span></span> |    <span data-ttu-id="eab89-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eab89-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="eab89-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="eab89-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="eab89-135">EDR</span><span class="sxs-lookup"><span data-stu-id="eab89-135">EDR</span></span>| <span data-ttu-id="eab89-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="eab89-137">WindowsDefenderAv</span></span> | <span data-ttu-id="eab89-138">Antivirus</span><span class="sxs-lookup"><span data-stu-id="eab89-138">Antivirus</span></span> | <span data-ttu-id="eab89-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-140">WindowsDefender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="eab89-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="eab89-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="eab89-141">SmartScreen</span></span> | <span data-ttu-id="eab89-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="eab89-143">CustomerTI</span></span> |  <span data-ttu-id="eab89-144">Anpassat TI</span><span class="sxs-lookup"><span data-stu-id="eab89-144">Custom TI</span></span> | <span data-ttu-id="eab89-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="eab89-146">OfficeATP</span></span> | <span data-ttu-id="eab89-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="eab89-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="eab89-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-149">MTP</span><span class="sxs-lookup"><span data-stu-id="eab89-149">MTP</span></span>   | <span data-ttu-id="eab89-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eab89-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="eab89-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="eab89-152">AzureATP</span></span> |    <span data-ttu-id="eab89-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="eab89-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="eab89-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="eab89-155">CustomDetection</span></span>   | <span data-ttu-id="eab89-156">Anpassad identifiering</span><span class="sxs-lookup"><span data-stu-id="eab89-156">Custom detection</span></span> | <span data-ttu-id="eab89-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="eab89-158">AutomatedInvestigation</span></span> |<span data-ttu-id="eab89-159">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="eab89-159">Automated investigation</span></span> | <span data-ttu-id="eab89-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="eab89-161">ThreatExperts</span></span> | <span data-ttu-id="eab89-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="eab89-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="eab89-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="eab89-164">TI från tredje part</span><span class="sxs-lookup"><span data-stu-id="eab89-164">3rd party TI</span></span> | <span data-ttu-id="eab89-165">Tredje parts sensor</span><span class="sxs-lookup"><span data-stu-id="eab89-165">3rd Party sensors</span></span> | <span data-ttu-id="eab89-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="eab89-167">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="eab89-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="eab89-168">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="eab89-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="eab89-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="eab89-170">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="eab89-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="eab89-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eab89-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="eab89-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="eab89-173">Skaffa Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="eab89-173">Office 365 ATP</span></span>  |<span data-ttu-id="eab89-174">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="eab89-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="eab89-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="eab89-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="eab89-176">Azure ATP</span></span>    |<span data-ttu-id="eab89-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="eab89-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="eab89-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="eab89-178">Rebranding</span></span> |

<span data-ttu-id="eab89-179">`DetectionSource`är tillgängligt i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="eab89-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="eab89-180">`ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="eab89-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="eab89-181">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="eab89-181">Related topics</span></span>
- [<span data-ttu-id="eab89-182">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="eab89-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="eab89-183">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="eab89-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)