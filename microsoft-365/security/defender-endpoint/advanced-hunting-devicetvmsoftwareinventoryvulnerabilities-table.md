---
title: Tabellen DeviceTvmSoftwareInventoryVulnerabilities i det avancerade sökschemat
description: Läs mer om inventeringen av programvara i dina enheter och deras säkerhetsproblem i tabellen DeviceTvmSoftwareInventoryVulnerabilities i tabellen för avancerad sökning.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163465"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="82d48-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="82d48-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82d48-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="82d48-105">**Applies to:**</span></span>

- [<span data-ttu-id="82d48-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="82d48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="82d48-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="82d48-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="82d48-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="82d48-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="82d48-109">Tabellen i det avancerade sökschemat innehåller & sårbarhetshanteringslager av programvara på dina enheter samt alla kända säkerhetsproblem `DeviceTvmSoftwareInventoryVulnerabilities` i dessa [](next-gen-threat-and-vuln-mgt.md) programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="82d48-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="82d48-110">Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.</span><span class="sxs-lookup"><span data-stu-id="82d48-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="82d48-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="82d48-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="82d48-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="82d48-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="82d48-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="82d48-113">Column name</span></span> | <span data-ttu-id="82d48-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="82d48-114">Data type</span></span> | <span data-ttu-id="82d48-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="82d48-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="82d48-116">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-116">string</span></span> | <span data-ttu-id="82d48-117">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="82d48-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="82d48-118">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-118">string</span></span> | <span data-ttu-id="82d48-119">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="82d48-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="82d48-120">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-120">string</span></span> | <span data-ttu-id="82d48-121">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="82d48-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="82d48-122">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="82d48-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="82d48-123">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-123">string</span></span> | <span data-ttu-id="82d48-124">Version av operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="82d48-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="82d48-125">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-125">string</span></span> | <span data-ttu-id="82d48-126">Arkitekturen för operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="82d48-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="82d48-127">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-127">string</span></span> | <span data-ttu-id="82d48-128">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="82d48-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="82d48-129">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-129">string</span></span> | <span data-ttu-id="82d48-130">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="82d48-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="82d48-131">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-131">string</span></span> | <span data-ttu-id="82d48-132">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="82d48-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="82d48-133">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-133">string</span></span> | <span data-ttu-id="82d48-134">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="82d48-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="82d48-135">sträng</span><span class="sxs-lookup"><span data-stu-id="82d48-135">string</span></span> | <span data-ttu-id="82d48-136">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="82d48-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="82d48-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="82d48-137">Related topics</span></span>

- [<span data-ttu-id="82d48-138">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="82d48-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="82d48-139">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="82d48-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="82d48-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="82d48-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="82d48-141">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="82d48-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
