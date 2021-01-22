---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i det avancerade sökschemat
description: Lär dig mer om säkerhetsproblem i programvaran som spåras & sårbarhetshantering i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade utbildningsschemat.
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schema, referens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, lager, svagheter, CVE-ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 00474ac13f88cd9a00ea2ba4a53a6e30ddd664c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931056"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="6ac17-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="6ac17-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ac17-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6ac17-105">**Applies to:**</span></span>
- <span data-ttu-id="6ac17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ac17-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6ac17-107">Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="6ac17-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="6ac17-108">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="6ac17-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6ac17-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6ac17-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6ac17-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6ac17-110">Column name</span></span> | <span data-ttu-id="6ac17-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6ac17-111">Data type</span></span> | <span data-ttu-id="6ac17-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6ac17-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="6ac17-113">sträng</span><span class="sxs-lookup"><span data-stu-id="6ac17-113">string</span></span> | <span data-ttu-id="6ac17-114">Unik identifierare som tilldelats säkerhetsproblemet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="6ac17-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="6ac17-115">sträng</span><span class="sxs-lookup"><span data-stu-id="6ac17-115">string</span></span> | <span data-ttu-id="6ac17-116">Allvarlighetspoäng som tilldelats säkerhetsproblemet under CVSS (Common Vulnerability Risk System)</span><span class="sxs-lookup"><span data-stu-id="6ac17-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="6ac17-117">boolesk</span><span class="sxs-lookup"><span data-stu-id="6ac17-117">boolean</span></span> | <span data-ttu-id="6ac17-118">Anger om sårbarhetskod för problemet är allmänt tillgänglig</span><span class="sxs-lookup"><span data-stu-id="6ac17-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="6ac17-119">sträng</span><span class="sxs-lookup"><span data-stu-id="6ac17-119">string</span></span> | <span data-ttu-id="6ac17-120">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="6ac17-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="6ac17-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6ac17-121">datetime</span></span> | <span data-ttu-id="6ac17-122">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="6ac17-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="6ac17-123">datetime</span><span class="sxs-lookup"><span data-stu-id="6ac17-123">datetime</span></span> | <span data-ttu-id="6ac17-124">Date vulnerability was disclosed to public</span><span class="sxs-lookup"><span data-stu-id="6ac17-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="6ac17-125">sträng</span><span class="sxs-lookup"><span data-stu-id="6ac17-125">string</span></span> | <span data-ttu-id="6ac17-126">Beskrivning av problemet och associerade risker</span><span class="sxs-lookup"><span data-stu-id="6ac17-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="6ac17-127">sträng</span><span class="sxs-lookup"><span data-stu-id="6ac17-127">string</span></span> | <span data-ttu-id="6ac17-128">Lista över alla programvaruprodukter som påverkas av problemet</span><span class="sxs-lookup"><span data-stu-id="6ac17-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6ac17-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6ac17-129">Related topics</span></span>

- [<span data-ttu-id="6ac17-130">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="6ac17-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6ac17-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6ac17-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6ac17-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6ac17-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6ac17-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="6ac17-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6ac17-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6ac17-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6ac17-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6ac17-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6ac17-136">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6ac17-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
