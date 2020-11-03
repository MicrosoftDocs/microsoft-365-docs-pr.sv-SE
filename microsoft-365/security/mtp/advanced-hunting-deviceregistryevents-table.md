---
title: DeviceRegistryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om register händelser som du kan fråga från tabellen DeviceRegistryEvents i det avancerade jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, registryevents, register, DeviceRegistryEvents, nyckel, under nyckel, värde
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1f7df85838654473fea593b235785b4320ea7164
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842684"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

`DeviceRegistryEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om hur du skapar och ändrar register poster. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `RegistryKey` | strängvärdet | Den register nyckel som den inspelade åtgärden tillämpades på |
| `RegistryValueType` | strängvärdet | Datatyp, till exempel binär eller sträng, av registervärdet som den inspelade åtgärden tillämpades för |
| `RegistryValueName` | strängvärdet | Namnet på det register värde som den inspelade åtgärden tillämpades på |
| `RegistryValueData` | strängvärdet | Data för registervärdet som den inspelade åtgärden tillämpades för |
| `PreviousRegistryValueName` | strängvärdet | Ursprungligt namn på registervärdet innan det ändrades |
| `PreviousRegistryValueData` | strängvärdet | Ursprunglig data för registervärdet innan det ändrades |
| `InitiatingProcessAccountDomain` | strängvärdet | Domän för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountName` | strängvärdet | Användar namn för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessSHA1` | strängvärdet | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | strängvärdet | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `InitiatingProcessMD5` | strängvärdet | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessFileName` | strängvärdet | Namn på processen som initierade händelsen |
| `InitiatingProcessId` | signera | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | strängvärdet | Kommando rad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid när processen som initierade händelsen startade |
| `InitiatingProcessFolderPath` | strängvärdet | Mapp som innehåller processen (bildfil) som initierade händelsen |
| `InitiatingProcessParentId` | signera | Process-ID (PID) för den överordnade processen som skapade processen för händelsen |
| `InitiatingProcessParentFileName` | strängvärdet | Namnet på den överordnade process som skapade processen som är ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade för processen som är ansvarig för händelsen startade |
| `InitiatingProcessIntegrityLevel` | strängvärdet | Integritets nivå för den process som initierade händelsen. Windows tilldelar integritets nivåer för processer baserat på vissa egenskaper, till exempel om de startades från en nedladdning via Internet. Dessa integritets nivåer påverkar behörigheter för resurser |
| `InitiatingProcessTokenElevation` | strängvärdet | Tokentyp som anger närvaron av en behörighets höjning (User Access Control) som tillämpas på processen som initierade händelsen |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `AppGuardContainerId` | strängvärdet | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaren |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
