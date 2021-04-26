---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i den avancerade tabellen för sökning.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024247"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="70715-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="70715-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="70715-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="70715-105">**Applies to:**</span></span>
- <span data-ttu-id="70715-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70715-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="70715-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="70715-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="70715-108">Tabellen i det avancerade sökschemat innehåller information om olika säkra konfigurationer – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="70715-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="70715-109">Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE ATT-&CK-tekniker och taktiker.</span><span class="sxs-lookup"><span data-stu-id="70715-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="70715-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="70715-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="70715-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="70715-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="70715-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="70715-112">Column name</span></span> | <span data-ttu-id="70715-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="70715-113">Data type</span></span> | <span data-ttu-id="70715-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="70715-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="70715-115">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-115">string</span></span> | <span data-ttu-id="70715-116">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="70715-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="70715-117">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-117">string</span></span> | <span data-ttu-id="70715-118">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="70715-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="70715-119">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-119">string</span></span> | <span data-ttu-id="70715-120">Visningsnamn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="70715-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="70715-121">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-121">string</span></span> | <span data-ttu-id="70715-122">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="70715-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="70715-123">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-123">string</span></span> | <span data-ttu-id="70715-124">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="70715-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="70715-125">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-125">string</span></span> | <span data-ttu-id="70715-126">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="70715-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="70715-127">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-127">string</span></span> |<span data-ttu-id="70715-128">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="70715-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="70715-129">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="70715-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="70715-130">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-130">string</span></span> | <span data-ttu-id="70715-131">Lista med branschstandarder som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="70715-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="70715-132">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-132">string</span></span> | <span data-ttu-id="70715-133">Etiketter som representerar olika attribut som används för att identifiera eller kategorisera en säkerhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="70715-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="70715-134">sträng</span><span class="sxs-lookup"><span data-stu-id="70715-134">string</span></span> | <span data-ttu-id="70715-135">Rekommenderade åtgärder för att minska eller hantera eventuella associerade risker</span><span class="sxs-lookup"><span data-stu-id="70715-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="70715-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="70715-136">Related topics</span></span>

- [<span data-ttu-id="70715-137">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="70715-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="70715-138">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="70715-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="70715-139">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="70715-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="70715-140">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="70715-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="70715-141">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="70715-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="70715-142">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="70715-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="70715-143">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="70715-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)