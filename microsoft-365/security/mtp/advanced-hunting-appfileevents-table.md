---
title: AppFileEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om filrelaterade händelser som är kopplade till moln program och-tjänster i tabellen AppFileEvents i det avancerade Antivirus schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AppFileEvents, Cloud App-säkerhet, MCAS
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
ms.openlocfilehash: 4221af6b0378e67e12852dbef0bbc0a11ff56511
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649481"
---
# <a name="appfileevents"></a><span data-ttu-id="0af1a-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0af1a-104">AppFileEvents</span></span>

<span data-ttu-id="0af1a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0af1a-105">**Applies to:**</span></span>
- <span data-ttu-id="0af1a-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0af1a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0af1a-107">`AppFileEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om filrelaterade aktiviteter i moln program och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="0af1a-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0af1a-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0af1a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0af1a-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0af1a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0af1a-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0af1a-110">Column name</span></span> | <span data-ttu-id="0af1a-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0af1a-111">Data type</span></span> | <span data-ttu-id="0af1a-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0af1a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0af1a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0af1a-113">datetime</span></span> | <span data-ttu-id="0af1a-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="0af1a-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0af1a-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-115">string</span></span> | <span data-ttu-id="0af1a-116">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="0af1a-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0af1a-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-117">string</span></span> | <span data-ttu-id="0af1a-118">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0af1a-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0af1a-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-119">string</span></span> | <span data-ttu-id="0af1a-120">Namnet på filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="0af1a-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0af1a-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-121">string</span></span> | <span data-ttu-id="0af1a-122">Mapp som innehåller filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="0af1a-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0af1a-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-123">string</span></span> | <span data-ttu-id="0af1a-124">Ursprungligt namn på den fil som har bytt namn som resultat av åtgärden</span><span class="sxs-lookup"><span data-stu-id="0af1a-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0af1a-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-125">string</span></span> | <span data-ttu-id="0af1a-126">Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="0af1a-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0af1a-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-127">string</span></span> | <span data-ttu-id="0af1a-128">Använda nätverks protokoll</span><span class="sxs-lookup"><span data-stu-id="0af1a-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0af1a-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-129">string</span></span> | <span data-ttu-id="0af1a-130">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="0af1a-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0af1a-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-131">string</span></span> | <span data-ttu-id="0af1a-132">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="0af1a-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0af1a-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-133">string</span></span> | <span data-ttu-id="0af1a-134">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="0af1a-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0af1a-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-135">string</span></span> | <span data-ttu-id="0af1a-136">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0af1a-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0af1a-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-137">string</span></span> | <span data-ttu-id="0af1a-138">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="0af1a-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0af1a-139">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="0af1a-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0af1a-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-140">string</span></span> | <span data-ttu-id="0af1a-141">Det fullständigt kvalificerade domän namnet (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="0af1a-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0af1a-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-142">string</span></span> | <span data-ttu-id="0af1a-143">Enhets typ</span><span class="sxs-lookup"><span data-stu-id="0af1a-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0af1a-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-144">string</span></span> | <span data-ttu-id="0af1a-145">Plattformen för det operativ system som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="0af1a-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0af1a-146">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0af1a-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0af1a-147">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-147">string</span></span> | <span data-ttu-id="0af1a-148">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="0af1a-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="0af1a-149">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-149">string</span></span> | <span data-ttu-id="0af1a-150">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0af1a-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0af1a-151">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-151">string</span></span> | <span data-ttu-id="0af1a-152">IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0af1a-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="0af1a-153">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-153">string</span></span> | <span data-ttu-id="0af1a-154">Ort, land eller annan geografisk plats som är kopplad till evenemanget</span><span class="sxs-lookup"><span data-stu-id="0af1a-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0af1a-155">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-155">string</span></span> | <span data-ttu-id="0af1a-156">Internet leverantör (ISP) associerad med slut punktens IP-adress</span><span class="sxs-lookup"><span data-stu-id="0af1a-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0af1a-157">tids</span><span class="sxs-lookup"><span data-stu-id="0af1a-157">long</span></span> | <span data-ttu-id="0af1a-158">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="0af1a-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0af1a-159">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0af1a-159">string</span></span> | <span data-ttu-id="0af1a-160">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="0af1a-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0af1a-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0af1a-161">Related topics</span></span>
- [<span data-ttu-id="0af1a-162">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0af1a-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0af1a-163">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0af1a-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0af1a-164">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0af1a-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0af1a-165">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="0af1a-165">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0af1a-166">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0af1a-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0af1a-167">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0af1a-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
