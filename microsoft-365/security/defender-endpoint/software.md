---
title: Programvarumetoder och egenskaper
description: Hämtar de senaste aviseringarna.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771423"
---
# <a name="software-resource-type"></a><span data-ttu-id="1cc5f-104">Programvaruresurstyp</span><span class="sxs-lookup"><span data-stu-id="1cc5f-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1cc5f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1cc5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1cc5f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1cc5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1cc5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cc5f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1cc5f-108">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1cc5f-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1cc5f-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1cc5f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1cc5f-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="1cc5f-111">Metoder</span><span class="sxs-lookup"><span data-stu-id="1cc5f-111">Methods</span></span>

<span data-ttu-id="1cc5f-112">Metod</span><span class="sxs-lookup"><span data-stu-id="1cc5f-112">Method</span></span> |<span data-ttu-id="1cc5f-113">Returtyp</span><span class="sxs-lookup"><span data-stu-id="1cc5f-113">Return Type</span></span> |<span data-ttu-id="1cc5f-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1cc5f-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="1cc5f-115">Lista programvara</span><span class="sxs-lookup"><span data-stu-id="1cc5f-115">List software</span></span>](get-software.md) | <span data-ttu-id="1cc5f-116">Insamling av programvara</span><span class="sxs-lookup"><span data-stu-id="1cc5f-116">Software collection</span></span> | <span data-ttu-id="1cc5f-117">Lista organisationens programvaruinventering.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="1cc5f-118">Hämta programvara efter Id</span><span class="sxs-lookup"><span data-stu-id="1cc5f-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="1cc5f-119">Programvara</span><span class="sxs-lookup"><span data-stu-id="1cc5f-119">Software</span></span> | <span data-ttu-id="1cc5f-120">Hämta en särskild programvara genom dess programvaru-ID.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="1cc5f-121">Lista distribution av programvaruversion</span><span class="sxs-lookup"><span data-stu-id="1cc5f-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="1cc5f-122">Distributionssamling</span><span class="sxs-lookup"><span data-stu-id="1cc5f-122">Distribution collection</span></span> | <span data-ttu-id="1cc5f-123">Lista distribution av programvaruversion efter programvaru-ID.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="1cc5f-124">Lista maskiner efter programvara</span><span class="sxs-lookup"><span data-stu-id="1cc5f-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="1cc5f-125">MachineRef-samling</span><span class="sxs-lookup"><span data-stu-id="1cc5f-125">MachineRef collection</span></span> | <span data-ttu-id="1cc5f-126">Hämta en lista över enheter som är associerade med programvaru-ID.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="1cc5f-127">Lista sårbarhet efter programvara</span><span class="sxs-lookup"><span data-stu-id="1cc5f-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="1cc5f-128">[Sårbarhetssamling](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="1cc5f-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="1cc5f-129">Hämta en lista över säkerhetsproblem som är associerade med programvaru-ID.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="1cc5f-130">Hämta saknade KB:er</span><span class="sxs-lookup"><span data-stu-id="1cc5f-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="1cc5f-131">KB-samling</span><span class="sxs-lookup"><span data-stu-id="1cc5f-131">KB collection</span></span> | <span data-ttu-id="1cc5f-132">Visa en lista över saknade KB som är kopplade till programvaru-ID:t</span><span class="sxs-lookup"><span data-stu-id="1cc5f-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="1cc5f-133">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="1cc5f-133">Properties</span></span>

<span data-ttu-id="1cc5f-134">Egenskap</span><span class="sxs-lookup"><span data-stu-id="1cc5f-134">Property</span></span> |   <span data-ttu-id="1cc5f-135">Typ</span><span class="sxs-lookup"><span data-stu-id="1cc5f-135">Type</span></span>   |   <span data-ttu-id="1cc5f-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1cc5f-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="1cc5f-137">id</span><span class="sxs-lookup"><span data-stu-id="1cc5f-137">id</span></span> | <span data-ttu-id="1cc5f-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="1cc5f-138">String</span></span> | <span data-ttu-id="1cc5f-139">Programvaru-ID</span><span class="sxs-lookup"><span data-stu-id="1cc5f-139">Software ID</span></span>
<span data-ttu-id="1cc5f-140">Namn</span><span class="sxs-lookup"><span data-stu-id="1cc5f-140">Name</span></span> | <span data-ttu-id="1cc5f-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="1cc5f-141">String</span></span> | <span data-ttu-id="1cc5f-142">Programvarunamn</span><span class="sxs-lookup"><span data-stu-id="1cc5f-142">Software name</span></span>
<span data-ttu-id="1cc5f-143">Leverantör</span><span class="sxs-lookup"><span data-stu-id="1cc5f-143">Vendor</span></span> | <span data-ttu-id="1cc5f-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="1cc5f-144">String</span></span> | <span data-ttu-id="1cc5f-145">Namn på programvaruleverantör</span><span class="sxs-lookup"><span data-stu-id="1cc5f-145">Software vendor name</span></span>
<span data-ttu-id="1cc5f-146">Svagheter</span><span class="sxs-lookup"><span data-stu-id="1cc5f-146">Weaknesses</span></span> | <span data-ttu-id="1cc5f-147">Long</span><span class="sxs-lookup"><span data-stu-id="1cc5f-147">Long</span></span> | <span data-ttu-id="1cc5f-148">Antal identifierade säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="1cc5f-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="1cc5f-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="1cc5f-149">publicExploit</span></span> | <span data-ttu-id="1cc5f-150">Boolesk</span><span class="sxs-lookup"><span data-stu-id="1cc5f-150">Boolean</span></span> | <span data-ttu-id="1cc5f-151">Offentlig sårbarhet finns för en del av sårbarheterna</span><span class="sxs-lookup"><span data-stu-id="1cc5f-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="1cc5f-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="1cc5f-152">activeAlert</span></span> | <span data-ttu-id="1cc5f-153">Boolesk</span><span class="sxs-lookup"><span data-stu-id="1cc5f-153">Boolean</span></span> | <span data-ttu-id="1cc5f-154">Aktiv avisering är kopplad till den här programvaran</span><span class="sxs-lookup"><span data-stu-id="1cc5f-154">Active alert is associated with this software</span></span>
<span data-ttu-id="1cc5f-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="1cc5f-155">exposedMachines</span></span> | <span data-ttu-id="1cc5f-156">Long</span><span class="sxs-lookup"><span data-stu-id="1cc5f-156">Long</span></span> | <span data-ttu-id="1cc5f-157">Antal exponerade enheter</span><span class="sxs-lookup"><span data-stu-id="1cc5f-157">Number of exposed devices</span></span>
<span data-ttu-id="1cc5f-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="1cc5f-158">impactScore</span></span> | <span data-ttu-id="1cc5f-159">Double</span><span class="sxs-lookup"><span data-stu-id="1cc5f-159">Double</span></span> | <span data-ttu-id="1cc5f-160">Effekterna av exponeringsresultatet för den här programvaran</span><span class="sxs-lookup"><span data-stu-id="1cc5f-160">Exposure score impact of this software</span></span>
