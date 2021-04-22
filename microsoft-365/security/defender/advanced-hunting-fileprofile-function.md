---
title: Funktionen FileProfile() i avancerad sökning för Microsoft 365 Defender
description: Lär dig använda FileProfile() för att utöka information om filer i avancerade sökresultat för sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function,richment
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935851"
---
# <a name="fileprofile"></a><span data-ttu-id="4a162-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="4a162-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4a162-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4a162-105">**Applies to:**</span></span>
- <span data-ttu-id="4a162-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a162-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4a162-107">Funktionen `FileProfile()` är en funktion för [](advanced-hunting-overview.md) avancerad sökning som lägger till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="4a162-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="4a162-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="4a162-108">Column</span></span> | <span data-ttu-id="4a162-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4a162-109">Data type</span></span> | <span data-ttu-id="4a162-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4a162-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="4a162-111">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-111">string</span></span> | <span data-ttu-id="4a162-112">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="4a162-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="4a162-113">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-113">string</span></span> | <span data-ttu-id="4a162-114">SHA-256 av filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="4a162-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="4a162-115">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-115">string</span></span> | <span data-ttu-id="4a162-116">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="4a162-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="4a162-117">int</span><span class="sxs-lookup"><span data-stu-id="4a162-117">int</span></span> | <span data-ttu-id="4a162-118">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="4a162-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="4a162-119">int</span><span class="sxs-lookup"><span data-stu-id="4a162-119">int</span></span> | <span data-ttu-id="4a162-120">Antal förekomster av entitet som observerats av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="4a162-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="4a162-121">datetime</span><span class="sxs-lookup"><span data-stu-id="4a162-121">datetime</span></span> | <span data-ttu-id="4a162-122">Datum och tid då enheten för första gången observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="4a162-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="4a162-123">datetime</span><span class="sxs-lookup"><span data-stu-id="4a162-123">datetime</span></span> | <span data-ttu-id="4a162-124">Datum och tid då enheten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="4a162-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="4a162-125">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-125">string</span></span> | <span data-ttu-id="4a162-126">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="4a162-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="4a162-127">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-127">string</span></span> | <span data-ttu-id="4a162-128">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="4a162-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="4a162-129">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-129">string</span></span> | <span data-ttu-id="4a162-130">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="4a162-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="4a162-131">boolesk</span><span class="sxs-lookup"><span data-stu-id="4a162-131">boolean</span></span> | <span data-ttu-id="4a162-132">Om det certifikat som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="4a162-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="4a162-133">boolesk</span><span class="sxs-lookup"><span data-stu-id="4a162-133">boolean</span></span> | <span data-ttu-id="4a162-134">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="4a162-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="4a162-135">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-135">string</span></span> | <span data-ttu-id="4a162-136">Status för filsignaturen: SigneradeValid – filen är signerad med en giltig signatur, SigneradInvalid – filen har signerats men certifikatet är ogiltigt, inte signerat – filen är inte signerad, okänd – information om filen kan inte hämtas</span><span class="sxs-lookup"><span data-stu-id="4a162-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="4a162-137">boolesk</span><span class="sxs-lookup"><span data-stu-id="4a162-137">boolean</span></span> | <span data-ttu-id="4a162-138">Om filen är en PE-fil (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="4a162-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="4a162-139">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-139">string</span></span> | <span data-ttu-id="4a162-140">Namn för identifiering av skadlig programvara eller andra hot som påträffades</span><span class="sxs-lookup"><span data-stu-id="4a162-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="4a162-141">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-141">string</span></span> | <span data-ttu-id="4a162-142">Namnet på organisationen som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="4a162-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="4a162-143">sträng</span><span class="sxs-lookup"><span data-stu-id="4a162-143">string</span></span> | <span data-ttu-id="4a162-144">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="4a162-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="4a162-145">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a162-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="4a162-146">Argument</span><span class="sxs-lookup"><span data-stu-id="4a162-146">Arguments</span></span>

- <span data-ttu-id="4a162-147">**x**– den kolumn med fil-ID som ska användas med funktionen : , , eller ; om `SHA1` det inte är `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` användningsområden</span><span class="sxs-lookup"><span data-stu-id="4a162-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="4a162-148">**y**– begränsning till antalet poster att utöka, 1-1000; funktionen använder 100 om det inte är anspekt</span><span class="sxs-lookup"><span data-stu-id="4a162-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="4a162-149">Tilläggsfunktioner visar endast kompletterande information när de är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="4a162-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="4a162-150">Tillgängligheten för informationen är varierad och beror på en mängd faktorer.</span><span class="sxs-lookup"><span data-stu-id="4a162-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="4a162-151">Tänk på det här när du använder FileProfile() i dina frågor eller när du skapar anpassade identifieringar.</span><span class="sxs-lookup"><span data-stu-id="4a162-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="4a162-152">För bästa resultat rekommenderar vi att du använder funktionen FileProfile() med SHA1.</span><span class="sxs-lookup"><span data-stu-id="4a162-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="4a162-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="4a162-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="4a162-154">Projicera endast KOLUMNEN SHA1 och utöka den</span><span class="sxs-lookup"><span data-stu-id="4a162-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="4a162-155">Förbättra de första 500 posterna och lista filer med låg nivå av arkiv</span><span class="sxs-lookup"><span data-stu-id="4a162-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="4a162-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4a162-156">Related topics</span></span>
- [<span data-ttu-id="4a162-157">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="4a162-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4a162-158">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="4a162-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4a162-159">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="4a162-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4a162-160">Hämta fler frågeexempel</span><span class="sxs-lookup"><span data-stu-id="4a162-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
