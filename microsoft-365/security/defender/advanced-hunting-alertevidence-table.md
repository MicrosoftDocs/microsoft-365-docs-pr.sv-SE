---
title: Tabellen AlertEvidence i det avancerade sökschemat
description: Läs mer om information som är kopplad till aviseringar i tabellen AlertEvidence i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3e4a8c9bffd285d45c7a4002b1ecd96e6dda40b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071649"
---
# <a name="alertevidence"></a><span data-ttu-id="885b1-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="885b1-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="885b1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="885b1-105">**Applies to:**</span></span>
- <span data-ttu-id="885b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="885b1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="885b1-107">Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL-adresser, användare och enheter – som associeras med aviseringar från Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="885b1-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="885b1-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="885b1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="885b1-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="885b1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="885b1-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="885b1-110">Column name</span></span> | <span data-ttu-id="885b1-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="885b1-111">Data type</span></span> | <span data-ttu-id="885b1-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="885b1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="885b1-113">datetime</span><span class="sxs-lookup"><span data-stu-id="885b1-113">datetime</span></span> | <span data-ttu-id="885b1-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="885b1-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="885b1-115">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-115">string</span></span> | <span data-ttu-id="885b1-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="885b1-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="885b1-117">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-117">string</span></span> | <span data-ttu-id="885b1-118">Produkt eller tjänst som tillhandahöll aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="885b1-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="885b1-119">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-119">string</span></span> | <span data-ttu-id="885b1-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="885b1-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="885b1-121">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-121">string</span></span> | <span data-ttu-id="885b1-122">Hur entitet involveras i en avisering, som anger om den påverkas eller inte är relaterad</span><span class="sxs-lookup"><span data-stu-id="885b1-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="885b1-123">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-123">string</span></span> | <span data-ttu-id="885b1-124">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="885b1-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="885b1-125">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-125">string</span></span> | <span data-ttu-id="885b1-126">Namnet på filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="885b1-127">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-127">string</span></span> | <span data-ttu-id="885b1-128">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="885b1-129">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-129">string</span></span> | <span data-ttu-id="885b1-130">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="885b1-131">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-131">string</span></span> | <span data-ttu-id="885b1-132">SHA-256 av filen som den inspelade åtgärden tillämpats på.</span><span class="sxs-lookup"><span data-stu-id="885b1-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="885b1-133">Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="885b1-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="885b1-134">int</span><span class="sxs-lookup"><span data-stu-id="885b1-134">int</span></span> | <span data-ttu-id="885b1-135">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="885b1-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="885b1-136">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-136">string</span></span> | <span data-ttu-id="885b1-137">Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="885b1-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="885b1-138">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-138">string</span></span> | <span data-ttu-id="885b1-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="885b1-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="885b1-140">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-140">string</span></span> | <span data-ttu-id="885b1-141">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="885b1-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="885b1-142">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-142">string</span></span> | <span data-ttu-id="885b1-143">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="885b1-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="885b1-144">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-144">string</span></span> | <span data-ttu-id="885b1-145">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="885b1-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="885b1-146">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-146">string</span></span> | <span data-ttu-id="885b1-147">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="885b1-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="885b1-148">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-148">string</span></span> | <span data-ttu-id="885b1-149">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="885b1-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="885b1-150">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-150">string</span></span> | <span data-ttu-id="885b1-151">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="885b1-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="885b1-152">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-152">string</span></span> | <span data-ttu-id="885b1-153">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="885b1-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="885b1-154">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-154">string</span></span> | <span data-ttu-id="885b1-155">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="885b1-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="885b1-156">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-156">string</span></span> | <span data-ttu-id="885b1-157">IP-adress tilldelad till den lokala enheten som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="885b1-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="885b1-158">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-158">string</span></span> | <span data-ttu-id="885b1-159">Unikt ID för e-postmeddelandet som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="885b1-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="885b1-160">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-160">string</span></span> | <span data-ttu-id="885b1-161">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="885b1-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="885b1-162">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-162">string</span></span> | <span data-ttu-id="885b1-163">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="885b1-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="885b1-164">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-164">string</span></span> | <span data-ttu-id="885b1-165">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="885b1-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="885b1-166">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-166">string</span></span> | <span data-ttu-id="885b1-167">Kommandorad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="885b1-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="885b1-168">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-168">string</span></span> | <span data-ttu-id="885b1-169">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="885b1-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="885b1-170">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-170">string</span></span> | <span data-ttu-id="885b1-171">Registernyckel som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="885b1-172">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-172">string</span></span> | <span data-ttu-id="885b1-173">Namnet på registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="885b1-174">sträng</span><span class="sxs-lookup"><span data-stu-id="885b1-174">string</span></span> | <span data-ttu-id="885b1-175">Data för registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="885b1-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="885b1-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="885b1-176">Related topics</span></span>
- [<span data-ttu-id="885b1-177">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="885b1-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="885b1-178">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="885b1-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="885b1-179">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="885b1-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="885b1-180">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="885b1-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="885b1-181">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="885b1-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="885b1-182">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="885b1-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
