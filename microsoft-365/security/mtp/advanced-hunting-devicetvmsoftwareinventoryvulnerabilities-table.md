---
title: DeviceTvmSoftwareInventoryVulnerabilities-tabellen i den avancerade sökschemat
description: Läs mer om inventeringen av programvaran i dina enheter och deras svagheter i tabellen Förser DeviceTvmSoftwareInventoryVulnerabilities i det avancerade sökschemat.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, lager, svagheter, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931080"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="8a822-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="8a822-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a822-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8a822-105">**Applies to:**</span></span>
- <span data-ttu-id="8a822-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a822-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8a822-107">Tabellen i det avancerade utbildningsschemat innehåller inventeringen av & vulnerability management av programvara på dina enheter samt eventuella kända säkerhetsproblem `DeviceTvmSoftwareInventoryVulnerabilities` i dessa [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) programvaruprodukter.</span><span class="sxs-lookup"><span data-stu-id="8a822-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="8a822-108">Den här tabellen innehåller även information om operativsystem, CVE-ID och information om allvarlighetsgrad för problemet.</span><span class="sxs-lookup"><span data-stu-id="8a822-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="8a822-109">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="8a822-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8a822-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8a822-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a822-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="8a822-111">Column name</span></span> | <span data-ttu-id="8a822-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="8a822-112">Data type</span></span> | <span data-ttu-id="8a822-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8a822-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="8a822-114">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-114">string</span></span> | <span data-ttu-id="8a822-115">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="8a822-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8a822-116">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-116">string</span></span> | <span data-ttu-id="8a822-117">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="8a822-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8a822-118">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-118">string</span></span> | <span data-ttu-id="8a822-119">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="8a822-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8a822-120">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8a822-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="8a822-121">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-121">string</span></span> | <span data-ttu-id="8a822-122">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="8a822-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="8a822-123">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-123">string</span></span> | <span data-ttu-id="8a822-124">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="8a822-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="8a822-125">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-125">string</span></span> | <span data-ttu-id="8a822-126">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="8a822-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="8a822-127">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-127">string</span></span> | <span data-ttu-id="8a822-128">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="8a822-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="8a822-129">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-129">string</span></span> | <span data-ttu-id="8a822-130">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="8a822-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="8a822-131">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-131">string</span></span> | <span data-ttu-id="8a822-132">Unik identifierare som tilldelats säkerhetsproblemet under systemet för vanliga säkerhetsproblem och exponeringar (CVE)</span><span class="sxs-lookup"><span data-stu-id="8a822-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="8a822-133">sträng</span><span class="sxs-lookup"><span data-stu-id="8a822-133">string</span></span> | <span data-ttu-id="8a822-134">Allvarlighetsnivå tilldelad till säkerhetsbristen baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden</span><span class="sxs-lookup"><span data-stu-id="8a822-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="8a822-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8a822-135">Related topics</span></span>

- [<span data-ttu-id="8a822-136">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="8a822-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a822-137">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="8a822-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a822-138">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="8a822-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a822-139">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="8a822-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a822-140">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8a822-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a822-141">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="8a822-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8a822-142">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="8a822-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
