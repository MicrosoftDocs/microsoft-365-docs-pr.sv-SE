---
title: DeviceEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om antivirus-, brand Väggs-och andra händelse typer i DeviceEvents-tabellen (Diverse Device Events) för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, säkerhets händelser, antivirus, brand vägg, sårbarhets skydd, DeviceEvents
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: fbe00c3ee33fd1e0f333447b2092d052fbb48834
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412232"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



De övriga enhets händelserna eller `DeviceEvents` tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika händelse typer, inklusive händelser som utlöses av säkerhets kontroller, till exempel Windows Defender Antivirus och sårbarhets skydd. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).


| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | strängvärdet | Namnet på filen som den inspelade åtgärden tillämpades för |
| `FolderPath` | strängvärdet | Mapp som innehåller filen som den inspelade åtgärden tillämpades för |
| `SHA1` | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| `SHA256` | strängvärdet | SHA-256 av filen som den registrerade åtgärden tillämpades på. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `MD5` | strängvärdet | MD5-hash för filen som den inspelade åtgärden tillämpades för |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `RemoteUrl` | strängvärdet | URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till |
| `RemoteDeviceName` | strängvärdet | Namnet på den dator som utförde en fjärråtgärd på den påverkade datorn. Beroende på vilken händelse som rapporteras kan detta namn vara ett fullkvalificerat domän namn (FQDN), ett NetBIOS-namn eller ett värdnamn utan domän information |
| `ProcessId` | signera | Process-ID (PID) för den nyskapade processen |
| `ProcessCommandLine` | strängvärdet | Kommando rad som används för att skapa den nya processen |
| `ProcessCreationTime` | datetime | Datum och tid då processen skapades |
| `ProcessTokenElevation` | strängvärdet | Tokentyp som anger närvaro eller frånvaro av behörighets höjning (UAC) för den nyskapade processen |
| `LogonId` | strängvärdet | Identifierare för en inloggningssession. Detta ID är endast unikt på samma dator mellan omstarter |
| `RegistryKey` | strängvärdet | Den register nyckel som den inspelade åtgärden tillämpades på |
| `RegistryValueName` | strängvärdet | Namnet på det register värde som den inspelade åtgärden tillämpades på |
| `RegistryValueData` | strängvärdet | Data för registervärdet som den inspelade åtgärden tillämpades för |
| `RemoteIP` | strängvärdet | IP-adress som var ansluten till |
| `RemotePort` | signera | TCP-port på fjär renheten som du anslöt till |
| `LocalIP` | strängvärdet | IP-adress som tilldelats till den lokala datorn under kommunikationen |
| `LocalPort` | signera | TCP-port på den lokala datorn som används vid kommunikation |
| `FileOriginUrl` | strängvärdet | URL dit filen laddades ned från |
| `FileOriginIP` | strängvärdet | IP-adress dit filen laddades ned från |
| `AdditionalFields` | strängvärdet | Ytterligare information om händelsen i JSON-mat ris format |
| `InitiatingProcessSHA1` | strängvärdet | SHA-1 av processen (bildfil) som initierade händelsen |
| `InitiatingProcessSHA256` | strängvärdet | SHA-256 av processen (bildfil) som initierade händelsen. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `InitiatingProcessFileName` | strängvärdet | Namn på processen som initierade händelsen |
| `InitiatingProcessFolderPath` | strängvärdet | Mapp som innehåller processen (bildfil) som initierade händelsen |
| `InitiatingProcessId` | signera | Process-ID (PID) för processen som initierade händelsen |
| `InitiatingProcessCommandLine` | strängvärdet | Kommando rad som används för att köra processen som initierade händelsen |
| `InitiatingProcessCreationTime` | datetime | Datum och tid när processen som initierade händelsen startade |
| `InitiatingProcessParentId` | signera | Process-ID (PID) för den överordnade processen som skapade processen för händelsen |
| `InitiatingProcessParentFileName` | strängvärdet | Namnet på den överordnade process som skapade processen som är ansvarig för händelsen |
| `InitiatingProcessParentCreationTime` | datetime | Datum och tid då den överordnade för processen som är ansvarig för händelsen startade |
| `InitiatingProcessMD5` | strängvärdet | MD5-hash för processen (bildfil) som initierade händelsen |
| `InitiatingProcessAccountDomain` | strängvärdet | Domän för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountName` | strängvärdet | Användar namn för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessAccountSid` | strängvärdet | Säkerhets identifierare (SID) för det konto som körde processen som är ansvarig för händelsen |
| `InitiatingProcessLogonId` | strängvärdet | ID för en inloggningssession för den process som initierade händelsen. Detta ID är endast unikt på samma dator mellan omstarter |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel |
| `AppGuardContainerId` | strängvärdet | Identifierare för den virtualiserade behållare som används av Application Guard för att isolera webbläsaren |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
