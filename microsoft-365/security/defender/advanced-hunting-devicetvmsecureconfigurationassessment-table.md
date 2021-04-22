---
title: Tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat
description: Läs mer om säkerhetsbedömningshändelser i tabellen DeviceTvmSecureConfigurationAssessment i den avancerade tabellen för sökning. Dessa hot & sårbarhetshanteringshändelser tillhandahåller enhetsinformation samt information om säkerhetskonfigurationer, påverkan och efterlevnadsinformation.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: e128eabc43c73949b5c747e51f3b59ac8b9a0ac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933031"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="22086-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="22086-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22086-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="22086-106">**Applies to:**</span></span>
- <span data-ttu-id="22086-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22086-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="22086-108">Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från [Threat & Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="22086-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="22086-109">Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="22086-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="22086-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="22086-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="22086-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="22086-111">Column name</span></span> | <span data-ttu-id="22086-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="22086-112">Data type</span></span> | <span data-ttu-id="22086-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="22086-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="22086-114">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-114">string</span></span> | <span data-ttu-id="22086-115">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="22086-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="22086-116">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-116">string</span></span> | <span data-ttu-id="22086-117">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="22086-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="22086-118">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-118">string</span></span> | <span data-ttu-id="22086-119">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="22086-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="22086-120">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="22086-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="22086-121">datetime</span><span class="sxs-lookup"><span data-stu-id="22086-121">datetime</span></span> | <span data-ttu-id="22086-122">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="22086-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="22086-123">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-123">string</span></span> | <span data-ttu-id="22086-124">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="22086-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="22086-125">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-125">string</span></span> | <span data-ttu-id="22086-126">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="22086-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="22086-127">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-127">string</span></span> | <span data-ttu-id="22086-128">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="22086-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="22086-129">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="22086-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="22086-130">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-130">string</span></span> | <span data-ttu-id="22086-131">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="22086-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="22086-132">boolesk</span><span class="sxs-lookup"><span data-stu-id="22086-132">boolean</span></span> | <span data-ttu-id="22086-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="22086-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="22086-134">boolesk</span><span class="sxs-lookup"><span data-stu-id="22086-134">boolean</span></span> | <span data-ttu-id="22086-135">Anger om konfigurationen eller principen gäller för enheten</span><span class="sxs-lookup"><span data-stu-id="22086-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="22086-136">sträng</span><span class="sxs-lookup"><span data-stu-id="22086-136">string</span></span> | <span data-ttu-id="22086-137">Ytterligare sammanhangsberoende information om konfigurationen eller principen</span><span class="sxs-lookup"><span data-stu-id="22086-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="22086-138">boolesk</span><span class="sxs-lookup"><span data-stu-id="22086-138">boolean</span></span> | <span data-ttu-id="22086-139">Anger om det kommer att finnas någon påverkan på användaren om konfigurationen eller principen tillämpas</span><span class="sxs-lookup"><span data-stu-id="22086-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="22086-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="22086-140">Related topics</span></span>

- [<span data-ttu-id="22086-141">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="22086-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22086-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="22086-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="22086-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="22086-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="22086-144">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="22086-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="22086-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="22086-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="22086-146">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="22086-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="22086-147">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="22086-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)