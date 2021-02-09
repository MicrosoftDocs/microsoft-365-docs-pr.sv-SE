---
title: Tabellen DeviceEvents i den avancerade sökschemat
description: Läs mer om antivirus, brandvägg och andra händelsetyper i tabellen för övriga enhetshändelser (DeviceEvents) i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, säkerhetshändelser, antivirus, brandvägg, sårbarhetsskydd, DeviceEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1340464fbe71e919a60668cf7d1b2f535eb6d260
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145331"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Diverse enhetshändelser eller -tabellen i det avancerade schemat för sökning innehåller information om olika händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel Windows Defender Antivirus och `DeviceEvents` sårbarhetsskydd. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)


| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | sträng | Namnet på filen där den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för den fil som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 för filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `AccountDomain` | sträng | Domänen för kontot |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `RemoteUrl` | sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `RemoteDeviceName` | sträng | Namnet på den dator som utförde en fjärråtgärd på den aktuella datorn. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `ProcessId` | int | Process-ID (PID) för den nya processen |
| `ProcessCommandLine` | sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessCreationTime` | datetime | Datum och tid då processen skapades |
| `ProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för den nya processen |
| `LogonId` | sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `RegistryKey` | sträng | Registernyckel som den inspelade åtgärden tillämpades på |
| `RegistryValueName` | sträng | Namn på registervärdet som den inspelade åtgärden tillämpats på |
| `RegistryValueData` | sträng | Data för registervärdet som den inspelade åtgärden tillämpats på |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemotePort` | int | TCP-port på fjärrenheten som var ansluten till |
| `LocalIP` | sträng | IP-adress tilldelad till den lokala datorn som används under kommunikation |
| `LocalPort` | int | TCP-port på den lokala datorn som används under kommunikation |
| `FileOriginUrl` | sträng | URL där filen laddades ned från |
| `FileOriginIP` | sträng | IP-adress där filen laddades ned från |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessFileSize` | long | Storlek på filen som körde processen som ansvarar för händelsen |
| `FileSize` | long | Storlek på filen i byte |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som avkortade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamnet för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountUpn` | sträng | Användarens huvudnamn (UPN) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountObjectId` | sträng | Azure AD-objekt-ID för användarkontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessLogonId` | sträng | Identifierare för en inloggningssession i processen som initierade händelsen. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
