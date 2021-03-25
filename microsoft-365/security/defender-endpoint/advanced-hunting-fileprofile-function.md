---
title: Funktionen FileProfile() i avancerad sökning efter Microsoft Defender för Endpoint
description: Lär dig använda FileProfile() för att utöka information om filer i avancerade sökresultat för sökfrågor
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076009"
---
# <a name="fileprofile"></a><span data-ttu-id="7e893-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="7e893-104">FileProfile()</span></span>

<span data-ttu-id="7e893-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7e893-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e893-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e893-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="7e893-107">Funktionen `FileProfile()` är en funktion för [](advanced-hunting-overview.md) avancerad sökning som lägger till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="7e893-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="7e893-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="7e893-108">Column</span></span> | <span data-ttu-id="7e893-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="7e893-109">Data type</span></span> | <span data-ttu-id="7e893-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e893-110">Description</span></span>
-|-|-
<span data-ttu-id="7e893-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="7e893-111">SHA1</span></span> | <span data-ttu-id="7e893-112">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-112">string</span></span> | <span data-ttu-id="7e893-113">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="7e893-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="7e893-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="7e893-114">SHA256</span></span> | <span data-ttu-id="7e893-115">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-115">string</span></span> | <span data-ttu-id="7e893-116">SHA-256 av filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="7e893-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="7e893-117">MD5</span><span class="sxs-lookup"><span data-stu-id="7e893-117">MD5</span></span> | <span data-ttu-id="7e893-118">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-118">string</span></span> | <span data-ttu-id="7e893-119">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="7e893-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="7e893-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="7e893-120">FileSize</span></span> | <span data-ttu-id="7e893-121">int</span><span class="sxs-lookup"><span data-stu-id="7e893-121">int</span></span> | <span data-ttu-id="7e893-122">Storlek på filen i byte</span><span class="sxs-lookup"><span data-stu-id="7e893-122">Size of the file in bytes</span></span>
<span data-ttu-id="7e893-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="7e893-123">GlobalPrevalence</span></span> | <span data-ttu-id="7e893-124">int</span><span class="sxs-lookup"><span data-stu-id="7e893-124">int</span></span> | <span data-ttu-id="7e893-125">Antal förekomster av entitet som observerats av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="7e893-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="7e893-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="7e893-126">GlobalFirstSeen</span></span> | <span data-ttu-id="7e893-127">datetime</span><span class="sxs-lookup"><span data-stu-id="7e893-127">datetime</span></span> | <span data-ttu-id="7e893-128">Datum och tid då enheten för första gången observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="7e893-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="7e893-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="7e893-129">GlobalLastSeen</span></span> | <span data-ttu-id="7e893-130">datetime</span><span class="sxs-lookup"><span data-stu-id="7e893-130">datetime</span></span> | <span data-ttu-id="7e893-131">Datum och tid då enheten senast observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="7e893-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="7e893-132">Undertecknaren</span><span class="sxs-lookup"><span data-stu-id="7e893-132">Signer</span></span> | <span data-ttu-id="7e893-133">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-133">string</span></span> | <span data-ttu-id="7e893-134">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="7e893-134">Information about the signer of the file</span></span>
<span data-ttu-id="7e893-135">Utfärdare</span><span class="sxs-lookup"><span data-stu-id="7e893-135">Issuer</span></span> | <span data-ttu-id="7e893-136">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-136">string</span></span> | <span data-ttu-id="7e893-137">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="7e893-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="7e893-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="7e893-138">SignerHash</span></span> | <span data-ttu-id="7e893-139">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-139">string</span></span> | <span data-ttu-id="7e893-140">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="7e893-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="7e893-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="7e893-141">IsCertificateValid</span></span> | <span data-ttu-id="7e893-142">boolesk</span><span class="sxs-lookup"><span data-stu-id="7e893-142">boolean</span></span> | <span data-ttu-id="7e893-143">Om det certifikat som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="7e893-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="7e893-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="7e893-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="7e893-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="7e893-145">boolean</span></span> | <span data-ttu-id="7e893-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e893-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="7e893-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="7e893-147">IsExecutable</span></span> | <span data-ttu-id="7e893-148">boolesk</span><span class="sxs-lookup"><span data-stu-id="7e893-148">boolean</span></span> | <span data-ttu-id="7e893-149">Om filen är en PE-fil (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="7e893-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="7e893-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="7e893-150">ThreatName</span></span> | <span data-ttu-id="7e893-151">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-151">string</span></span> | <span data-ttu-id="7e893-152">Namn för identifiering av skadlig programvara eller andra hot som påträffades</span><span class="sxs-lookup"><span data-stu-id="7e893-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="7e893-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="7e893-153">Publisher</span></span> | <span data-ttu-id="7e893-154">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-154">string</span></span> | <span data-ttu-id="7e893-155">Namnet på organisationen som publicerade filen</span><span class="sxs-lookup"><span data-stu-id="7e893-155">Name of the organization that published the file</span></span>
<span data-ttu-id="7e893-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="7e893-156">SoftwareName</span></span> | <span data-ttu-id="7e893-157">sträng</span><span class="sxs-lookup"><span data-stu-id="7e893-157">string</span></span> | <span data-ttu-id="7e893-158">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="7e893-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="7e893-159">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e893-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="7e893-160">Argument</span><span class="sxs-lookup"><span data-stu-id="7e893-160">Arguments</span></span>

- <span data-ttu-id="7e893-161">**x** – kolumn med fil-ID som ska användas: , eller ; funktion `SHA1` som används om det inte är `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` anspekt</span><span class="sxs-lookup"><span data-stu-id="7e893-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="7e893-162">**y** – begränsning till antalet poster att utöka, 1-1000; funktionen använder 100 om det inte är anspekt</span><span class="sxs-lookup"><span data-stu-id="7e893-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="7e893-163">Exempel</span><span class="sxs-lookup"><span data-stu-id="7e893-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="7e893-164">Projicera endast KOLUMNEN SHA1 och utöka den</span><span class="sxs-lookup"><span data-stu-id="7e893-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="7e893-165">Förbättra de första 500 posterna och lista filer med låg nivå av arkiv</span><span class="sxs-lookup"><span data-stu-id="7e893-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="7e893-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7e893-166">Related topics</span></span>

- [<span data-ttu-id="7e893-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7e893-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e893-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="7e893-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7e893-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7e893-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
