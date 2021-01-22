---
title: Tabellen AppFileEvents i det avancerade sökschemat
description: Läs mer om filrelaterade händelser som är associerade med molnappar och -tjänster i tabellen AppFileEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932880"
---
# <a name="appfileevents"></a><span data-ttu-id="59af8-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="59af8-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59af8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="59af8-105">**Applies to:**</span></span>
- <span data-ttu-id="59af8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59af8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="59af8-107">Tabellen `AppFileEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="59af8-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="59af8-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="59af8-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="59af8-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="59af8-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="59af8-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="59af8-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="59af8-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="59af8-111">Column name</span></span> | <span data-ttu-id="59af8-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="59af8-112">Data type</span></span> | <span data-ttu-id="59af8-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="59af8-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="59af8-114">datetime</span><span class="sxs-lookup"><span data-stu-id="59af8-114">datetime</span></span> | <span data-ttu-id="59af8-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="59af8-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="59af8-116">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-116">string</span></span> | <span data-ttu-id="59af8-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="59af8-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="59af8-118">Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="59af8-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="59af8-119">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-119">string</span></span> | <span data-ttu-id="59af8-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="59af8-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="59af8-121">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-121">string</span></span> | <span data-ttu-id="59af8-122">Namnet på filen där den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="59af8-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="59af8-123">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-123">string</span></span> | <span data-ttu-id="59af8-124">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="59af8-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="59af8-125">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-125">string</span></span> | <span data-ttu-id="59af8-126">Det ursprungliga namnet på filen som ändrades på grund av åtgärden</span><span class="sxs-lookup"><span data-stu-id="59af8-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="59af8-127">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-127">string</span></span> | <span data-ttu-id="59af8-128">Originalmapp som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="59af8-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="59af8-129">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-129">string</span></span> | <span data-ttu-id="59af8-130">Nätverksprotokoll som används</span><span class="sxs-lookup"><span data-stu-id="59af8-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="59af8-131">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-131">string</span></span> | <span data-ttu-id="59af8-132">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="59af8-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="59af8-133">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-133">string</span></span> | <span data-ttu-id="59af8-134">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="59af8-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="59af8-135">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-135">string</span></span> | <span data-ttu-id="59af8-136">Kontots huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="59af8-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="59af8-137">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-137">string</span></span> | <span data-ttu-id="59af8-138">Unikt ID för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="59af8-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="59af8-139">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-139">string</span></span> | <span data-ttu-id="59af8-140">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="59af8-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="59af8-141">Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="59af8-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="59af8-142">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-142">string</span></span> | <span data-ttu-id="59af8-143">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="59af8-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="59af8-144">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-144">string</span></span> | <span data-ttu-id="59af8-145">Typ av enhet</span><span class="sxs-lookup"><span data-stu-id="59af8-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="59af8-146">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-146">string</span></span> | <span data-ttu-id="59af8-147">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="59af8-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="59af8-148">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="59af8-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="59af8-149">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-149">string</span></span> | <span data-ttu-id="59af8-150">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="59af8-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="59af8-151">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-151">string</span></span> | <span data-ttu-id="59af8-152">Namn på den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="59af8-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="59af8-153">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-153">string</span></span> | <span data-ttu-id="59af8-154">IP-adressen för den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="59af8-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="59af8-155">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-155">string</span></span> | <span data-ttu-id="59af8-156">Stad, land eller annan geografisk plats som är kopplad till händelsen</span><span class="sxs-lookup"><span data-stu-id="59af8-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="59af8-157">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-157">string</span></span> | <span data-ttu-id="59af8-158">Internet tjänstprovider (ISP) som är kopplad till slutpunktens IP-adress</span><span class="sxs-lookup"><span data-stu-id="59af8-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="59af8-159">long</span><span class="sxs-lookup"><span data-stu-id="59af8-159">long</span></span> | <span data-ttu-id="59af8-160">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="59af8-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="59af8-161">sträng</span><span class="sxs-lookup"><span data-stu-id="59af8-161">string</span></span> | <span data-ttu-id="59af8-162">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="59af8-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="59af8-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="59af8-163">Related topics</span></span>
- [<span data-ttu-id="59af8-164">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="59af8-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59af8-165">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="59af8-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="59af8-166">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="59af8-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="59af8-167">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="59af8-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="59af8-168">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="59af8-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="59af8-169">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="59af8-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
