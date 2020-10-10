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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2e5cdf40f93e0fefccdeee8c605c20e5d29da6af
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414208"
---
# <a name="appfileevents"></a><span data-ttu-id="2c64c-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="2c64c-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c64c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c64c-105">**Applies to:**</span></span>
- <span data-ttu-id="2c64c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2c64c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2c64c-107">`AppFileEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om filrelaterade aktiviteter i moln program och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="2c64c-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="2c64c-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="2c64c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2c64c-109">Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="2c64c-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="2c64c-110">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2c64c-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2c64c-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="2c64c-111">Column name</span></span> | <span data-ttu-id="2c64c-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2c64c-112">Data type</span></span> | <span data-ttu-id="2c64c-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2c64c-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2c64c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="2c64c-114">datetime</span></span> | <span data-ttu-id="2c64c-115">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="2c64c-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2c64c-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-116">string</span></span> | <span data-ttu-id="2c64c-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="2c64c-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="2c64c-118">Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="2c64c-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="2c64c-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-119">string</span></span> | <span data-ttu-id="2c64c-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="2c64c-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="2c64c-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-121">string</span></span> | <span data-ttu-id="2c64c-122">Namnet på filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="2c64c-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="2c64c-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-123">string</span></span> | <span data-ttu-id="2c64c-124">Mapp som innehåller filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="2c64c-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="2c64c-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-125">string</span></span> | <span data-ttu-id="2c64c-126">Ursprungligt namn på den fil som har bytt namn som resultat av åtgärden</span><span class="sxs-lookup"><span data-stu-id="2c64c-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="2c64c-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-127">string</span></span> | <span data-ttu-id="2c64c-128">Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="2c64c-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="2c64c-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-129">string</span></span> | <span data-ttu-id="2c64c-130">Använda nätverks protokoll</span><span class="sxs-lookup"><span data-stu-id="2c64c-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="2c64c-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-131">string</span></span> | <span data-ttu-id="2c64c-132">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="2c64c-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2c64c-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-133">string</span></span> | <span data-ttu-id="2c64c-134">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="2c64c-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2c64c-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-135">string</span></span> | <span data-ttu-id="2c64c-136">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="2c64c-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2c64c-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-137">string</span></span> | <span data-ttu-id="2c64c-138">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="2c64c-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2c64c-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-139">string</span></span> | <span data-ttu-id="2c64c-140">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="2c64c-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2c64c-141">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="2c64c-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="2c64c-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-142">string</span></span> | <span data-ttu-id="2c64c-143">Det fullständigt kvalificerade domän namnet (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="2c64c-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="2c64c-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-144">string</span></span> | <span data-ttu-id="2c64c-145">Enhets typ</span><span class="sxs-lookup"><span data-stu-id="2c64c-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="2c64c-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-146">string</span></span> | <span data-ttu-id="2c64c-147">Plattformen för det operativ system som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="2c64c-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2c64c-148">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2c64c-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="2c64c-149">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-149">string</span></span> | <span data-ttu-id="2c64c-150">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="2c64c-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="2c64c-151">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-151">string</span></span> | <span data-ttu-id="2c64c-152">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="2c64c-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="2c64c-153">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-153">string</span></span> | <span data-ttu-id="2c64c-154">IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="2c64c-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="2c64c-155">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-155">string</span></span> | <span data-ttu-id="2c64c-156">Ort, land eller annan geografisk plats som är kopplad till evenemanget</span><span class="sxs-lookup"><span data-stu-id="2c64c-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="2c64c-157">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-157">string</span></span> | <span data-ttu-id="2c64c-158">Internet leverantör (ISP) associerad med slut punktens IP-adress</span><span class="sxs-lookup"><span data-stu-id="2c64c-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="2c64c-159">tids</span><span class="sxs-lookup"><span data-stu-id="2c64c-159">long</span></span> | <span data-ttu-id="2c64c-160">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="2c64c-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="2c64c-161">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="2c64c-161">string</span></span> | <span data-ttu-id="2c64c-162">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="2c64c-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2c64c-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2c64c-163">Related topics</span></span>
- [<span data-ttu-id="2c64c-164">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="2c64c-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c64c-165">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="2c64c-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2c64c-166">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="2c64c-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2c64c-167">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="2c64c-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2c64c-168">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="2c64c-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2c64c-169">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="2c64c-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
