---
title: DeviceTvmSecureConfigurationAssessment-tabell i det avancerade jakt-schemat
description: Lär dig mer om hot & sårbarhet hantera händelser för säkerhets utvärdering i DeviceTvmSecureConfigurationAssessment-tabellen för det avancerade jakt schemat. De här händelserna innehåller dator information och information om säkerhets konfiguration, konsekvens och efterlevnad.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b186574cfc1307dfd8a01f7a77ef60bf91f4b162
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197003"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="c8456-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="c8456-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8456-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c8456-106">**Applies to:**</span></span>
- <span data-ttu-id="c8456-107">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c8456-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="c8456-108">Varje rad i `DeviceTvmSecureConfigurationAssessment` tabellen innehåller en utvärderings händelse för en viss säkerhets konfiguration från [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="c8456-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="c8456-109">Använd den här referensen för att kontrol lera de senaste utvärderings resultaten och fastställa om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="c8456-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="c8456-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c8456-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c8456-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="c8456-111">Column name</span></span> | <span data-ttu-id="c8456-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="c8456-112">Data type</span></span> | <span data-ttu-id="c8456-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c8456-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c8456-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-114">string</span></span> | <span data-ttu-id="c8456-115">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="c8456-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c8456-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-116">string</span></span> | <span data-ttu-id="c8456-117">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="c8456-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c8456-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-118">string</span></span> | <span data-ttu-id="c8456-119">Plattformen för det operativ system som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="c8456-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c8456-120">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c8456-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="c8456-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c8456-121">datetime</span></span> | <span data-ttu-id="c8456-122">Datum och tid när posten skapades</span><span class="sxs-lookup"><span data-stu-id="c8456-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="c8456-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-123">string</span></span> | <span data-ttu-id="c8456-124">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="c8456-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="c8456-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-125">string</span></span> | <span data-ttu-id="c8456-126">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="c8456-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="c8456-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-127">string</span></span> | <span data-ttu-id="c8456-128">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="c8456-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="c8456-129">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="c8456-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="c8456-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c8456-130">string</span></span> | <span data-ttu-id="c8456-131">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="c8456-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="c8456-132">returtyp</span><span class="sxs-lookup"><span data-stu-id="c8456-132">boolean</span></span> | <span data-ttu-id="c8456-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="c8456-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c8456-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c8456-134">Related topics</span></span>

- [<span data-ttu-id="c8456-135">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="c8456-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c8456-136">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c8456-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c8456-137">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="c8456-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c8456-138">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="c8456-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c8456-139">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c8456-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c8456-140">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c8456-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c8456-141">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="c8456-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
