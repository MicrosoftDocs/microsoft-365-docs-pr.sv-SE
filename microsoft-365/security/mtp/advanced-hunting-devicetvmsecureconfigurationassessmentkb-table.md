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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6186bd37735b5225fd33905395055228972fc27c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847590"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



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
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hotet & säkerhets problem hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
