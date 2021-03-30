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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408629"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="7e6de-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="7e6de-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e6de-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7e6de-105">**Applies to:**</span></span>
- [<span data-ttu-id="7e6de-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e6de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="7e6de-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7e6de-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7e6de-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7e6de-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7e6de-109">Tabellen i det avancerade schemat för sökning innehåller lager för hantering av hot och sårbarhet för programvara som för närvarande är installerad på enheter i nätverket, inklusive information om slutet `DeviceTvmSoftwareInventory` på supporten. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="7e6de-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="7e6de-110">Du kan till exempel leta efter händelser som innefattar enheter som installeras med en för närvarande sårbar programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="7e6de-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="7e6de-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="7e6de-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7e6de-112">DeviceTVMSoftwareInventory innehåller alla program som hot och sårbarhetshantering kunde matcha mot en gemensam plattformsuppräkning (CPE) – oavsett om den är sårbar eller inte.</span><span class="sxs-lookup"><span data-stu-id="7e6de-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="7e6de-113">Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="7e6de-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="7e6de-114">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om sårbarhetshanteringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7e6de-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="7e6de-115">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="7e6de-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="7e6de-116">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="7e6de-116">Column name</span></span> | <span data-ttu-id="7e6de-117">Datatyp</span><span class="sxs-lookup"><span data-stu-id="7e6de-117">Data type</span></span> | <span data-ttu-id="7e6de-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7e6de-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="7e6de-119">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-119">string</span></span> | <span data-ttu-id="7e6de-120">Unikt ID för enheten i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="7e6de-121">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-121">string</span></span> | <span data-ttu-id="7e6de-122">Fullständigt kvalificerat domännamn (FQDN) för enheten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="7e6de-123">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-123">string</span></span> | <span data-ttu-id="7e6de-124">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7e6de-125">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7e6de-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="7e6de-126">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-126">string</span></span> | <span data-ttu-id="7e6de-127">Version av operativsystemet som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="7e6de-128">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-128">string</span></span> | <span data-ttu-id="7e6de-129">Arkitekturen för operativsystemet som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="7e6de-130">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-130">string</span></span> | <span data-ttu-id="7e6de-131">Namnet på programvaruleverantören.</span><span class="sxs-lookup"><span data-stu-id="7e6de-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="7e6de-132">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-132">string</span></span> | <span data-ttu-id="7e6de-133">Namnet på programvaruprodukten.</span><span class="sxs-lookup"><span data-stu-id="7e6de-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="7e6de-134">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-134">string</span></span> | <span data-ttu-id="7e6de-135">Versionsnummer för programvaran.</span><span class="sxs-lookup"><span data-stu-id="7e6de-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="7e6de-136">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-136">string</span></span> | <span data-ttu-id="7e6de-137">Visar livscykelfasen för programvaruprodukten i förhållande till dess angivna datum för support (EOS) eller slutet av livscykeln (EOL).</span><span class="sxs-lookup"><span data-stu-id="7e6de-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="7e6de-138">sträng</span><span class="sxs-lookup"><span data-stu-id="7e6de-138">string</span></span> | <span data-ttu-id="7e6de-139">Supporten (EOS) eller slutet på livscykeln (EOL) för programvaran.</span><span class="sxs-lookup"><span data-stu-id="7e6de-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7e6de-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7e6de-140">Related topics</span></span>

- [<span data-ttu-id="7e6de-141">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7e6de-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e6de-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="7e6de-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7e6de-143">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7e6de-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="7e6de-144">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="7e6de-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
