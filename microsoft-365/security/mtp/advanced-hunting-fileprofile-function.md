---
title: FileProfile ()-funktion i avancerad jakt för skydd mot Microsoft Threat
description: Lär dig hur du använder FileProfile () för att utöka informationen om filer i de avancerade frågeresultaten
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, FileProfile, fil profil, funktion och berikning
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
ms.openlocfilehash: d0fd359bb6f56f7c20b0a39b7fd45ec551e7e49e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797788"
---
# <a name="fileprofile"></a><span data-ttu-id="effce-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="effce-104">FileProfile()</span></span>

<span data-ttu-id="effce-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="effce-105">**Applies to:**</span></span>
- <span data-ttu-id="effce-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="effce-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="effce-107">`FileProfile()`Funktionen är en mångsidig funktion i [Avancerad jakt](advanced-hunting-overview.md) som lägger till följande data i filer som hittas av frågan.</span><span class="sxs-lookup"><span data-stu-id="effce-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="effce-108">Kolumn</span><span class="sxs-lookup"><span data-stu-id="effce-108">Column</span></span> | <span data-ttu-id="effce-109">Datatyp</span><span class="sxs-lookup"><span data-stu-id="effce-109">Data type</span></span> | <span data-ttu-id="effce-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="effce-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="effce-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="effce-111">SHA1</span></span> | <span data-ttu-id="effce-112">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-112">string</span></span> | <span data-ttu-id="effce-113">SHA-1 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="effce-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="effce-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="effce-114">SHA256</span></span> | <span data-ttu-id="effce-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-115">string</span></span> | <span data-ttu-id="effce-116">SHA-256 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="effce-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="effce-117">MD5</span><span class="sxs-lookup"><span data-stu-id="effce-117">MD5</span></span> | <span data-ttu-id="effce-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-118">string</span></span> | <span data-ttu-id="effce-119">MD5-hash för filen som den inspelade åtgärden tillämpades för</span><span class="sxs-lookup"><span data-stu-id="effce-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="effce-120">Storlek</span><span class="sxs-lookup"><span data-stu-id="effce-120">FileSize</span></span> | <span data-ttu-id="effce-121">signera</span><span class="sxs-lookup"><span data-stu-id="effce-121">int</span></span> | <span data-ttu-id="effce-122">Storleken på filen i byte</span><span class="sxs-lookup"><span data-stu-id="effce-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="effce-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="effce-123">GlobalPrevalence</span></span> | <span data-ttu-id="effce-124">signera</span><span class="sxs-lookup"><span data-stu-id="effce-124">int</span></span> | <span data-ttu-id="effce-125">Antal instanser av enheten som Microsoft globalt har iakttagit</span><span class="sxs-lookup"><span data-stu-id="effce-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="effce-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="effce-126">GlobalFirstSeen</span></span> | <span data-ttu-id="effce-127">datetime</span><span class="sxs-lookup"><span data-stu-id="effce-127">datetime</span></span> | <span data-ttu-id="effce-128">Datum och tid då enheten först observerades av Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="effce-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="effce-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="effce-129">GlobalLastSeen</span></span> | <span data-ttu-id="effce-130">datetime</span><span class="sxs-lookup"><span data-stu-id="effce-130">datetime</span></span> | <span data-ttu-id="effce-131">Datum och tid då enheten senast kom från Microsoft globalt</span><span class="sxs-lookup"><span data-stu-id="effce-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="effce-132">Undertecknarens</span><span class="sxs-lookup"><span data-stu-id="effce-132">Signer</span></span> | <span data-ttu-id="effce-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-133">string</span></span> | <span data-ttu-id="effce-134">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="effce-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="effce-135">Utgivaren</span><span class="sxs-lookup"><span data-stu-id="effce-135">Issuer</span></span> | <span data-ttu-id="effce-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-136">string</span></span> | <span data-ttu-id="effce-137">Information om utfärdande av certifikat utfärdare (CA)</span><span class="sxs-lookup"><span data-stu-id="effce-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="effce-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="effce-138">SignerHash</span></span> | <span data-ttu-id="effce-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-139">string</span></span> | <span data-ttu-id="effce-140">Unikt hashvärde identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="effce-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="effce-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="effce-141">IsCertificateValid</span></span> | <span data-ttu-id="effce-142">returtyp</span><span class="sxs-lookup"><span data-stu-id="effce-142">boolean</span></span> | <span data-ttu-id="effce-143">Om certifikatet som används för att signera filen är giltigt</span><span class="sxs-lookup"><span data-stu-id="effce-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="effce-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="effce-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="effce-145">returtyp</span><span class="sxs-lookup"><span data-stu-id="effce-145">boolean</span></span> | <span data-ttu-id="effce-146">Anger om undertecknaren hos rot certifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="effce-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="effce-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="effce-147">IsExecutable</span></span> | <span data-ttu-id="effce-148">returtyp</span><span class="sxs-lookup"><span data-stu-id="effce-148">boolean</span></span> | <span data-ttu-id="effce-149">Om filen är en fil för Portable körbara filer (PE)</span><span class="sxs-lookup"><span data-stu-id="effce-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="effce-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="effce-150">ThreatName</span></span> | <span data-ttu-id="effce-151">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-151">string</span></span> | <span data-ttu-id="effce-152">Identifierings namn för skadlig program vara eller andra hot Funna</span><span class="sxs-lookup"><span data-stu-id="effce-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="effce-153">Skapas</span><span class="sxs-lookup"><span data-stu-id="effce-153">Publisher</span></span> | <span data-ttu-id="effce-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-154">string</span></span> | <span data-ttu-id="effce-155">Namn på organisationen som har publicerat filen</span><span class="sxs-lookup"><span data-stu-id="effce-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="effce-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="effce-156">SoftwareName</span></span> | <span data-ttu-id="effce-157">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="effce-157">string</span></span> | <span data-ttu-id="effce-158">Namnet på program varu produkten</span><span class="sxs-lookup"><span data-stu-id="effce-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="effce-159">Frågesyntaxen</span><span class="sxs-lookup"><span data-stu-id="effce-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="effce-160">Argument</span><span class="sxs-lookup"><span data-stu-id="effce-160">Arguments</span></span>

- <span data-ttu-id="effce-161">**x** — kolumnen fil-ID som ska användas: `SHA1` , `SHA256` `InitiatingProcessSHA1` eller `InitiatingProcessSHA256` ; funktionen används `SHA1` om ospecificerad</span><span class="sxs-lookup"><span data-stu-id="effce-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="effce-162">**y** – begränsa antalet poster som ska utökas, 1-1000; funktionen använder 100 om ospecificerad</span><span class="sxs-lookup"><span data-stu-id="effce-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="effce-163">Exempel</span><span class="sxs-lookup"><span data-stu-id="effce-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="effce-164">Endast kolumnen SHA1 och utöka den</span><span class="sxs-lookup"><span data-stu-id="effce-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="effce-165">Utöka de första 500-posterna och visa en lista över lågprioriterade filer</span><span class="sxs-lookup"><span data-stu-id="effce-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="effce-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="effce-166">Related topics</span></span>
- [<span data-ttu-id="effce-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="effce-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="effce-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="effce-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="effce-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="effce-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="effce-170">Exempel på fler frågor</span><span class="sxs-lookup"><span data-stu-id="effce-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)