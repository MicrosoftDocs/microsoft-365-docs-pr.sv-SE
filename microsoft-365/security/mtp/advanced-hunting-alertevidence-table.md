---
title: Tabellen AlertEvidence i det avancerade sökschemat
description: Läs mer om information som är kopplad till aviseringar i tabellen AlertEvidence i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto
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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145307"
---
# <a name="alertevidence"></a><span data-ttu-id="b0eb5-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="b0eb5-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0eb5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b0eb5-105">**Applies to:**</span></span>
- <span data-ttu-id="b0eb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0eb5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b0eb5-107">Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL:er, användare eller enheter – som är associerade med aviseringar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b0eb5-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="b0eb5-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b0eb5-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="b0eb5-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b0eb5-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="b0eb5-110">Column name</span></span> | <span data-ttu-id="b0eb5-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="b0eb5-111">Data type</span></span> | <span data-ttu-id="b0eb5-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0eb5-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b0eb5-113">datetime</span><span class="sxs-lookup"><span data-stu-id="b0eb5-113">datetime</span></span> | <span data-ttu-id="b0eb5-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="b0eb5-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="b0eb5-115">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-115">string</span></span> | <span data-ttu-id="b0eb5-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="b0eb5-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="b0eb5-117">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-117">string</span></span> | <span data-ttu-id="b0eb5-118">Produkt eller tjänst som tillhandahållit aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="b0eb5-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="b0eb5-119">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-119">string</span></span> | <span data-ttu-id="b0eb5-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="b0eb5-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="b0eb5-121">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-121">string</span></span> | <span data-ttu-id="b0eb5-122">Hur entiteten involveras i en avisering, som anger om den påverkas eller inte är bara relaterad</span><span class="sxs-lookup"><span data-stu-id="b0eb5-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="b0eb5-123">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-123">string</span></span> | <span data-ttu-id="b0eb5-124">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="b0eb5-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="b0eb5-125">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-125">string</span></span> | <span data-ttu-id="b0eb5-126">Namnet på filen där den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="b0eb5-127">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-127">string</span></span> | <span data-ttu-id="b0eb5-128">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="b0eb5-129">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-129">string</span></span> | <span data-ttu-id="b0eb5-130">SHA-1 för den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="b0eb5-131">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-131">string</span></span> | <span data-ttu-id="b0eb5-132">SHA-256 för filen som den inspelade åtgärden tillämpats på.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="b0eb5-133">Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b0eb5-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="b0eb5-134">int</span><span class="sxs-lookup"><span data-stu-id="b0eb5-134">int</span></span> | <span data-ttu-id="b0eb5-135">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="b0eb5-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="b0eb5-136">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-136">string</span></span> | <span data-ttu-id="b0eb5-137">Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="b0eb5-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="b0eb5-138">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-138">string</span></span> | <span data-ttu-id="b0eb5-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="b0eb5-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="b0eb5-140">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-140">string</span></span> | <span data-ttu-id="b0eb5-141">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="b0eb5-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="b0eb5-142">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-142">string</span></span> | <span data-ttu-id="b0eb5-143">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="b0eb5-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b0eb5-144">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-144">string</span></span> | <span data-ttu-id="b0eb5-145">Domänen för kontot</span><span class="sxs-lookup"><span data-stu-id="b0eb5-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b0eb5-146">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-146">string</span></span> | <span data-ttu-id="b0eb5-147">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="b0eb5-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b0eb5-148">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-148">string</span></span> | <span data-ttu-id="b0eb5-149">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0eb5-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="b0eb5-150">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-150">string</span></span> | <span data-ttu-id="b0eb5-151">Kontots huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="b0eb5-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="b0eb5-152">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-152">string</span></span> | <span data-ttu-id="b0eb5-153">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="b0eb5-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b0eb5-154">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-154">string</span></span> | <span data-ttu-id="b0eb5-155">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="b0eb5-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="b0eb5-156">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-156">string</span></span> | <span data-ttu-id="b0eb5-157">IP-adress tilldelad till den lokala enheten som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="b0eb5-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="b0eb5-158">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-158">string</span></span> | <span data-ttu-id="b0eb5-159">Unikt ID för e-postmeddelandet som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="b0eb5-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="b0eb5-160">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-160">string</span></span> | <span data-ttu-id="b0eb5-161">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="b0eb5-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="b0eb5-162">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-162">string</span></span> | <span data-ttu-id="b0eb5-163">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="b0eb5-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="b0eb5-164">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-164">string</span></span> | <span data-ttu-id="b0eb5-165">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="b0eb5-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="b0eb5-166">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-166">string</span></span> | <span data-ttu-id="b0eb5-167">Kommandorad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="b0eb5-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="b0eb5-168">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-168">string</span></span> | <span data-ttu-id="b0eb5-169">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="b0eb5-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="b0eb5-170">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-170">string</span></span> | <span data-ttu-id="b0eb5-171">Registernyckel som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="b0eb5-172">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-172">string</span></span> | <span data-ttu-id="b0eb5-173">Namn på registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="b0eb5-174">sträng</span><span class="sxs-lookup"><span data-stu-id="b0eb5-174">string</span></span> | <span data-ttu-id="b0eb5-175">Data för registervärdet som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="b0eb5-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b0eb5-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b0eb5-176">Related topics</span></span>
- [<span data-ttu-id="b0eb5-177">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b0eb5-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0eb5-178">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="b0eb5-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0eb5-179">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="b0eb5-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b0eb5-180">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="b0eb5-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b0eb5-181">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="b0eb5-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b0eb5-182">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="b0eb5-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
