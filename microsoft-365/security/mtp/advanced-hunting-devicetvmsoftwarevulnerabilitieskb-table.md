---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabell i det avancerade jakt-schemat
description: Lär dig mer om de program varu problem som spåras av hotet & säkerhets problem hantering i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade antivirus programmet.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, program vara, inventering, sårbarhet, CVE-ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2255751eb98dd0cc80c1cb690b2d521af7e8d3ed
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412988"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="30e4f-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="30e4f-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30e4f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="30e4f-105">**Applies to:**</span></span>
- <span data-ttu-id="30e4f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="30e4f-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="30e4f-107">`DeviceTvmSoftwareVulnerabilitiesKB`Tabellen i det avancerade jakt schema innehåller en lista över sårbarhets [& sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="30e4f-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="30e4f-108">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="30e4f-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="30e4f-109">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="30e4f-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="30e4f-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="30e4f-110">Column name</span></span> | <span data-ttu-id="30e4f-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="30e4f-111">Data type</span></span> | <span data-ttu-id="30e4f-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="30e4f-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="30e4f-113">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="30e4f-113">string</span></span> | <span data-ttu-id="30e4f-114">Unik identifierare tilldelad säkerhets luckan under de allmänna sårbarheterna och exponeringarna (CVE)</span><span class="sxs-lookup"><span data-stu-id="30e4f-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="30e4f-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="30e4f-115">string</span></span> | <span data-ttu-id="30e4f-116">Allvarlighets grad tilldelad det säkerhets problem som är kopplat till det vanliga säkerhets problemet (CVSS)</span><span class="sxs-lookup"><span data-stu-id="30e4f-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="30e4f-117">returtyp</span><span class="sxs-lookup"><span data-stu-id="30e4f-117">boolean</span></span> | <span data-ttu-id="30e4f-118">Anger om en skadlig kod för problemet är allmänt tillgänglig</span><span class="sxs-lookup"><span data-stu-id="30e4f-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="30e4f-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="30e4f-119">string</span></span> | <span data-ttu-id="30e4f-120">Allvarlighets grad tilldelad säkerhets luckan baserat på CVSS Poäng och dynamiska faktorer som påverkas av hotets liggande</span><span class="sxs-lookup"><span data-stu-id="30e4f-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="30e4f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="30e4f-121">datetime</span></span> | <span data-ttu-id="30e4f-122">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="30e4f-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="30e4f-123">datetime</span><span class="sxs-lookup"><span data-stu-id="30e4f-123">datetime</span></span> | <span data-ttu-id="30e4f-124">Datum då säkerhets luckan skickades till offentlig</span><span class="sxs-lookup"><span data-stu-id="30e4f-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="30e4f-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="30e4f-125">string</span></span> | <span data-ttu-id="30e4f-126">Beskrivning av säkerhets problem och associerade risker</span><span class="sxs-lookup"><span data-stu-id="30e4f-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="30e4f-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="30e4f-127">string</span></span> | <span data-ttu-id="30e4f-128">Lista över alla program varu produkter som påverkas av problemet</span><span class="sxs-lookup"><span data-stu-id="30e4f-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="30e4f-129">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="30e4f-129">Related topics</span></span>

- [<span data-ttu-id="30e4f-130">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="30e4f-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="30e4f-131">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="30e4f-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="30e4f-132">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="30e4f-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="30e4f-133">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="30e4f-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="30e4f-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="30e4f-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="30e4f-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="30e4f-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="30e4f-136">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="30e4f-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
