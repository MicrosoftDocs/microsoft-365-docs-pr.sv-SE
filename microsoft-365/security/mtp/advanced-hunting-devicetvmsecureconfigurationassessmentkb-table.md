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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6186bd37735b5225fd33905395055228972fc27c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847590"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="be259-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="be259-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be259-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="be259-105">**Applies to:**</span></span>
- <span data-ttu-id="be259-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be259-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="be259-107">`DeviceTvmSecureConfigurationAssessmentKB`Tabellen i det avancerade jakt-schemat innehåller information om de olika säkra konfigurationerna – till exempel om du har automatiska uppdateringar på en enhet [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)– som det rör sig om att uppdatera data.</span><span class="sxs-lookup"><span data-stu-id="be259-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="be259-108">Det inkluderar också risk information, relaterade bransch benchmarks och tillämpliga MITRE att&CK teknik och taktiker.</span><span class="sxs-lookup"><span data-stu-id="be259-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="be259-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="be259-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="be259-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="be259-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="be259-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="be259-111">Column name</span></span> | <span data-ttu-id="be259-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="be259-112">Data type</span></span> | <span data-ttu-id="be259-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="be259-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="be259-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-114">string</span></span> | <span data-ttu-id="be259-115">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="be259-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="be259-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-116">string</span></span> | <span data-ttu-id="be259-117">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="be259-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="be259-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-118">string</span></span> | <span data-ttu-id="be259-119">Visnings namn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="be259-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="be259-120">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-120">string</span></span> | <span data-ttu-id="be259-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="be259-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="be259-122">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-122">string</span></span> | <span data-ttu-id="be259-123">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="be259-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="be259-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-124">string</span></span> | <span data-ttu-id="be259-125">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="be259-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="be259-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-126">string</span></span> |<span data-ttu-id="be259-127">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="be259-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="be259-128">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="be259-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="be259-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-129">string</span></span> | <span data-ttu-id="be259-130">Lista över riktmärken för branschen rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="be259-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="be259-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-131">string</span></span> | <span data-ttu-id="be259-132">Lista över Mitre att&CK Ramverks tekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="be259-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="be259-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="be259-133">string</span></span> | <span data-ttu-id="be259-134">Lista över Mitre att&CK ramverk taktiker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="be259-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be259-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="be259-135">Related topics</span></span>

- [<span data-ttu-id="be259-136">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="be259-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be259-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="be259-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="be259-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="be259-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="be259-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="be259-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="be259-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="be259-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="be259-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="be259-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="be259-142">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="be259-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
