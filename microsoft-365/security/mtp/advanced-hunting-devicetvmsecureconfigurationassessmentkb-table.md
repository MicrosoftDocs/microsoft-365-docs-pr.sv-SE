---
title: DeviceTvmSecureConfigurationAssessmentKB-tabellen i det avancerade jaktschemat
description: Lär dig mer om de olika säkra konfigurationer som bedömts av Threat & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverk, kunskapsbas, KB, DeviceTvmSecureConfigurationAssesmentKB
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
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327997"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="88f45-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="88f45-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="88f45-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="88f45-105">**Applies to:**</span></span>
- <span data-ttu-id="88f45-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="88f45-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="88f45-107">`DeviceTvmSecureConfigurationAssessmentKB`Tabellen i det avancerade jaktschemat innehåller information om de olika säkra konfigurationerna, till exempel om en enhet har automatiska uppdateringar på , kontrollerad av Hot & [Sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="88f45-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="88f45-108">Den innehåller också riskinformation, relaterade branschriktmärken och tillämpliga MITRE ATT-&CK-tekniker och taktik.</span><span class="sxs-lookup"><span data-stu-id="88f45-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="88f45-109">Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="88f45-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="88f45-110">Information om andra tabeller i det avancerade jaktschemat finns [i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="88f45-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="88f45-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="88f45-111">Column name</span></span> | <span data-ttu-id="88f45-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="88f45-112">Data type</span></span> | <span data-ttu-id="88f45-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="88f45-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="88f45-114">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-114">string</span></span> | <span data-ttu-id="88f45-115">Unik identifierare för en specifik konfiguration</span><span class="sxs-lookup"><span data-stu-id="88f45-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="88f45-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-116">string</span></span> | <span data-ttu-id="88f45-117">Nominell påverkan av konfigurationen till den totala konfigurationspoängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="88f45-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="88f45-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-118">string</span></span> | <span data-ttu-id="88f45-119">Visningsnamnet på konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88f45-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="88f45-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-120">string</span></span> | <span data-ttu-id="88f45-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88f45-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="88f45-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-122">string</span></span> | <span data-ttu-id="88f45-123">Beskrivning av den tillhörande risken</span><span class="sxs-lookup"><span data-stu-id="88f45-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="88f45-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-124">string</span></span> | <span data-ttu-id="88f45-125">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="88f45-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="88f45-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-126">string</span></span> |<span data-ttu-id="88f45-127">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="88f45-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="88f45-128">I många fall beskriver detta specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="88f45-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="88f45-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-129">string</span></span> | <span data-ttu-id="88f45-130">Lista över branschriktmärken som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="88f45-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="88f45-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-131">string</span></span> | <span data-ttu-id="88f45-132">Lista över Mitre ATT&CK-ramtekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88f45-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="88f45-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="88f45-133">string</span></span> | <span data-ttu-id="88f45-134">Lista över Mitre ATT&CK ram taktik i samband med konfigurationen</span><span class="sxs-lookup"><span data-stu-id="88f45-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="88f45-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88f45-135">Related topics</span></span>

- [<span data-ttu-id="88f45-136">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="88f45-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88f45-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="88f45-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88f45-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="88f45-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="88f45-139">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="88f45-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88f45-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="88f45-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="88f45-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="88f45-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="88f45-142">Översikt över hantering av hot & sårbarhet</span><span class="sxs-lookup"><span data-stu-id="88f45-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
