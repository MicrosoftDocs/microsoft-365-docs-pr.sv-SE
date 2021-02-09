---
title: Tabellen DeviceRegistryEvents i den avancerade sökschemat
description: Läs mer om registerhändelser som du kan fråga från tabellen DeviceRegistryEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, registryevents, registry, DeviceRegistryEvents, key, subkey, value
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
ms.openlocfilehash: 6bd0e4fe3173fa899b0b9c86d6f85d724b52be3a
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145013"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `DeviceRegistryEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om hur registerposter kan skapas och ändras. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `RegistryKey` | sträng | Registernyckel som den inspelade åtgärden tillämpades på |
| `RegistryValueType` | sträng | Datatyp, till exempel binär eller sträng, för registervärdet som den inspelade åtgärden tillämpats på |
| `RegistryValueName` | sträng | Namn på registervärdet som den inspelade åtgärden tillämpats på |
| `RegistryValueData` | sträng | Data för registervärdet som den inspelade åtgärden tillämpats på |
| `PreviousRegistryKey` | sträng | Den ursprungliga registernyckeln för registervärdet innan den ändrades |
| `PreviousRegistryValueName` | sträng | Det ursprungliga namnet på registervärdet innan det ändrades |
| `PreviousRegistryValueData` | sträng | Ursprungliga data för registervärdet innan det ändrades |
| `InitiatingProcessAccountDomain` | sträng | Domän för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountName` | sträng | Användarnamnet för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountUpn` | sträng | Användarens huvudnamn (UPN) för det konto som körde processen som ansvarar för händelsen |
| `InitiatingProcessAccountObjectId` | sträng | Azure AD-objekt-ID för användarkontot som körde processen som ansvarar för händelsen |
| `InitiatingProcessSHA1` | sträng | SHA-1 för processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | sträng | SHA-256 för processen (bildfil) som initierade händelsen. Det här fältet fylls vanligtvis inte i – använd SHA1-kolumnen när den är tillgänglig. |
| `InitiatingProcessMD5` | sträng | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | sträng | Namn på processen som initierade händelsen |
| `InitiatingProcessFileSize` | long | Storlek på filen som körde processen som ansvarar för händelsen |
| `InitiatingProcessId` | int | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | sträng | Kommandorad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid då processen som initierade händelsen startades |
| `InitiatingProcessFolderPath` | sträng | Mapp som innehåller den process (bildfil) som initierade händelsen |
| `InitiatingProcessParentId` | int | Process-ID (PID) för den överordnade process som avkortade processen som ansvarar för händelsen |
| `InitiatingProcessParentFileName` | sträng | Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade processen som ansvarar för händelsen startades |
| `InitiatingProcessIntegrityLevel` | sträng | Integritetsnivån för processen som initierade händelsen. Windows tilldelar integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning. De här integritetsnivåerna påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | sträng | Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp |
| `AppGuardContainerId` | sträng | Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
