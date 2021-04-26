---
title: Tabellen DeviceTvmSoftwareVulnerabilities i det avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som åtgärdar varje sårbarhet i tabellen DeviceTvmSoftwareVulnerabilities i tabellen advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023815"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

>[!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Tabellen `DeviceTvmSoftwareVulnerabilities` i det avancerade sökschemat innehåller listan över & [sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) av säkerhetsproblem i installerade programvaruprodukter. Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation. Du kan till exempel använda den här tabellen för att leta efter händelser som innefattar enheter som har allvarligt säkerhetsproblem med programvaran. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

>[!NOTE]
> Tabellerna `DeviceTvmSoftwareInventory` och de har ersatt `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen. Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av trådlöst arbete eller för att leta efter sårbara enheter.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `OSVersion` | sträng | Version av operativsystemet som körs på datorn |
| `OSArchitecture` | sträng | Arkitekturen för operativsystemet som körs på datorn |
| `SoftwareVendor` | sträng | Namnet på programvaruleverantören |
| `SoftwareName` | sträng | Namnet på programvaruprodukten |
| `SoftwareVersion` | sträng | Versionsnummer för programvaran |
| `CveId` | sträng | Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE) |
| `VulnerabilitySeverityLevel` | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden |
| `RecommendedSecurityUpdate` | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet |
| `RecommendedSecurityUpdateId` | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar |



## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)