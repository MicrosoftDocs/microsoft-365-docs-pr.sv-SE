---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i det avancerade jaktschemat
description: Lär dig mer om de olika säkra konfigurationer som bedöms av Threat & Sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverk, kunskapsbas, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807966"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="65ea9-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="65ea9-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="65ea9-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="65ea9-105">**Applies to:**</span></span>
- <span data-ttu-id="65ea9-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="65ea9-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="65ea9-107">Tabellen `DeviceTvmSecureConfigurationAssessmentKB` i det avancerade jaktschemat innehåller information om de olika säkra konfigurationerna, till exempel om en enhet har automatiska uppdateringar på , som kontrolleras av [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="65ea9-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="65ea9-108">Den innehåller också riskinformation, relaterade branschriktmärken och tillämpliga MITRE ATT&CK-tekniker och taktik.</span><span class="sxs-lookup"><span data-stu-id="65ea9-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="65ea9-109">Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="65ea9-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="65ea9-110">Information om andra tabeller i det avancerade jaktschemat finns i [den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="65ea9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65ea9-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="65ea9-111">Column name</span></span> | <span data-ttu-id="65ea9-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="65ea9-112">Data type</span></span> | <span data-ttu-id="65ea9-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="65ea9-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="65ea9-114">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-114">string</span></span> | <span data-ttu-id="65ea9-115">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="65ea9-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="65ea9-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-116">string</span></span> | <span data-ttu-id="65ea9-117">Nominell effekt av konfigurationen till den totala konfigurationspoängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="65ea9-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="65ea9-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-118">string</span></span> | <span data-ttu-id="65ea9-119">Visa namnet på konfigurationen</span><span class="sxs-lookup"><span data-stu-id="65ea9-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="65ea9-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-120">string</span></span> | <span data-ttu-id="65ea9-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="65ea9-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="65ea9-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-122">string</span></span> | <span data-ttu-id="65ea9-123">Beskrivning av den tillhörande risken</span><span class="sxs-lookup"><span data-stu-id="65ea9-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="65ea9-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-124">string</span></span> | <span data-ttu-id="65ea9-125">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="65ea9-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="65ea9-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-126">string</span></span> |<span data-ttu-id="65ea9-127">Underkategori eller undergruppering som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="65ea9-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="65ea9-128">I många fall beskriver detta specifika funktioner eller funktioner.</span><span class="sxs-lookup"><span data-stu-id="65ea9-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="65ea9-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-129">string</span></span> | <span data-ttu-id="65ea9-130">Lista över branschriktmärken som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="65ea9-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="65ea9-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-131">string</span></span> | <span data-ttu-id="65ea9-132">Lista över Mitre ATT&CK ramtekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="65ea9-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="65ea9-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="65ea9-133">string</span></span> | <span data-ttu-id="65ea9-134">Lista över Mitre ATT&CK ram taktik i samband med konfigurationen</span><span class="sxs-lookup"><span data-stu-id="65ea9-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="65ea9-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65ea9-135">Related topics</span></span>

- [<span data-ttu-id="65ea9-136">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="65ea9-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65ea9-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="65ea9-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65ea9-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="65ea9-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65ea9-139">Jaga hot mellan enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="65ea9-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65ea9-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="65ea9-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65ea9-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="65ea9-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="65ea9-142">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="65ea9-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
