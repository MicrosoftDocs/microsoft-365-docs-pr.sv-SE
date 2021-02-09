---
title: DeviceTvmSecureConfigurationAssessmentKB-tabell i den avancerade sökschemat
description: Lär dig mer om de olika säkra konfigurationerna som bedöms av Threat & Vulnerability Management i tabellen DeviceTvmSecureConfigurationAssessmentKB i det avancerade sökschemat.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, MITRE ATT&CK-ramverk, kunskapsbas, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145457"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen i det avancerade schemat för sökning innehåller information om de olika säkra konfigurationerna – till exempel om en enhet har automatiska uppdateringar på – som kontrolleras av `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Den innehåller även riskinformation, relaterade branschstandarder och tillämpliga MITRE ATT&CK-tekniker och taktiker. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `ConfigurationId` | sträng | Unikt ID för en viss konfiguration |
| `ConfigurationImpact` | sträng | Klassificerad inverkan på konfigurationen till det övergripande konfigurationsresultatet (1–10) |
| `ConfigurationName` | sträng | Visningsnamn för konfigurationen |
| `ConfigurationDescription` | sträng | Beskrivning av konfigurationen |
| `RiskDescription` | sträng | Beskrivning av den associerade risken |
| `ConfigurationCategory` | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, nätverk, konton, säkerhetskontroller|
| `ConfigurationSubcategory` | sträng |Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner. |
| `ConfigurationBenchmarks` | sträng | Lista över branschstandarder som rekommenderar samma eller liknande konfiguration |
| `Tags` | sträng | Etiketter som representerar olika attribut som används för att identifiera eller kategorisera en säkerhetskonfiguration |
| `RemediationOptions` | sträng | Rekommenderade åtgärder för att minska eller hantera eventuella associerade risker |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
