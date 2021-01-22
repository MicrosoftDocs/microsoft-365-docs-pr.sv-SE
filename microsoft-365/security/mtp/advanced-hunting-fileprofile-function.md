---
title: Funktionen FileProfile() för avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder FileProfile() för att utöka information om filer i dina avancerade sökfrågeresultat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929556"
---
# <a name="fileprofile"></a><span data-ttu-id="6bd72-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="6bd72-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6bd72-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6bd72-105">**Applies to:**</span></span>
- <span data-ttu-id="6bd72-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bd72-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6bd72-107">Funktionen `FileProfile()` är en funktion för avancerad sökning som [lägger](advanced-hunting-overview.md) till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="6bd72-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="6bd72-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="6bd72-108">Column</span></span> | <span data-ttu-id="6bd72-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6bd72-109">Data type</span></span> | <span data-ttu-id="6bd72-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6bd72-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="6bd72-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="6bd72-111">SHA1</span></span> | <span data-ttu-id="6bd72-112">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-112">string</span></span> | <span data-ttu-id="6bd72-113">SHA-1 för den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6bd72-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="6bd72-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="6bd72-114">SHA256</span></span> | <span data-ttu-id="6bd72-115">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-115">string</span></span> | <span data-ttu-id="6bd72-116">SHA-256 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6bd72-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="6bd72-117">MD5</span><span class="sxs-lookup"><span data-stu-id="6bd72-117">MD5</span></span> | <span data-ttu-id="6bd72-118">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-118">string</span></span> | <span data-ttu-id="6bd72-119">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="6bd72-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="6bd72-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="6bd72-120">FileSize</span></span> | <span data-ttu-id="6bd72-121">int</span><span class="sxs-lookup"><span data-stu-id="6bd72-121">int</span></span> | <span data-ttu-id="6bd72-122">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="6bd72-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="6bd72-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="6bd72-123">GlobalPrevalence</span></span> | <span data-ttu-id="6bd72-124">int</span><span class="sxs-lookup"><span data-stu-id="6bd72-124">int</span></span> | <span data-ttu-id="6bd72-125">Antal förekomster av entitet som observerats av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="6bd72-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="6bd72-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="6bd72-126">GlobalFirstSeen</span></span> | <span data-ttu-id="6bd72-127">datetime</span><span class="sxs-lookup"><span data-stu-id="6bd72-127">datetime</span></span> | <span data-ttu-id="6bd72-128">Datum och tid då entiteten observerades första gången av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="6bd72-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="6bd72-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="6bd72-129">GlobalLastSeen</span></span> | <span data-ttu-id="6bd72-130">datetime</span><span class="sxs-lookup"><span data-stu-id="6bd72-130">datetime</span></span> | <span data-ttu-id="6bd72-131">Datum och tid då entiteten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="6bd72-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="6bd72-132">Undertecknaren</span><span class="sxs-lookup"><span data-stu-id="6bd72-132">Signer</span></span> | <span data-ttu-id="6bd72-133">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-133">string</span></span> | <span data-ttu-id="6bd72-134">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="6bd72-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="6bd72-135">Utfärdare</span><span class="sxs-lookup"><span data-stu-id="6bd72-135">Issuer</span></span> | <span data-ttu-id="6bd72-136">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-136">string</span></span> | <span data-ttu-id="6bd72-137">Information om den certifikatutfärdare som utfärdar certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="6bd72-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="6bd72-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="6bd72-138">SignerHash</span></span> | <span data-ttu-id="6bd72-139">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-139">string</span></span> | <span data-ttu-id="6bd72-140">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="6bd72-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="6bd72-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="6bd72-141">IsCertificateValid</span></span> | <span data-ttu-id="6bd72-142">boolesk</span><span class="sxs-lookup"><span data-stu-id="6bd72-142">boolean</span></span> | <span data-ttu-id="6bd72-143">Om certifikatet som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="6bd72-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="6bd72-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="6bd72-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="6bd72-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="6bd72-145">boolean</span></span> | <span data-ttu-id="6bd72-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="6bd72-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="6bd72-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="6bd72-147">IsExecutable</span></span> | <span data-ttu-id="6bd72-148">boolesk</span><span class="sxs-lookup"><span data-stu-id="6bd72-148">boolean</span></span> | <span data-ttu-id="6bd72-149">Om filen är en PORTABLE Executable-fil (PE)</span><span class="sxs-lookup"><span data-stu-id="6bd72-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="6bd72-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="6bd72-150">ThreatName</span></span> | <span data-ttu-id="6bd72-151">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-151">string</span></span> | <span data-ttu-id="6bd72-152">Identifieringsnamn för skadlig kod eller andra hot hittades</span><span class="sxs-lookup"><span data-stu-id="6bd72-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="6bd72-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="6bd72-153">Publisher</span></span> | <span data-ttu-id="6bd72-154">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-154">string</span></span> | <span data-ttu-id="6bd72-155">Namn på organisationen som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="6bd72-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="6bd72-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="6bd72-156">SoftwareName</span></span> | <span data-ttu-id="6bd72-157">sträng</span><span class="sxs-lookup"><span data-stu-id="6bd72-157">string</span></span> | <span data-ttu-id="6bd72-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="6bd72-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="6bd72-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bd72-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="6bd72-160">Argument</span><span class="sxs-lookup"><span data-stu-id="6bd72-160">Arguments</span></span>

- <span data-ttu-id="6bd72-161">**x**– kolumn med fil-ID som ska användas för: , , eller `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` funktionen, `SHA1` om det inte har specificerats</span><span class="sxs-lookup"><span data-stu-id="6bd72-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="6bd72-162">**y**– begränsa antalet poster att utöka, 1–1 000; används 100 om de inte är angivna</span><span class="sxs-lookup"><span data-stu-id="6bd72-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="6bd72-163">Exempel</span><span class="sxs-lookup"><span data-stu-id="6bd72-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="6bd72-164">Projicera endast SHA1-kolumnen och utöka den</span><span class="sxs-lookup"><span data-stu-id="6bd72-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="6bd72-165">Förbättra de första 500 posterna och lista filer som inte är så högena</span><span class="sxs-lookup"><span data-stu-id="6bd72-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="6bd72-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6bd72-166">Related topics</span></span>
- [<span data-ttu-id="6bd72-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6bd72-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6bd72-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6bd72-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6bd72-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6bd72-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6bd72-170">Hämta fler frågeexempel</span><span class="sxs-lookup"><span data-stu-id="6bd72-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
