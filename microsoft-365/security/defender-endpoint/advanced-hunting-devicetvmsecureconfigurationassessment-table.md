---
title: Tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat
description: Lär dig mer & om säkerhetsutvärderingshändelser för sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessment i tabellen Advanced hunting schema. Dessa händelser ger enhetsinformation och information om säkerhetskonfigurationer, påverkan och efterlevnadsinformation.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075049"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="e4e21-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="e4e21-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4e21-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e4e21-106">**Applies to:**</span></span>
- [<span data-ttu-id="e4e21-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4e21-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="e4e21-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e4e21-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e4e21-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e4e21-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e4e21-110">Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från [Threat & Vulnerability Management.](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="e4e21-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="e4e21-111">Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="e4e21-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="e4e21-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="e4e21-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="e4e21-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="e4e21-113">Column name</span></span> | <span data-ttu-id="e4e21-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="e4e21-114">Data type</span></span> | <span data-ttu-id="e4e21-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e4e21-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e4e21-116">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-116">string</span></span> | <span data-ttu-id="e4e21-117">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="e4e21-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e4e21-118">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-118">string</span></span> | <span data-ttu-id="e4e21-119">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="e4e21-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="e4e21-120">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-120">string</span></span> | <span data-ttu-id="e4e21-121">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="e4e21-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e4e21-122">Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e4e21-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="e4e21-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e4e21-123">datetime</span></span> |<span data-ttu-id="e4e21-124">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="e4e21-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="e4e21-125">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-125">string</span></span> | <span data-ttu-id="e4e21-126">Unikt ID för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="e4e21-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e4e21-127">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-127">string</span></span> | <span data-ttu-id="e4e21-128">Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller</span><span class="sxs-lookup"><span data-stu-id="e4e21-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="e4e21-129">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-129">string</span></span> |<span data-ttu-id="e4e21-130">Underkategori eller undergrupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="e4e21-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e4e21-131">I många fall beskrivs specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="e4e21-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e4e21-132">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-132">string</span></span> | <span data-ttu-id="e4e21-133">Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10)</span><span class="sxs-lookup"><span data-stu-id="e4e21-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="e4e21-134">boolesk</span><span class="sxs-lookup"><span data-stu-id="e4e21-134">boolean</span></span> | <span data-ttu-id="e4e21-135">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="e4e21-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="e4e21-136">boolesk</span><span class="sxs-lookup"><span data-stu-id="e4e21-136">boolean</span></span> | <span data-ttu-id="e4e21-137">Anger om konfigurationen eller principen gäller för enheten</span><span class="sxs-lookup"><span data-stu-id="e4e21-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="e4e21-138">sträng</span><span class="sxs-lookup"><span data-stu-id="e4e21-138">string</span></span> | <span data-ttu-id="e4e21-139">Ytterligare sammanhangsberoende information om konfigurationen eller principen</span><span class="sxs-lookup"><span data-stu-id="e4e21-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="e4e21-140">boolesk</span><span class="sxs-lookup"><span data-stu-id="e4e21-140">boolean</span></span> | <span data-ttu-id="e4e21-141">Anger om det kommer att finnas någon påverkan på användaren om konfigurationen eller principen tillämpas</span><span class="sxs-lookup"><span data-stu-id="e4e21-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e4e21-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e4e21-142">Related topics</span></span>

- [<span data-ttu-id="e4e21-143">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="e4e21-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e4e21-144">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="e4e21-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4e21-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="e4e21-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e4e21-146">Översikt över hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="e4e21-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)