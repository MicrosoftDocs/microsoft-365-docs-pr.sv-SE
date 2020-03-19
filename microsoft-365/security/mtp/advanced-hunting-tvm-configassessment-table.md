---
title: DeviceTvmSecureConfigurationBedömningstabell i det avancerade jaktschemat
description: Lär dig mer om säkerhetsbedömningshändelser för Hot & sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessment i det avancerade jaktschemat. Dessa händelser ger maskininformation samt information om säkerhetskonfiguration, påverkan och efterlevnad.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811143"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="5bc6b-105">DeviceTvmSecureConfigurationBedömning</span><span class="sxs-lookup"><span data-stu-id="5bc6b-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="5bc6b-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="5bc6b-106">**Applies to:**</span></span>
- <span data-ttu-id="5bc6b-107">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="5bc6b-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="5bc6b-108">Varje rad `DeviceTvmSecureConfigurationAssessment` i tabellen innehåller en utvärderingshändelse för en specifik säkerhetskonfiguration från [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="5bc6b-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5bc6b-109">Använd den här referensen för att kontrollera de senaste bedömningsresultaten och avgöra om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="5bc6b-110">Information om andra tabeller i det avancerade jaktschemat finns i [den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5bc6b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5bc6b-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="5bc6b-111">Column name</span></span> | <span data-ttu-id="5bc6b-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="5bc6b-112">Data type</span></span> | <span data-ttu-id="5bc6b-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5bc6b-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5bc6b-114">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-114">string</span></span> | <span data-ttu-id="5bc6b-115">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="5bc6b-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5bc6b-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-116">string</span></span> | <span data-ttu-id="5bc6b-117">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="5bc6b-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="5bc6b-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-118">string</span></span> | <span data-ttu-id="5bc6b-119">Plattformen för operativsystemet som körs på maskinen.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="5bc6b-120">Detta anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="5bc6b-121">Datetime</span><span class="sxs-lookup"><span data-stu-id="5bc6b-121">datetime</span></span> | <span data-ttu-id="5bc6b-122">Datum och tid då posten genererades</span><span class="sxs-lookup"><span data-stu-id="5bc6b-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="5bc6b-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-123">string</span></span> | <span data-ttu-id="5bc6b-124">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="5bc6b-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5bc6b-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-125">string</span></span> | <span data-ttu-id="5bc6b-126">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="5bc6b-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="5bc6b-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-127">string</span></span> | <span data-ttu-id="5bc6b-128">Underkategori eller undergruppering som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5bc6b-129">I många fall beskriver detta specifika funktioner eller funktioner.</span><span class="sxs-lookup"><span data-stu-id="5bc6b-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5bc6b-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="5bc6b-130">string</span></span> | <span data-ttu-id="5bc6b-131">Nominell effekt av konfigurationen till den totala konfigurationspoängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="5bc6b-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="5bc6b-132">Boolean</span><span class="sxs-lookup"><span data-stu-id="5bc6b-132">boolean</span></span> | <span data-ttu-id="5bc6b-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="5bc6b-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bc6b-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5bc6b-134">Related topics</span></span>

- [<span data-ttu-id="5bc6b-135">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="5bc6b-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5bc6b-136">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="5bc6b-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5bc6b-137">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="5bc6b-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5bc6b-138">Jaga hot mellan enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="5bc6b-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5bc6b-139">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="5bc6b-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5bc6b-140">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="5bc6b-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5bc6b-141">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="5bc6b-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
