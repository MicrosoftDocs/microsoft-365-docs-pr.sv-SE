---
title: AppFileEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser som är associerade med molnappar och molntjänster i tabellen AppFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204761"
---
# <a name="appfileevents"></a><span data-ttu-id="7ea3d-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7ea3d-104">AppFileEvents</span></span>

<span data-ttu-id="7ea3d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="7ea3d-105">**Applies to:**</span></span>
- <span data-ttu-id="7ea3d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="7ea3d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7ea3d-107">`AppFileEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om filrelaterade aktiviteter i molnappar och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7ea3d-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7ea3d-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7ea3d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7ea3d-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="7ea3d-110">Column name</span></span> | <span data-ttu-id="7ea3d-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="7ea3d-111">Data type</span></span> | <span data-ttu-id="7ea3d-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7ea3d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7ea3d-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="7ea3d-113">datetime</span></span> | <span data-ttu-id="7ea3d-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="7ea3d-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7ea3d-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-115">string</span></span> | <span data-ttu-id="7ea3d-116">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="7ea3d-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="7ea3d-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-117">string</span></span> | <span data-ttu-id="7ea3d-118">Ansökan som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="7ea3d-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="7ea3d-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-119">string</span></span> | <span data-ttu-id="7ea3d-120">Namnet på den fil som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="7ea3d-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="7ea3d-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-121">string</span></span> | <span data-ttu-id="7ea3d-122">Mapp som innehåller filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="7ea3d-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="7ea3d-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-123">string</span></span> | <span data-ttu-id="7ea3d-124">Det ursprungliga namnet på filen som har bytt namn till följd av åtgärden</span><span class="sxs-lookup"><span data-stu-id="7ea3d-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="7ea3d-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-125">string</span></span> | <span data-ttu-id="7ea3d-126">Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="7ea3d-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="7ea3d-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-127">string</span></span> | <span data-ttu-id="7ea3d-128">Nätverksprotokoll som används</span><span class="sxs-lookup"><span data-stu-id="7ea3d-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="7ea3d-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-129">string</span></span> | <span data-ttu-id="7ea3d-130">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="7ea3d-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7ea3d-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-131">string</span></span> | <span data-ttu-id="7ea3d-132">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="7ea3d-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7ea3d-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-133">string</span></span> | <span data-ttu-id="7ea3d-134">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="7ea3d-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7ea3d-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-135">string</span></span> | <span data-ttu-id="7ea3d-136">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="7ea3d-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7ea3d-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-137">string</span></span> | <span data-ttu-id="7ea3d-138">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7ea3d-139">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7ea3d-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-140">string</span></span> | <span data-ttu-id="7ea3d-141">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="7ea3d-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="7ea3d-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-142">string</span></span> | <span data-ttu-id="7ea3d-143">Typ av enhet</span><span class="sxs-lookup"><span data-stu-id="7ea3d-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="7ea3d-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-144">string</span></span> | <span data-ttu-id="7ea3d-145">Plattform för operativsystemet som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7ea3d-146">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7ea3d-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-147">string</span></span> | <span data-ttu-id="7ea3d-148">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="7ea3d-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7ea3d-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-149">string</span></span> | <span data-ttu-id="7ea3d-150">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="7ea3d-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7ea3d-151">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-151">string</span></span> | <span data-ttu-id="7ea3d-152">IP-adressen för den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="7ea3d-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="7ea3d-153">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-153">string</span></span> | <span data-ttu-id="7ea3d-154">Ort, land eller annan geografisk plats som är associerad med händelsen</span><span class="sxs-lookup"><span data-stu-id="7ea3d-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="7ea3d-155">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-155">string</span></span> | <span data-ttu-id="7ea3d-156">Internet-leverantör (ISP) som är associerad med IP-adressen för slutpunkten</span><span class="sxs-lookup"><span data-stu-id="7ea3d-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="7ea3d-157">Lång</span><span class="sxs-lookup"><span data-stu-id="7ea3d-157">long</span></span> | <span data-ttu-id="7ea3d-158">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="7ea3d-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7ea3d-159">Sträng</span><span class="sxs-lookup"><span data-stu-id="7ea3d-159">string</span></span> | <span data-ttu-id="7ea3d-160">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="7ea3d-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7ea3d-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7ea3d-161">Related topics</span></span>
- [<span data-ttu-id="7ea3d-162">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7ea3d-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ea3d-163">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="7ea3d-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7ea3d-164">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="7ea3d-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7ea3d-165">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="7ea3d-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7ea3d-166">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7ea3d-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7ea3d-167">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="7ea3d-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
