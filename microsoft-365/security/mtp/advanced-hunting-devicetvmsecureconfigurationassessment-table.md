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
ms.openlocfilehash: 38f5cefb9095ca6c1f628f25a5ed374516c2b0a4
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649007"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="4a521-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="4a521-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="4a521-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4a521-106">**Applies to:**</span></span>
- <span data-ttu-id="4a521-107">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="4a521-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="4a521-108">Varje rad i `DeviceTvmSecureConfigurationAssessment` tabellen innehåller en utvärderings händelse för en viss säkerhets konfiguration från [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="4a521-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="4a521-109">Använd den här referensen för att kontrol lera de senaste utvärderings resultaten och fastställa om enheter är kompatibla.</span><span class="sxs-lookup"><span data-stu-id="4a521-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="4a521-110">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4a521-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4a521-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="4a521-111">Column name</span></span> | <span data-ttu-id="4a521-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="4a521-112">Data type</span></span> | <span data-ttu-id="4a521-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4a521-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="4a521-114">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-114">string</span></span> | <span data-ttu-id="4a521-115">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="4a521-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4a521-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-116">string</span></span> | <span data-ttu-id="4a521-117">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="4a521-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="4a521-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-118">string</span></span> | <span data-ttu-id="4a521-119">Plattformen för det operativ system som körs på datorn.</span><span class="sxs-lookup"><span data-stu-id="4a521-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="4a521-120">Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4a521-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="4a521-121">datetime</span><span class="sxs-lookup"><span data-stu-id="4a521-121">datetime</span></span> | <span data-ttu-id="4a521-122">Datum och tid när posten skapades</span><span class="sxs-lookup"><span data-stu-id="4a521-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="4a521-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-123">string</span></span> | <span data-ttu-id="4a521-124">Unik identifierare för en viss konfiguration</span><span class="sxs-lookup"><span data-stu-id="4a521-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="4a521-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-125">string</span></span> | <span data-ttu-id="4a521-126">Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller</span><span class="sxs-lookup"><span data-stu-id="4a521-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="4a521-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-127">string</span></span> | <span data-ttu-id="4a521-128">Under kategori eller under grupp som konfigurationen tillhör.</span><span class="sxs-lookup"><span data-stu-id="4a521-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="4a521-129">I många fall beskrivs specifika funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="4a521-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="4a521-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="4a521-130">string</span></span> | <span data-ttu-id="4a521-131">Märkeffekt som påverkar konfigurationen till total poängen (1-10)</span><span class="sxs-lookup"><span data-stu-id="4a521-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="4a521-132">returtyp</span><span class="sxs-lookup"><span data-stu-id="4a521-132">boolean</span></span> | <span data-ttu-id="4a521-133">Anger om konfigurationen eller principen är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="4a521-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4a521-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4a521-134">Related topics</span></span>

- [<span data-ttu-id="4a521-135">Har varit inaktivt för hot</span><span class="sxs-lookup"><span data-stu-id="4a521-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4a521-136">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="4a521-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4a521-137">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="4a521-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4a521-138">Olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="4a521-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4a521-139">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="4a521-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4a521-140">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="4a521-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="4a521-141">Översikt över hotet & säkerhets problem hantering</span><span class="sxs-lookup"><span data-stu-id="4a521-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
