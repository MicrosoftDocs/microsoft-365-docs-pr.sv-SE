---
title: DeviceFileEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser i tabellen DeviceFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, filecreationevents, DeviceFileEvents, filer, sökväg, hash, sha1, sha256, md5
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
ms.openlocfilehash: 67749125d2f62f2774c36e6970cf8901b1fd5784
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899309"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**Gäller:**
- Microsoft Hotskydd

`DeviceFileEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om filskapande, ändring och andra filsystemhändelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `FileName` | Sträng | Namnet på den fil som den registrerade åtgärden tillämpades på |
| `FolderPath` | Sträng | Mapp som innehåller filen som den inspelade åtgärden tillämpades på |
| `SHA1` | Sträng | SHA-1 i den akt som den registrerade åtgärden tillämpades på |
| `SHA256` | Sträng | SHA-256 i filen som den inspelade åtgärden tillämpades på. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `MD5` | Sträng | MD5-hash i filen som den registrerade åtgärden tillämpades på |
| `FileOriginUrl` | Sträng | URL där filen hämtades från |
| `FileOriginReferrerUrl` | Sträng | URL till webbsidan som länkar till den nedladdade filen |
| `FileOriginIP` | Sträng | IP-adress där filen hämtades från |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessMD5` | Sträng | MD5-hash i processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namn på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivå för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de lanserades från en nedladdning på Internet. Dessa integritetsnivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger närvaron eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpas på den process som initierade händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namn på den överordnade process som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som var ansvarig för händelsen startades |
| `RequestProtocol` | Sträng | Nätverksprotokoll, om tillämpligt, används för att initiera aktiviteten: Okänd, Lokal, SMB eller NFS |
| `ShareName` | Sträng | Namn på delad mapp som innehåller filen |
| `RequestSourceIP` | Sträng | IPv4- eller IPv6-adress för fjärrenheten som initierade aktiviteten |
| `RequestSourcePort` | Sträng | Källport på fjärrenheten som initierade aktiviteten |
| `RequestAccountName` | Sträng | Användarnamn för det konto som används för att fjärr initiera aktiviteten |
| `RequestAccountDomain` | Sträng | Domän för kontot som används för att fjärrutitiera aktiviteten |
| `RequestAccountSid` | Sträng | Säkerhetsidentifierare (SID) för det konto som används för att fjärr initiera aktiviteten |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `SensitivityLabel` | Sträng | Etikett som används på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det för informationsskydd |
| `SensitivitySubLabel` | Sträng | Sublabel tillämpas på ett e-postmeddelande, fil eller annat innehåll för att klassificera det för informationsskydd; känslighetsunderlaborering grupperas under känslighetsetiketter men behandlas oberoende av |
| `IsAzureInfoProtectionApplied` | Boolean | Anger om filen är krypterad av Azure Information Protection |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)