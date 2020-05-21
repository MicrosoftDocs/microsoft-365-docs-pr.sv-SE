---
title: DeviceTvmSoftwareInventoryVulnerabilities tabellen i det avancerade jaktschemat
description: Lär dig mer om inventeringen av programvara i dina enheter och deras sårbarheter i tabellen DeviceTvmSoftwareInventoryVulnerabilities i det avancerade jaktschemat.
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, inventering, sårbarheter, CVE ID, OS DeviceTvmSoftwareIntoryVulnerabilities
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
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327996"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**Gäller:**
- Microsoft Hotskydd



`DeviceTvmSoftwareInventoryVulnerabilities`Tabellen i det avancerade jaktschemat innehåller [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) hantering av programvara på dina enheter samt eventuella kända sårbarheter i dessa programvaruprodukter. Den här tabellen innehåller även information om operativsystemet, CVE-ID:er och allvarlighetsgradinformation för säkerhetsproblem. Använd den här referensen om du vill skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade jaktschemat finns [i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `OSPlatform` | Sträng | Plattform för operativsystemet som körs på maskinen. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `OSVersion` | Sträng | Version av operativsystemet som körs på datorn |
| `OSArchitecture` | Sträng | Arkitektur för operativsystemet som körs på datorn |
| `SoftwareVendor` | Sträng | Programvaruleverantörens namn |
| `SoftwareName` | Sträng | Namnet på programvaruprodukten |
| `SoftwareVersion` | Sträng | Versionsnummer för programvaruprodukten |
| `CveId` | Sträng | Unik identifierare som tilldelats säkerhetsproblemet under CVE-systemet (Common Vulnerabilities and Exposures) |
| `VulnerabilitySeverityLevel` | Sträng | Allvarlighetsgrad som tilldelats säkerhetsproblemet baserat på CVSS-poängen och dynamiska faktorer som påverkas av hotbilden |



## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hantering av hot & sårbarhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
