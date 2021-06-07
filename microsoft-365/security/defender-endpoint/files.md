---
title: Filresurstyp
description: Hämta de senaste Microsoft Defender för slutpunktsaviseringar som är relaterade till filer.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771195"
---
# <a name="file-resource-type"></a><span data-ttu-id="34d4c-104">Filresurstyp</span><span class="sxs-lookup"><span data-stu-id="34d4c-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="34d4c-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="34d4c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="34d4c-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="34d4c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="34d4c-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="34d4c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="34d4c-108">Representerar en filentitet i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="34d4c-109">Metoder</span><span class="sxs-lookup"><span data-stu-id="34d4c-109">Methods</span></span>
<span data-ttu-id="34d4c-110">Metod</span><span class="sxs-lookup"><span data-stu-id="34d4c-110">Method</span></span>|<span data-ttu-id="34d4c-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="34d4c-111">Return Type</span></span> |<span data-ttu-id="34d4c-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="34d4c-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="34d4c-113">Hämta fil</span><span class="sxs-lookup"><span data-stu-id="34d4c-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="34d4c-114">fil</span><span class="sxs-lookup"><span data-stu-id="34d4c-114">file</span></span>](files.md) | <span data-ttu-id="34d4c-115">Hämta en enda fil</span><span class="sxs-lookup"><span data-stu-id="34d4c-115">Get a single file</span></span> 
[<span data-ttu-id="34d4c-116">Listfilrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="34d4c-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="34d4c-117">[aviseringssamling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="34d4c-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="34d4c-118">Få [aviseringsenheterna](alerts.md) som är associerade med filen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="34d4c-119">Listfilrelaterade datorer</span><span class="sxs-lookup"><span data-stu-id="34d4c-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="34d4c-120">[maskinsamling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="34d4c-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="34d4c-121">Få de [datorenheter](machine.md) som är associerade med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="34d4c-122">filstatistik</span><span class="sxs-lookup"><span data-stu-id="34d4c-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="34d4c-123">Statistiksammanfattning</span><span class="sxs-lookup"><span data-stu-id="34d4c-123">Statistics summary</span></span> | <span data-ttu-id="34d4c-124">Hämtar den första filen som var den första filen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="34d4c-125">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="34d4c-125">Properties</span></span>
|<span data-ttu-id="34d4c-126">Egenskap</span><span class="sxs-lookup"><span data-stu-id="34d4c-126">Property</span></span> | <span data-ttu-id="34d4c-127">Typ</span><span class="sxs-lookup"><span data-stu-id="34d4c-127">Type</span></span>    |   <span data-ttu-id="34d4c-128">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="34d4c-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="34d4c-129">sha1</span><span class="sxs-lookup"><span data-stu-id="34d4c-129">sha1</span></span> | <span data-ttu-id="34d4c-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-130">String</span></span> | <span data-ttu-id="34d4c-131">Hashtaggen Sha1 för filinnehållet</span><span class="sxs-lookup"><span data-stu-id="34d4c-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="34d4c-132">sha256</span><span class="sxs-lookup"><span data-stu-id="34d4c-132">sha256</span></span> | <span data-ttu-id="34d4c-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-133">String</span></span> | <span data-ttu-id="34d4c-134">Sha256-hash för filinnehållet</span><span class="sxs-lookup"><span data-stu-id="34d4c-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="34d4c-135">globalprevalence</span><span class="sxs-lookup"><span data-stu-id="34d4c-135">globalPrevalence</span></span> | <span data-ttu-id="34d4c-136">Nullbar long</span><span class="sxs-lookup"><span data-stu-id="34d4c-136">Nullable long</span></span> | <span data-ttu-id="34d4c-137">Filarysen i hela organisationen</span><span class="sxs-lookup"><span data-stu-id="34d4c-137">File prevalence across organization</span></span> |
|<span data-ttu-id="34d4c-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="34d4c-138">globalFirstObserved</span></span> | <span data-ttu-id="34d4c-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="34d4c-139">DateTimeOffset</span></span> | <span data-ttu-id="34d4c-140">Första gången filen observerades</span><span class="sxs-lookup"><span data-stu-id="34d4c-140">First time the file was observed</span></span> |
|<span data-ttu-id="34d4c-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="34d4c-141">globalLastObserved</span></span> | <span data-ttu-id="34d4c-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="34d4c-142">DateTimeOffset</span></span> | <span data-ttu-id="34d4c-143">Senaste gången filen observerades</span><span class="sxs-lookup"><span data-stu-id="34d4c-143">Last time the file was observed</span></span> |
|<span data-ttu-id="34d4c-144">storlek</span><span class="sxs-lookup"><span data-stu-id="34d4c-144">size</span></span> | <span data-ttu-id="34d4c-145">Nullbar long</span><span class="sxs-lookup"><span data-stu-id="34d4c-145">Nullable long</span></span> | <span data-ttu-id="34d4c-146">Storlek på filen</span><span class="sxs-lookup"><span data-stu-id="34d4c-146">Size of the file</span></span> |
|<span data-ttu-id="34d4c-147">fileType</span><span class="sxs-lookup"><span data-stu-id="34d4c-147">fileType</span></span> | <span data-ttu-id="34d4c-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-148">String</span></span> | <span data-ttu-id="34d4c-149">Typ av fil</span><span class="sxs-lookup"><span data-stu-id="34d4c-149">Type of the file</span></span> |
|<span data-ttu-id="34d4c-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="34d4c-150">isPeFile</span></span> | <span data-ttu-id="34d4c-151">Boolesk</span><span class="sxs-lookup"><span data-stu-id="34d4c-151">Boolean</span></span> | <span data-ttu-id="34d4c-152">true om filen är bärbar körbar (t.ex. "DLL", "EXE" osv.)</span><span class="sxs-lookup"><span data-stu-id="34d4c-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="34d4c-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="34d4c-153">filePublisher</span></span> | <span data-ttu-id="34d4c-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-154">String</span></span> | <span data-ttu-id="34d4c-155">Filutgivare</span><span class="sxs-lookup"><span data-stu-id="34d4c-155">File publisher</span></span> |
|<span data-ttu-id="34d4c-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="34d4c-156">fileProductName</span></span> | <span data-ttu-id="34d4c-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-157">String</span></span> | <span data-ttu-id="34d4c-158">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="34d4c-158">Product name</span></span> |
|<span data-ttu-id="34d4c-159">undertecknare</span><span class="sxs-lookup"><span data-stu-id="34d4c-159">signer</span></span> | <span data-ttu-id="34d4c-160">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-160">String</span></span> | <span data-ttu-id="34d4c-161">Fil signerare</span><span class="sxs-lookup"><span data-stu-id="34d4c-161">File signer</span></span> |
|<span data-ttu-id="34d4c-162">utfärdare</span><span class="sxs-lookup"><span data-stu-id="34d4c-162">issuer</span></span> | <span data-ttu-id="34d4c-163">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-163">String</span></span> | <span data-ttu-id="34d4c-164">Filutfärdare</span><span class="sxs-lookup"><span data-stu-id="34d4c-164">File issuer</span></span> |
|<span data-ttu-id="34d4c-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="34d4c-165">signerHash</span></span> | <span data-ttu-id="34d4c-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-166">String</span></span> | <span data-ttu-id="34d4c-167">Hash-kod för signeringscertifikatet</span><span class="sxs-lookup"><span data-stu-id="34d4c-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="34d4c-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="34d4c-168">isValidCertificate</span></span> | <span data-ttu-id="34d4c-169">Boolesk</span><span class="sxs-lookup"><span data-stu-id="34d4c-169">Boolean</span></span> | <span data-ttu-id="34d4c-170">Signeringscertifikat har verifierats av Microsoft Defender för Endpoint-agenten</span><span class="sxs-lookup"><span data-stu-id="34d4c-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="34d4c-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="34d4c-171">determinationType</span></span> | <span data-ttu-id="34d4c-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-172">String</span></span> | <span data-ttu-id="34d4c-173">Avgöra vilken typ av fil som ska avgöras</span><span class="sxs-lookup"><span data-stu-id="34d4c-173">The determination type of the file</span></span> |
|<span data-ttu-id="34d4c-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="34d4c-174">determinationValue</span></span> | <span data-ttu-id="34d4c-175">Sträng</span><span class="sxs-lookup"><span data-stu-id="34d4c-175">String</span></span> | <span data-ttu-id="34d4c-176">Determination value</span><span class="sxs-lookup"><span data-stu-id="34d4c-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="34d4c-177">Json-representation</span><span class="sxs-lookup"><span data-stu-id="34d4c-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
