---
title: Tabellen DeviceTvmSecureConfigurationAssessment i det avancerade sökschemat
description: Lär dig mer & om säkerhetsutvärderingshändelser för sårbarhetshantering i tabellen DeviceTvmSecureConfigurationAssessment i tabellen Advanced hunting schema. Dessa händelser ger enhetsinformation och information om säkerhetskonfigurationer, påverkan och efterlevnadsinformation.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075049"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Varje rad i tabellen `DeviceTvmSecureConfigurationAssessment` innehåller en bedömningshändelse för en viss säkerhetskonfiguration från [Threat & Vulnerability Management.](next-gen-threat-and-vuln-mgt.md) Använd den här referensen för att kontrollera de senaste utvärderingsresultaten och avgöra om enheter är kompatibla.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.|
| `Timestamp` | datetime |Datum och tid då posten skapades |
| `ConfigurationId` | sträng | Unikt ID för en viss konfiguration |
| `ConfigurationCategory` | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller |
| `ConfigurationSubcategory` | sträng |Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner. |
| `ConfigurationImpact` | sträng | Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10) |
| `IsCompliant` | boolesk | Anger om konfigurationen eller principen är korrekt konfigurerad |
| `IsApplicable` | boolesk | Anger om konfigurationen eller principen gäller för enheten |
| `Context` | sträng | Ytterligare sammanhangsberoende information om konfigurationen eller principen |
| `IsExpectedUserImpactCompliant` | boolesk | Anger om det kommer att finnas någon påverkan på användaren om konfigurationen eller principen tillämpas |

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Översikt över hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)