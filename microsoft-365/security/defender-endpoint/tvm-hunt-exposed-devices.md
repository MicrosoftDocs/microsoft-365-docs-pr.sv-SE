---
title: Jaga efter exponerade enheter
description: Lär dig hur hantering av hot och hot kan användas för att hjälpa säkerhetsadministratörer, IT-administratörer och SecOps att samarbeta.
keywords: mdatp-tvm-scenarier, mdatp, tvm, tvm-scenarier, minska exponering av hot & sårbarhet, minska hot och sårbarhet, förbättra säkerhetskonfiguration, öka Microsoft Secure Score för enheter, öka hot & sårbarhet Microsoft Secure Score för enheter, Microsoft Secure Score för enheter, exponeringsresultat, säkerhetskontroller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 99e59005bc01a113567e64c921ddcdc1d66785d2
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408297"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Leta efter exponerade enheter – hantering av hot och sårbarhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Använd avancerad sökning för att hitta säkerhetsproblem

Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata. Du kan proaktivt kontrollera händelser i nätverket för att hitta hotindikatorer och enheter. Den flexibla åtkomsten till data gör att du inte behöver hålla efter både kända och potentiella hot. [Läs mer om avancerad sökning](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Schematabeller

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) – Inventering av programvara installerad på enheter, inklusive deras versionsinformation och supportens slutdatum.

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Säkerhetsproblem i programvaran som finns på enheter och listan med tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) – Kunskapsbas för offentligt säkerhetsproblem, inklusive huruvida sårbarhetskod är offentligt tillgänglig.

- [DeviceTvmSecureConfigurationAssessment – utvärderingshändelser](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) för hot och sårbarhetshantering, som anger status för olika säkerhetskonfigurationer på enheter.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) – Kunskapsbas av olika säkerhetskonfigurationer som används av Threat & Vulnerability Management för att utvärdera enheter. inkluderar mappningar till olika standarder och riktvärde

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Kontrollera vilka enheter som ingår i varningar med hög allvarlighetsgrad

1. Gå till **Avancerad sökning** från det vänstra navigeringsfönstret i Microsoft Defender Säkerhetscenter.

2. Rulla ned till TVM:s avancerade sökscheman och bekanta dig med kolumnnamnen.

3. Ange följande frågor:

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

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [API:er](next-gen-threat-and-vuln-mgt.md#apis)
- [Konfigurera dataåtkomst för roller för hantering av hot och problem](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Översikt över avancerad jakt](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Alla avancerade tabeller för sökning](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
