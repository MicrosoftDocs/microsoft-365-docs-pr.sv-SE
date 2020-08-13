---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i det avancerade jakt-schemat
description: Lär dig mer om de olika säkra konfigurationerna bedömda av hotet & säkerhets problem hantering i tabellen DeviceTvmSecureConfigurationAssessmentKB för Advanced jakt-schemat.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, säkerhets konfiguration, MITRE att&CK ramverk, kunskaps bas, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 2c16929555b3923086e249db61cebb3cf7af17c8
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648971"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Gäller för:**
- Microsoft Hotskydd



`DeviceTvmSecureConfigurationAssessmentKB`Tabellen i det avancerade jakt-schemat innehåller information om de olika säkra konfigurationerna – till exempel om du har automatiska uppdateringar på en enhet [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)– som det rör sig om att uppdatera data. Det inkluderar också risk information, relaterade bransch benchmarks och tillämpliga MITRE att&CK teknik och taktiker. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `ConfigurationId` | strängvärdet | Unik identifierare för en viss konfiguration |
| `ConfigurationImpact` | strängvärdet | Märkeffekt som påverkar konfigurationen till total poängen (1-10) |
| `ConfigurationName` | strängvärdet | Visnings namn för konfigurationen |
| `ConfigurationDescription` | strängvärdet | Beskrivning av konfigurationen |
| `RiskDescription` | strängvärdet | Beskrivning av den associerade risken |
| `ConfigurationCategory` | strängvärdet | Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller|
| `ConfigurationSubcategory` | strängvärdet |Under kategori eller under grupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner och funktioner. |
| `ConfigurationBenchmarks` | strängvärdet | Lista över riktmärken för branschen rekommenderar samma eller liknande konfiguration |
| `RelatedMitreTechniques` | strängvärdet | Lista över Mitre att&CK Ramverks tekniker relaterade till konfigurationen |
| `RelatedMitreTactics ` | strängvärdet | Lista över Mitre att&CK ramverk taktiker relaterade till konfigurationen |

## <a name="related-topics"></a>Relaterade ämnen

- [Har varit inaktivt för hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hotet & säkerhets problem hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
