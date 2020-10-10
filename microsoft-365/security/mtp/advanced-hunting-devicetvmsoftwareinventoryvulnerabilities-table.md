---
title: DeviceTvmSoftwareInventoryVulnerabilities-tabell i det avancerade jakt-schemat
description: Lär dig mer om inventering av program vara på dina enheter och deras säkerhets problem i DeviceTvmSoftwareInventoryVulnerabilities-tabellen i det avancerade antivirus programmet.
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, Hot & sårbarhets hantering, TVM, enhets hantering, program vara, inventering, sårbarhet, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d8858fe9acd8183ad0d8644a9d5e4d70d32990a6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413228"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



`DeviceTvmSoftwareInventoryVulnerabilities`Tabellen i det avancerade jakt-schemat innehåller [hotet & sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av program vara på dina enheter samt eventuella kända säkerhets problem i dessa program varu produkter. Den här tabellen innehåller information om operativ system, CVE-ID och säkerhets problem. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på datorn. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `OSVersion` | strängvärdet | Version av operativ systemet som körs på datorn |
| `OSArchitecture` | strängvärdet | Arkitekturen för operativ systemet som körs på datorn |
| `SoftwareVendor` | strängvärdet | Namn på program varu leverantören |
| `SoftwareName` | strängvärdet | Namnet på program varu produkten |
| `SoftwareVersion` | strängvärdet | Versions nummer för program varu produkten |
| `CveId` | strängvärdet | Unik identifierare tilldelad säkerhets luckan under de allmänna sårbarheterna och exponeringarna (CVE) |
| `VulnerabilitySeverityLevel` | strängvärdet | Allvarlighets grad tilldelad säkerhets luckan baserat på CVSS Poäng och dynamiska faktorer som påverkas av hotets liggande |



## <a name="related-topics"></a>Relaterade ämnen

- [Har varit inaktivt för hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hotet & säkerhets problem hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
