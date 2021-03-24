---
title: Funktionen FileProfile() i avancerad sökning för Microsoft 365 Defender
description: Lär dig använda FileProfile() för att utöka information om filer i avancerade sökresultat för sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070121"
---
# <a name="fileprofile"></a><span data-ttu-id="1685b-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="1685b-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1685b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1685b-105">**Applies to:**</span></span>
- <span data-ttu-id="1685b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1685b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1685b-107">Funktionen `FileProfile()` är en funktion för [](advanced-hunting-overview.md) avancerad sökning som lägger till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="1685b-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="1685b-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="1685b-108">Column</span></span> | <span data-ttu-id="1685b-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="1685b-109">Data type</span></span> | <span data-ttu-id="1685b-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1685b-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="1685b-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="1685b-111">SHA1</span></span> | <span data-ttu-id="1685b-112">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-112">string</span></span> | <span data-ttu-id="1685b-113">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1685b-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1685b-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="1685b-114">SHA256</span></span> | <span data-ttu-id="1685b-115">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-115">string</span></span> | <span data-ttu-id="1685b-116">SHA-256 av filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1685b-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1685b-117">MD5</span><span class="sxs-lookup"><span data-stu-id="1685b-117">MD5</span></span> | <span data-ttu-id="1685b-118">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-118">string</span></span> | <span data-ttu-id="1685b-119">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1685b-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="1685b-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="1685b-120">FileSize</span></span> | <span data-ttu-id="1685b-121">int</span><span class="sxs-lookup"><span data-stu-id="1685b-121">int</span></span> | <span data-ttu-id="1685b-122">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="1685b-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="1685b-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="1685b-123">GlobalPrevalence</span></span> | <span data-ttu-id="1685b-124">int</span><span class="sxs-lookup"><span data-stu-id="1685b-124">int</span></span> | <span data-ttu-id="1685b-125">Antal förekomster av entitet som observerats av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="1685b-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="1685b-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="1685b-126">GlobalFirstSeen</span></span> | <span data-ttu-id="1685b-127">datetime</span><span class="sxs-lookup"><span data-stu-id="1685b-127">datetime</span></span> | <span data-ttu-id="1685b-128">Datum och tid då enheten för första gången observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="1685b-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="1685b-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="1685b-129">GlobalLastSeen</span></span> | <span data-ttu-id="1685b-130">datetime</span><span class="sxs-lookup"><span data-stu-id="1685b-130">datetime</span></span> | <span data-ttu-id="1685b-131">Datum och tid då enheten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="1685b-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="1685b-132">Undertecknaren</span><span class="sxs-lookup"><span data-stu-id="1685b-132">Signer</span></span> | <span data-ttu-id="1685b-133">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-133">string</span></span> | <span data-ttu-id="1685b-134">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="1685b-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="1685b-135">Utfärdare</span><span class="sxs-lookup"><span data-stu-id="1685b-135">Issuer</span></span> | <span data-ttu-id="1685b-136">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-136">string</span></span> | <span data-ttu-id="1685b-137">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="1685b-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="1685b-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="1685b-138">SignerHash</span></span> | <span data-ttu-id="1685b-139">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-139">string</span></span> | <span data-ttu-id="1685b-140">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="1685b-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="1685b-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="1685b-141">IsCertificateValid</span></span> | <span data-ttu-id="1685b-142">boolesk</span><span class="sxs-lookup"><span data-stu-id="1685b-142">boolean</span></span> | <span data-ttu-id="1685b-143">Om det certifikat som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="1685b-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="1685b-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="1685b-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="1685b-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="1685b-145">boolean</span></span> | <span data-ttu-id="1685b-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="1685b-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="1685b-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="1685b-147">IsExecutable</span></span> | <span data-ttu-id="1685b-148">boolesk</span><span class="sxs-lookup"><span data-stu-id="1685b-148">boolean</span></span> | <span data-ttu-id="1685b-149">Om filen är en PE-fil (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="1685b-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="1685b-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="1685b-150">ThreatName</span></span> | <span data-ttu-id="1685b-151">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-151">string</span></span> | <span data-ttu-id="1685b-152">Namn för identifiering av skadlig programvara eller andra hot som påträffades</span><span class="sxs-lookup"><span data-stu-id="1685b-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="1685b-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="1685b-153">Publisher</span></span> | <span data-ttu-id="1685b-154">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-154">string</span></span> | <span data-ttu-id="1685b-155">Namnet på organisationen som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="1685b-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="1685b-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="1685b-156">SoftwareName</span></span> | <span data-ttu-id="1685b-157">sträng</span><span class="sxs-lookup"><span data-stu-id="1685b-157">string</span></span> | <span data-ttu-id="1685b-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="1685b-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="1685b-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="1685b-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="1685b-160">Argument</span><span class="sxs-lookup"><span data-stu-id="1685b-160">Arguments</span></span>

- <span data-ttu-id="1685b-161">**x**– den kolumn med fil-ID som ska användas med funktionen : , , eller ; om `SHA1` det inte är `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` användningsområden</span><span class="sxs-lookup"><span data-stu-id="1685b-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="1685b-162">**y**– begränsning till antalet poster att utöka, 1-1000; funktionen använder 100 om det inte är anspekt</span><span class="sxs-lookup"><span data-stu-id="1685b-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="1685b-163">Tilläggsfunktioner visar endast kompletterande information när de är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="1685b-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="1685b-164">Tillgängligheten för informationen är varierad och beror på en mängd faktorer.</span><span class="sxs-lookup"><span data-stu-id="1685b-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="1685b-165">Tänk på det här när du använder FileProfile() i dina frågor eller när du skapar anpassade identifieringar.</span><span class="sxs-lookup"><span data-stu-id="1685b-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="1685b-166">För bästa resultat rekommenderar vi att du använder funktionen FileProfile() med SHA1.</span><span class="sxs-lookup"><span data-stu-id="1685b-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="1685b-167">Exempel</span><span class="sxs-lookup"><span data-stu-id="1685b-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="1685b-168">Projicera endast KOLUMNEN SHA1 och utöka den</span><span class="sxs-lookup"><span data-stu-id="1685b-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="1685b-169">Förbättra de första 500 posterna och lista filer med låg nivå av arkiv</span><span class="sxs-lookup"><span data-stu-id="1685b-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="1685b-170">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1685b-170">Related topics</span></span>
- [<span data-ttu-id="1685b-171">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1685b-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1685b-172">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="1685b-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1685b-173">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="1685b-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1685b-174">Hämta fler frågeexempel</span><span class="sxs-lookup"><span data-stu-id="1685b-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
