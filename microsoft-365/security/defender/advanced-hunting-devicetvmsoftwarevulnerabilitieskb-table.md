---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade sökschemat.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & hantering av säkerhetsrisker, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023803"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="88041-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="88041-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="88041-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88041-105">**Applies to:**</span></span>
- <span data-ttu-id="88041-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88041-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="88041-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="88041-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="88041-108">Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="88041-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="88041-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="88041-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="88041-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="88041-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="88041-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="88041-111">Column name</span></span> | <span data-ttu-id="88041-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="88041-112">Data type</span></span> | <span data-ttu-id="88041-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="88041-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="88041-114">sträng</span><span class="sxs-lookup"><span data-stu-id="88041-114">string</span></span> | <span data-ttu-id="88041-115">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="88041-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="88041-116">sträng</span><span class="sxs-lookup"><span data-stu-id="88041-116">string</span></span> | <span data-ttu-id="88041-117">Allvarlighetspoäng som tilldelats säkerhetsrisken under th Common Vulnerability Score System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="88041-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="88041-118">boolesk</span><span class="sxs-lookup"><span data-stu-id="88041-118">boolean</span></span> | <span data-ttu-id="88041-119">Anger om sårbarhetskod för problemet är offentligt tillgänglig</span><span class="sxs-lookup"><span data-stu-id="88041-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="88041-120">sträng</span><span class="sxs-lookup"><span data-stu-id="88041-120">string</span></span> | <span data-ttu-id="88041-121">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="88041-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="88041-122">datetime</span><span class="sxs-lookup"><span data-stu-id="88041-122">datetime</span></span> | <span data-ttu-id="88041-123">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="88041-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="88041-124">datetime</span><span class="sxs-lookup"><span data-stu-id="88041-124">datetime</span></span> | <span data-ttu-id="88041-125">Date vulnerability was disclosed to public</span><span class="sxs-lookup"><span data-stu-id="88041-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="88041-126">sträng</span><span class="sxs-lookup"><span data-stu-id="88041-126">string</span></span> | <span data-ttu-id="88041-127">Beskrivning av sårbarhet och associerade risker</span><span class="sxs-lookup"><span data-stu-id="88041-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="88041-128">sträng</span><span class="sxs-lookup"><span data-stu-id="88041-128">string</span></span> | <span data-ttu-id="88041-129">Lista över alla programvaruprodukter som påverkas av problemet</span><span class="sxs-lookup"><span data-stu-id="88041-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="88041-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88041-130">Related topics</span></span>

- [<span data-ttu-id="88041-131">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="88041-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88041-132">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="88041-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88041-133">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="88041-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="88041-134">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="88041-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88041-135">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="88041-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="88041-136">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="88041-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="88041-137">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="88041-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)