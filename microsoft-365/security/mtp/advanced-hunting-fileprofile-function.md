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
ms.openlocfilehash: 6465821ff1b8e8ea23cc5cf6b205f65a483bbe82
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204953"
---
# <a name="fileprofile"></a><span data-ttu-id="fce8b-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="fce8b-104">FileProfile()</span></span>

<span data-ttu-id="fce8b-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="fce8b-105">**Applies to:**</span></span>
- <span data-ttu-id="fce8b-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="fce8b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fce8b-107">`FileProfile()`Funktionen är en anrikningsfunktion i avancerad [jakt](advanced-hunting-overview.md) som lägger till följande data i filer som hittades av frågan.</span><span class="sxs-lookup"><span data-stu-id="fce8b-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="fce8b-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="fce8b-108">Column</span></span> | <span data-ttu-id="fce8b-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="fce8b-109">Data type</span></span> | <span data-ttu-id="fce8b-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fce8b-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="fce8b-111">SHA1 (SHA1)</span><span class="sxs-lookup"><span data-stu-id="fce8b-111">SHA1</span></span> | <span data-ttu-id="fce8b-112">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-112">string</span></span> | <span data-ttu-id="fce8b-113">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="fce8b-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="fce8b-114">SHA256 (SHA256)</span><span class="sxs-lookup"><span data-stu-id="fce8b-114">SHA256</span></span> | <span data-ttu-id="fce8b-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-115">string</span></span> | <span data-ttu-id="fce8b-116">SHA-256 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="fce8b-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="fce8b-117">VD5</span><span class="sxs-lookup"><span data-stu-id="fce8b-117">MD5</span></span> | <span data-ttu-id="fce8b-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-118">string</span></span> | <span data-ttu-id="fce8b-119">MD5-hash i filen som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="fce8b-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="fce8b-120">Filstorlek</span><span class="sxs-lookup"><span data-stu-id="fce8b-120">FileSize</span></span> | <span data-ttu-id="fce8b-121">Int</span><span class="sxs-lookup"><span data-stu-id="fce8b-121">int</span></span> | <span data-ttu-id="fce8b-122">Filens storlek i byte</span><span class="sxs-lookup"><span data-stu-id="fce8b-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="fce8b-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="fce8b-123">GlobalPrevalence</span></span> | <span data-ttu-id="fce8b-124">Int</span><span class="sxs-lookup"><span data-stu-id="fce8b-124">int</span></span> | <span data-ttu-id="fce8b-125">Antal instanser av den enhet som Microsoft har observerat globalt</span><span class="sxs-lookup"><span data-stu-id="fce8b-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="fce8b-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="fce8b-126">GlobalFirstSeen</span></span> | <span data-ttu-id="fce8b-127">Datetime</span><span class="sxs-lookup"><span data-stu-id="fce8b-127">datetime</span></span> | <span data-ttu-id="fce8b-128">Datum och tid då enheten först observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="fce8b-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="fce8b-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="fce8b-129">GlobalLastSeen</span></span> | <span data-ttu-id="fce8b-130">Datetime</span><span class="sxs-lookup"><span data-stu-id="fce8b-130">datetime</span></span> | <span data-ttu-id="fce8b-131">Datum och tid då entiteten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="fce8b-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="fce8b-132">Signerat</span><span class="sxs-lookup"><span data-stu-id="fce8b-132">Signer</span></span> | <span data-ttu-id="fce8b-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-133">string</span></span> | <span data-ttu-id="fce8b-134">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="fce8b-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="fce8b-135">Emittenten</span><span class="sxs-lookup"><span data-stu-id="fce8b-135">Issuer</span></span> | <span data-ttu-id="fce8b-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-136">string</span></span> | <span data-ttu-id="fce8b-137">Information om den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="fce8b-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="fce8b-138">SignerHash (Teckenhash)</span><span class="sxs-lookup"><span data-stu-id="fce8b-138">SignerHash</span></span> | <span data-ttu-id="fce8b-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-139">string</span></span> | <span data-ttu-id="fce8b-140">Unikt hash-värde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="fce8b-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="fce8b-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="fce8b-141">IsCertificateValid</span></span> | <span data-ttu-id="fce8b-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="fce8b-142">boolean</span></span> | <span data-ttu-id="fce8b-143">Om certifikatet som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="fce8b-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="fce8b-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="fce8b-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="fce8b-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="fce8b-145">boolean</span></span> | <span data-ttu-id="fce8b-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="fce8b-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="fce8b-147">Ärutgrundbar</span><span class="sxs-lookup"><span data-stu-id="fce8b-147">IsExecutable</span></span> | <span data-ttu-id="fce8b-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="fce8b-148">boolean</span></span> | <span data-ttu-id="fce8b-149">Om filen är en PE-fil (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="fce8b-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="fce8b-150">ThreatName (HotName)</span><span class="sxs-lookup"><span data-stu-id="fce8b-150">ThreatName</span></span> | <span data-ttu-id="fce8b-151">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-151">string</span></span> | <span data-ttu-id="fce8b-152">Identifieringsnamn för skadlig kod eller andra hot som hittats</span><span class="sxs-lookup"><span data-stu-id="fce8b-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="fce8b-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="fce8b-153">Publisher</span></span> | <span data-ttu-id="fce8b-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-154">string</span></span> | <span data-ttu-id="fce8b-155">Namn på den organisation som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="fce8b-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="fce8b-156">SoftwareName (SoftwareName)</span><span class="sxs-lookup"><span data-stu-id="fce8b-156">SoftwareName</span></span> | <span data-ttu-id="fce8b-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="fce8b-157">string</span></span> | <span data-ttu-id="fce8b-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="fce8b-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="fce8b-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="fce8b-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="fce8b-160">Argument</span><span class="sxs-lookup"><span data-stu-id="fce8b-160">Arguments</span></span>

- <span data-ttu-id="fce8b-161">**x** — fil-ID-kolumn som ska användas: `SHA1` , , eller ; funktionen använder om den inte `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` anges</span><span class="sxs-lookup"><span data-stu-id="fce8b-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="fce8b-162">**y** — gräns för antalet poster som ska berikas, 1–1000. funktion använder 100 om ospecificerad</span><span class="sxs-lookup"><span data-stu-id="fce8b-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="fce8b-163">Exempel</span><span class="sxs-lookup"><span data-stu-id="fce8b-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="fce8b-164">Projicera endast SHA1-kolumnen och berika den</span><span class="sxs-lookup"><span data-stu-id="fce8b-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="fce8b-165">Berika de första 500 posterna och lista filer med låg prevalens</span><span class="sxs-lookup"><span data-stu-id="fce8b-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="fce8b-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fce8b-166">Related topics</span></span>
- [<span data-ttu-id="fce8b-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="fce8b-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fce8b-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="fce8b-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fce8b-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="fce8b-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)