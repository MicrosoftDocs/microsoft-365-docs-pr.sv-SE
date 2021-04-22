---
title: Tabellen DeviceTvmSoftwareVulnerabilities i det avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet i tabellen DeviceTvmSoftwareVulnerabilities i tabellen advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 24da8f556fe9f8a3b8172afe87ea9a87e4522d44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934831"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="5ec25-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="5ec25-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5ec25-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5ec25-105">**Applies to:**</span></span>
- <span data-ttu-id="5ec25-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ec25-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="5ec25-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="5ec25-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5ec25-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="5ec25-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5ec25-109">Tabellen `DeviceTvmSoftwareVulnerabilities` i det avancerade sökschemat innehåller listan över & [sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av säkerhetsproblem i installerade programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="5ec25-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="5ec25-110">Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.</span><span class="sxs-lookup"><span data-stu-id="5ec25-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="5ec25-111">Du kan till exempel använda den här tabellen för att leta efter händelser som innefattar enheter som har allvarligt säkerhetsproblem med programvaran.</span><span class="sxs-lookup"><span data-stu-id="5ec25-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="5ec25-112">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="5ec25-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="5ec25-113">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="5ec25-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="5ec25-114">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av trådlöst arbete eller för att leta efter sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="5ec25-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="5ec25-115">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="5ec25-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5ec25-116">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="5ec25-116">Column name</span></span> | <span data-ttu-id="5ec25-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="5ec25-117">Data type</span></span> | <span data-ttu-id="5ec25-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5ec25-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5ec25-119">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-119">string</span></span> | <span data-ttu-id="5ec25-120">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="5ec25-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5ec25-121">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-121">string</span></span> | <span data-ttu-id="5ec25-122">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="5ec25-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="5ec25-123">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-123">string</span></span> | <span data-ttu-id="5ec25-124">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="5ec25-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="5ec25-125">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5ec25-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="5ec25-126">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-126">string</span></span> | <span data-ttu-id="5ec25-127">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="5ec25-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="5ec25-128">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-128">string</span></span> | <span data-ttu-id="5ec25-129">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="5ec25-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="5ec25-130">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-130">string</span></span> | <span data-ttu-id="5ec25-131">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="5ec25-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="5ec25-132">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-132">string</span></span> | <span data-ttu-id="5ec25-133">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="5ec25-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="5ec25-134">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-134">string</span></span> | <span data-ttu-id="5ec25-135">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="5ec25-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="5ec25-136">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-136">string</span></span> | <span data-ttu-id="5ec25-137">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="5ec25-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="5ec25-138">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-138">string</span></span> | <span data-ttu-id="5ec25-139">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="5ec25-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="5ec25-140">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-140">string</span></span> | <span data-ttu-id="5ec25-141">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet</span><span class="sxs-lookup"><span data-stu-id="5ec25-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="5ec25-142">sträng</span><span class="sxs-lookup"><span data-stu-id="5ec25-142">string</span></span> | <span data-ttu-id="5ec25-143">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="5ec25-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="5ec25-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5ec25-144">Related topics</span></span>

- [<span data-ttu-id="5ec25-145">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="5ec25-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ec25-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="5ec25-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ec25-147">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="5ec25-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5ec25-148">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="5ec25-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5ec25-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="5ec25-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5ec25-150">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="5ec25-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5ec25-151">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="5ec25-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)