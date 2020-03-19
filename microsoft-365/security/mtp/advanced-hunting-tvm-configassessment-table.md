---
title: DeviceTvmSecureConfigurationBedömningstabell i det avancerade jaktschemat
description: Lär dig mer om säkerhetsbedömningshändelser för Hot & sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessment i det avancerade jaktschemat. Dessa händelser ger maskininformation samt information om säkerhetskonfiguration, påverkan och efterlevnad.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811143"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationBedömning

**Gäller:**
- Skydd av Hot mot Microsoft



Varje rad `DeviceTvmSecureConfigurationAssessment` i tabellen innehåller en utvärderingshändelse för en specifik säkerhetskonfiguration från [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Använd den här referensen för att kontrollera de senaste bedömningsresultaten och avgöra om enheter är kompatibla.

Information om andra tabeller i det avancerade jaktschemat finns i [den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `OSPlatform` | Sträng | Plattformen för operativsystemet som körs på maskinen. Detta anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.|
| `Timestamp` | Datetime | Datum och tid då posten genererades |
| `ConfigurationId` | Sträng | Unik identifierare för en viss konfiguration |
| `ConfigurationCategory` | Sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller |
| `ConfigurationSubcategory` | Sträng | Underkategori eller undergruppering som konfigurationen tillhör. I många fall beskriver detta specifika funktioner eller funktioner. |
| `ConfigurationImpact` | Sträng | Nominell effekt av konfigurationen till den totala konfigurationspoängen (1-10) |
| `IsCompliant` | Boolean | Anger om konfigurationen eller principen är korrekt konfigurerad |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
