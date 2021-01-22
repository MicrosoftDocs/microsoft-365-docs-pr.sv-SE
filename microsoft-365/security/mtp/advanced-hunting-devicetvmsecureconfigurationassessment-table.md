---
title: DeviceTvmSecureConfigurationAssessment-tabell i det avancerade sökschemat
description: Läs mer om säkerhetsbedömningshändelser i tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat. Dessa hot & säkerhetshanteringshändelser tillhandahåller enhetsinformation samt information om säkerhetskonfigurationer, påverkan och efterlevnad.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931104"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="af28f-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="af28f-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af28f-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af28f-106">**Applies to:**</span></span>
- <span data-ttu-id="af28f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af28f-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="af28f-108">Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från Hot och [& sårbarhetshantering.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="af28f-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="af28f-109">Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheterna är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="af28f-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="af28f-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="af28f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="af28f-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="af28f-111">Column name</span></span> | <span data-ttu-id="af28f-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="af28f-112">Data type</span></span> | <span data-ttu-id="af28f-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="af28f-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="af28f-114">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-114">string</span></span> | <span data-ttu-id="af28f-115">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="af28f-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="af28f-116">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-116">string</span></span> | <span data-ttu-id="af28f-117">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="af28f-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="af28f-118">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-118">string</span></span> | <span data-ttu-id="af28f-119">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="af28f-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="af28f-120">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="af28f-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="af28f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="af28f-121">datetime</span></span> | <span data-ttu-id="af28f-122">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="af28f-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="af28f-123">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-123">string</span></span> | <span data-ttu-id="af28f-124">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="af28f-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="af28f-125">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-125">string</span></span> | <span data-ttu-id="af28f-126">Kategori eller gruppering som konfigurationen tillhör: Program, OS, nätverk, konton, säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="af28f-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="af28f-127">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-127">string</span></span> | <span data-ttu-id="af28f-128">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="af28f-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="af28f-129">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="af28f-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="af28f-130">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-130">string</span></span> | <span data-ttu-id="af28f-131">Klassificerad inverkan på konfigurationen till det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="af28f-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="af28f-132">boolesk</span><span class="sxs-lookup"><span data-stu-id="af28f-132">boolean</span></span> | <span data-ttu-id="af28f-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="af28f-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="af28f-134">boolesk</span><span class="sxs-lookup"><span data-stu-id="af28f-134">boolean</span></span> | <span data-ttu-id="af28f-135">Anger om konfigurationen eller principen gäller för enheten</span><span class="sxs-lookup"><span data-stu-id="af28f-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="af28f-136">sträng</span><span class="sxs-lookup"><span data-stu-id="af28f-136">string</span></span> | <span data-ttu-id="af28f-137">Ytterligare sammanhangsberoende information om konfigurationen eller principen</span><span class="sxs-lookup"><span data-stu-id="af28f-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="af28f-138">boolesk</span><span class="sxs-lookup"><span data-stu-id="af28f-138">boolean</span></span> | <span data-ttu-id="af28f-139">Anger om det kommer att finnas påverkan på användare om konfigurationen eller principen tillämpas</span><span class="sxs-lookup"><span data-stu-id="af28f-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="af28f-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="af28f-140">Related topics</span></span>

- [<span data-ttu-id="af28f-141">Proaktivt leta efter hot</span><span class="sxs-lookup"><span data-stu-id="af28f-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af28f-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="af28f-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="af28f-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="af28f-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="af28f-144">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="af28f-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="af28f-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="af28f-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="af28f-146">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="af28f-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="af28f-147">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="af28f-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
