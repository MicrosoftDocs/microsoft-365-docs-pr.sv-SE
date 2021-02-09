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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145493"
---
# <a name="appfileevents"></a><span data-ttu-id="72ece-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="72ece-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72ece-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="72ece-105">**Applies to:**</span></span>
- <span data-ttu-id="72ece-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72ece-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="72ece-107">Tabellen `AppFileEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="72ece-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="72ece-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="72ece-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="72ece-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="72ece-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="72ece-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="72ece-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="72ece-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="72ece-111">Column name</span></span> | <span data-ttu-id="72ece-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="72ece-112">Data type</span></span> | <span data-ttu-id="72ece-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="72ece-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="72ece-114">datetime</span><span class="sxs-lookup"><span data-stu-id="72ece-114">datetime</span></span> | <span data-ttu-id="72ece-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="72ece-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="72ece-116">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-116">string</span></span> | <span data-ttu-id="72ece-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="72ece-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="72ece-118">Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="72ece-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="72ece-119">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-119">string</span></span> | <span data-ttu-id="72ece-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="72ece-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="72ece-121">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-121">string</span></span> | <span data-ttu-id="72ece-122">Namnet på filen där den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="72ece-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="72ece-123">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-123">string</span></span> | <span data-ttu-id="72ece-124">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="72ece-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="72ece-125">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-125">string</span></span> | <span data-ttu-id="72ece-126">Det ursprungliga namnet på filen som ändrades på grund av åtgärden</span><span class="sxs-lookup"><span data-stu-id="72ece-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="72ece-127">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-127">string</span></span> | <span data-ttu-id="72ece-128">Originalmapp som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="72ece-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="72ece-129">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-129">string</span></span> | <span data-ttu-id="72ece-130">Nätverksprotokoll som används</span><span class="sxs-lookup"><span data-stu-id="72ece-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="72ece-131">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-131">string</span></span> | <span data-ttu-id="72ece-132">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="72ece-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="72ece-133">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-133">string</span></span> | <span data-ttu-id="72ece-134">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="72ece-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="72ece-135">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-135">string</span></span> | <span data-ttu-id="72ece-136">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="72ece-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="72ece-137">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-137">string</span></span> | <span data-ttu-id="72ece-138">Kontots huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="72ece-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="72ece-139">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-139">string</span></span> | <span data-ttu-id="72ece-140">Unikt ID för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="72ece-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="72ece-141">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-141">string</span></span> | <span data-ttu-id="72ece-142">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="72ece-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="72ece-143">Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="72ece-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="72ece-144">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-144">string</span></span> | <span data-ttu-id="72ece-145">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="72ece-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="72ece-146">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-146">string</span></span> | <span data-ttu-id="72ece-147">Typ av enhet</span><span class="sxs-lookup"><span data-stu-id="72ece-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="72ece-148">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-148">string</span></span> | <span data-ttu-id="72ece-149">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="72ece-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="72ece-150">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="72ece-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="72ece-151">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-151">string</span></span> | <span data-ttu-id="72ece-152">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="72ece-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="72ece-153">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-153">string</span></span> | <span data-ttu-id="72ece-154">TCP-port som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="72ece-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="72ece-155">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-155">string</span></span> | <span data-ttu-id="72ece-156">Namn på den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="72ece-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="72ece-157">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-157">string</span></span> | <span data-ttu-id="72ece-158">IP-adressen för den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="72ece-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="72ece-159">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-159">string</span></span> | <span data-ttu-id="72ece-160">Målport för relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="72ece-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="72ece-161">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-161">string</span></span> | <span data-ttu-id="72ece-162">Stad, land eller annan geografisk plats som är kopplad till händelsen</span><span class="sxs-lookup"><span data-stu-id="72ece-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="72ece-163">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-163">string</span></span> | <span data-ttu-id="72ece-164">Internet tjänstprovider (ISP) som är kopplad till slutpunktens IP-adress</span><span class="sxs-lookup"><span data-stu-id="72ece-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="72ece-165">long</span><span class="sxs-lookup"><span data-stu-id="72ece-165">long</span></span> | <span data-ttu-id="72ece-166">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="72ece-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="72ece-167">sträng</span><span class="sxs-lookup"><span data-stu-id="72ece-167">string</span></span> | <span data-ttu-id="72ece-168">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="72ece-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="72ece-169">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="72ece-169">Related topics</span></span>
- [<span data-ttu-id="72ece-170">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="72ece-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72ece-171">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="72ece-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72ece-172">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="72ece-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="72ece-173">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="72ece-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="72ece-174">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="72ece-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="72ece-175">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="72ece-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
