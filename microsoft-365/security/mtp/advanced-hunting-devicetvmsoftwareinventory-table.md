---
title: DeviceTvmSoftwareInventory-tabell i det avancerade sökschemat
description: Läs mer om inventeringen av programvara i dina enheter i tabellen DeviceTvmSoftwareInventory i det avancerade sökschemat.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, lager, svagheter, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: maccruz
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5edb6205e0392441163060aa7181ca031e1fbb0d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416844"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="3b708-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="3b708-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3b708-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3b708-105">**Applies to:**</span></span>
- <span data-ttu-id="3b708-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b708-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3b708-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="3b708-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3b708-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="3b708-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="3b708-109">Tabellen i det avancerade utbildningsschemat innehåller & sårbarhetshanteringslager av programvara som för närvarande är installerad på enheter i nätverket, inklusive information om slutet `DeviceTvmSoftwareInventory` på supporten. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="3b708-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="3b708-110">Du kan till exempel jaga händelser som innefattar enheter som installeras med en för närvarande sårbar programvaruversion.</span><span class="sxs-lookup"><span data-stu-id="3b708-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="3b708-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="3b708-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="3b708-112">Tabellerna `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` och tabellerna har ersatt `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="3b708-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="3b708-113">Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av vulnerablity eller för att leta efter sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="3b708-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="3b708-114">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="3b708-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3b708-115">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="3b708-115">Column name</span></span> | <span data-ttu-id="3b708-116">Datatyp</span><span class="sxs-lookup"><span data-stu-id="3b708-116">Data type</span></span> | <span data-ttu-id="3b708-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3b708-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3b708-118">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-118">string</span></span> | <span data-ttu-id="3b708-119">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="3b708-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3b708-120">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-120">string</span></span> | <span data-ttu-id="3b708-121">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="3b708-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="3b708-122">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-122">string</span></span> | <span data-ttu-id="3b708-123">Operativsystemets plattform som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="3b708-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="3b708-124">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="3b708-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="3b708-125">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-125">string</span></span> | <span data-ttu-id="3b708-126">Version av operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="3b708-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="3b708-127">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-127">string</span></span> | <span data-ttu-id="3b708-128">Arkitekturen för operativsystemet som körs på datorn</span><span class="sxs-lookup"><span data-stu-id="3b708-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="3b708-129">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-129">string</span></span> | <span data-ttu-id="3b708-130">Namnet på programvaruleverantören</span><span class="sxs-lookup"><span data-stu-id="3b708-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="3b708-131">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-131">string</span></span> | <span data-ttu-id="3b708-132">Namnet på programvaruprodukten</span><span class="sxs-lookup"><span data-stu-id="3b708-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="3b708-133">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-133">string</span></span> | <span data-ttu-id="3b708-134">Versionsnummer för programvaran</span><span class="sxs-lookup"><span data-stu-id="3b708-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="3b708-135">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-135">string</span></span> | <span data-ttu-id="3b708-136">Visar livscykelfasen för programvaran i förhållande till dess angivna supportdatum (EOS) eller slutdatum (EOL)</span><span class="sxs-lookup"><span data-stu-id="3b708-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="3b708-137">sträng</span><span class="sxs-lookup"><span data-stu-id="3b708-137">string</span></span> | <span data-ttu-id="3b708-138">Supporten för EOS (EOS) eller slutet av livscykeln (EOL) för programvaran</span><span class="sxs-lookup"><span data-stu-id="3b708-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="3b708-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3b708-139">Related topics</span></span>

- [<span data-ttu-id="3b708-140">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="3b708-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3b708-141">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="3b708-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3b708-142">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="3b708-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3b708-143">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="3b708-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3b708-144">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="3b708-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3b708-145">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="3b708-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3b708-146">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="3b708-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)