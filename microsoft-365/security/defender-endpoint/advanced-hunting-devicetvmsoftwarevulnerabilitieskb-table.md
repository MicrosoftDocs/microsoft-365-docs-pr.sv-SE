---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som spåras av Threat & Vulnerability Management i tabellen DeviceTvmSoftwareVulnerabilitiesKB i det avancerade sökschemat.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerilitiesKB
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
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070922"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Tabellen `DeviceTvmSoftwareVulnerabilitiesKB` i det avancerade schemat för sökning innehåller listan över säkerhetsproblem som [& sårbarhetshantering](next-gen-threat-and-vuln-mgt.md) bedömer enheter för. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `CveId` | sträng | Unik identifierare som tilldelats säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE) |
| `CvssScore` | sträng | Allvarlighetspoäng som tilldelats säkerhetsrisken under th Common Vulnerability Score System (CVSS) |
| `IsExploitAvailable` | boolesk | Anger om sårbarhetskod för problemet är offentligt tillgänglig |
| `VulnerabilitySeverityLevel` | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden |
| `LastModifiedTime` | datetime | Datum och tid då objektet eller relaterade metadata senast ändrades |
| `PublishedDate` | datetime | Date vulnerability was disclosed to public |
| `VulnerabilityDescription` | sträng | Beskrivning av sårbarhet och associerade risker |
| `AffectedSoftware` | sträng | Lista över alla programvaruprodukter som påverkas av problemet |

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Översikt över hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
