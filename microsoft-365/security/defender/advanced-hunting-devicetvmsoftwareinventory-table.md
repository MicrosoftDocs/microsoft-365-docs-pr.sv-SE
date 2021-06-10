---
title: DeviceTvmSoftwareInventory-tabell i det avancerade sökschemat
description: Läs mer om lagret av programvara på dina enheter i tabellen DeviceTvmSoftwareInventory i det avancerade schemat för sökning.
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024235"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="12836-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="12836-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="12836-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="12836-105">**Applies to:**</span></span>
- <span data-ttu-id="12836-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12836-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="12836-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="12836-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="12836-108">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="12836-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="12836-109">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="12836-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="12836-110">Tabellen i det avancerade sökschemat innehåller inventeringen av & Sårbarhetshantering för programvara som är installerad på enheter i nätverket, inklusive information om slutet `DeviceTvmSoftwareInventory` på supporten. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="12836-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="12836-111">Du kan till exempel leta efter händelser som innefattar enheter som installeras med en för närvarande sårbar programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="12836-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="12836-112">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="12836-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="12836-113">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="12836-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="12836-114">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av trådlöst arbete eller för att leta efter sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="12836-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="12836-115">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="12836-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="12836-116">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="12836-116">Column name</span></span> | <span data-ttu-id="12836-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="12836-117">Data type</span></span> | <span data-ttu-id="12836-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="12836-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="12836-119">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-119">string</span></span> | <span data-ttu-id="12836-120">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="12836-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="12836-121">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-121">string</span></span> | <span data-ttu-id="12836-122">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="12836-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="12836-123">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-123">string</span></span> | <span data-ttu-id="12836-124">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="12836-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="12836-125">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="12836-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="12836-126">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-126">string</span></span> | <span data-ttu-id="12836-127">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="12836-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="12836-128">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-128">string</span></span> | <span data-ttu-id="12836-129">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="12836-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="12836-130">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-130">string</span></span> | <span data-ttu-id="12836-131">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="12836-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="12836-132">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-132">string</span></span> | <span data-ttu-id="12836-133">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="12836-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="12836-134">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-134">string</span></span> | <span data-ttu-id="12836-135">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="12836-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="12836-136">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-136">string</span></span> | <span data-ttu-id="12836-137">Visar livscykelfasen för programvaruprodukten i förhållande till dess angivna datum för support (EOS) eller slutet av livscykeln (EOL)</span><span class="sxs-lookup"><span data-stu-id="12836-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="12836-138">sträng</span><span class="sxs-lookup"><span data-stu-id="12836-138">string</span></span> | <span data-ttu-id="12836-139">Supportdatum (EOS) eller slutet på livscykeln (EOL) för programvaran</span><span class="sxs-lookup"><span data-stu-id="12836-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="12836-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="12836-140">Related topics</span></span>

- [<span data-ttu-id="12836-141">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="12836-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="12836-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="12836-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="12836-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="12836-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="12836-144">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="12836-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="12836-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="12836-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="12836-146">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="12836-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="12836-147">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="12836-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)