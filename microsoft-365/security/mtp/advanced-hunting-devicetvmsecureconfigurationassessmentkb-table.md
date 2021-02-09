---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av Threat & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade sökschemat.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverk, kunskapsbas, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145457"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="9b1a2-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="9b1a2-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b1a2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9b1a2-105">**Applies to:**</span></span>
- <span data-ttu-id="9b1a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b1a2-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9b1a2-107">Tabellen i det avancerade schemat för sökning innehåller information om de olika säkra konfigurationerna – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="9b1a2-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="9b1a2-108">Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE ATT&CK-tekniker och taktiker.</span><span class="sxs-lookup"><span data-stu-id="9b1a2-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="9b1a2-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="9b1a2-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9b1a2-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9b1a2-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9b1a2-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="9b1a2-111">Column name</span></span> | <span data-ttu-id="9b1a2-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="9b1a2-112">Data type</span></span> | <span data-ttu-id="9b1a2-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b1a2-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="9b1a2-114">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-114">string</span></span> | <span data-ttu-id="9b1a2-115">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="9b1a2-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="9b1a2-116">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-116">string</span></span> | <span data-ttu-id="9b1a2-117">Klassificerad inverkan på konfigurationen till det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="9b1a2-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="9b1a2-118">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-118">string</span></span> | <span data-ttu-id="9b1a2-119">Visningsnamn för konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9b1a2-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="9b1a2-120">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-120">string</span></span> | <span data-ttu-id="9b1a2-121">Beskrivning av konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9b1a2-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="9b1a2-122">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-122">string</span></span> | <span data-ttu-id="9b1a2-123">Beskrivning av den associerade risken</span><span class="sxs-lookup"><span data-stu-id="9b1a2-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="9b1a2-124">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-124">string</span></span> | <span data-ttu-id="9b1a2-125">Kategori eller gruppering som konfigurationen tillhör: Program, OS, nätverk, konton, säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="9b1a2-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="9b1a2-126">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-126">string</span></span> |<span data-ttu-id="9b1a2-127">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="9b1a2-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="9b1a2-128">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="9b1a2-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="9b1a2-129">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-129">string</span></span> | <span data-ttu-id="9b1a2-130">Lista över branschstandarder som rekommenderar samma eller liknande konfiguration</span><span class="sxs-lookup"><span data-stu-id="9b1a2-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="9b1a2-131">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-131">string</span></span> | <span data-ttu-id="9b1a2-132">Etiketter som representerar olika attribut som används för att identifiera eller kategorisera en säkerhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="9b1a2-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="9b1a2-133">sträng</span><span class="sxs-lookup"><span data-stu-id="9b1a2-133">string</span></span> | <span data-ttu-id="9b1a2-134">Rekommenderade åtgärder för att minska eller hantera eventuella associerade risker</span><span class="sxs-lookup"><span data-stu-id="9b1a2-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9b1a2-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9b1a2-135">Related topics</span></span>

- [<span data-ttu-id="9b1a2-136">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="9b1a2-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9b1a2-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="9b1a2-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9b1a2-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="9b1a2-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9b1a2-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="9b1a2-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9b1a2-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="9b1a2-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9b1a2-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="9b1a2-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9b1a2-142">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="9b1a2-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
