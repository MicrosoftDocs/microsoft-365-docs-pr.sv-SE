---
title: AlertEvidence-tabell i det avancerade jakt-schemat
description: Lär dig mer om information som är associerad med aviseringar i AlertEvidence-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto
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
ms.openlocfilehash: 549eed005e06a7d52ce2f881820ae9fdeffdfea7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847686"
---
# <a name="alertevidence"></a><span data-ttu-id="f2aef-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f2aef-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f2aef-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f2aef-105">**Applies to:**</span></span>
- <span data-ttu-id="f2aef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2aef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f2aef-107">`AlertEvidence`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika enheter — filer, IP-adresser, URL: er, användare eller enheter – associerade med aviseringar från Microsoft Defender för slut punkt, Microsoft defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identiteten.</span><span class="sxs-lookup"><span data-stu-id="f2aef-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="f2aef-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="f2aef-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f2aef-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f2aef-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f2aef-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="f2aef-110">Column name</span></span> | <span data-ttu-id="f2aef-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="f2aef-111">Data type</span></span> | <span data-ttu-id="f2aef-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f2aef-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f2aef-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f2aef-113">datetime</span></span> | <span data-ttu-id="f2aef-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="f2aef-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="f2aef-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-115">string</span></span> | <span data-ttu-id="f2aef-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="f2aef-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="f2aef-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-117">string</span></span> | <span data-ttu-id="f2aef-118">Produkt eller tjänst som tillhandahöll aviserings informationen</span><span class="sxs-lookup"><span data-stu-id="f2aef-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="f2aef-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-119">string</span></span> | <span data-ttu-id="f2aef-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="f2aef-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="f2aef-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-121">string</span></span> | <span data-ttu-id="f2aef-122">Hur enheten är involverad i en avisering och visar om den påverkas eller bara är relaterad</span><span class="sxs-lookup"><span data-stu-id="f2aef-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="f2aef-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-123">string</span></span> | <span data-ttu-id="f2aef-124">Anger om enheten är källa eller mål för en nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="f2aef-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="f2aef-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-125">string</span></span> | <span data-ttu-id="f2aef-126">Namnet på filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="f2aef-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f2aef-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-127">string</span></span> | <span data-ttu-id="f2aef-128">Mapp som innehåller filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="f2aef-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="f2aef-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-129">string</span></span> | <span data-ttu-id="f2aef-130">SHA-1 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="f2aef-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="f2aef-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-131">string</span></span> | <span data-ttu-id="f2aef-132">SHA-256 av filen som den registrerade åtgärden tillämpades på.</span><span class="sxs-lookup"><span data-stu-id="f2aef-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="f2aef-133">Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="f2aef-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="f2aef-134">signera</span><span class="sxs-lookup"><span data-stu-id="f2aef-134">int</span></span> | <span data-ttu-id="f2aef-135">Storleken på filen i byte</span><span class="sxs-lookup"><span data-stu-id="f2aef-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="f2aef-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-136">string</span></span> | <span data-ttu-id="f2aef-137">Familjen skadlig program vara som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="f2aef-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="f2aef-138">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-138">string</span></span> | <span data-ttu-id="f2aef-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="f2aef-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="f2aef-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-140">string</span></span> | <span data-ttu-id="f2aef-141">URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till</span><span class="sxs-lookup"><span data-stu-id="f2aef-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="f2aef-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-142">string</span></span> | <span data-ttu-id="f2aef-143">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="f2aef-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f2aef-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-144">string</span></span> | <span data-ttu-id="f2aef-145">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="f2aef-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f2aef-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-146">string</span></span> | <span data-ttu-id="f2aef-147">Kontots säkerhets identifierare (SID)</span><span class="sxs-lookup"><span data-stu-id="f2aef-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f2aef-148">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-148">string</span></span> | <span data-ttu-id="f2aef-149">Unik identifierare för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2aef-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="f2aef-150">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-150">string</span></span> | <span data-ttu-id="f2aef-151">Unik identifierare för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="f2aef-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f2aef-152">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-152">string</span></span> | <span data-ttu-id="f2aef-153">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="f2aef-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="f2aef-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-154">string</span></span> | <span data-ttu-id="f2aef-155">IP-adress som tilldelats till den lokala enheten under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="f2aef-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="f2aef-156">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-156">string</span></span> | <span data-ttu-id="f2aef-157">Unik identifierare för e-posten som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="f2aef-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="f2aef-158">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-158">string</span></span> | <span data-ttu-id="f2aef-159">Ämne för e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="f2aef-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="f2aef-160">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-160">string</span></span> | <span data-ttu-id="f2aef-161">Unik identifierare för programmet</span><span class="sxs-lookup"><span data-stu-id="f2aef-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="f2aef-162">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-162">string</span></span> | <span data-ttu-id="f2aef-163">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="f2aef-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="f2aef-164">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-164">string</span></span> | <span data-ttu-id="f2aef-165">Kommando rad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="f2aef-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="f2aef-166">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f2aef-166">string</span></span> | <span data-ttu-id="f2aef-167">Ytterligare information om händelsen i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="f2aef-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f2aef-168">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f2aef-168">Related topics</span></span>
- [<span data-ttu-id="f2aef-169">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f2aef-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f2aef-170">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="f2aef-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f2aef-171">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="f2aef-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f2aef-172">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="f2aef-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f2aef-173">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="f2aef-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f2aef-174">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="f2aef-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
