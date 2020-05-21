---
title: DeviceTvmSoftwareInventoryVulnerabilities tabellen i det avancerade jaktschemat
description: Lär dig mer om inventeringen av programvara i dina enheter och deras sårbarheter i tabellen DeviceTvmSoftwareInventoryVulnerabilities i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, inventering, sårbarheter, CVE ID, OS DeviceTvmSoftwareIntoryVulnerabilities
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
ms.openlocfilehash: 0a7ac5a68bcdb12b3cdcd94cac8012c7807a6e2b
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327996"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="d92a0-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="d92a0-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="d92a0-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="d92a0-105">**Applies to:**</span></span>
- <span data-ttu-id="d92a0-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="d92a0-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d92a0-107">`DeviceTvmSoftwareInventoryVulnerabilities`Tabellen i det avancerade jaktschemat innehåller [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) hantering av programvara på dina enheter samt eventuella kända sårbarheter i dessa programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="d92a0-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="d92a0-108">Den här tabellen innehåller även information om operativsystemet, CVE-ID:er och allvarlighetsgradinformation för säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="d92a0-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="d92a0-109">Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="d92a0-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d92a0-110">Information om andra tabeller i det avancerade jaktschemat finns [i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d92a0-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d92a0-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d92a0-111">Column name</span></span> | <span data-ttu-id="d92a0-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d92a0-112">Data type</span></span> | <span data-ttu-id="d92a0-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d92a0-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d92a0-114">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-114">string</span></span> | <span data-ttu-id="d92a0-115">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="d92a0-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d92a0-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-116">string</span></span> | <span data-ttu-id="d92a0-117">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="d92a0-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="d92a0-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-118">string</span></span> | <span data-ttu-id="d92a0-119">Plattform för operativsystemet som körs på maskinen.</span><span class="sxs-lookup"><span data-stu-id="d92a0-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="d92a0-120">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d92a0-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="d92a0-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-121">string</span></span> | <span data-ttu-id="d92a0-122">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="d92a0-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="d92a0-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-123">string</span></span> | <span data-ttu-id="d92a0-124">Arkitektur för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="d92a0-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="d92a0-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-125">string</span></span> | <span data-ttu-id="d92a0-126">Programvaruleverantörens namn</span><span class="sxs-lookup"><span data-stu-id="d92a0-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="d92a0-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-127">string</span></span> | <span data-ttu-id="d92a0-128">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="d92a0-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="d92a0-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-129">string</span></span> | <span data-ttu-id="d92a0-130">Versionsnummer för programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="d92a0-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="d92a0-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-131">string</span></span> | <span data-ttu-id="d92a0-132">Unik identifierare som tilldelats säkerhetsproblemet under CVE-systemet (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="d92a0-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d92a0-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="d92a0-133">string</span></span> | <span data-ttu-id="d92a0-134">Allvarlighetsgrad som tilldelats säkerhetsproblemet baserat på CVSS-poängen och dynamiska faktorer som påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="d92a0-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="d92a0-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d92a0-135">Related topics</span></span>

- [<span data-ttu-id="d92a0-136">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="d92a0-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d92a0-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d92a0-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d92a0-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="d92a0-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d92a0-139">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d92a0-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d92a0-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d92a0-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d92a0-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="d92a0-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d92a0-142">Översikt över hantering av hot & sårbarhet</span><span class="sxs-lookup"><span data-stu-id="d92a0-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
