---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabell i det avancerade jakt-schemat
description: Lär dig mer om de program varu problem som spåras av hotet & säkerhets problem hantering i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade antivirus programmet.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, program vara, inventering, sårbarhet, CVE-ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: b7ec1a314875327bee6c9f16900874ee109e0a25
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429881"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`DeviceTvmSoftwareVulnerabilitiesKB`Tabellen i det avancerade jakt schema innehåller en lista över sårbarhets [& sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `CveId` | strängvärdet | Unik identifierare tilldelad säkerhets luckan under de allmänna sårbarheterna och exponeringarna (CVE) |
| `CvssScore` | strängvärdet | Allvarlighets grad tilldelad det säkerhets problem som är kopplat till det vanliga säkerhets problemet (CVSS) |
| `IsExploitAvailable` | returtyp | Anger om en skadlig kod för problemet är allmänt tillgänglig |
| `VulnerabilitySeverityLevel` | strängvärdet | Allvarlighets grad tilldelad säkerhets luckan baserat på CVSS Poäng och dynamiska faktorer som påverkas av hotets liggande |
| `LastModifiedTime` | datetime | Datum och tid då objektet eller relaterade metadata senast ändrades |
| `PublishedDate` | datetime | Datum då säkerhets luckan skickades till offentlig |
| `VulnerabilityDescription` | strängvärdet | Beskrivning av säkerhets problem och associerade risker |
| `AffectedSoftware` | strängvärdet | Lista över alla program varu produkter som påverkas av problemet |

## <a name="related-topics"></a>Relaterade ämnen

- [Har varit inaktivt för hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hotet & säkerhets problem hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
