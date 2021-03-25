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
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199987"
---
# <a name="file-resource-type"></a><span data-ttu-id="8dcf6-104">Filresurstyp</span><span class="sxs-lookup"><span data-stu-id="8dcf6-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8dcf6-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8dcf6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8dcf6-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8dcf6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8dcf6-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="8dcf6-108">Representerar en filentitet i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="8dcf6-109">Metoder</span><span class="sxs-lookup"><span data-stu-id="8dcf6-109">Methods</span></span>
<span data-ttu-id="8dcf6-110">Metod</span><span class="sxs-lookup"><span data-stu-id="8dcf6-110">Method</span></span>|<span data-ttu-id="8dcf6-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="8dcf6-111">Return Type</span></span> |<span data-ttu-id="8dcf6-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8dcf6-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="8dcf6-113">Hämta fil</span><span class="sxs-lookup"><span data-stu-id="8dcf6-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="8dcf6-114">fil</span><span class="sxs-lookup"><span data-stu-id="8dcf6-114">file</span></span>](files.md) | <span data-ttu-id="8dcf6-115">Hämta en enda fil</span><span class="sxs-lookup"><span data-stu-id="8dcf6-115">Get a single file</span></span> 
[<span data-ttu-id="8dcf6-116">Listfilrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="8dcf6-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="8dcf6-117">[aviseringssamling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="8dcf6-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="8dcf6-118">Få [aviseringsenheterna](alerts.md) som är associerade med filen.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="8dcf6-119">Listfilrelaterade datorer</span><span class="sxs-lookup"><span data-stu-id="8dcf6-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="8dcf6-120">[maskinsamling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="8dcf6-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="8dcf6-121">Få de [datorenheter](machine.md) som är associerade med aviseringen.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="8dcf6-122">filstatistik</span><span class="sxs-lookup"><span data-stu-id="8dcf6-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="8dcf6-123">Statistiksammanfattning</span><span class="sxs-lookup"><span data-stu-id="8dcf6-123">Statistics summary</span></span> | <span data-ttu-id="8dcf6-124">Hämtar den första filen som var den första filen.</span><span class="sxs-lookup"><span data-stu-id="8dcf6-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="8dcf6-125">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="8dcf6-125">Properties</span></span>
|<span data-ttu-id="8dcf6-126">Egenskap</span><span class="sxs-lookup"><span data-stu-id="8dcf6-126">Property</span></span> | <span data-ttu-id="8dcf6-127">Skriv</span><span class="sxs-lookup"><span data-stu-id="8dcf6-127">Type</span></span>    |   <span data-ttu-id="8dcf6-128">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8dcf6-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="8dcf6-129">sha1</span><span class="sxs-lookup"><span data-stu-id="8dcf6-129">sha1</span></span> | <span data-ttu-id="8dcf6-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-130">String</span></span> | <span data-ttu-id="8dcf6-131">Hashtaggen Sha1 för filinnehållet</span><span class="sxs-lookup"><span data-stu-id="8dcf6-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="8dcf6-132">sha256</span><span class="sxs-lookup"><span data-stu-id="8dcf6-132">sha256</span></span> | <span data-ttu-id="8dcf6-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-133">String</span></span> | <span data-ttu-id="8dcf6-134">Sha256-hash för filinnehållet</span><span class="sxs-lookup"><span data-stu-id="8dcf6-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="8dcf6-135">globalprevalence</span><span class="sxs-lookup"><span data-stu-id="8dcf6-135">globalPrevalence</span></span> | <span data-ttu-id="8dcf6-136">Nullbar long</span><span class="sxs-lookup"><span data-stu-id="8dcf6-136">Nullable long</span></span> | <span data-ttu-id="8dcf6-137">Filarysen i hela organisationen</span><span class="sxs-lookup"><span data-stu-id="8dcf6-137">File prevalence across organization</span></span> |
|<span data-ttu-id="8dcf6-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="8dcf6-138">globalFirstObserved</span></span> | <span data-ttu-id="8dcf6-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8dcf6-139">DateTimeOffset</span></span> | <span data-ttu-id="8dcf6-140">Första gången filen observerades</span><span class="sxs-lookup"><span data-stu-id="8dcf6-140">First time the file was observed</span></span> |
|<span data-ttu-id="8dcf6-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="8dcf6-141">globalLastObserved</span></span> | <span data-ttu-id="8dcf6-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8dcf6-142">DateTimeOffset</span></span> | <span data-ttu-id="8dcf6-143">Senaste gången filen observerades</span><span class="sxs-lookup"><span data-stu-id="8dcf6-143">Last time the file was observed</span></span> |
|<span data-ttu-id="8dcf6-144">storlek</span><span class="sxs-lookup"><span data-stu-id="8dcf6-144">size</span></span> | <span data-ttu-id="8dcf6-145">Nullbar long</span><span class="sxs-lookup"><span data-stu-id="8dcf6-145">Nullable long</span></span> | <span data-ttu-id="8dcf6-146">Storlek på filen</span><span class="sxs-lookup"><span data-stu-id="8dcf6-146">Size of the file</span></span> |
|<span data-ttu-id="8dcf6-147">fileType</span><span class="sxs-lookup"><span data-stu-id="8dcf6-147">fileType</span></span> | <span data-ttu-id="8dcf6-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-148">String</span></span> | <span data-ttu-id="8dcf6-149">Typ av fil</span><span class="sxs-lookup"><span data-stu-id="8dcf6-149">Type of the file</span></span> |
|<span data-ttu-id="8dcf6-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="8dcf6-150">isPeFile</span></span> | <span data-ttu-id="8dcf6-151">Boolesk</span><span class="sxs-lookup"><span data-stu-id="8dcf6-151">Boolean</span></span> | <span data-ttu-id="8dcf6-152">true om filen är bärbar körbar (t.ex. "DLL", "EXE" osv.)</span><span class="sxs-lookup"><span data-stu-id="8dcf6-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="8dcf6-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="8dcf6-153">filePublisher</span></span> | <span data-ttu-id="8dcf6-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-154">String</span></span> | <span data-ttu-id="8dcf6-155">Filutgivare</span><span class="sxs-lookup"><span data-stu-id="8dcf6-155">File publisher</span></span> |
|<span data-ttu-id="8dcf6-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="8dcf6-156">fileProductName</span></span> | <span data-ttu-id="8dcf6-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-157">String</span></span> | <span data-ttu-id="8dcf6-158">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="8dcf6-158">Product name</span></span> |
|<span data-ttu-id="8dcf6-159">undertecknare</span><span class="sxs-lookup"><span data-stu-id="8dcf6-159">signer</span></span> | <span data-ttu-id="8dcf6-160">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-160">String</span></span> | <span data-ttu-id="8dcf6-161">Fil signerare</span><span class="sxs-lookup"><span data-stu-id="8dcf6-161">File signer</span></span> |
|<span data-ttu-id="8dcf6-162">utfärdare</span><span class="sxs-lookup"><span data-stu-id="8dcf6-162">issuer</span></span> | <span data-ttu-id="8dcf6-163">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-163">String</span></span> | <span data-ttu-id="8dcf6-164">Filutfärdare</span><span class="sxs-lookup"><span data-stu-id="8dcf6-164">File issuer</span></span> |
|<span data-ttu-id="8dcf6-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="8dcf6-165">signerHash</span></span> | <span data-ttu-id="8dcf6-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-166">String</span></span> | <span data-ttu-id="8dcf6-167">Hash-kod för signeringscertifikatet</span><span class="sxs-lookup"><span data-stu-id="8dcf6-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="8dcf6-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="8dcf6-168">isValidCertificate</span></span> | <span data-ttu-id="8dcf6-169">Boolesk</span><span class="sxs-lookup"><span data-stu-id="8dcf6-169">Boolean</span></span> | <span data-ttu-id="8dcf6-170">Signeringscertifikat har verifierats av Microsoft Defender för Endpoint-agenten</span><span class="sxs-lookup"><span data-stu-id="8dcf6-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="8dcf6-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="8dcf6-171">determinationType</span></span> | <span data-ttu-id="8dcf6-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-172">String</span></span> | <span data-ttu-id="8dcf6-173">Avgöra vilken typ av fil som ska avgöras</span><span class="sxs-lookup"><span data-stu-id="8dcf6-173">The determination type of the file</span></span> |
|<span data-ttu-id="8dcf6-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="8dcf6-174">determinationValue</span></span> | <span data-ttu-id="8dcf6-175">Sträng</span><span class="sxs-lookup"><span data-stu-id="8dcf6-175">String</span></span> | <span data-ttu-id="8dcf6-176">Determination value</span><span class="sxs-lookup"><span data-stu-id="8dcf6-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="8dcf6-177">Json-representation</span><span class="sxs-lookup"><span data-stu-id="8dcf6-177">Json representation</span></span>

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
