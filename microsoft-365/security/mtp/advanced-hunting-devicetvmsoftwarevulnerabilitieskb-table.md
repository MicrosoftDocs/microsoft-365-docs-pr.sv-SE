---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i det avancerade jaktschemat
description: Lär dig mer om de sårbarheter för programvara som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schema, referens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, inventering, sårbarheter, CVE ID, CVSS, DeviceTvmSoftBevulnerabilitiesKB
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
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44328004"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

**Gäller:**
- Microsoft Hotskydd



`DeviceTvmSoftwareVulnerabilitiesKB`Tabellen i det avancerade jaktschemat innehåller en lista över sårbarheter Hot & [Sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) bedömer enheter för. Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jaktschemat finns [i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `CveId` | Sträng | Unik identifierare som tilldelats säkerhetsproblemet under CVE-systemet (Common Vulnerabilities and Exposures) |
| `CvssScore` | Sträng | Allvarlighetsgrad som tilldelats säkerhetsproblemet under cvss (Common Vulnerability Scoring System) |
| `IsExploitAvailable` | Boolean | Anger om det är allmänt tillgängligt för att utnyttja kod för säkerhetsproblemet |
| `VulnerabilitySeverityLevel` | Sträng | Allvarlighetsgrad som tilldelats säkerhetsproblemet baserat på CVSS-poängen och dynamiska faktorer som påverkas av hotbilden |
| `LastModifiedTime` | Datetime | Datum och tid då objektet eller relaterade metadata senast ändrades |
| `PublishedDate` | Datetime | Datum sårbarhet avslöjades för allmänheten |
| `VulnerabilityDescription` | Sträng | Beskrivning av sårbarhet och därmed förbundna risker |
| `AffectedSoftware` | Sträng | Lista över alla programvaruprodukter som påverkas av sårbarheten |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hantering av hot & sårbarhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
