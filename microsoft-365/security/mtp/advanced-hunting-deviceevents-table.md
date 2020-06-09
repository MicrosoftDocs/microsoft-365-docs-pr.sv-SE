---
title: DeviceEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om antivirus-, brandväggs- och andra händelsetyper i tabellen Diverse enhetshändelser (DeviceEvents) i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, säkerhetshändelser, antivirus, brandvägg, utnyttja vakt, DeviceEvents
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
ms.openlocfilehash: f340a34b3c88f1caba83861c4d36ce140846d495
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617180"
---
# <a name="deviceevents"></a>DeviceEvents

**Gäller:**
- Microsoft Hotskydd



Diverse enhetshändelser eller `DeviceEvents` tabell i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om olika händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel Windows Defender Antivirus och utnyttja skydd. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

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
| `AccountDomain` | Sträng | Kontots domän |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `RemoteUrl` | Sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `RemoteDeviceName` | Sträng | Namn på den maskin som utförde en fjärroperation på den berörda datorn. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `ProcessId` | Int | Process-ID (PID) för den nyskapade processen |
| `ProcessCommandLine` | Sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessCreationTime` | Datetime | Datum och tid då processen skapades |
| `ProcessTokenElevation` | Sträng | Tokentyp som anger närvaron eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpas på den nyligen skapade processen |
| `LogonId` | Sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `RegistryKey` | Sträng | registernyckeln att den registrerade åtgärden tillämpades på |
| `RegistryValueName` | Sträng | Namnet på det registervärde som den registrerade åtgärden tillämpades på |
| `RegistryValueData` | Sträng | Uppgifter om det registervärde som den registrerade åtgärden tillämpades på |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemotePort` | Int | TCP-porten på fjärrenheten som var ansluten till |
| `LocalIP` | Sträng | IP-adress som tilldelats den lokala dator som används under kommunikation |
| `LocalPort` | Int | TCP-port på den lokala maskinen som används under kommunikation |
| `FileOriginUrl` | Sträng | URL där filen hämtades från |
| `FileOriginIP` | Sträng | IP-adress där filen hämtades från |
| `AdditionalFields` | Sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `InitiatingProcessFileName` | Sträng | Namnet på den process som initierade händelsen |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namn på den överordnade process som gav upphov till den process som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `InitiatingProcessMD5` | Sträng | MD5-hash i processen (bildfil) som initierade händelsen |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessLogonId` | Sträng | Identifierare för en inloggningssession för processen som initierade händelsen. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
