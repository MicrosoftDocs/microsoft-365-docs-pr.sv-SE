---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i det avancerade jaktschemat
description: Lär dig mer om de sårbarheter för programvara som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schema, referens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, inventering, sårbarheter, CVE ID, CVSS, DeviceTvmSoftBevulnerabilitiesKB
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
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44328004"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="98083-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="98083-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="98083-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="98083-105">**Applies to:**</span></span>
- <span data-ttu-id="98083-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="98083-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="98083-107">`DeviceTvmSoftwareVulnerabilitiesKB`Tabellen i det avancerade jaktschemat innehåller en lista över sårbarheter Hot & [Sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="98083-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="98083-108">Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="98083-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="98083-109">Information om andra tabeller i det avancerade jaktschemat finns [i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="98083-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="98083-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="98083-110">Column name</span></span> | <span data-ttu-id="98083-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="98083-111">Data type</span></span> | <span data-ttu-id="98083-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="98083-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="98083-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="98083-113">string</span></span> | <span data-ttu-id="98083-114">Unik identifierare som tilldelats säkerhetsproblemet under CVE-systemet (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="98083-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="98083-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="98083-115">string</span></span> | <span data-ttu-id="98083-116">Allvarlighetsgrad som tilldelats säkerhetsproblemet under cvss (Common Vulnerability Scoring System)</span><span class="sxs-lookup"><span data-stu-id="98083-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="98083-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="98083-117">boolean</span></span> | <span data-ttu-id="98083-118">Anger om det är allmänt tillgängligt för att utnyttja kod för säkerhetsproblemet</span><span class="sxs-lookup"><span data-stu-id="98083-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="98083-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="98083-119">string</span></span> | <span data-ttu-id="98083-120">Allvarlighetsgrad som tilldelats säkerhetsproblemet baserat på CVSS-poängen och dynamiska faktorer som påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="98083-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="98083-121">Datetime</span><span class="sxs-lookup"><span data-stu-id="98083-121">datetime</span></span> | <span data-ttu-id="98083-122">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="98083-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="98083-123">Datetime</span><span class="sxs-lookup"><span data-stu-id="98083-123">datetime</span></span> | <span data-ttu-id="98083-124">Datum sårbarhet avslöjades för allmänheten</span><span class="sxs-lookup"><span data-stu-id="98083-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="98083-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="98083-125">string</span></span> | <span data-ttu-id="98083-126">Beskrivning av sårbarhet och därmed förbundna risker</span><span class="sxs-lookup"><span data-stu-id="98083-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="98083-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="98083-127">string</span></span> | <span data-ttu-id="98083-128">Lista över alla programvaruprodukter som påverkas av sårbarheten</span><span class="sxs-lookup"><span data-stu-id="98083-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="98083-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="98083-129">Related topics</span></span>

- [<span data-ttu-id="98083-130">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="98083-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98083-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="98083-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98083-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="98083-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="98083-133">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="98083-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="98083-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="98083-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="98083-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="98083-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="98083-136">Översikt över hantering av hot & sårbarhet</span><span class="sxs-lookup"><span data-stu-id="98083-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
