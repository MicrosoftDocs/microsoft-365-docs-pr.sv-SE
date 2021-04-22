---
title: Tabellen AlertEvidence i det avancerade sökschemat
description: Läs mer om information som är kopplad till aviseringar i tabellen AlertEvidence i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932589"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade sökschemat innehåller information om olika enheter – `AlertEvidence` filer, IP-adresser, URL-adresser, användare och enheter – som associeras med aviseringar från Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `AlertId` | sträng | Unikt ID för aviseringen |
| `ServiceSource` | sträng | Produkt eller tjänst som tillhandahöll aviseringsinformationen |
| `EntityType` | sträng | Typ av objekt, till exempel en fil, en process, en enhet eller en användare |
| `EvidenceRole` | sträng | Hur entitet involveras i en avisering, som anger om den påverkas eller inte är relaterad |
| `EvidenceDirection` | sträng | Anger om entiteten är källan eller målet för en nätverksanslutning |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `FileSize` | int | Storlek på filen i byte |
| `ThreatFamily` | sträng | Programfamilj som den misstänkta eller skadliga filen eller processen har klassificerats under |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemoteUrl` | sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure Active Directory |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `LocalIP` | sträng | IP-adress tilldelad till den lokala enheten som används under kommunikation |
| `NetworkMessageId` | sträng | Unikt ID för e-postmeddelandet som genereras av Office 365 |
| `EmailSubject` | sträng | E-postmeddelandets ämne |
| `ApplicationId` | sträng | Unikt ID för programmet |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `ProcessCommandLine` | sträng | Kommandorad som används för att skapa den nya processen |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `RegistryKey` |sträng | Registernyckel som den inspelade åtgärden tillämpats på |
| `RegistryValueName` |sträng | Namnet på registervärdet som den inspelade åtgärden tillämpats på |
| `RegistryValueData` |sträng | Data för registervärdet som den inspelade åtgärden tillämpats på |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
