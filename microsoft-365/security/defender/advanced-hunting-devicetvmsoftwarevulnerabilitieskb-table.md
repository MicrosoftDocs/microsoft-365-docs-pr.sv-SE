---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade sökschemat.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, datatyp, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 4b5d11788f0914749edaa58b927ef6d4bcc1a3f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498940"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="6ecec-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="6ecec-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ecec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6ecec-105">**Applies to:**</span></span>
- <span data-ttu-id="6ecec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ecec-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6ecec-107">Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="6ecec-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="6ecec-108">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="6ecec-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6ecec-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6ecec-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6ecec-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6ecec-110">Column name</span></span> | <span data-ttu-id="6ecec-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6ecec-111">Data type</span></span> | <span data-ttu-id="6ecec-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6ecec-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="6ecec-113">sträng</span><span class="sxs-lookup"><span data-stu-id="6ecec-113">string</span></span> | <span data-ttu-id="6ecec-114">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="6ecec-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="6ecec-115">sträng</span><span class="sxs-lookup"><span data-stu-id="6ecec-115">string</span></span> | <span data-ttu-id="6ecec-116">Allvarlighetspoäng som tilldelats säkerhetsrisken under th Common Vulnerability Score System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="6ecec-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="6ecec-117">boolesk</span><span class="sxs-lookup"><span data-stu-id="6ecec-117">boolean</span></span> | <span data-ttu-id="6ecec-118">Anger om sårbarhetskod för problemet är offentligt tillgänglig</span><span class="sxs-lookup"><span data-stu-id="6ecec-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="6ecec-119">sträng</span><span class="sxs-lookup"><span data-stu-id="6ecec-119">string</span></span> | <span data-ttu-id="6ecec-120">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="6ecec-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="6ecec-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6ecec-121">datetime</span></span> | <span data-ttu-id="6ecec-122">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="6ecec-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="6ecec-123">datetime</span><span class="sxs-lookup"><span data-stu-id="6ecec-123">datetime</span></span> | <span data-ttu-id="6ecec-124">Date vulnerability was disclosed to public</span><span class="sxs-lookup"><span data-stu-id="6ecec-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="6ecec-125">sträng</span><span class="sxs-lookup"><span data-stu-id="6ecec-125">string</span></span> | <span data-ttu-id="6ecec-126">Beskrivning av sårbarhet och associerade risker</span><span class="sxs-lookup"><span data-stu-id="6ecec-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="6ecec-127">sträng</span><span class="sxs-lookup"><span data-stu-id="6ecec-127">string</span></span> | <span data-ttu-id="6ecec-128">Lista över alla programvaruprodukter som påverkas av problemet</span><span class="sxs-lookup"><span data-stu-id="6ecec-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6ecec-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6ecec-129">Related topics</span></span>

- [<span data-ttu-id="6ecec-130">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="6ecec-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6ecec-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6ecec-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6ecec-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6ecec-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6ecec-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="6ecec-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6ecec-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6ecec-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6ecec-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6ecec-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6ecec-136">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6ecec-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)