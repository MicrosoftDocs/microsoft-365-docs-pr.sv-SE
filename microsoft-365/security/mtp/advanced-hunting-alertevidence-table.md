---
title: Tabellen AlertEvidence i det avancerade sökschemat
description: Läs mer om information som är kopplad till aviseringar i tabellen AlertEvidence i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, Aviseringinfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932316"
---
# <a name="alertevidence"></a><span data-ttu-id="e3fb4-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="e3fb4-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e3fb4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e3fb4-105">**Applies to:**</span></span>
- <span data-ttu-id="e3fb4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3fb4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e3fb4-107">Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL:er, användare eller enheter – som är associerade med aviseringar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e3fb4-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="e3fb4-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="e3fb4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e3fb4-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="e3fb4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e3fb4-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="e3fb4-110">Column name</span></span> | <span data-ttu-id="e3fb4-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e3fb4-111">Data type</span></span> | <span data-ttu-id="e3fb4-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e3fb4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e3fb4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e3fb4-113">datetime</span></span> | <span data-ttu-id="e3fb4-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="e3fb4-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="e3fb4-115">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-115">string</span></span> | <span data-ttu-id="e3fb4-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="e3fb4-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="e3fb4-117">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-117">string</span></span> | <span data-ttu-id="e3fb4-118">Produkt eller tjänst som tillhandahållit aviseringsinformationen</span><span class="sxs-lookup"><span data-stu-id="e3fb4-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="e3fb4-119">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-119">string</span></span> | <span data-ttu-id="e3fb4-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="e3fb4-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="e3fb4-121">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-121">string</span></span> | <span data-ttu-id="e3fb4-122">Hur entiteten involveras i en avisering, som anger om den påverkas eller inte är bara relaterad</span><span class="sxs-lookup"><span data-stu-id="e3fb4-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="e3fb4-123">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-123">string</span></span> | <span data-ttu-id="e3fb4-124">Anger om entiteten är källan eller målet för en nätverksanslutning</span><span class="sxs-lookup"><span data-stu-id="e3fb4-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="e3fb4-125">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-125">string</span></span> | <span data-ttu-id="e3fb4-126">Namnet på filen där den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="e3fb4-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="e3fb4-127">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-127">string</span></span> | <span data-ttu-id="e3fb4-128">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="e3fb4-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e3fb4-129">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-129">string</span></span> | <span data-ttu-id="e3fb4-130">SHA-1 för den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="e3fb4-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="e3fb4-131">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-131">string</span></span> | <span data-ttu-id="e3fb4-132">SHA-256 för filen som den inspelade åtgärden tillämpats på.</span><span class="sxs-lookup"><span data-stu-id="e3fb4-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="e3fb4-133">Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e3fb4-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="e3fb4-134">int</span><span class="sxs-lookup"><span data-stu-id="e3fb4-134">int</span></span> | <span data-ttu-id="e3fb4-135">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="e3fb4-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="e3fb4-136">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-136">string</span></span> | <span data-ttu-id="e3fb4-137">Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="e3fb4-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="e3fb4-138">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-138">string</span></span> | <span data-ttu-id="e3fb4-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="e3fb4-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e3fb4-140">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-140">string</span></span> | <span data-ttu-id="e3fb4-141">URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till</span><span class="sxs-lookup"><span data-stu-id="e3fb4-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="e3fb4-142">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-142">string</span></span> | <span data-ttu-id="e3fb4-143">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="e3fb4-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e3fb4-144">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-144">string</span></span> | <span data-ttu-id="e3fb4-145">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="e3fb4-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e3fb4-146">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-146">string</span></span> | <span data-ttu-id="e3fb4-147">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="e3fb4-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e3fb4-148">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-148">string</span></span> | <span data-ttu-id="e3fb4-149">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e3fb4-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="e3fb4-150">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-150">string</span></span> | <span data-ttu-id="e3fb4-151">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="e3fb4-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e3fb4-152">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-152">string</span></span> | <span data-ttu-id="e3fb4-153">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="e3fb4-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="e3fb4-154">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-154">string</span></span> | <span data-ttu-id="e3fb4-155">IP-adress tilldelad till den lokala enheten som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="e3fb4-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="e3fb4-156">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-156">string</span></span> | <span data-ttu-id="e3fb4-157">Unikt ID för e-postmeddelandet som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="e3fb4-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="e3fb4-158">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-158">string</span></span> | <span data-ttu-id="e3fb4-159">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="e3fb4-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="e3fb4-160">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-160">string</span></span> | <span data-ttu-id="e3fb4-161">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="e3fb4-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="e3fb4-162">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-162">string</span></span> | <span data-ttu-id="e3fb4-163">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="e3fb4-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="e3fb4-164">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-164">string</span></span> | <span data-ttu-id="e3fb4-165">Kommandorad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="e3fb4-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="e3fb4-166">sträng</span><span class="sxs-lookup"><span data-stu-id="e3fb4-166">string</span></span> | <span data-ttu-id="e3fb4-167">Ytterligare information om händelsen i JSON-matrisformat</span><span class="sxs-lookup"><span data-stu-id="e3fb4-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e3fb4-168">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e3fb4-168">Related topics</span></span>
- [<span data-ttu-id="e3fb4-169">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e3fb4-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e3fb4-170">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="e3fb4-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e3fb4-171">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="e3fb4-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e3fb4-172">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="e3fb4-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e3fb4-173">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="e3fb4-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e3fb4-174">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="e3fb4-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
