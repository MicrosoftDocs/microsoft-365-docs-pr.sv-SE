---
title: DeviceTvmSoftwareInventorySårbarheter i det avancerade jaktschemat
description: Lär dig mer om inventeringen av programvara i dina enheter och deras sårbarheter i tabellen DeviceTvmSoftwareInventoryVulnerabilities i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, inventering, sårbarheter, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 0a7ac5a68bcdb12b3cdcd94cac8012c7807a6e2b
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811499"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventorySårbarheter

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `DeviceTvmSoftwareInventoryVulnerabilities` i det avancerade jaktschemat innehåller [inventeringen hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av programvara på dina enheter samt alla kända sårbarheter i dessa programvaruprodukter. Den här tabellen innehåller även information om operativsystemet, CD-ID:n och allvarlighetsinformation för säkerhetsproblem. Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jaktschemat finns i [den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `OSPlatform` | Sträng | Plattformen för operativsystemet som körs på maskinen. Detta anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `OSVersion` | Sträng | Version av operativsystemet som körs på maskinen |
| `OSArchitecture` | Sträng | Arkitektur av operativsystemet som körs på maskinen |
| `SoftwareVendor` | Sträng | Programvaruleverantörens namn |
| `SoftwareName` | Sträng | Programvaruproduktens namn |
| `SoftwareVersion` | Sträng | Programvaruproduktens versionsnummer |
| `CveId` | Sträng | Unik identifierare som tilldelats säkerhetsproblemet under cve-systemet (Common Vulnerabilities and Exposures) |
| `VulnerabilitySeverityLevel` | Sträng | Allvarlighetsgrad som tilldelats säkerhetsproblemet baserat på CVSS-poängen och dynamiska faktorer som påverkas av hotlandskapet |



## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
