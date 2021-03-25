---
title: DeviceTvmSoftwareInventory-tabell i det avancerade sökschemat
description: Läs mer om lagret av programvara på dina enheter i tabellen DeviceTvmSoftwareInventory i det avancerade schemat för sökning.
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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075545"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="2588b-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="2588b-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2588b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2588b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2588b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2588b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="2588b-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2588b-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2588b-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2588b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2588b-109">Tabellen i det avancerade sökschemat innehåller inventeringen av & Sårbarhetshantering för programvara som är installerad på enheter i nätverket, inklusive information om slutet `DeviceTvmSoftwareInventory` på supporten. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="2588b-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="2588b-110">Du kan till exempel leta efter händelser som innefattar enheter som installeras med en för närvarande sårbar programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="2588b-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="2588b-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="2588b-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="2588b-112">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="2588b-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="2588b-113">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om sårbarhetshanteringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="2588b-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="2588b-114">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="2588b-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="2588b-115">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="2588b-115">Column name</span></span> | <span data-ttu-id="2588b-116">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2588b-116">Data type</span></span> | <span data-ttu-id="2588b-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2588b-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2588b-118">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-118">string</span></span> | <span data-ttu-id="2588b-119">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="2588b-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2588b-120">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-120">string</span></span> | <span data-ttu-id="2588b-121">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="2588b-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="2588b-122">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-122">string</span></span> | <span data-ttu-id="2588b-123">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="2588b-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2588b-124">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2588b-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="2588b-125">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-125">string</span></span> | <span data-ttu-id="2588b-126">Version av operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="2588b-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="2588b-127">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-127">string</span></span> | <span data-ttu-id="2588b-128">Arkitekturen för operativsystemet som körs på enheten</span><span class="sxs-lookup"><span data-stu-id="2588b-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="2588b-129">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-129">string</span></span> | <span data-ttu-id="2588b-130">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="2588b-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="2588b-131">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-131">string</span></span> | <span data-ttu-id="2588b-132">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="2588b-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="2588b-133">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-133">string</span></span> | <span data-ttu-id="2588b-134">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="2588b-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="2588b-135">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-135">string</span></span> | <span data-ttu-id="2588b-136">Visar livscykelfasen för programvaruprodukten i förhållande till dess angivna datum för support (EOS) eller slutet av livscykeln (EOL)</span><span class="sxs-lookup"><span data-stu-id="2588b-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="2588b-137">sträng</span><span class="sxs-lookup"><span data-stu-id="2588b-137">string</span></span> | <span data-ttu-id="2588b-138">Supportdatum (EOS) eller slutet på livscykeln (EOL) för programvaran</span><span class="sxs-lookup"><span data-stu-id="2588b-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="2588b-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2588b-139">Related topics</span></span>

- [<span data-ttu-id="2588b-140">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="2588b-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2588b-141">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="2588b-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2588b-142">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="2588b-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2588b-143">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="2588b-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

