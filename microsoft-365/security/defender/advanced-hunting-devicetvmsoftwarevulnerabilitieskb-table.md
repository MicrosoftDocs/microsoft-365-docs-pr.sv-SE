---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade sökschemat.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & hantering av säkerhetsrisker, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023803"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint



Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `CveId` | sträng | Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE) |
| `CvssScore` | sträng | Allvarlighetspoäng som tilldelats säkerhetsrisken under th Common Vulnerability Score System (CVSS) |
| `IsExploitAvailable` | boolesk | Anger om sårbarhetskod för problemet är offentligt tillgänglig |
| `VulnerabilitySeverityLevel` | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden |
| `LastModifiedTime` | datetime | Datum och tid då objektet eller relaterade metadata senast ändrades |
| `PublishedDate` | datetime | Date vulnerability was disclosed to public |
| `VulnerabilityDescription` | sträng | Beskrivning av sårbarhet och associerade risker |
| `AffectedSoftware` | sträng | Lista över alla programvaruprodukter som påverkas av problemet |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)