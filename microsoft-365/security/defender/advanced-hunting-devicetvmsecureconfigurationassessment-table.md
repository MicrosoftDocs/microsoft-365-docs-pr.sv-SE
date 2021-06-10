---
title: Tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat
description: Läs mer om säkerhetsbedömningshändelser i tabellen DeviceTvmSecureConfigurationAssessment i den avancerade tabellen för sökning. Dessa hot & hantering av säkerhetsrisker tillhandahåller enhetsinformation och information om säkerhetskonfigurationer, påverkan och efterlevnadsinformation.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & hantering av säkerhetsrisker, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024223"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="5fffa-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="5fffa-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fffa-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5fffa-106">**Applies to:**</span></span>
- <span data-ttu-id="5fffa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fffa-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5fffa-108">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fffa-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="5fffa-109">Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från [Threat & Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="5fffa-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5fffa-110">Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="5fffa-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="5fffa-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="5fffa-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5fffa-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="5fffa-112">Column name</span></span> | <span data-ttu-id="5fffa-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="5fffa-113">Data type</span></span> | <span data-ttu-id="5fffa-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5fffa-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5fffa-115">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-115">string</span></span> | <span data-ttu-id="5fffa-116">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="5fffa-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5fffa-117">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-117">string</span></span> | <span data-ttu-id="5fffa-118">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="5fffa-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5fffa-119">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-119">string</span></span> | <span data-ttu-id="5fffa-120">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="5fffa-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5fffa-121">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5fffa-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="5fffa-122">datetime</span><span class="sxs-lookup"><span data-stu-id="5fffa-122">datetime</span></span> | <span data-ttu-id="5fffa-123">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="5fffa-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="5fffa-124">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-124">string</span></span> | <span data-ttu-id="5fffa-125">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="5fffa-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5fffa-126">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-126">string</span></span> | <span data-ttu-id="5fffa-127">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="5fffa-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="5fffa-128">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-128">string</span></span> | <span data-ttu-id="5fffa-129">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="5fffa-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5fffa-130">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="5fffa-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5fffa-131">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-131">string</span></span> | <span data-ttu-id="5fffa-132">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="5fffa-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="5fffa-133">boolesk</span><span class="sxs-lookup"><span data-stu-id="5fffa-133">boolean</span></span> | <span data-ttu-id="5fffa-134">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="5fffa-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="5fffa-135">boolesk</span><span class="sxs-lookup"><span data-stu-id="5fffa-135">boolean</span></span> | <span data-ttu-id="5fffa-136">Anger om konfigurationen eller principen gäller för enheten</span><span class="sxs-lookup"><span data-stu-id="5fffa-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="5fffa-137">sträng</span><span class="sxs-lookup"><span data-stu-id="5fffa-137">string</span></span> | <span data-ttu-id="5fffa-138">Ytterligare sammanhangsberoende information om konfigurationen eller principen</span><span class="sxs-lookup"><span data-stu-id="5fffa-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="5fffa-139">boolesk</span><span class="sxs-lookup"><span data-stu-id="5fffa-139">boolean</span></span> | <span data-ttu-id="5fffa-140">Anger om det kommer att finnas någon påverkan på användaren om konfigurationen eller principen tillämpas</span><span class="sxs-lookup"><span data-stu-id="5fffa-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5fffa-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5fffa-141">Related topics</span></span>

- [<span data-ttu-id="5fffa-142">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="5fffa-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5fffa-143">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="5fffa-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5fffa-144">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="5fffa-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5fffa-145">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="5fffa-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5fffa-146">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="5fffa-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5fffa-147">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="5fffa-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5fffa-148">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="5fffa-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)