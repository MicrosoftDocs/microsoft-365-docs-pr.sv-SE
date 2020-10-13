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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 8c9e886f205a3d1b402b8c39718b6ee49b86a11d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429893"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="a4a49-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="a4a49-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a4a49-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a4a49-106">**Applies to:**</span></span>
- <span data-ttu-id="a4a49-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a4a49-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="a4a49-108">Varje rad i `DeviceTvmSecureConfigurationAssessment` tabellen innehåller en utvärderings händelse för en viss säkerhets konfiguration från [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="a4a49-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="a4a49-109">Använd den här referensen för att kontrol lera de senaste utvärderings resultaten och fastställa om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="a4a49-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="a4a49-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a4a49-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a4a49-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="a4a49-111">Column name</span></span> | <span data-ttu-id="a4a49-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="a4a49-112">Data type</span></span> | <span data-ttu-id="a4a49-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a4a49-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a4a49-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-114">string</span></span> | <span data-ttu-id="a4a49-115">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="a4a49-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a4a49-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-116">string</span></span> | <span data-ttu-id="a4a49-117">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="a4a49-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="a4a49-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-118">string</span></span> | <span data-ttu-id="a4a49-119">Plattformen för det operativ system som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="a4a49-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="a4a49-120">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a4a49-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="a4a49-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a49-121">datetime</span></span> | <span data-ttu-id="a4a49-122">Datum och tid när posten skapades</span><span class="sxs-lookup"><span data-stu-id="a4a49-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="a4a49-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-123">string</span></span> | <span data-ttu-id="a4a49-124">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="a4a49-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="a4a49-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-125">string</span></span> | <span data-ttu-id="a4a49-126">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="a4a49-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="a4a49-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-127">string</span></span> | <span data-ttu-id="a4a49-128">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="a4a49-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="a4a49-129">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="a4a49-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="a4a49-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a4a49-130">string</span></span> | <span data-ttu-id="a4a49-131">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="a4a49-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="a4a49-132">returtyp</span><span class="sxs-lookup"><span data-stu-id="a4a49-132">boolean</span></span> | <span data-ttu-id="a4a49-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="a4a49-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a4a49-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a4a49-134">Related topics</span></span>

- [<span data-ttu-id="a4a49-135">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="a4a49-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a4a49-136">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="a4a49-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a4a49-137">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="a4a49-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a4a49-138">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="a4a49-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a4a49-139">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="a4a49-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a4a49-140">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="a4a49-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a4a49-141">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="a4a49-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
