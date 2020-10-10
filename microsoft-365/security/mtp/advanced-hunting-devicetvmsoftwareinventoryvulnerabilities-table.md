---
title: DeviceTvmSoftwareInventoryVulnerabilities-tabell i det avancerade jakt-schemat
description: Lär dig mer om inventering av program vara på dina enheter och deras säkerhets problem i DeviceTvmSoftwareInventoryVulnerabilities-tabellen i det avancerade antivirus programmet.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, program vara, inventering, sårbarhet, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d8858fe9acd8183ad0d8644a9d5e4d70d32990a6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413228"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="8b859-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="8b859-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8b859-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8b859-105">**Applies to:**</span></span>
- <span data-ttu-id="8b859-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8b859-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="8b859-107">`DeviceTvmSoftwareInventoryVulnerabilities`Tabellen i det avancerade jakt-schemat innehåller [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av program vara på dina enheter samt eventuella kända säkerhets problem i dessa program varu produkter.</span><span class="sxs-lookup"><span data-stu-id="8b859-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="8b859-108">Den här tabellen innehåller information om operativ system, CVE-ID och säkerhets problem.</span><span class="sxs-lookup"><span data-stu-id="8b859-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="8b859-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="8b859-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8b859-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8b859-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8b859-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8b859-111">Column name</span></span> | <span data-ttu-id="8b859-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="8b859-112">Data type</span></span> | <span data-ttu-id="8b859-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b859-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="8b859-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-114">string</span></span> | <span data-ttu-id="8b859-115">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="8b859-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8b859-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-116">string</span></span> | <span data-ttu-id="8b859-117">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="8b859-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8b859-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-118">string</span></span> | <span data-ttu-id="8b859-119">Plattformen för det operativ system som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="8b859-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8b859-120">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8b859-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="8b859-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-121">string</span></span> | <span data-ttu-id="8b859-122">Version av operativ systemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="8b859-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="8b859-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-123">string</span></span> | <span data-ttu-id="8b859-124">Arkitekturen för operativ systemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="8b859-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="8b859-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-125">string</span></span> | <span data-ttu-id="8b859-126">Namn på program varu leverantören</span><span class="sxs-lookup"><span data-stu-id="8b859-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="8b859-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-127">string</span></span> | <span data-ttu-id="8b859-128">Namnet på program varu produkten</span><span class="sxs-lookup"><span data-stu-id="8b859-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="8b859-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-129">string</span></span> | <span data-ttu-id="8b859-130">Versions nummer för program varu produkten</span><span class="sxs-lookup"><span data-stu-id="8b859-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="8b859-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-131">string</span></span> | <span data-ttu-id="8b859-132">Unik identifierare tilldelad säkerhets luckan under de allmänna sårbarheterna och exponeringarna (CVE)</span><span class="sxs-lookup"><span data-stu-id="8b859-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="8b859-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="8b859-133">string</span></span> | <span data-ttu-id="8b859-134">Allvarlighets grad tilldelad säkerhets luckan baserat på CVSS Poäng och dynamiska faktorer som påverkas av hotets liggande</span><span class="sxs-lookup"><span data-stu-id="8b859-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="8b859-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8b859-135">Related topics</span></span>

- [<span data-ttu-id="8b859-136">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="8b859-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8b859-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="8b859-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8b859-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="8b859-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8b859-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="8b859-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8b859-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8b859-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8b859-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="8b859-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8b859-142">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="8b859-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
