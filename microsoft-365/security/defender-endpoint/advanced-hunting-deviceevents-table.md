---
title: Tabellen DeviceEvents i det avancerade sökschemat
description: Läs mer om antivirus, brandväggen och andra händelsetyper i tabellen för diverse enhetshändelser (DeviceEvents) i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, säkerhetshändelser, antivirus, brandvägg, sårbarhetsskydd, MiscEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072425"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Diverse enhetshändelser eller -tabeller i det avancerade sökschemat innehåller information om olika händelsetyper, inklusive händelser som utlöses av säkerhetskontroller, till exempel `DeviceEvents` Microsoft Defender Antivirus och sårbarhetsskydd. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från tabellen.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountName` |sträng | Användarnamn för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `RemoteUrl` | sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `RemoteDeviceName` | sträng | Namnet på enheten som utförde en fjärråtgärd på den aktuella enheten. Beroende på vilken händelse som rapporteras kan det här namnet vara ett fullständigt kvalificerat domännamn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domäninformation |
| `ProcessId` | int | Process-ID (PID) för den nya processen |
| `ProcessCommandLine` | sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessCreationTime` | datetime | Datum och tid då processen skapades |
| `ProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för den nya processen |
| `LogonId` | sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma enhet bara mellan omstarter |
| `RegistryKey` | sträng | Registernyckel som den inspelade åtgärden tillämpats på |
| `RegistryValueName` | sträng | Namnet på registervärdet som den inspelade åtgärden tillämpats på |
| `RegistryValueData` | sträng | Data för registervärdet som den inspelade åtgärden tillämpats på |
| `RemoteIP` | sträng | IP-adress som var ansluten till |
| `RemotePort` | int | TCP-port på den fjärrenhet som var ansluten till |
| `LocalIP` | sträng | IP-adress tilldelad till den lokala enheten som används under kommunikation |
| `LocalPort` | int | TCP-port på den lokala enheten som används under kommunikation |
| `FileOriginUrl` | sträng | URL som filen laddades ned från |
| `FileOriginIP` | sträng | IP-adress där filen laddades ned från |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessLogonId` | sträng | Identifierare för en inloggningssession i processen som initierade händelsen. Den här identifieraren är unik på samma enhet bara mellan omstarter |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
