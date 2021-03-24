---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade sökschemat.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerilitiesKB
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
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070922"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="802e9-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="802e9-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="802e9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="802e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="802e9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="802e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="802e9-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="802e9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="802e9-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="802e9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="802e9-109">Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](next-gen-threat-and-vuln-mgt.md) bedömer enheter för.</span><span class="sxs-lookup"><span data-stu-id="802e9-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="802e9-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="802e9-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="802e9-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="802e9-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="802e9-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="802e9-112">Column name</span></span> | <span data-ttu-id="802e9-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="802e9-113">Data type</span></span> | <span data-ttu-id="802e9-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="802e9-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="802e9-115">sträng</span><span class="sxs-lookup"><span data-stu-id="802e9-115">string</span></span> | <span data-ttu-id="802e9-116">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="802e9-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="802e9-117">sträng</span><span class="sxs-lookup"><span data-stu-id="802e9-117">string</span></span> | <span data-ttu-id="802e9-118">Allvarlighetspoäng som tilldelats säkerhetsrisken under th Common Vulnerability Score System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="802e9-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="802e9-119">boolesk</span><span class="sxs-lookup"><span data-stu-id="802e9-119">boolean</span></span> | <span data-ttu-id="802e9-120">Anger om sårbarhetskod för problemet är offentligt tillgänglig</span><span class="sxs-lookup"><span data-stu-id="802e9-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="802e9-121">sträng</span><span class="sxs-lookup"><span data-stu-id="802e9-121">string</span></span> | <span data-ttu-id="802e9-122">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="802e9-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="802e9-123">datetime</span><span class="sxs-lookup"><span data-stu-id="802e9-123">datetime</span></span> | <span data-ttu-id="802e9-124">Datum och tid då objektet eller relaterade metadata senast ändrades</span><span class="sxs-lookup"><span data-stu-id="802e9-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="802e9-125">datetime</span><span class="sxs-lookup"><span data-stu-id="802e9-125">datetime</span></span> | <span data-ttu-id="802e9-126">Date vulnerability was disclosed to public</span><span class="sxs-lookup"><span data-stu-id="802e9-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="802e9-127">sträng</span><span class="sxs-lookup"><span data-stu-id="802e9-127">string</span></span> | <span data-ttu-id="802e9-128">Beskrivning av sårbarhet och associerade risker</span><span class="sxs-lookup"><span data-stu-id="802e9-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="802e9-129">sträng</span><span class="sxs-lookup"><span data-stu-id="802e9-129">string</span></span> | <span data-ttu-id="802e9-130">Lista över alla programvaruprodukter som påverkas av problemet</span><span class="sxs-lookup"><span data-stu-id="802e9-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="802e9-131">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="802e9-131">Related topics</span></span>

- [<span data-ttu-id="802e9-132">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="802e9-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="802e9-133">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="802e9-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="802e9-134">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="802e9-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="802e9-135">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="802e9-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
