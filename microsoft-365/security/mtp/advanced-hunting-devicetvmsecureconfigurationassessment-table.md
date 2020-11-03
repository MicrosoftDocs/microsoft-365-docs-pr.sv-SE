---
title: DeviceTvmSecureConfigurationAssessment-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser för säkerhets utvärdering i DeviceTvmSecureConfigurationAssessment-tabellen för Advanced jakt-schemat. De här hotet & säkerhets problem hanterings händelser tillhandahåller enhets information samt information om säkerhets konfiguration, konsekvens och efterlevnad.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, säkerhets konfiguration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847614"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Varje rad i `DeviceTvmSecureConfigurationAssessment` tabellen innehåller en utvärderings händelse för en viss säkerhets konfiguration från [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Använd den här referensen för att kontrol lera de senaste utvärderings resultaten och fastställa om enheter är kompatibla.

Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | strängvärdet | Unik identifierare för enheten i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten |
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på enheten. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.|
| `Timestamp` | datetime | Datum och tid när posten skapades |
| `ConfigurationId` | strängvärdet | Unik identifierare för en viss konfiguration |
| `ConfigurationCategory` | strängvärdet | Kategori eller gruppering som konfigurationen tillhör: program, operativ system, nätverk, konton, säkerhets kontroller |
| `ConfigurationSubcategory` | strängvärdet | Under kategori eller under grupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner och funktioner. |
| `ConfigurationImpact` | strängvärdet | Märkeffekt som påverkar konfigurationen till total poängen (1-10) |
| `IsCompliant` | returtyp | Anger om konfigurationen eller principen är korrekt konfigurerad |
| `IsApplicable` | returtyp | Anger om konfigurationen eller policyn gäller för enheten |
| `Context` | strängvärdet | Ytterligare information om konfigurationen eller policyn |
| `IsExpectedUserImpactCompliant` | returtyp | Anger om användaren kan påverka om konfigurationen eller principen tillämpas |

## <a name="related-topics"></a>Relaterade ämnen

- [Har varit inaktivt för hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hotet & säkerhets problem hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
