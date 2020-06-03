---
title: FileProfile() funktion i avancerad jakt på Microsoft Threat Protection
description: Lär dig hur du använder FileProfile() för att berika information om filer i dina avancerade jaktfrågeresultat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, anrikning
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
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515940"
---
# <a name="fileprofile"></a><span data-ttu-id="250d4-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="250d4-104">FileProfile()</span></span>

<span data-ttu-id="250d4-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="250d4-105">**Applies to:**</span></span>
- <span data-ttu-id="250d4-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="250d4-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="250d4-107">`FileProfile()`Funktionen är en anrikningsfunktion i avancerad [jakt](advanced-hunting-overview.md) som lägger till följande data i filer som hittades av frågan.</span><span class="sxs-lookup"><span data-stu-id="250d4-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="250d4-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="250d4-108">Column</span></span> | <span data-ttu-id="250d4-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="250d4-109">Data type</span></span> | <span data-ttu-id="250d4-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="250d4-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="250d4-111">SHA1 (SHA1)</span><span class="sxs-lookup"><span data-stu-id="250d4-111">SHA1</span></span> | <span data-ttu-id="250d4-112">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-112">string</span></span> | <span data-ttu-id="250d4-113">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="250d4-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="250d4-114">SHA256 (SHA256)</span><span class="sxs-lookup"><span data-stu-id="250d4-114">SHA256</span></span> | <span data-ttu-id="250d4-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-115">string</span></span> | <span data-ttu-id="250d4-116">SHA-256 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="250d4-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="250d4-117">VD5</span><span class="sxs-lookup"><span data-stu-id="250d4-117">MD5</span></span> | <span data-ttu-id="250d4-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-118">string</span></span> | <span data-ttu-id="250d4-119">MD5-hash i filen som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="250d4-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="250d4-120">Filstorlek</span><span class="sxs-lookup"><span data-stu-id="250d4-120">FileSize</span></span> | <span data-ttu-id="250d4-121">Int</span><span class="sxs-lookup"><span data-stu-id="250d4-121">int</span></span> | <span data-ttu-id="250d4-122">Filens storlek i byte</span><span class="sxs-lookup"><span data-stu-id="250d4-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="250d4-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="250d4-123">GlobalPrevalence</span></span> | <span data-ttu-id="250d4-124">Int</span><span class="sxs-lookup"><span data-stu-id="250d4-124">int</span></span> | <span data-ttu-id="250d4-125">Antal instanser av den enhet som Microsoft observerat globalt</span><span class="sxs-lookup"><span data-stu-id="250d4-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="250d4-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="250d4-126">GlobalFirstSeen</span></span> | <span data-ttu-id="250d4-127">Datetime</span><span class="sxs-lookup"><span data-stu-id="250d4-127">datetime</span></span> | <span data-ttu-id="250d4-128">Datum och tid då enheten först observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="250d4-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="250d4-129">GlobalSeen</span><span class="sxs-lookup"><span data-stu-id="250d4-129">GlobalLastSeen</span></span> | <span data-ttu-id="250d4-130">Datetime</span><span class="sxs-lookup"><span data-stu-id="250d4-130">datetime</span></span> | <span data-ttu-id="250d4-131">Datum och tid då entiteten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="250d4-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="250d4-132">Signerat</span><span class="sxs-lookup"><span data-stu-id="250d4-132">Signer</span></span> | <span data-ttu-id="250d4-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-133">string</span></span> | <span data-ttu-id="250d4-134">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="250d4-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="250d4-135">Emittenten</span><span class="sxs-lookup"><span data-stu-id="250d4-135">Issuer</span></span> | <span data-ttu-id="250d4-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-136">string</span></span> | <span data-ttu-id="250d4-137">Information om den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="250d4-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="250d4-138">SignerHash (Teckenhash)</span><span class="sxs-lookup"><span data-stu-id="250d4-138">SignerHash</span></span> | <span data-ttu-id="250d4-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-139">string</span></span> | <span data-ttu-id="250d4-140">Unikt hash-värde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="250d4-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="250d4-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="250d4-141">IsCertificateValid</span></span> | <span data-ttu-id="250d4-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="250d4-142">boolean</span></span> | <span data-ttu-id="250d4-143">Om certifikatet som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="250d4-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="250d4-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="250d4-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="250d4-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="250d4-145">boolean</span></span> | <span data-ttu-id="250d4-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="250d4-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="250d4-147">Ärutgrundbar</span><span class="sxs-lookup"><span data-stu-id="250d4-147">IsExecutable</span></span> | <span data-ttu-id="250d4-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="250d4-148">boolean</span></span> | <span data-ttu-id="250d4-149">Om filen är en PE-fil (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="250d4-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="250d4-150">ThreatName (HotName)</span><span class="sxs-lookup"><span data-stu-id="250d4-150">ThreatName</span></span> | <span data-ttu-id="250d4-151">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-151">string</span></span> | <span data-ttu-id="250d4-152">Identifieringsnamn för skadlig kod eller andra hot som hittats</span><span class="sxs-lookup"><span data-stu-id="250d4-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="250d4-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="250d4-153">Publisher</span></span> | <span data-ttu-id="250d4-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-154">string</span></span> | <span data-ttu-id="250d4-155">Namn på den organisation som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="250d4-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="250d4-156">SoftwareName (SoftwareName)</span><span class="sxs-lookup"><span data-stu-id="250d4-156">SoftwareName</span></span> | <span data-ttu-id="250d4-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="250d4-157">string</span></span> | <span data-ttu-id="250d4-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="250d4-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="250d4-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="250d4-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="250d4-160">Argument</span><span class="sxs-lookup"><span data-stu-id="250d4-160">Arguments</span></span>

- <span data-ttu-id="250d4-161">**x** — fil-ID-kolumn som ska användas: `SHA1` , , eller ; funktionen använder om den inte `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` anges</span><span class="sxs-lookup"><span data-stu-id="250d4-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="250d4-162">**y** — gräns för antalet poster som ska berikas, 1–1000. funktion använder 100 om ospecificerad</span><span class="sxs-lookup"><span data-stu-id="250d4-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="250d4-163">Exempel</span><span class="sxs-lookup"><span data-stu-id="250d4-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="250d4-164">Projicera endast SHA1-kolumnen och berika den</span><span class="sxs-lookup"><span data-stu-id="250d4-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="250d4-165">Berika de första 500 posterna och lista filer med lågprevalens</span><span class="sxs-lookup"><span data-stu-id="250d4-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="250d4-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="250d4-166">Related topics</span></span>
- [<span data-ttu-id="250d4-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="250d4-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="250d4-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="250d4-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="250d4-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="250d4-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)