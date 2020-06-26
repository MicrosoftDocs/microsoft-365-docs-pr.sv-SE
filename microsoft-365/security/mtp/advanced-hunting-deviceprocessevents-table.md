---
title: DeviceProcessEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om processlek- eller skapelsehändelser i DeviceProcessEventstable av det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, processcreationevents, DeviceProcessEvents, process-ID, kommandorad, DeviceProcessEvents
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
ms.openlocfilehash: 104ca1b89c4dd6ede2ad06404bbdc0da7d11f689
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899237"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

**Gäller:**
- Microsoft Hotskydd



`DeviceProcessEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om processskapande och relaterade händelser. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

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
| `ProcessId` | Int | Process-ID (PID) för den nyskapade processen |
| `ProcessCommandLine` | Sträng | Kommandorad som används för att skapa den nya processen |
| `ProcessIntegrityLevel` | Sträng | Integritetsnivå för den nyskapade processen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de lanserades från ett internet som hämtats. Dessa integritetsnivåer påverkar behörigheter för resurser |
| `ProcessTokenElevation` | Sträng | Tokentyp som anger närvaron eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpas på den nyligen skapade processen |
| `ProcessCreationTime` | Datetime | Datum och tid då processen skapades |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `LogonId` | Sträng | Identifierare för en inloggningssession. Den här identifieraren är unik på samma dator endast mellan omstarter |
| `InitiatingProcessAccountDomain` | Sträng | Domän för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountName` | Sträng | Användarnamn för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessAccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som var ansvarig för händelsen |
| `InitiatingProcessLogonId` | Sträng | Identifierare för en inloggningssession för processen som initierade händelsen. Den här identifieraren är unik på samma dator endast mellan omstarter. |
| `InitiatingProcessIntegrityLevel` | Sträng | Integritetsnivå för den process som initierade händelsen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de lanserades från en nedladdning på Internet. Dessa integritetsnivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | Sträng | Tokentyp som anger närvaron eller frånvaron av UAC-behörighetshöjning (User Access Control) som tillämpas på den process som initierade händelsen |
| `InitiatingProcessSHA1` | Sträng | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | Sträng | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `InitiatingProcessMD5` | Sträng | MD5-hash i processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | Sträng | Namn på den process som initierade händelsen |
| `InitiatingProcessId` | Int | Process-ID (PID) för den process som initierade händelsen |
| `InitiatingProcessCommandLine` | Sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | Datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | Sträng | Mapp som innehåller processen (bildfilen) som initierade händelsen |
| `InitiatingProcessParentId` | Int | Process-ID (PID) för den överordnade processen som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentFileName` | Sträng | Namn på den överordnade process som gav upphov till den process som var ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | Datetime | Datum och tid då den överordnade processen som var ansvarig för händelsen startades |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | Sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
