---
title: Tabellen DeviceEvents i det avancerade jaktschemat
description: Lär dig mer om antivirus-, brandväggs- och andra händelsetyper i tabellen diverse enhetshändelser (DeviceEvents) i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, säkerhetshändelser, antivirus, brandvägg, utnyttja vakt, DeviceEvents
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
ms.openlocfilehash: f99420b978f77f8b4a4660394d4a6f335c5aad66
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807151"
---
# <a name="deviceevents"></a>Enhetshändelser

**Gäller:**
- Skydd av Hot mot Microsoft



Händelserna eller `DeviceEvents` tabellen för diverse enheter i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om olika händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel Windows Defender Antivirus och utnyttja skydd. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

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
| `AccountDomain` | Sträng | Kontodomänen |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountSid` | Sträng | SID(SECURITY Identifier) för kontot |
| `RemoteUrl` | Sträng | url eller fullständigt kvalificerat domännamn (FQDN) som var ansluten till |
| `RemoteDeviceName` | Sträng | Namnet på maskinen som utförde en fjärråtgärd på den berörda datorn. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `ProcessId` | Int | Process-ID (PID) för den nyligen skapade processen |
| `ProcessCommandLine` | Sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessCreationTime` | Datetime | Datum och tid då processen skapades |
| `ProcessTokenElevation` | Sträng | Tokentyp som anger förekomst eller frånvaro av UAC-behörighetshöjning (User Access Control) som tillämpas på den nyligen skapade processen |
| `LogonId` | Sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `RegistryKey` | Sträng | Registernyckel som den inspelade åtgärden tillämpades på |
| `RegistryValueName` | Sträng | Namn på det registervärde som den registrerade åtgärden tillämpades på |
| `RegistryValueData` | Sträng | Uppgifter om registervärdet som den registrerade åtgärden tillämpades på |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemotePort` | Int | TCP-port på fjärrenheten som var ansluten till |
| `LocalIP` | Sträng | IP-adress som tilldelats den lokala maskinen som användes under kommunikationen |
| `LocalPort` | Int | TCP-port på den lokala maskinen som används under kommunikation |
| `FileOriginUrl` | Sträng | URL där filen hämtades från |
| `FileOriginIP` | Sträng | IP-adress där filen hämtades från |
| `AdditionalFields` | Sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt |
| `InitiatingProcessFileName` | Sträng | Namnet på den process som initierade händelsen |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra den process som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namnet på den överordnade process som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `InitiatingProcessMD5` | Sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde den process som ansvarar för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessLogonId` | Sträng | Identifierare för en inloggningssession av processen som initierade händelsen. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaraktiviteten |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
