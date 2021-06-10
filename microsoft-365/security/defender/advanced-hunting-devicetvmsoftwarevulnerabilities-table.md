---
title: Tabellen DeviceTvmSoftwareVulnerabilities i det avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet i tabellen DeviceTvmSoftwareVulnerabilities i tabellen advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & hantering av säkerhetsrisker, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023815"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="9e7f3-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="9e7f3-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e7f3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9e7f3-105">**Applies to:**</span></span>
- <span data-ttu-id="9e7f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e7f3-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9e7f3-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e7f3-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9e7f3-108">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9e7f3-109">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9e7f3-110">Tabellen `DeviceTvmSoftwareVulnerabilities` i det avancerade sökschemat innehåller listan över & [sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av säkerhetsproblem i installerade programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="9e7f3-111">Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="9e7f3-112">Du kan till exempel använda den här tabellen för att leta efter händelser som innefattar enheter som har allvarligt säkerhetsproblem med programvaran.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="9e7f3-113">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="9e7f3-114">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="9e7f3-115">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av trådlöst arbete eller för att leta efter sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="9e7f3-116">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9e7f3-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e7f3-117">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="9e7f3-117">Column name</span></span> | <span data-ttu-id="9e7f3-118">Datatyp</span><span class="sxs-lookup"><span data-stu-id="9e7f3-118">Data type</span></span> | <span data-ttu-id="9e7f3-119">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e7f3-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="9e7f3-120">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-120">string</span></span> | <span data-ttu-id="9e7f3-121">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="9e7f3-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9e7f3-122">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-122">string</span></span> | <span data-ttu-id="9e7f3-123">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="9e7f3-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="9e7f3-124">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-124">string</span></span> | <span data-ttu-id="9e7f3-125">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="9e7f3-126">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="9e7f3-127">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-127">string</span></span> | <span data-ttu-id="9e7f3-128">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="9e7f3-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="9e7f3-129">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-129">string</span></span> | <span data-ttu-id="9e7f3-130">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="9e7f3-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="9e7f3-131">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-131">string</span></span> | <span data-ttu-id="9e7f3-132">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="9e7f3-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="9e7f3-133">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-133">string</span></span> | <span data-ttu-id="9e7f3-134">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="9e7f3-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="9e7f3-135">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-135">string</span></span> | <span data-ttu-id="9e7f3-136">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="9e7f3-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="9e7f3-137">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-137">string</span></span> | <span data-ttu-id="9e7f3-138">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="9e7f3-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="9e7f3-139">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-139">string</span></span> | <span data-ttu-id="9e7f3-140">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="9e7f3-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="9e7f3-141">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-141">string</span></span> | <span data-ttu-id="9e7f3-142">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet</span><span class="sxs-lookup"><span data-stu-id="9e7f3-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="9e7f3-143">sträng</span><span class="sxs-lookup"><span data-stu-id="9e7f3-143">string</span></span> | <span data-ttu-id="9e7f3-144">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="9e7f3-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="9e7f3-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9e7f3-145">Related topics</span></span>

- [<span data-ttu-id="9e7f3-146">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="9e7f3-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e7f3-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="9e7f3-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e7f3-148">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="9e7f3-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e7f3-149">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="9e7f3-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e7f3-150">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="9e7f3-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e7f3-151">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="9e7f3-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9e7f3-152">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="9e7f3-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)