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
ms.openlocfilehash: 7b1f581e1cfc8345df6e7b8053621cf46110c355
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499882"
---
# <a name="alertevidence"></a><span data-ttu-id="6735a-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="6735a-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6735a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6735a-105">**Applies to:**</span></span>
- <span data-ttu-id="6735a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6735a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6735a-107">Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL-adresser, användare och enheter – som associeras med aviseringar från Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6735a-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6735a-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="6735a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6735a-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6735a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6735a-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6735a-110">Column name</span></span> | <span data-ttu-id="6735a-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6735a-111">Data type</span></span> | <span data-ttu-id="6735a-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6735a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6735a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6735a-113">datetime</span></span> | <span data-ttu-id="6735a-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="6735a-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="6735a-115">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-115">string</span></span> | <span data-ttu-id="6735a-116">Unikt ID för aviseringen</span><span class="sxs-lookup"><span data-stu-id="6735a-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="6735a-117">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-117">string</span></span> | <span data-ttu-id="6735a-118">Produkt eller tjänst som tillhandahöll aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="6735a-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="6735a-119">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-119">string</span></span> | <span data-ttu-id="6735a-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="6735a-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="6735a-121">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-121">string</span></span> | <span data-ttu-id="6735a-122">Hur entitet involveras i en avisering, som anger om den påverkas eller inte är relaterad</span><span class="sxs-lookup"><span data-stu-id="6735a-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="6735a-123">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-123">string</span></span> | <span data-ttu-id="6735a-124">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="6735a-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="6735a-125">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-125">string</span></span> | <span data-ttu-id="6735a-126">Namnet på filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6735a-127">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-127">string</span></span> | <span data-ttu-id="6735a-128">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6735a-129">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-129">string</span></span> | <span data-ttu-id="6735a-130">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="6735a-131">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-131">string</span></span> | <span data-ttu-id="6735a-132">SHA-256 av filen som den inspelade åtgärden tillämpats på.</span><span class="sxs-lookup"><span data-stu-id="6735a-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="6735a-133">Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6735a-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="6735a-134">int</span><span class="sxs-lookup"><span data-stu-id="6735a-134">int</span></span> | <span data-ttu-id="6735a-135">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="6735a-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="6735a-136">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-136">string</span></span> | <span data-ttu-id="6735a-137">Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="6735a-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="6735a-138">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-138">string</span></span> | <span data-ttu-id="6735a-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="6735a-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6735a-140">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-140">string</span></span> | <span data-ttu-id="6735a-141">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="6735a-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="6735a-142">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-142">string</span></span> | <span data-ttu-id="6735a-143">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="6735a-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6735a-144">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-144">string</span></span> | <span data-ttu-id="6735a-145">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="6735a-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6735a-146">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-146">string</span></span> | <span data-ttu-id="6735a-147">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="6735a-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6735a-148">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-148">string</span></span> | <span data-ttu-id="6735a-149">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6735a-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="6735a-150">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-150">string</span></span> | <span data-ttu-id="6735a-151">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="6735a-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="6735a-152">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-152">string</span></span> | <span data-ttu-id="6735a-153">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="6735a-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6735a-154">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-154">string</span></span> | <span data-ttu-id="6735a-155">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="6735a-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="6735a-156">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-156">string</span></span> | <span data-ttu-id="6735a-157">IP-adress tilldelad till den lokala enheten som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="6735a-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6735a-158">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-158">string</span></span> | <span data-ttu-id="6735a-159">Unikt ID för e-postmeddelandet som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="6735a-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="6735a-160">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-160">string</span></span> | <span data-ttu-id="6735a-161">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="6735a-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="6735a-162">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-162">string</span></span> | <span data-ttu-id="6735a-163">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="6735a-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="6735a-164">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-164">string</span></span> | <span data-ttu-id="6735a-165">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="6735a-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="6735a-166">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-166">string</span></span> | <span data-ttu-id="6735a-167">Kommandorad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="6735a-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="6735a-168">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-168">string</span></span> | <span data-ttu-id="6735a-169">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="6735a-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="6735a-170">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-170">string</span></span> | <span data-ttu-id="6735a-171">Registernyckel som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="6735a-172">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-172">string</span></span> | <span data-ttu-id="6735a-173">Namnet på registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="6735a-174">sträng</span><span class="sxs-lookup"><span data-stu-id="6735a-174">string</span></span> | <span data-ttu-id="6735a-175">Data för registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6735a-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6735a-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6735a-176">Related topics</span></span>
- [<span data-ttu-id="6735a-177">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6735a-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6735a-178">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6735a-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6735a-179">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6735a-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6735a-180">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="6735a-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6735a-181">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6735a-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6735a-182">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6735a-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
