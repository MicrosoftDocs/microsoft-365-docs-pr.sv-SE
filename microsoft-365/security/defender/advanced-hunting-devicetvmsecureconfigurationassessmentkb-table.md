---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i den avancerade tabellen för sökning.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & hantering av säkerhetsrisker, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024247"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint



Tabellen i det avancerade sökschemat innehåller information om olika säkra konfigurationer – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE ATT-&CK-tekniker och taktiker. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `ConfigurationId` | sträng | Unikt ID för en viss konfiguration |
| `ConfigurationImpact` | sträng | Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10) |
| `ConfigurationName` | sträng | Visningsnamn för konfigurationen |
| `ConfigurationDescription` | sträng | Beskrivning av konfigurationen |
| `RiskDescription` | sträng | Beskrivning av den associerade risken |
| `ConfigurationCategory` | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller|
| `ConfigurationSubcategory` | sträng |Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner. |
| `ConfigurationBenchmarks` | sträng | Lista med branschstandarder som rekommenderar samma eller liknande konfiguration |
| `Tags` | sträng | Etiketter som representerar olika attribut som används för att identifiera eller kategorisera en säkerhetskonfiguration |
| `RemediationOptions` | sträng | Rekommenderade åtgärder för att minska eller hantera eventuella associerade risker |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)