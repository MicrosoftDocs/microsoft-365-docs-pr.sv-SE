---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av Threat & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade sökschemat.
keywords: avancerad sökning, hotsökning, sökning på cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverket, kunskapsbas, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 4cd23b8f3ba99b38264b9bf1ba18e8ec2574bab6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931068"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="33bb5-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="33bb5-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="33bb5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="33bb5-105">**Applies to:**</span></span>
- <span data-ttu-id="33bb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33bb5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="33bb5-107">Tabellen i det avancerade schemat för sökning innehåller information om de olika säkra konfigurationerna – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="33bb5-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="33bb5-108">Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE-att-&CK-tekniker och taktiker.</span><span class="sxs-lookup"><span data-stu-id="33bb5-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="33bb5-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="33bb5-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="33bb5-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="33bb5-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="33bb5-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="33bb5-111">Column name</span></span> | <span data-ttu-id="33bb5-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="33bb5-112">Data type</span></span> | <span data-ttu-id="33bb5-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33bb5-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="33bb5-114">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-114">string</span></span> | <span data-ttu-id="33bb5-115">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="33bb5-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="33bb5-116">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-116">string</span></span> | <span data-ttu-id="33bb5-117">Klassificerad inverkan på konfigurationen till det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="33bb5-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="33bb5-118">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-118">string</span></span> | <span data-ttu-id="33bb5-119">Visningsnamn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="33bb5-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="33bb5-120">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-120">string</span></span> | <span data-ttu-id="33bb5-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="33bb5-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="33bb5-122">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-122">string</span></span> | <span data-ttu-id="33bb5-123">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="33bb5-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="33bb5-124">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-124">string</span></span> | <span data-ttu-id="33bb5-125">Kategori eller gruppering som konfigurationen tillhör: Program, OS, nätverk, konton, säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="33bb5-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="33bb5-126">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-126">string</span></span> |<span data-ttu-id="33bb5-127">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="33bb5-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="33bb5-128">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="33bb5-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="33bb5-129">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-129">string</span></span> | <span data-ttu-id="33bb5-130">Lista över branschstandarder som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="33bb5-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="33bb5-131">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-131">string</span></span> | <span data-ttu-id="33bb5-132">Lista över Mitre ATT&CK Framework-tekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="33bb5-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="33bb5-133">sträng</span><span class="sxs-lookup"><span data-stu-id="33bb5-133">string</span></span> | <span data-ttu-id="33bb5-134">Lista över Mitre ATT&CK Framework-taktiker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="33bb5-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="33bb5-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="33bb5-135">Related topics</span></span>

- [<span data-ttu-id="33bb5-136">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="33bb5-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="33bb5-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="33bb5-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="33bb5-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="33bb5-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="33bb5-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="33bb5-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="33bb5-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="33bb5-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="33bb5-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="33bb5-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="33bb5-142">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="33bb5-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
