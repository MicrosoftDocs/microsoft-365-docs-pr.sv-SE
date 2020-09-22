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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a7e2eca147bb956606380b9ac97a91b898830dd0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197275"
---
# <a name="alertevidence"></a><span data-ttu-id="9dba5-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9dba5-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9dba5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9dba5-105">**Applies to:**</span></span>
- <span data-ttu-id="9dba5-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="9dba5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9dba5-107">`AlertEvidence`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika enheter — filer, IP-adresser, URL: er, användare eller enheter – associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="9dba5-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="9dba5-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="9dba5-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9dba5-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9dba5-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9dba5-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="9dba5-110">Column name</span></span> | <span data-ttu-id="9dba5-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="9dba5-111">Data type</span></span> | <span data-ttu-id="9dba5-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9dba5-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9dba5-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9dba5-113">datetime</span></span> | <span data-ttu-id="9dba5-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="9dba5-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="9dba5-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-115">string</span></span> | <span data-ttu-id="9dba5-116">Unik identifierare för aviseringen</span><span class="sxs-lookup"><span data-stu-id="9dba5-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="9dba5-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-117">string</span></span> | <span data-ttu-id="9dba5-118">Produkt eller tjänst som tillhandahöll aviserings informationen</span><span class="sxs-lookup"><span data-stu-id="9dba5-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="9dba5-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-119">string</span></span> | <span data-ttu-id="9dba5-120">Typ av objekt, till exempel en fil, en process, en enhet eller en användare</span><span class="sxs-lookup"><span data-stu-id="9dba5-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="9dba5-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-121">string</span></span> | <span data-ttu-id="9dba5-122">Hur enheten är involverad i en avisering och visar om den påverkas eller bara är relaterad</span><span class="sxs-lookup"><span data-stu-id="9dba5-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="9dba5-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-123">string</span></span> | <span data-ttu-id="9dba5-124">Anger om enheten är källa eller mål för en nätverks anslutning</span><span class="sxs-lookup"><span data-stu-id="9dba5-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="9dba5-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-125">string</span></span> | <span data-ttu-id="9dba5-126">Namnet på filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="9dba5-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="9dba5-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-127">string</span></span> | <span data-ttu-id="9dba5-128">Mapp som innehåller filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="9dba5-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9dba5-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-129">string</span></span> | <span data-ttu-id="9dba5-130">SHA-1 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="9dba5-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="9dba5-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-131">string</span></span> | <span data-ttu-id="9dba5-132">SHA-256 av filen som den registrerade åtgärden tillämpades på.</span><span class="sxs-lookup"><span data-stu-id="9dba5-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="9dba5-133">Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="9dba5-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="9dba5-134">signera</span><span class="sxs-lookup"><span data-stu-id="9dba5-134">int</span></span> | <span data-ttu-id="9dba5-135">Storleken på filen i byte</span><span class="sxs-lookup"><span data-stu-id="9dba5-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="9dba5-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-136">string</span></span> | <span data-ttu-id="9dba5-137">Familjen skadlig program vara som den misstänkta eller skadliga filen eller processen har klassificerats under</span><span class="sxs-lookup"><span data-stu-id="9dba5-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="9dba5-138">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-138">string</span></span> | <span data-ttu-id="9dba5-139">IP-adress som var ansluten till</span><span class="sxs-lookup"><span data-stu-id="9dba5-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="9dba5-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-140">string</span></span> | <span data-ttu-id="9dba5-141">URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till</span><span class="sxs-lookup"><span data-stu-id="9dba5-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="9dba5-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-142">string</span></span> | <span data-ttu-id="9dba5-143">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="9dba5-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9dba5-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-144">string</span></span> | <span data-ttu-id="9dba5-145">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="9dba5-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9dba5-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-146">string</span></span> | <span data-ttu-id="9dba5-147">Kontots säkerhets identifierare (SID)</span><span class="sxs-lookup"><span data-stu-id="9dba5-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9dba5-148">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-148">string</span></span> | <span data-ttu-id="9dba5-149">Unik identifierare för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9dba5-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="9dba5-150">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-150">string</span></span> | <span data-ttu-id="9dba5-151">Unik identifierare för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="9dba5-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9dba5-152">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-152">string</span></span> | <span data-ttu-id="9dba5-153">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="9dba5-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="9dba5-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-154">string</span></span> | <span data-ttu-id="9dba5-155">IP-adress som tilldelats till den lokala enheten under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="9dba5-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="9dba5-156">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-156">string</span></span> | <span data-ttu-id="9dba5-157">Unik identifierare för e-posten som genereras av Office 365</span><span class="sxs-lookup"><span data-stu-id="9dba5-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="9dba5-158">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-158">string</span></span> | <span data-ttu-id="9dba5-159">Ämne för e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="9dba5-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="9dba5-160">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-160">string</span></span> | <span data-ttu-id="9dba5-161">Unik identifierare för programmet</span><span class="sxs-lookup"><span data-stu-id="9dba5-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="9dba5-162">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-162">string</span></span> | <span data-ttu-id="9dba5-163">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="9dba5-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="9dba5-164">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-164">string</span></span> | <span data-ttu-id="9dba5-165">Kommando rad som används för att skapa den nya processen</span><span class="sxs-lookup"><span data-stu-id="9dba5-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="9dba5-166">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="9dba5-166">string</span></span> | <span data-ttu-id="9dba5-167">Ytterligare information om händelsen i JSON-mat ris format</span><span class="sxs-lookup"><span data-stu-id="9dba5-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9dba5-168">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9dba5-168">Related topics</span></span>
- [<span data-ttu-id="9dba5-169">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="9dba5-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9dba5-170">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="9dba5-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9dba5-171">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="9dba5-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9dba5-172">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="9dba5-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9dba5-173">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="9dba5-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9dba5-174">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="9dba5-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
