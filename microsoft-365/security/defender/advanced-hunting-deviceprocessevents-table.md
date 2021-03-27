---
title: Tabellen DeviceProcessEvents i det avancerade sökschemat
description: Läs mer om processen som gäller för att skapa och hantera händelser i tabellen DeviceProcessEventstable för den avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schemareferens, kusto, tabell, kolumn, datatyp, processcreationevents, DeviceProcessEvents, process-id, kommandorad, DeviceProcessEvents
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 363d80431c14bc550cba34850c85593163aea1b1
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382847"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Tabellen `DeviceProcessEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om processskapande och relaterade händelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `FileName` | sträng | Namnet på filen som den inspelade åtgärden tillämpats på |
| `FolderPath` | sträng | Mapp som innehåller den fil som den inspelade åtgärden tillämpats på |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `FileSize` | long | Storlek på filen i byte |
| `ProcessVersionInfoCompanyName` | sträng | Företagsnamn från versionsinformationen för den nya processen |
| `ProcessVersionInfoProductName` | sträng | Produktnamn från versionsinformationen för den nya processen |
| `ProcessVersionInfoProductVersion` | sträng | Produktversion från versionsinformationen för den nya processen |
| `ProcessVersionInfoInternalFileName` | sträng | Internt filnamn från versionsinformationen för den nya processen |
| `ProcessVersionInfoOriginalFileName` | sträng | Det ursprungliga filnamnet från versionsinformationen för den nya processen |
| `ProcessVersionInfoFileDescription` | sträng | Beskrivning av versionsinformationen för den nya processen |
| `ProcessId` | int | Process-ID (PID) för den nya processen |
| `ProcessCommandLine` | sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessIntegrityLevel` | sträng | Integritetsnivån för den nyligen skapade processen. I Windows tilldelas processer integritetsnivåer baserat på vissa egenskaper, till exempel om de startades från ett nedladdat Internet. De här integritetsnivåerna påverkar behörigheter till resurser |
| `ProcessTokenElevation` | sträng | Anger vilken typ av tokenhöjd som används för den nya processen. Möjliga värden: TokenElevationTypeLimited (begränsad), TokenElevationTypeDefault (standard) och TokenElevationTypeFull (förhöjd) |
| `ProcessCreationTime` | datetime | Datum och tid då processen skapades |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `LogonId` | sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator bara mellan omstarter |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamn för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountUpn` | sträng | Användarkontons huvudnamn (UPN) för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountObjectId` | sträng | Azure AD-objekt-ID för användarkontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessLogonId` | sträng | Identifierare för en inloggningssession i processen som initierade händelsen. Den här identifieraren är unik på samma dator bara mellan omstarter. |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter till resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFileSize` | long | Storlek på filen som körde processen som ansvarar för händelsen |
| `InitiatingProcessVersionInfoCompanyName` | sträng | Företagsnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoProductName` | sträng | Produktnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoProductVersion` | sträng | Produktversion från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoInternalFileName` | sträng | Internt filnamn från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoOriginalFileName` | sträng | Det ursprungliga filnamnet från versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessVersionInfoFileDescription` | sträng | Beskrivning av versionsinformationen för processen (bildfilen) som ansvarar för händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då föräldern till processen som ansvarar för händelsen startades |
| `InitiatingProcessSignerType` | sträng | Typ av fil signering av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSignatureStatus` | sträng | Information om signaturstatus för processen (bildfil) som initierade händelsen |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |
| `AdditionalFields` | sträng | Ytterligare information om händelsen i JSON-matrisformat |


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
