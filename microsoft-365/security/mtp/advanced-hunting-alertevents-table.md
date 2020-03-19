---
title: AlertEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om händelser för aviseringargenerering i tabellen AlertEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, alertevents, alertevents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808630"
---
# <a name="alertevents"></a><span data-ttu-id="6732b-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="6732b-104">AlertEvents</span></span>

<span data-ttu-id="6732b-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="6732b-105">**Applies to:**</span></span>
- <span data-ttu-id="6732b-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="6732b-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="6732b-107">Tabellen `AlertEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om Microsoft Defender ATP-aviseringar.</span><span class="sxs-lookup"><span data-stu-id="6732b-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="6732b-108">Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="6732b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6732b-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6732b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6732b-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6732b-110">Column name</span></span> | <span data-ttu-id="6732b-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6732b-111">Data type</span></span> | <span data-ttu-id="6732b-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6732b-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="6732b-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-113">string</span></span> | <span data-ttu-id="6732b-114">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="6732b-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="6732b-115">Datetime</span><span class="sxs-lookup"><span data-stu-id="6732b-115">datetime</span></span> | <span data-ttu-id="6732b-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="6732b-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6732b-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-117">string</span></span> | <span data-ttu-id="6732b-118">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="6732b-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6732b-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-119">string</span></span> | <span data-ttu-id="6732b-120">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="6732b-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="6732b-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-121">string</span></span> | <span data-ttu-id="6732b-122">Anger den potentiella påverkan (hög, medel eller låg) av hotindikatorn eller brottsaktiviteten som identifierats av</span><span class="sxs-lookup"><span data-stu-id="6732b-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="6732b-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-123">string</span></span> | <span data-ttu-id="6732b-124">Typ av hotindikator eller överträdelseaktivitet som identifierats av registreringen</span><span class="sxs-lookup"><span data-stu-id="6732b-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="6732b-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-125">string</span></span> | <span data-ttu-id="6732b-126">Registreringens namn</span><span class="sxs-lookup"><span data-stu-id="6732b-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="6732b-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-127">string</span></span> | <span data-ttu-id="6732b-128">Namnet på den fil som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="6732b-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6732b-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-129">string</span></span> | <span data-ttu-id="6732b-130">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="6732b-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6732b-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-131">string</span></span> | <span data-ttu-id="6732b-132">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="6732b-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="6732b-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-133">string</span></span> | <span data-ttu-id="6732b-134">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="6732b-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="6732b-135">Lång</span><span class="sxs-lookup"><span data-stu-id="6732b-135">long</span></span> | <span data-ttu-id="6732b-136">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="6732b-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6732b-137">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp</span><span class="sxs-lookup"><span data-stu-id="6732b-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="6732b-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="6732b-138">string</span></span> | <span data-ttu-id="6732b-139">Tabell som innehåller information om händelsen</span><span class="sxs-lookup"><span data-stu-id="6732b-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6732b-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6732b-140">Related topics</span></span>
- [<span data-ttu-id="6732b-141">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="6732b-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6732b-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6732b-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6732b-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6732b-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6732b-144">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6732b-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6732b-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6732b-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6732b-146">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6732b-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
