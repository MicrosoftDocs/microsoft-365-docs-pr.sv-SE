---
title: Jaga efter exponerade enheter
description: Lär dig hur hantering av hot och hot kan användas för att hjälpa säkerhetsadministratörer, IT-administratörer och SecOps att samarbeta.
keywords: Microsoft Defender för Endpoint-tvm-scenarier, Microsoft Defender för slutpunkt, tvm, tvm-scenarier, minska exponering av hot & sårbarhet, minska hot och sårbarhet, förbättra säkerhetskonfiguration, öka Microsoft Secure Score för enheter, öka hot & sårbarhet Microsoft Secure Score för enheter, Microsoft Secure Score för enheter, exponeringsresultat, säkerhetskontroller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934099"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="177c4-104">Leta efter exponerade enheter – hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="177c4-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="177c4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="177c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="177c4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="177c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="177c4-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="177c4-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="177c4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="177c4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="177c4-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="177c4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="177c4-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="177c4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="177c4-111">Använd avancerad sökning för att hitta säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="177c4-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="177c4-112">Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata.</span><span class="sxs-lookup"><span data-stu-id="177c4-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="177c4-113">Du kan proaktivt kontrollera händelser i nätverket för att hitta hotindikatorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="177c4-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="177c4-114">Den flexibla åtkomsten till data gör att du inte behöver hålla efter både kända och potentiella hot.</span><span class="sxs-lookup"><span data-stu-id="177c4-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="177c4-115">Läs mer om avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="177c4-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="177c4-116">Schematabeller</span><span class="sxs-lookup"><span data-stu-id="177c4-116">Schema tables</span></span>

- <span data-ttu-id="177c4-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) – Inventering av programvara installerad på enheter, inklusive deras versionsinformation och supportens slutdatum.</span><span class="sxs-lookup"><span data-stu-id="177c4-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="177c4-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Säkerhetsproblem i programvaran som finns på enheter och listan med tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet.</span><span class="sxs-lookup"><span data-stu-id="177c4-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="177c4-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) – Kunskapsbas för offentligt säkerhetsproblem, inklusive huruvida sårbarhetskod är offentligt tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="177c4-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="177c4-120">[DeviceTvmSecureConfigurationAssessment – utvärderingshändelser](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) för hot och sårbarhetshantering, som anger status för olika säkerhetskonfigurationer på enheter.</span><span class="sxs-lookup"><span data-stu-id="177c4-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="177c4-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) – Kunskapsbas av olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att utvärdera enheter. inkluderar mappningar till olika standarder och riktvärde</span><span class="sxs-lookup"><span data-stu-id="177c4-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="177c4-122">Kontrollera vilka enheter som ingår i varningar med hög allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="177c4-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="177c4-123">Gå till **Avancerad sökning** från det vänstra navigeringsfönstret i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="177c4-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="177c4-124">Rulla ned till TVM:s avancerade sökscheman och bekanta dig med kolumnnamnen.</span><span class="sxs-lookup"><span data-stu-id="177c4-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="177c4-125">Ange följande frågor:</span><span class="sxs-lookup"><span data-stu-id="177c4-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="177c4-126">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="177c4-126">Related topics</span></span>

- [<span data-ttu-id="177c4-127">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="177c4-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="177c4-128">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="177c4-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="177c4-129">API:er</span><span class="sxs-lookup"><span data-stu-id="177c4-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="177c4-130">Konfigurera dataåtkomst för roller för hantering av hot och problem</span><span class="sxs-lookup"><span data-stu-id="177c4-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="177c4-131">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="177c4-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="177c4-132">Alla avancerade tabeller för sökning</span><span class="sxs-lookup"><span data-stu-id="177c4-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
