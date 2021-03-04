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
ms.openlocfilehash: f2e92967b8951cd0f5a3c394a537404db1d53819
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424029"
---
# <a name="fileprofile"></a><span data-ttu-id="d55a1-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="d55a1-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d55a1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d55a1-105">**Applies to:**</span></span>
- <span data-ttu-id="d55a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d55a1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d55a1-107">Funktionen `FileProfile()` är en funktion för avancerad sökning som [lägger](advanced-hunting-overview.md) till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="d55a1-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="d55a1-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="d55a1-108">Column</span></span> | <span data-ttu-id="d55a1-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d55a1-109">Data type</span></span> | <span data-ttu-id="d55a1-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d55a1-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="d55a1-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="d55a1-111">SHA1</span></span> | <span data-ttu-id="d55a1-112">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-112">string</span></span> | <span data-ttu-id="d55a1-113">SHA-1 för den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="d55a1-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="d55a1-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="d55a1-114">SHA256</span></span> | <span data-ttu-id="d55a1-115">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-115">string</span></span> | <span data-ttu-id="d55a1-116">SHA-256 av filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="d55a1-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="d55a1-117">MD5</span><span class="sxs-lookup"><span data-stu-id="d55a1-117">MD5</span></span> | <span data-ttu-id="d55a1-118">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-118">string</span></span> | <span data-ttu-id="d55a1-119">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="d55a1-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="d55a1-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="d55a1-120">FileSize</span></span> | <span data-ttu-id="d55a1-121">int</span><span class="sxs-lookup"><span data-stu-id="d55a1-121">int</span></span> | <span data-ttu-id="d55a1-122">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="d55a1-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="d55a1-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="d55a1-123">GlobalPrevalence</span></span> | <span data-ttu-id="d55a1-124">int</span><span class="sxs-lookup"><span data-stu-id="d55a1-124">int</span></span> | <span data-ttu-id="d55a1-125">Antal förekomster av entitet som observerats av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="d55a1-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="d55a1-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="d55a1-126">GlobalFirstSeen</span></span> | <span data-ttu-id="d55a1-127">datetime</span><span class="sxs-lookup"><span data-stu-id="d55a1-127">datetime</span></span> | <span data-ttu-id="d55a1-128">Datum och tid då entiteten observerades första gången av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="d55a1-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="d55a1-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="d55a1-129">GlobalLastSeen</span></span> | <span data-ttu-id="d55a1-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d55a1-130">datetime</span></span> | <span data-ttu-id="d55a1-131">Datum och tid då entiteten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="d55a1-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="d55a1-132">Undertecknaren</span><span class="sxs-lookup"><span data-stu-id="d55a1-132">Signer</span></span> | <span data-ttu-id="d55a1-133">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-133">string</span></span> | <span data-ttu-id="d55a1-134">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="d55a1-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="d55a1-135">Utfärdare</span><span class="sxs-lookup"><span data-stu-id="d55a1-135">Issuer</span></span> | <span data-ttu-id="d55a1-136">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-136">string</span></span> | <span data-ttu-id="d55a1-137">Information om den certifikatutfärdare som utfärdar certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="d55a1-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="d55a1-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="d55a1-138">SignerHash</span></span> | <span data-ttu-id="d55a1-139">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-139">string</span></span> | <span data-ttu-id="d55a1-140">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="d55a1-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="d55a1-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="d55a1-141">IsCertificateValid</span></span> | <span data-ttu-id="d55a1-142">boolesk</span><span class="sxs-lookup"><span data-stu-id="d55a1-142">boolean</span></span> | <span data-ttu-id="d55a1-143">Om certifikatet som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="d55a1-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="d55a1-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="d55a1-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="d55a1-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="d55a1-145">boolean</span></span> | <span data-ttu-id="d55a1-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="d55a1-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="d55a1-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="d55a1-147">IsExecutable</span></span> | <span data-ttu-id="d55a1-148">boolesk</span><span class="sxs-lookup"><span data-stu-id="d55a1-148">boolean</span></span> | <span data-ttu-id="d55a1-149">Om filen är en PORTABLE Executable-fil (PE)</span><span class="sxs-lookup"><span data-stu-id="d55a1-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="d55a1-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="d55a1-150">ThreatName</span></span> | <span data-ttu-id="d55a1-151">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-151">string</span></span> | <span data-ttu-id="d55a1-152">Identifieringsnamn för skadlig kod eller andra hot hittades</span><span class="sxs-lookup"><span data-stu-id="d55a1-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="d55a1-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="d55a1-153">Publisher</span></span> | <span data-ttu-id="d55a1-154">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-154">string</span></span> | <span data-ttu-id="d55a1-155">Namnet på organisationen som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="d55a1-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="d55a1-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="d55a1-156">SoftwareName</span></span> | <span data-ttu-id="d55a1-157">sträng</span><span class="sxs-lookup"><span data-stu-id="d55a1-157">string</span></span> | <span data-ttu-id="d55a1-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="d55a1-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="d55a1-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="d55a1-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="d55a1-160">Argument</span><span class="sxs-lookup"><span data-stu-id="d55a1-160">Arguments</span></span>

- <span data-ttu-id="d55a1-161">**x**– kolumn med fil-ID som ska användas för: , , eller `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` funktionen, `SHA1` om det inte har specificerats</span><span class="sxs-lookup"><span data-stu-id="d55a1-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="d55a1-162">**y**– begränsa antalet poster att utöka, 1–1 000; används 100 om de inte är angivna</span><span class="sxs-lookup"><span data-stu-id="d55a1-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="d55a1-163">Tilläggsfunktioner visar endast kompletterande information när de är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="d55a1-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="d55a1-164">Tillgängligheten på informationen är varierad och beror på många faktorer.</span><span class="sxs-lookup"><span data-stu-id="d55a1-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="d55a1-165">Tänk på det här när du använder FileProfile() i dina frågor eller när du skapar anpassade identifieringar.</span><span class="sxs-lookup"><span data-stu-id="d55a1-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="d55a1-166">För bästa resultat rekommenderar vi att du använder funktionen FileProfile() med SHA1.</span><span class="sxs-lookup"><span data-stu-id="d55a1-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="d55a1-167">Exempel</span><span class="sxs-lookup"><span data-stu-id="d55a1-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="d55a1-168">Projicera endast SHA1-kolumnen och utöka den</span><span class="sxs-lookup"><span data-stu-id="d55a1-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="d55a1-169">Förbättra de första 500 posterna och lista filer som inte är så högena</span><span class="sxs-lookup"><span data-stu-id="d55a1-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="d55a1-170">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d55a1-170">Related topics</span></span>
- [<span data-ttu-id="d55a1-171">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d55a1-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d55a1-172">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d55a1-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d55a1-173">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d55a1-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d55a1-174">Hämta fler frågeexempel</span><span class="sxs-lookup"><span data-stu-id="d55a1-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
