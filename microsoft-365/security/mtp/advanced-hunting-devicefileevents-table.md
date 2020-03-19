---
title: Tabellen DeviceFileEvents i det avancerade jaktschemat
description: Lär dig mer om filrelaterade händelser i tabellen DeviceFileEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, filskapandehändelser, DeviceFileEvents, filer, sökväg, hash, sha1, sha256, md5
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
ms.openlocfilehash: 07569b93244bd420fe5961e20e6951ea84ae47d7
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810620"
---
# <a name="devicefileevents"></a>DeviceFileEvents (På video)

**Gäller:**
- Skydd av Hot mot Microsoft



Tabellen `DeviceFileEvents` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om filskapande, ändring och andra filsystemhändelser. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `FileName` | Sträng | Namnet på filen som den inspelade åtgärden tillämpades på |
| `FolderPath` | Sträng | Mapp som innehåller filen som den inspelade åtgärden tillämpades på |
| `SHA1` | Sträng | SHA-1 i akten som den inspelade åtgärden tillämpades på |
| `SHA256` | Sträng | SHA-256 i filen som den inspelade åtgärden tillämpades på. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt |
| `MD5` | Sträng | MD5-hash i ärendet om att den registrerade åtgärden tillämpades på |
| `FileOriginUrl` | Sträng | URL där filen hämtades från |
| `FileOriginReferrerUrl` | Sträng | URL till webbsidan som länkar till den nedladdade filen |
| `FileOriginIP` | Sträng | IP-adress där filen hämtades från |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde den process som ansvarar för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessMD5` | Sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namnet på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra den process som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivån för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer som baseras på vissa egenskaper, till exempel om de lanserades från en internetnedladdning. Dessa integritetsnivåer påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger förekomsten eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpats på den process som initierade händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namnet på den överordnade process som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaraktiviteten |
| `SensitivityLabel` | Sträng | Etikett som används på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det för informationsskydd |
| `SensitivitySubLabel` | Sträng | Underetikett som används på ett e-postmeddelande, en fil eller annat innehåll för att klassificera det för informationsskydd. känslighetsunderetiketter grupperas under känslighetsetiketter men behandlas oberoende av |
| `IsAzureInfoProtectionApplied` | Boolean | Anger om filen krypteras av Azure Information Protection |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
