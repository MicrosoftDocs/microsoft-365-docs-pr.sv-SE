---
title: DeviceAlertEvents-tabellen i det avancerade sökschemat
description: Läs mer om händelser för aviseringsgenerering i tabellen DeviceAlertEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, microsoft defender for endpoint, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939657"
---
# <a name="devicealertevents"></a><span data-ttu-id="c4ad8-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="c4ad8-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4ad8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c4ad8-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4ad8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c4ad8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="c4ad8-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c4ad8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4ad8-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c4ad8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c4ad8-109">Tabellen `DeviceAlertEvents` i det avancerade schemat [för](advanced-hunting-overview.md) sökning innehåller information om aviseringar i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="c4ad8-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="c4ad8-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="c4ad8-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c4ad8-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="c4ad8-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c4ad8-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="c4ad8-112">Column name</span></span> | <span data-ttu-id="c4ad8-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="c4ad8-113">Data type</span></span> | <span data-ttu-id="c4ad8-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c4ad8-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="c4ad8-115">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-115">string</span></span> | <span data-ttu-id="c4ad8-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="c4ad8-117">datetime</span><span class="sxs-lookup"><span data-stu-id="c4ad8-117">datetime</span></span> | <span data-ttu-id="c4ad8-118">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="c4ad8-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c4ad8-119">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-119">string</span></span> | <span data-ttu-id="c4ad8-120">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="c4ad8-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c4ad8-121">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-121">string</span></span> | <span data-ttu-id="c4ad8-122">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="c4ad8-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="c4ad8-123">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-123">string</span></span> | <span data-ttu-id="c4ad8-124">Anger den potentiella påverkan (hög, medium eller låg) av hotindikatorn eller intrångsaktiviteten som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="c4ad8-125">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-125">string</span></span> | <span data-ttu-id="c4ad8-126">Typ av hotindikator eller intrångsaktivitet som identifieras av aviseringen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="c4ad8-127">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-127">string</span></span> | <span data-ttu-id="c4ad8-128">Aviseringens rubrik</span><span class="sxs-lookup"><span data-stu-id="c4ad8-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="c4ad8-129">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-129">string</span></span> | <span data-ttu-id="c4ad8-130">Namnet på filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="c4ad8-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c4ad8-131">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-131">string</span></span> | <span data-ttu-id="c4ad8-132">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="c4ad8-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c4ad8-133">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-133">string</span></span> | <span data-ttu-id="c4ad8-134">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="c4ad8-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="c4ad8-135">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-135">string</span></span> | <span data-ttu-id="c4ad8-136">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="c4ad8-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="c4ad8-137">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-137">string</span></span> | <span data-ttu-id="c4ad8-138">MITRE ATT&CK-tekniker som är kopplade till aktiviteten som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="c4ad8-139">long</span><span class="sxs-lookup"><span data-stu-id="c4ad8-139">long</span></span> | <span data-ttu-id="c4ad8-140">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="c4ad8-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c4ad8-141">För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och</span><span class="sxs-lookup"><span data-stu-id="c4ad8-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="c4ad8-142">sträng</span><span class="sxs-lookup"><span data-stu-id="c4ad8-142">string</span></span> | <span data-ttu-id="c4ad8-143">Tabell som innehåller information om händelsen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c4ad8-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c4ad8-144">Related topics</span></span>
- [<span data-ttu-id="c4ad8-145">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c4ad8-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4ad8-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c4ad8-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c4ad8-147">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c4ad8-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
