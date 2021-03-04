---
title: DeviceTvmSoftwareVulnerabilities-tabellen i den avancerade sökschemat
description: Läs mer om säkerhetsproblem i programvaran som finns på enheter och listan över tillgängliga säkerhetsuppdateringar som åtgärdar varje problem i tabellen DeviceTvmSoftwareVulnerabilities i tabellen för avancerad sökning.
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, hot & sårbarhetshantering, TVM, enhetshantering, programvara, lager, svagheter, CVE-ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c5a143d835120339ade006dfd2dc394ec7c542d3
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423879"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Tabellen `DeviceTvmSoftwareVulnerabilities` i det avancerade schemat för sökning innehåller listan med & [för](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) sårbarhetshantering av säkerhetsproblem i installerade programvaruprodukter. Den här tabellen innehåller även information om operativsystem, CVE-ID och information om allvarlighetsgrad för problemet. Du kan till exempel använda den här tabellen för att leta efter händelser som innefattar enheter som har allvarliga säkerhetsproblem i deras programvara. Använd den här referensen för att skapa frågor som returnerar information från tabellen.

>[!NOTE]
> Tabellerna `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` och tabellerna har ersatt `DeviceTvmSoftwareInventoryVulnerabilities` tabellen. Tillsammans innehåller de två första tabellerna fler kolumner som du kan använda för att informera om dina åtgärder för hantering av vulnerablity eller för att leta efter sårbara enheter.

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
| `CveId` | sträng | Unik identifierare som tilldelats säkerhetsproblemet under systemet för vanliga säkerhetsproblem och exponeringar (CVE) |
| `VulnerabilitySeverityLevel` | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer påverkas av hotbilden |
| `RecommendedSecurityUpdate` | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet |
| `RecommendedSecurityUpdateId` | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbasartiklar (KB) |



## <a name="related-topics"></a>Relaterade ämnen

- [Proaktivt leta efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över hot & sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
