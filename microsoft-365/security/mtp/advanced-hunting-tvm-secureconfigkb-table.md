---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i det avancerade jaktschemat
description: Lär dig mer om de olika säkra konfigurationer som bedöms av Threat & Sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverk, kunskapsbas, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807966"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `DeviceTvmSecureConfigurationAssessmentKB` i det avancerade jaktschemat innehåller information om de olika säkra konfigurationerna, till exempel om en enhet har automatiska uppdateringar på , som kontrolleras av [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Den innehåller också riskinformation, relaterade branschriktmärken och tillämpliga MITRE ATT&CK-tekniker och taktik. Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jaktschemat finns i [den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `ConfigurationId` | Sträng | Unik identifierare för en viss konfiguration |
| `ConfigurationImpact` | Sträng | Nominell effekt av konfigurationen till den totala konfigurationspoängen (1-10) |
| `ConfigurationName` | Sträng | Visa namnet på konfigurationen |
| `ConfigurationDescription` | Sträng | Beskrivning av konfigurationen |
| `RiskDescription` | Sträng | Beskrivning av den tillhörande risken |
| `ConfigurationCategory` | Sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller|
| `ConfigurationSubcategory` | Sträng |Underkategori eller undergruppering som konfigurationen tillhör. I många fall beskriver detta specifika funktioner eller funktioner. |
| `ConfigurationBenchmarks` | Sträng | Lista över branschriktmärken som rekommenderar samma eller liknande konfiguration |
| `RelatedMitreTechniques` | Sträng | Lista över Mitre ATT&CK ramtekniker relaterade till konfigurationen |
| `RelatedMitreTactics ` | Sträng | Lista över Mitre ATT&CK ram taktik i samband med konfigurationen |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
