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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430157"
---
# <a name="appfileevents"></a><span data-ttu-id="48d74-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="48d74-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="48d74-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="48d74-105">**Applies to:**</span></span>
- <span data-ttu-id="48d74-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="48d74-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="48d74-107">`AppFileEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om filrelaterade aktiviteter i moln program och tjänster som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="48d74-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="48d74-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="48d74-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="48d74-109">Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="48d74-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="48d74-110">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="48d74-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="48d74-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="48d74-111">Column name</span></span> | <span data-ttu-id="48d74-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="48d74-112">Data type</span></span> | <span data-ttu-id="48d74-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="48d74-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="48d74-114">datetime</span><span class="sxs-lookup"><span data-stu-id="48d74-114">datetime</span></span> | <span data-ttu-id="48d74-115">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="48d74-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="48d74-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-116">string</span></span> | <span data-ttu-id="48d74-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="48d74-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="48d74-118">Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="48d74-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="48d74-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-119">string</span></span> | <span data-ttu-id="48d74-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="48d74-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="48d74-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-121">string</span></span> | <span data-ttu-id="48d74-122">Namnet på filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="48d74-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="48d74-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-123">string</span></span> | <span data-ttu-id="48d74-124">Mapp som innehåller filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="48d74-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="48d74-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-125">string</span></span> | <span data-ttu-id="48d74-126">Ursprungligt namn på den fil som har bytt namn som resultat av åtgärden</span><span class="sxs-lookup"><span data-stu-id="48d74-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="48d74-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-127">string</span></span> | <span data-ttu-id="48d74-128">Den ursprungliga mappen som innehåller filen innan den inspelade åtgärden tillämpades</span><span class="sxs-lookup"><span data-stu-id="48d74-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="48d74-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-129">string</span></span> | <span data-ttu-id="48d74-130">Använda nätverks protokoll</span><span class="sxs-lookup"><span data-stu-id="48d74-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="48d74-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-131">string</span></span> | <span data-ttu-id="48d74-132">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="48d74-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="48d74-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-133">string</span></span> | <span data-ttu-id="48d74-134">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="48d74-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="48d74-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-135">string</span></span> | <span data-ttu-id="48d74-136">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="48d74-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="48d74-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-137">string</span></span> | <span data-ttu-id="48d74-138">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="48d74-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="48d74-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-139">string</span></span> | <span data-ttu-id="48d74-140">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="48d74-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="48d74-141">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="48d74-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="48d74-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-142">string</span></span> | <span data-ttu-id="48d74-143">Det fullständigt kvalificerade domän namnet (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="48d74-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="48d74-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-144">string</span></span> | <span data-ttu-id="48d74-145">Enhets typ</span><span class="sxs-lookup"><span data-stu-id="48d74-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="48d74-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-146">string</span></span> | <span data-ttu-id="48d74-147">Plattformen för det operativ system som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="48d74-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="48d74-148">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="48d74-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="48d74-149">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-149">string</span></span> | <span data-ttu-id="48d74-150">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="48d74-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="48d74-151">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-151">string</span></span> | <span data-ttu-id="48d74-152">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="48d74-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="48d74-153">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-153">string</span></span> | <span data-ttu-id="48d74-154">IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="48d74-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="48d74-155">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-155">string</span></span> | <span data-ttu-id="48d74-156">Ort, land eller annan geografisk plats som är kopplad till evenemanget</span><span class="sxs-lookup"><span data-stu-id="48d74-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="48d74-157">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-157">string</span></span> | <span data-ttu-id="48d74-158">Internet leverantör (ISP) associerad med slut punktens IP-adress</span><span class="sxs-lookup"><span data-stu-id="48d74-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="48d74-159">tids</span><span class="sxs-lookup"><span data-stu-id="48d74-159">long</span></span> | <span data-ttu-id="48d74-160">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="48d74-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="48d74-161">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="48d74-161">string</span></span> | <span data-ttu-id="48d74-162">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="48d74-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="48d74-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="48d74-163">Related topics</span></span>
- [<span data-ttu-id="48d74-164">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="48d74-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48d74-165">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="48d74-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="48d74-166">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="48d74-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="48d74-167">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="48d74-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="48d74-168">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="48d74-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="48d74-169">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="48d74-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
