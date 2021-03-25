---
title: Tabellen DeviceTvmSoftwareVulnerabilities i det avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet i tabellen DeviceTvmSoftwareVulnerabilities i tabellen advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076034"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="47a2e-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="47a2e-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47a2e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="47a2e-105">**Applies to:**</span></span>
- [<span data-ttu-id="47a2e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="47a2e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="47a2e-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="47a2e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47a2e-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="47a2e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="47a2e-109">Tabellen `DeviceTvmSoftwareVulnerabilities` i det avancerade sökschemat innehåller listan över & [sårbarhetshantering](next-gen-threat-and-vuln-mgt.md) av säkerhetsproblem i installerade programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="47a2e-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="47a2e-110">Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.</span><span class="sxs-lookup"><span data-stu-id="47a2e-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="47a2e-111">Du kan till exempel använda den här tabellen för att leta efter händelser som innefattar enheter som har allvarligt säkerhetsproblem med programvaran.</span><span class="sxs-lookup"><span data-stu-id="47a2e-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="47a2e-112">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="47a2e-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="47a2e-113">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="47a2e-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="47a2e-114">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om sårbarhetshanteringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="47a2e-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="47a2e-115">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="47a2e-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="47a2e-116">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="47a2e-116">Column name</span></span> | <span data-ttu-id="47a2e-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="47a2e-117">Data type</span></span> | <span data-ttu-id="47a2e-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="47a2e-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="47a2e-119">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-119">string</span></span> | <span data-ttu-id="47a2e-120">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="47a2e-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="47a2e-121">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-121">string</span></span> | <span data-ttu-id="47a2e-122">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="47a2e-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="47a2e-123">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-123">string</span></span> | <span data-ttu-id="47a2e-124">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="47a2e-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="47a2e-125">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="47a2e-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="47a2e-126">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-126">string</span></span> | <span data-ttu-id="47a2e-127">Version av operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="47a2e-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="47a2e-128">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-128">string</span></span> | <span data-ttu-id="47a2e-129">Arkitekturen för operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="47a2e-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="47a2e-130">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-130">string</span></span> | <span data-ttu-id="47a2e-131">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="47a2e-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="47a2e-132">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-132">string</span></span> | <span data-ttu-id="47a2e-133">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="47a2e-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="47a2e-134">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-134">string</span></span> | <span data-ttu-id="47a2e-135">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="47a2e-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="47a2e-136">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-136">string</span></span> | <span data-ttu-id="47a2e-137">Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="47a2e-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="47a2e-138">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-138">string</span></span> | <span data-ttu-id="47a2e-139">Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="47a2e-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="47a2e-140">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-140">string</span></span> | <span data-ttu-id="47a2e-141">Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet</span><span class="sxs-lookup"><span data-stu-id="47a2e-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="47a2e-142">sträng</span><span class="sxs-lookup"><span data-stu-id="47a2e-142">string</span></span> | <span data-ttu-id="47a2e-143">Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar</span><span class="sxs-lookup"><span data-stu-id="47a2e-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="47a2e-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="47a2e-144">Related topics</span></span>

- [<span data-ttu-id="47a2e-145">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="47a2e-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="47a2e-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="47a2e-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="47a2e-147">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="47a2e-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="47a2e-148">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="47a2e-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
