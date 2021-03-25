---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i tabellen Advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075042"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="e6bb8-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="e6bb8-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6bb8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e6bb8-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6bb8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6bb8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="e6bb8-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e6bb8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e6bb8-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e6bb8-109">Tabellen i det avancerade sökschemat innehåller information om olika säkra konfigurationer – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="e6bb8-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="e6bb8-110">Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE ATT-&CK-tekniker och taktiker.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="e6bb8-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e6bb8-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="e6bb8-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="e6bb8-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="e6bb8-113">Column name</span></span> | <span data-ttu-id="e6bb8-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e6bb8-114">Data type</span></span> | <span data-ttu-id="e6bb8-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6bb8-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="e6bb8-116">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-116">string</span></span> | <span data-ttu-id="e6bb8-117">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="e6bb8-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e6bb8-118">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-118">string</span></span> | <span data-ttu-id="e6bb8-119">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="e6bb8-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="e6bb8-120">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-120">string</span></span> | <span data-ttu-id="e6bb8-121">Visningsnamn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="e6bb8-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="e6bb8-122">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-122">string</span></span> | <span data-ttu-id="e6bb8-123">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="e6bb8-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="e6bb8-124">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-124">string</span></span> | <span data-ttu-id="e6bb8-125">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="e6bb8-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e6bb8-126">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-126">string</span></span> | <span data-ttu-id="e6bb8-127">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="e6bb8-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="e6bb8-128">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-128">string</span></span> |<span data-ttu-id="e6bb8-129">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e6bb8-130">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="e6bb8-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="e6bb8-131">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-131">string</span></span> | <span data-ttu-id="e6bb8-132">Lista med branschstandarder som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="e6bb8-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="e6bb8-133">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-133">string</span></span> | <span data-ttu-id="e6bb8-134">Lista över Mitre ATT&CK Framework-tekniker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="e6bb8-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="e6bb8-135">sträng</span><span class="sxs-lookup"><span data-stu-id="e6bb8-135">string</span></span> | <span data-ttu-id="e6bb8-136">Lista över Mitre ATT&CK framework-taktiker relaterade till konfigurationen</span><span class="sxs-lookup"><span data-stu-id="e6bb8-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e6bb8-137">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e6bb8-137">Related topics</span></span>

- [<span data-ttu-id="e6bb8-138">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e6bb8-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e6bb8-139">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="e6bb8-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e6bb8-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="e6bb8-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e6bb8-141">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="e6bb8-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
