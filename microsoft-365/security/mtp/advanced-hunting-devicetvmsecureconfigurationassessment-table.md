---
title: DeviceTvmSecureConfigurationAssessment-tabell i det avancerade sökschemat
description: Läs mer om säkerhetsbedömningshändelser i tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat. Dessa hot & säkerhetshanteringshändelser tillhandahåller enhetsinformation samt information om säkerhetskonfigurationer, påverkan och efterlevnad.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, säkerhetskonfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931104"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från Hot och [& sårbarhetshantering.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheterna är kompatibla.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.|
| `Timestamp` | datetime | Datum och tid då posten skapades |
| `ConfigurationId` | sträng | Unikt ID för en viss konfiguration |
| `ConfigurationCategory` | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, nätverk, konton, säkerhetskontroller |
| `ConfigurationSubcategory` | sträng | Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner. |
| `ConfigurationImpact` | sträng | Klassificerad inverkan på konfigurationen till det övergripande konfigurationsresultatet (1–10) |
| `IsCompliant` | boolesk | Anger om konfigurationen eller principen är korrekt konfigurerad |
| `IsApplicable` | boolesk | Anger om konfigurationen eller principen gäller för enheten |
| `Context` | sträng | Ytterligare sammanhangsberoende information om konfigurationen eller principen |
| `IsExpectedUserImpactCompliant` | boolesk | Anger om det kommer att finnas påverkan på användare om konfigurationen eller principen tillämpas |

## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
