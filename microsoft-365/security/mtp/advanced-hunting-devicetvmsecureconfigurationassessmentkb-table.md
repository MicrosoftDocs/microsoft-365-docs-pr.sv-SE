---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i det avancerade jakt-schemat
description: Lär dig mer om de olika säkra konfigurationerna bedömda av hotet & säkerhets problem hantering i tabellen DeviceTvmSecureConfigurationAssessmentKB för Advanced jakt-schemat.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, säkerhets konfiguration, MITRE att&CK ramverk, kunskaps bas, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 2c16929555b3923086e249db61cebb3cf7af17c8
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648971"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="95d4d-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="95d4d-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="95d4d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="95d4d-105">**Applies to:**</span></span>
- <span data-ttu-id="95d4d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="95d4d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="95d4d-107">`DeviceTvmSecureConfigurationAssessmentKB`Tabellen i det avancerade jakt-schemat innehåller information om de olika säkra konfigurationerna – till exempel om du har automatiska uppdateringar på en enhet [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)– som det rör sig om att uppdatera data.</span><span class="sxs-lookup"><span data-stu-id="95d4d-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="95d4d-108">Det inkluderar också risk information, relaterade bransch benchmarks och tillämpliga MITRE att&CK teknik och taktiker.</span><span class="sxs-lookup"><span data-stu-id="95d4d-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="95d4d-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="95d4d-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="95d4d-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="95d4d-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="95d4d-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="95d4d-111">Column name</span></span> | <span data-ttu-id="95d4d-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="95d4d-112">Data type</span></span> | <span data-ttu-id="95d4d-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="95d4d-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="95d4d-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-114">string</span></span> | <span data-ttu-id="95d4d-115">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="95d4d-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="95d4d-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-116">string</span></span> | <span data-ttu-id="95d4d-117">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="95d4d-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="95d4d-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-118">string</span></span> | <span data-ttu-id="95d4d-119">Visnings namn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="95d4d-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="95d4d-120">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-120">string</span></span> | <span data-ttu-id="95d4d-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="95d4d-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="95d4d-122">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-122">string</span></span> | <span data-ttu-id="95d4d-123">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="95d4d-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="95d4d-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-124">string</span></span> | <span data-ttu-id="95d4d-125">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="95d4d-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="95d4d-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-126">string</span></span> |<span data-ttu-id="95d4d-127">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="95d4d-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="95d4d-128">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="95d4d-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="95d4d-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-129">string</span></span> | <span data-ttu-id="95d4d-130">Lista över riktmärken för branschen rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="95d4d-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="95d4d-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-131">string</span></span> | <span data-ttu-id="95d4d-132">Lista över Mitre att&CK Ramverks tekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="95d4d-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="95d4d-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="95d4d-133">string</span></span> | <span data-ttu-id="95d4d-134">Lista över Mitre att&CK ramverk taktiker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="95d4d-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="95d4d-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="95d4d-135">Related topics</span></span>

- [<span data-ttu-id="95d4d-136">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="95d4d-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="95d4d-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="95d4d-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="95d4d-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="95d4d-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="95d4d-139">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="95d4d-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="95d4d-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="95d4d-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="95d4d-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="95d4d-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="95d4d-142">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="95d4d-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
