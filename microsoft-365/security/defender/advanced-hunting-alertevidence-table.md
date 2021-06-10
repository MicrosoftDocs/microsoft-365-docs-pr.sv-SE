---
title: Tabellen AlertEvidence i det avancerade sökschemat
description: Läs mer om information som är kopplad till aviseringar i tabellen AlertEvidence i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932589"
---
# <a name="alertevidence"></a><span data-ttu-id="ff7f9-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ff7f9-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ff7f9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ff7f9-105">**Applies to:**</span></span>
- <span data-ttu-id="ff7f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff7f9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ff7f9-107">Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL-adresser, användare och enheter – som associeras med aviseringar från Microsoft Defender för slutpunkt, Microsoft Defender för [](advanced-hunting-overview.md) Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet.</span><span class="sxs-lookup"><span data-stu-id="ff7f9-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="ff7f9-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="ff7f9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ff7f9-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="ff7f9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ff7f9-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="ff7f9-110">Column name</span></span> | <span data-ttu-id="ff7f9-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="ff7f9-111">Data type</span></span> | <span data-ttu-id="ff7f9-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ff7f9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ff7f9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ff7f9-113">datetime</span></span> | <span data-ttu-id="ff7f9-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="ff7f9-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="ff7f9-115">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-115">string</span></span> | <span data-ttu-id="ff7f9-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="ff7f9-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="ff7f9-117">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-117">string</span></span> | <span data-ttu-id="ff7f9-118">Produkt eller tjänst som tillhandahöll aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="ff7f9-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="ff7f9-119">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-119">string</span></span> | <span data-ttu-id="ff7f9-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="ff7f9-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="ff7f9-121">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-121">string</span></span> | <span data-ttu-id="ff7f9-122">Hur entitet involveras i en avisering, som anger om den påverkas eller inte är relaterad</span><span class="sxs-lookup"><span data-stu-id="ff7f9-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="ff7f9-123">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-123">string</span></span> | <span data-ttu-id="ff7f9-124">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="ff7f9-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="ff7f9-125">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-125">string</span></span> | <span data-ttu-id="ff7f9-126">Namnet på filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="ff7f9-127">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-127">string</span></span> | <span data-ttu-id="ff7f9-128">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="ff7f9-129">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-129">string</span></span> | <span data-ttu-id="ff7f9-130">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="ff7f9-131">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-131">string</span></span> | <span data-ttu-id="ff7f9-132">SHA-256 av filen som den inspelade åtgärden tillämpats på.</span><span class="sxs-lookup"><span data-stu-id="ff7f9-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="ff7f9-133">Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="ff7f9-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="ff7f9-134">int</span><span class="sxs-lookup"><span data-stu-id="ff7f9-134">int</span></span> | <span data-ttu-id="ff7f9-135">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="ff7f9-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="ff7f9-136">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-136">string</span></span> | <span data-ttu-id="ff7f9-137">Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="ff7f9-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="ff7f9-138">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-138">string</span></span> | <span data-ttu-id="ff7f9-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="ff7f9-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ff7f9-140">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-140">string</span></span> | <span data-ttu-id="ff7f9-141">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="ff7f9-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="ff7f9-142">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-142">string</span></span> | <span data-ttu-id="ff7f9-143">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="ff7f9-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ff7f9-144">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-144">string</span></span> | <span data-ttu-id="ff7f9-145">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="ff7f9-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ff7f9-146">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-146">string</span></span> | <span data-ttu-id="ff7f9-147">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="ff7f9-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ff7f9-148">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-148">string</span></span> | <span data-ttu-id="ff7f9-149">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff7f9-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="ff7f9-150">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-150">string</span></span> | <span data-ttu-id="ff7f9-151">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="ff7f9-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="ff7f9-152">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-152">string</span></span> | <span data-ttu-id="ff7f9-153">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="ff7f9-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ff7f9-154">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-154">string</span></span> | <span data-ttu-id="ff7f9-155">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="ff7f9-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="ff7f9-156">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-156">string</span></span> | <span data-ttu-id="ff7f9-157">IP-adress tilldelad till den lokala enheten som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="ff7f9-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ff7f9-158">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-158">string</span></span> | <span data-ttu-id="ff7f9-159">Unikt ID för e-postmeddelandet som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="ff7f9-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="ff7f9-160">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-160">string</span></span> | <span data-ttu-id="ff7f9-161">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="ff7f9-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="ff7f9-162">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-162">string</span></span> | <span data-ttu-id="ff7f9-163">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="ff7f9-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="ff7f9-164">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-164">string</span></span> | <span data-ttu-id="ff7f9-165">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="ff7f9-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="ff7f9-166">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-166">string</span></span> | <span data-ttu-id="ff7f9-167">Kommandorad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="ff7f9-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="ff7f9-168">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-168">string</span></span> | <span data-ttu-id="ff7f9-169">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="ff7f9-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="ff7f9-170">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-170">string</span></span> | <span data-ttu-id="ff7f9-171">Registernyckel som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="ff7f9-172">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-172">string</span></span> | <span data-ttu-id="ff7f9-173">Namnet på registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="ff7f9-174">sträng</span><span class="sxs-lookup"><span data-stu-id="ff7f9-174">string</span></span> | <span data-ttu-id="ff7f9-175">Data för registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="ff7f9-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ff7f9-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ff7f9-176">Related topics</span></span>
- [<span data-ttu-id="ff7f9-177">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ff7f9-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ff7f9-178">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="ff7f9-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ff7f9-179">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="ff7f9-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ff7f9-180">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="ff7f9-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ff7f9-181">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="ff7f9-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ff7f9-182">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="ff7f9-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
