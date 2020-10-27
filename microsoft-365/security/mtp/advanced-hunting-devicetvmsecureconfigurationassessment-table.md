---
title: DeviceTvmSecureConfigurationAssessment-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser för säkerhets utvärdering i DeviceTvmSecureConfigurationAssessment-tabellen för Advanced jakt-schemat. De här hotet & säkerhets problem hanterings händelser tillhandahåller enhets information samt information om säkerhets konfiguration, konsekvens och efterlevnad.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, säkerhets konfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770079"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="88727-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="88727-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="88727-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88727-106">**Applies to:**</span></span>
- <span data-ttu-id="88727-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="88727-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="88727-108">Varje rad i `DeviceTvmSecureConfigurationAssessment` tabellen innehåller en utvärderings händelse för en viss säkerhets konfiguration från [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="88727-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="88727-109">Använd den här referensen för att kontrol lera de senaste utvärderings resultaten och fastställa om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="88727-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="88727-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="88727-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="88727-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="88727-111">Column name</span></span> | <span data-ttu-id="88727-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="88727-112">Data type</span></span> | <span data-ttu-id="88727-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="88727-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="88727-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-114">string</span></span> | <span data-ttu-id="88727-115">Unik identifierare för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="88727-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="88727-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-116">string</span></span> | <span data-ttu-id="88727-117">Det fullständigt kvalificerade domän namnet (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="88727-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="88727-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-118">string</span></span> | <span data-ttu-id="88727-119">Plattformen för det operativ system som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="88727-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="88727-120">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="88727-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="88727-121">datetime</span><span class="sxs-lookup"><span data-stu-id="88727-121">datetime</span></span> | <span data-ttu-id="88727-122">Datum och tid när posten skapades</span><span class="sxs-lookup"><span data-stu-id="88727-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="88727-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-123">string</span></span> | <span data-ttu-id="88727-124">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="88727-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="88727-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-125">string</span></span> | <span data-ttu-id="88727-126">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="88727-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="88727-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-127">string</span></span> | <span data-ttu-id="88727-128">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="88727-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="88727-129">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="88727-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="88727-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-130">string</span></span> | <span data-ttu-id="88727-131">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="88727-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="88727-132">returtyp</span><span class="sxs-lookup"><span data-stu-id="88727-132">boolean</span></span> | <span data-ttu-id="88727-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="88727-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="88727-134">returtyp</span><span class="sxs-lookup"><span data-stu-id="88727-134">boolean</span></span> | <span data-ttu-id="88727-135">Anger om konfigurationen eller policyn gäller för enheten</span><span class="sxs-lookup"><span data-stu-id="88727-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="88727-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="88727-136">string</span></span> | <span data-ttu-id="88727-137">Ytterligare information om konfigurationen eller policyn</span><span class="sxs-lookup"><span data-stu-id="88727-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="88727-138">returtyp</span><span class="sxs-lookup"><span data-stu-id="88727-138">boolean</span></span> | <span data-ttu-id="88727-139">Anger om användaren kan påverka om konfigurationen eller principen tillämpas</span><span class="sxs-lookup"><span data-stu-id="88727-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="88727-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88727-140">Related topics</span></span>

- [<span data-ttu-id="88727-141">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="88727-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88727-142">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="88727-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88727-143">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="88727-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="88727-144">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="88727-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="88727-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="88727-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="88727-146">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="88727-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="88727-147">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="88727-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
